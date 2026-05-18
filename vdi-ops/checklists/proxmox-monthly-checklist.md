# Proxmox 월간점검 체크리스트

목적: Proxmox VE 기반 ERP/업무 VM 환경에서 스토리지 full, LVM-thin out-of-data-space, 스냅샷 누적, VM 내부 디스크 부족을 조기에 발견한다.

- 점검 주기: 월 1회
- 우선 적용 대상: 대진글라스 ERP Proxmox 등 단일 호스트/소규모 운영 환경
- 핵심 위험 기준: `local-lvm` 또는 `pve/data` 사용률 80% 이상 주의, 90% 이상 조치 필요, 95% 이상 긴급

## 1. 기본 정보

| 항목 | 내용 |
|---|---|
| 점검일 |  |
| 고객사 |  |
| Proxmox 호스트명 |  |
| 점검자 |  |
| Proxmox 버전 |  |
| 주요 VM |  |
| 특이사항 |  |

## 2. VM 상태 확인

```bash
qm list
```

| VMID | VM명 | 상태 | 비고 |
|---:|---|---|---|
|  |  |  |  |

확인 기준:
- 모든 운영 VM이 정상 `running` 상태인지 확인
- 불필요하게 켜진 템플릿/테스트 VM이 있는지 확인
- 재시작 반복, 멈춤, 콘솔 블랙스크린 여부 확인

## 3. 호스트 자원 확인

```bash
uptime
free -h
df -h
```

| 항목 | 정상 기준 | 점검 결과 | 판정 |
|---|---|---|---|
| Load Average | CPU 코어 수 대비 과도하지 않음 |  |  |
| RAM 사용률 | Swap 과다 사용 없음 |  |  |
| `/` 루트 사용률 | 80% 미만 권장 |  |  |

주의:
- `df -h`에는 `local-lvm` 사용률이 직접 보이지 않는다.
- VM 디스크 공간은 반드시 `pvesm status`, `lvs`로 별도 확인한다.

## 4. Proxmox 스토리지 사용량 확인 — 중요

```bash
pvesm status
lvs -a
vgs
```

| 스토리지 | 사용률 | 여유공간 | 판정 |
|---|---:|---:|---|
| local |  |  |  |
| local-lvm / pve-data |  |  |  |
| VG VFree |  |  |  |

판정 기준:
- `local-lvm` 80% 이상: 스냅샷/백업/VM 내부 디스크 정리 계획 수립
- `local-lvm` 90% 이상: 즉시 정리 또는 증설 검토
- `local-lvm` 95% 이상: 신규 스냅샷/백업/대용량 작업 금지
- `pve/data Data%` 100%: VM I/O 중단 위험, 긴급 장애 상태

장애 로그 예시:

```text
device-mapper: thin: reached low water mark
switching pool to out-of-data-space
INFO: task lvs blocked for more than 120 seconds
```

위 메시지가 있으면 VM 리셋보다 스토리지 공간 확보가 우선이다.

## 5. 스냅샷 점검

```bash
qm listsnapshot <VMID>
```

예:

```bash
qm listsnapshot 101
qm listsnapshot 102
```

| VMID | 스냅샷명 | 생성일/목적 | 유지 필요 여부 | 조치 |
|---:|---|---|---|---|
|  |  |  |  |  |

운영 기준:
- 작업 완료 후 불필요한 스냅샷은 월간점검 시 삭제 검토
- 오래된 스냅샷은 VM 디스크 증가와 thin pool full 원인이 될 수 있음
- 삭제는 Proxmox 명령 또는 GUI로 수행한다.

스냅샷 삭제:

```bash
qm delsnapshot <VMID> <스냅샷명>
```

주의:
- `lvremove snap_vm-...` 직접 삭제는 원칙적으로 금지
- 삭제 전 운영 영향과 백업 여부 확인
- 삭제 중에는 중단하지 않음

## 6. VM 내부 디스크 사용량 확인

각 VM OS 내부에서 확인한다.

### Linux VM

```bash
df -h
journalctl -p warning..alert -S "30 days ago"
```

### Windows VM

PowerShell:

```powershell
Get-Volume | Select-Object DriveLetter, FileSystemLabel, SizeRemaining, Size
Get-EventLog -LogName System -EntryType Error,Warning -Newest 50
```

| VMID | VM명 | 주요 드라이브 사용률 | 조치 필요 여부 |
|---:|---|---:|---|
|  |  |  |  |

판정 기준:
- 80% 이상: 정리 계획
- 90% 이상: 조치 필요
- 95% 이상: 긴급 정리 또는 디스크 확장 검토

## 7. 백업/덤프 파일 확인

```bash
find /var/lib/vz/dump -type f -printf '%TY-%Tm-%Td %TH:%TM %s %p\n' 2>/dev/null | sort | tail -30
```

확인 항목:
- 오래된 백업 파일 누적 여부
- 백업 실패 로그 여부
- 백업 위치가 `local` 또는 `local-lvm`을 압박하는지 확인

## 8. 커널/스토리지 오류 로그 확인

```bash
dmesg -T | egrep -i "error|fail|timeout|reset|i/o|blocked|oom|killed|nvme|sata|scsi|ata|ext4|zfs|thin" | tail -100
journalctl -k -S "30 days ago" | egrep -i "error|fail|timeout|reset|i/o|blocked|oom|killed|thin" | tail -100
```

중요 키워드:
- `out-of-data-space`
- `I/O error`
- `task blocked for more than`
- `Out of memory`
- `Killed process`
- `ata reset`, `nvme timeout`
- `EXT4-fs error`, `ZFS error`
- `Hardware Error`, `ECC`, `memory error`

## 9. SMART/디스크 상태 확인

디스크 목록:

```bash
lsblk -o NAME,SIZE,TYPE,FSTYPE,MOUNTPOINT,MODEL,SERIAL
```

SMART 확인 예:

```bash
smartctl -a /dev/sda
smartctl -a /dev/sdb
```

`smartctl`이 없으면:

```bash
apt install smartmontools
```

확인 기준:
- Reallocated/Pending/Uncorrectable sector 증가 여부
- SSD wearout/lifetime 경고 여부
- 디스크 timeout/reset 로그 여부

## 10. 조치 기준

| 상황 | 조치 |
|---|---|
| local-lvm 80% 이상 | 스냅샷/백업/VM 내부 디스크 정리 계획 |
| local-lvm 90% 이상 | 불필요 스냅샷 삭제, 백업 정리, 디스크 증설 검토 |
| local-lvm 95% 이상 | 대용량 작업 중지, 즉시 공간 확보 |
| pve/data 100% | VM 리셋 반복 금지, VM 정지 후 공간 확보 또는 디스크 증설 |
| VM 내부 디스크 90% 이상 | 로그/백업/임시파일 정리, 필요 시 디스크 확장 |
| I/O error/timeout | 디스크/RAID/케이블/컨트롤러 점검 및 백업 우선 |
| OOM 로그 | VM 메모리 할당/호스트 RAM/swap 점검 |

## 11. 월간점검 결과 요약

| 구분 | 결과 |
|---|---|
| 전체 상태 | 정상 / 주의 / 장애위험 |
| local-lvm 사용률 |  |
| 가장 사용률 높은 VM 디스크 |  |
| 삭제한 스냅샷 |  |
| 정리한 백업/파일 |  |
| 발견한 오류 로그 |  |
| 고객 안내 필요 여부 |  |
| 다음 조치 |  |

## 12. 고객 보고용 문구

정상 시:

```text
Proxmox 호스트 및 주요 VM 월간점검 결과, VM 상태와 스토리지 사용량은 정상 범위입니다. 주요 오류 로그는 확인되지 않았으며, 현재 추가 조치는 필요하지 않습니다.
```

주의 시:

```text
Proxmox 스토리지/VM 디스크 사용량이 증가하고 있어 사전 정리가 필요합니다. 장애 예방을 위해 불필요한 스냅샷과 백업 파일을 정리하고, 필요 시 디스크 증설을 검토하겠습니다.
```

긴급 시:

```text
Proxmox local-lvm 스토리지 사용률이 임계치에 도달하여 VM 디스크 I/O 장애 위험이 있습니다. VM 리셋보다 스토리지 공간 확보가 우선이며, DB 보호를 위해 순차적으로 VM을 정지한 뒤 공간 확보/확장 후 재기동하겠습니다.
```

## 13. 대진글라스 ERP 장애 재발 방지 메모

- ERPWEB01 / ERPDB01 운영 환경에서는 `local-lvm` 사용률을 매월 확인한다.
- 스냅샷은 작업 전 임시 보호 목적으로만 사용하고, 작업 완료 후 장기 보관하지 않는다.
- DB 서버는 반복 강제 리셋을 피하고, 스토리지 full 여부를 먼저 확인한다.
- VM 내부 디스크 사용률도 함께 확인한다.
- `device-mapper thin out-of-data-space` 로그가 보이면 즉시 스토리지 공간 확보를 우선한다.
