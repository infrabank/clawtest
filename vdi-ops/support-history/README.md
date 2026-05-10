# 기존 기술지원 내역 통합 색인

원본 저장소 `https://github.com/infrabank/maint`의 고객사별 `기술지원_요청내역.md`에서 추출한 SR/작업 항목입니다.

> 민감할 수 있는 환경정보, IP, 담당자 연락처는 포함하지 않았습니다.

## 고객사별 요약

| 고객사 | 전체 | 진행/미완료 | 완료 | P1 | P2 | P3 | 상세 |
|---|---:|---:|---:|---:|---:|---:|---|
| DJGLASS | 6 | 6 | 0 | 0 | 6 | 0 | [DJGLASS.md](DJGLASS.md) |
| KIEP | 8 | 0 | 8 | 0 | 8 | 0 | [KIEP.md](KIEP.md) |
| KISTI | 3 | 1 | 2 | 0 | 3 | 0 | [KISTI.md](KISTI.md) |
| KRIHS | 11 | 1 | 10 | 0 | 11 | 0 | [KRIHS.md](KRIHS.md) |
| MODS | 89 | 61 | 28 | 14 | 36 | 39 | [MODS.md](MODS.md) |
| MPM | 1 | 0 | 1 | 0 | 1 | 0 | [MPM.md](MPM.md) |
| SFD | 22 | 14 | 8 | 0 | 22 | 0 | [SFD.md](SFD.md) |

## 전체 진행/미완료 항목

| 고객사 | SR | 우선순위 | 제목 |
|---|---|---|---|
| DJGLASS | SR001 | P2 | SR001: 전사 인터넷 장애 — 방화벽(SECUI MF2 800) 강제 재부팅으로 복구 |
| DJGLASS | - | P2 | 방화벽 시스템 로그 확인 (재부팅 전 시점 에러/경고) |
| DJGLASS | - | P2 | 펌웨어 버전 확인 및 SECUI 벤더에 알려진 이슈 문의 |
| DJGLASS | - | P2 | 세션 수 모니터링 (동시 세션 수 vs 장비 최대 세션 수) |
| DJGLASS | - | P2 | 가동 시간(uptime) 확인 — 이번 재부팅 전 마지막 재부팅 시점 |
| DJGLASS | - | P2 | 이중화 구성 검토 제안 (전사 인터넷이 단일 장비에 의존하는 리스크) |
| KISTI | SR003 | P2 | SR003 — Horizon Client 인증서 및 접속 오류 |
| KRIHS | SR010 | P2 | SR010 — Horizon Support Bundle 분석 · CS/UAG 경미 이슈 |
| MODS | - | P1 | 고객 회신 확인 후 후속 조치 결정 |
| MODS | - | P1 | 방화벽 정책 변경 신청 — 보안팀 승인 추적 |
| MODS | - | P1 | 라온테크 김창영 이사를 통해 천학범 이사의 123↔124 차단 사유 확인 요청 |
| MODS | - | P1 | 사유 파악 후 기술적 대응 방안 재수립 |
| MODS | - | P1 | 나눔아이티 소통 창구 대안 검토 (문서/이메일 등) |
| MODS | - | P1 | 승인 완료 시 즉시 ESXi IP 이전 착수 |
| MODS | SR014 | P2 | SR014: 스토리지 운영방안 PM 회의 (Thin 유지 + VM 제한 + 운영 규칙) |
| MODS | - | P2 | PM 회의 진행 (2026-04-22) |
| MODS | SR014 | P2 | 회의 결과 반영 → SR014 wiki 후속 기록 |
| MODS | - | P2 | L08/L09 Storage vMotion 실행 |
| MODS | SR001 | P2 | SR001 Dashboard VSPE1090 이관 + VM 수 패널 추가 |
| MODS | SR012 | P2 | SR012: HW/SW 유지관리 비용 산정 |
| MODS | - | P2 | 기존장비 유지관리 비용 산출 |
| MODS | - | P2 | 신규장비 유지관리 비용 산출 |
| MODS | - | P2 | SW 유지관리 비용 산출 |
| MODS | - | P2 | 비용 산출서 작성 및 회신 |
| MODS | - | P2 | Horizon GPU Pool 구성 |
| MODS | - | P2 | 최종 검증 체크리스트 완료 |
| MODS | - | P2 | AI LLM 서버(동일 모델) 교체 필요 여부 문의 — 답변 완료 |
| MODS | - | P2 | ESXi 7대 관리 IP 이전 (124.x → 123.x) |
| MODS | - | P2 | 방화벽 승인 확인 후 착수 |
| MODS | - | P2 | 이전 순서 및 다운타임 계획 수립 |
| MODS | - | P2 | 이전 후 vCenter 연결 정상 확인 |
| MODS | - | P2 | 완료 후 네트워크 구성도 업데이트 |
| MODS | - | P2 | 3월 셋째주 정기 방문 점검 준비 |
| MODS | - | P2 | 점검 대상 센터 및 장비 목록 확정 |
| MODS | - | P2 | 점검 체크리스트 준비 |
| MODS | - | P2 | 점검 문서 양식 업데이트 |
| MODS | SR006 | P3 | SR006: VDI 대용량 통계 데이터 처리 성능 개선 |
| MODS | - | P3 | 고객 제출 및 피드백 반영 |
| MODS | - | P3 | 현장 진단 실시 (체크리스트 기반) |
| MODS | - | P3 | 100GB 대용량 파일 처리 검토 (GIS, Python 분석) |
| MODS | - | P3 | 현재 스토리지 구성 및 IOPS 확인 |
| MODS | - | P3 | 해당 VM 디스크 할당량 검토 |
| MODS | - | P3 | GIS/Python 분석 시 메모리 요구량 산정 |
| MODS | - | P3 | 임시 스토리지 분리 마운트 여부 검토 |
| MODS | - | P3 | Windows 11 업데이트 적용 |
| MODS | - | P3 | 대상 VM 범위 확인 (골든 이미지 기준) |
| MODS | - | P3 | 테스트 VM 선적용 후 검증 |
| MODS | - | P3 | Recompose 일정 수립 |
| MODS | - | P3 | AD 컴퓨터 계정명 변경 가능 여부 검토 |
| MODS | - | P3 | 현재 MODS 기반 명명 규칙 확인 |
| MODS | - | P3 | 변경 시 Horizon 풀 및 GPO 영향도 분석 |
| MODS | - | P3 | 변경 절차 및 위험성 안내 |
| MODS | - | P3 | 제로클라이언트 vs 씬클라이언트 구매 결정 |
| MODS | - | P3 | 사용 환경 분류 (VDI 전용 vs 혼용) |
| MODS | - | P3 | 원격 관리 지원 여부 비교 |
| MODS | - | P3 | 구매 단가 및 총소유비용(TCO) 비교 |
| MODS | - | P3 | 성능 요구 수준 확인 (4K, 멀티모니터 등) |
| MODS | - | P3 | 검토 의견서 작성 |
| MODS | - | P3 | 사용자 계정별 디스크 사용량 대시보드 개발 검토 |
| MODS | - | P3 | 관련 API 확인 (vCenter / Horizon / 커스텀) |
| MODS | - | P3 | 대시보드 플랫폼 결정 (자체 웹, Grafana, vROps) |
| MODS | - | P3 | 데이터 수집 방식 결정 (PowerShell, API polling) |
| MODS | - | P3 | 지역센터 IP 관리 체계 수립 |
| MODS | - | P3 | 지역센터별 IP 대역 현황 파악 |
| MODS | - | P3 | IP 관리 도구 선정 (Excel / phpIPAM / NetBox) |
| MODS | - | P3 | 충돌 방지 정책 수립 |
| MODS | - | P3 | 점검 문서 업데이트 |
| MODS | - | P3 | 최신 구성 현황 반영 |
| MODS | - | P3 | 네트워크 분리 작업 결과 반영 예정 (ESXi IP 이전 완료 후) |
| SFD | SR002 | P2 | SR002: 현장출동영상 VDI 공유 스토리지(FC SAN) 증설 — 시나리오 확정 |
| SFD | - | P2 | DL380 정확한 CPU 모델 확인 (Xeon Gold 6226R → EVC Cascade Lake 적용 확정) |
| SFD | - | P2 | DL380 현재 ESXi 6.7 U 패치 레벨 |
| SFD | - | P2 | DL380 PCIe 슬롯 여유 (T4×2 + FC HBA 동시 장착 가능 여부) |
| SFD | - | P2 | DL380 · PR660 FC HBA 모델 확정 (Emulex LPe35000 / QLogic 27xx 등) |
| SFD | - | P2 | Unity XT 380 FC SLIC 구성 (포트 수, 16G/32G) |
| SFD | - | P2 | FC 케이블 타입(OM4)/길이 산정 (4쌍) |
| SFD | - | P2 | Horizon 라이선스 등급 (8.0 업그레이드 호환) |
| SFD | - | P2 | 현재 VM 30대 디스크 총 사이즈 (Cold Migration 시간 산정) |
| SFD | - | P2 | 기존 vCenter 6.7 VM 의 호스트 위치 (DL360 / DL380 중) |
| SFD | - | P2 | 작업 윈도우 (1·2·3차 야간 일정) |
| SFD | SR001 | P2 | SR001: 부강119센터 제로클라이언트 전원 불량 |
| SFD | - | P2 | 고장 단말기 수리 가능 여부 확인 (LG A/S 또는 자체 수리) |
| SFD | - | P2 | 수리 완료 시 다른 센터용 임시 예비장비로 보유 |

## 전체 완료 항목

| 고객사 | SR | 우선순위 | 제목 |
|---|---|---|---|
| KIEP | SR001 | P2 | SR001 — 첫방문 사전확인 체크리스트 |
| KIEP | SR002 | P2 | SR002 — Master VM 구축 |
| KIEP | SR003 | P2 | SR003 — OSOT 적용가이드 |
| KIEP | SR004 | P2 | SR004 — FSLogix 구성 |
| KIEP | SR005 | P2 | SR005 — 고정형마스터VM 배포 |
| KIEP | SR006 | P2 | SR006 — DefaultProfile 설정 |
| KIEP | SR007 | P2 | SR007 — 사용자VM 생성 |
| KIEP | SR008 | P2 | SR008 — Windows 11 Upgrade 완료보고서 |
| KISTI | SR001 | P2 | SR001 — FSLogix 적용절차 |
| KISTI | SR002 | P2 | SR002 — VM 연결오류 분석 |
| KRIHS | SR001 | P2 | SR001 — CS 패치 작업계획서 |
| KRIHS | SR002 | P2 | SR002 — CS 정기재부팅 스케줄 |
| KRIHS | SR003 | P2 | SR003 — Internal Repo 계획서 |
| KRIHS | SR004 | P2 | SR004 — Open VM Tools 계획서 |
| KRIHS | SR005 | P2 | SR005 — KIWI 고도화 / DB 장애 검토 |
| KRIHS | SR006 | P2 | SR006 — CS01 AD 연결 RCA |
| KRIHS | SR007 | P2 | SR007 — CS 패치작업 (2026-03-25) |
| KRIHS | SR008 | P2 | SR008 — HyperFlex Control VM 장애 |
| KRIHS | SR009 | P2 | SR009 — view DB 트랜잭션 로그 Full (MSSQL 9002) |
| KRIHS | SR011 | P2 | SR011 — AD DC 전용 백업 구성 |
| MODS | - | P1 | AD 서버 시간 2018년으로 변경 요청 대응 |
| MODS | - | P1 | 요청 목적 및 배경 확인 |
| MODS | - | P1 | AD 복제 오류·Kerberos 인증 실패 위험성 고객 안내 |
| MODS | - | P1 | 요청 불가 통보 완료 |
| MODS | - | P1 | 스토리지 Thin → Thick 원복 요청 — 보류 안내 완료 |
| MODS | - | P1 | 9월 당시 Thick 환경 스토리지 사용량 90% 이상 확인 |
| MODS | - | P1 | Datastore 여유 공간 부족으로 원복 위험성 분석 |
| MODS | - | P1 | 보류 및 Thin 유지 권장 의견 메일 발송 |
| MODS | - | P2 | 브리핑 문서 작성 (MODS_스토리지_운영방안_브리핑_20260422.docx) |
| MODS | SR011 | P2 | SR011: GPU 서버 교체 설치 (NVIDIA L40S vGPU) |
| MODS | - | P2 | 기존 GPU 서버 설정 분석 (support bundle) |
| MODS | - | P2 | 교체 설치 절차서 작성 (MODS_GPU_서버_교체_설치_절차서.docx) |
| MODS | - | P2 | FC HBA WWPN → SAN 스위치 Zone 등록 요청 메일 발송 (2026-04-08, 이영일 팀장/천학범 이사) |
| MODS | - | P2 | 새 서버 입고 확인 |
| MODS | - | P2 | BIOS 설정 (VT-d, SR-IOV, Above 4G Decoding) |
| MODS | - | P2 | ESXi 8.0U3h 클린 설치 |
| MODS | - | P2 | vCenter GPU 클러스터 등록 (기존 호스트 제거 → 신규 호스트 추가) |
| MODS | - | P2 | 네트워크/스토리지 구성 |
| MODS | - | P2 | NVIDIA vGPU Manager 설치 및 검증 |
| MODS | - | P2 | NVIDIA DLS(nls-3.6.0-bios) 설치 — https://10.134.124.169 |
| MODS | - | P2 | vGPU 프로파일 설정 및 테스트 VM 검증 (임시 Windows 11 VM '새 가상시스템', 4Q 프로필) |
| MODS | - | P2 | 그래픽 드라이버 설치 + License Lease 확인 완료 |
| MODS | - | P3 | SAS WORK/UTILLOC I/O 메커니즘 조사 (공식 문서 기반) |
| MODS | - | P3 | R tempdir/Arrow/data.table 성능 조사 (공식 문서 기반) |
| MODS | - | P3 | VMware VDI 스토리지 베스트 프랙티스 조사 |
| MODS | - | P3 | MODS VDI 성능 개선 제안서 작성 (MODS_VDI_성능개선_제안서.docx) |
| MODS | - | P3 | 현장 진단 체크리스트 작성 (MODS_VDI_진단_체크리스트.docx) |
| MODS | - | P3 | SAS/R 성능 설정 가이드 작성 (SAS_R_성능설정_가이드.docx) |
| MPM | - | P2 | 2026년 1분기 Citrix 점검보고서 |
| SFD | SR002 | P2 | 백업 솔루션 — SR002 범위 제외 결정 (2026-04-25, decision-backup-policy cancelled — 협의가 한정 + Veeam Community 공공기관 리스크). 별도 SOW 로 Veeam Foundation/Essentials 유료 또는 국산 백업 검토 권고. |
| SFD | - | P2 | 기존 vCenter — VCSA 6.7.0.51000 (build 19300125), IP 10.159.246.11, EOL 상태 (2026-04-25 확인) — 8.0 신규 구축으로 대체 후 폐기 |
| SFD | - | P2 | AD DC 단일 운영 (1대) — DC02 추가는 별도 SR (2026-04-25 확인) |
| SFD | - | P2 | 폴더명 리네임 완료 (`SR002_현장출동영상VDI_iSCSI공유스토리지_설계` → `_FC공유스토리지_설계`, 2026-04-25) |
| SFD | - | P2 | 현장 방문 점검 (부강119센터, 11:30~13:30) |
| SFD | - | P2 | 원인 확인: 전원연결부 단자 물리적 파손 |
| SFD | - | P2 | 동일 모델(LG 24CAV37K) 현장영상전용 단말기의 IP를 수정하여 대체 투입 |
| SFD | - | P2 | 고장 단말기 회수 (수리 가능 여부 확인 예정) |

## 고객사별 산출물 파일 수

| 고객사 | 산출물/자료 파일 수 |
|---|---:|
| DJGLASS | 2 |
| KIEP | 46 |
| KINAC | 0 |
| KINS | 0 |
| KISTI | 38 |
| KLRI | 4 |
| KRIHS | 75 |
| KRISO | 2 |
| MODS | 155 |
| MPM | 5 |
| SFD | 46 |
