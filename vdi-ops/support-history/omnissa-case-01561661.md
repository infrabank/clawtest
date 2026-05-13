# Omnissa Support Case 01561661 추적 기록

작성/갱신일: 2026-05-13

## Case 정보

- Case: `01561661`
- 제품/영역: Omnissa Horizon 8 / Horizon Admin certificate management
- 제목: `Horizon Admin certificate management CS error occurs without usage issues`
- 담당자: Kedaar Kamath / Omnissa Global Customer Service Team
- 고객 참조: KRIHS 담당자 참조 포함
- Thread marker: `thread::kjWkDOOQOM2QRmdAKTIEazg::`

## 이슈 요약

Horizon Admin 인증서 관리 화면에서 certificate management 관련 CS error 또는 인증서 경고가 발생하나, 실제 사용상 문제는 없는 상태로 보인다.

Omnissa는 `CertificateRevocationCheckType` 관련 registry path 확인을 요청했으나, 현장 Connection Server에서 안내받은 경로가 존재하지 않았다.

확인한 Horizon 버전:

- `VMware Horizon 8.9.0.21593375`

확인한 registry path:

- `HKLM\Software\VMware\Horizon\Security` — 존재하지 않음
- `HKLM\Software\Omnissa\Horizon\Security` — 존재하지 않음

## 주요 타임라인

### 2026-04-20

현우님이 Omnissa 요청에 따라 인증서 관련 정보를 회신.

- 인증서 경고 메시지 스크린샷 제공
- 인증서 만료일: 2026-07-28
- CA-signed certificate 사용
- Wildcard certificate 사용

### 2026-05-04

현우님이 registry path 확인 결과를 Omnissa에 회신.

요지:

- `HKLM\Software\VMware\Horizon\Security` 경로 없음
- `HKLM\Software\Omnissa\Horizon\Security` 경로 없음
- 따라서 `CertificateRevocationCheckType` string value 확인 불가
- Horizon version: `VMware Horizon 8.9.0.21593375`
- 해당 Horizon 버전에 맞는 registry path/configuration location 확인 요청

### 2026-05-06 / 2026-05-08 / 2026-05-11

Omnissa가 고객 환경에서 registry path를 실시간 검증하기 위해 Zoom session 가능 여부를 반복 문의.

- Scheduler: `https://scheduler.zoom.us/kedaar-kamath`
- 요청사항: customer environment에서 registry path live validation

### 2026-05-13

현우님이 Omnissa archive warning 이후 case 재활성화/계속 진행 의사를 회신함.

회신 요지:

- 지연 답변 사과
- Case 01561661 계속 진행 및 reactivation 요청
- 기존에 두 registry path가 존재하지 않았음을 재확인
- Horizon version `VMware Horizon 8.9.0.21593375` 명시
- Zoom session 가능하나, 일정 전 정확한 registry path/configuration location 및 validation steps를 이메일로 먼저 공유 요청
- spoken English communication이 어려우므로 Zoom에서는 screen sharing/chat 중심 진행 요청

## 현재 상태

- 상태: Omnissa 답변 대기
- 다음 단계:
  1. Omnissa가 정확한 registry/configuration path 또는 validation steps를 이메일로 보내는지 확인
  2. 필요 시 KRIHS 담당자와 Zoom 가능한 시간 조율
  3. Kedaar scheduler로 Zoom session 예약
  4. Zoom 전 Connection Server 접근 권한, 관리자 권한, regedit/PowerShell 실행 가능 여부 확인

## Zoom 전 준비 체크리스트

- [ ] 고객 담당자와 원격 접속/Zoom 가능 시간 확인
- [ ] Connection Server 관리자 계정 준비
- [ ] registry editor 또는 PowerShell 실행 권한 확인
- [ ] Horizon Console 접속 가능 여부 확인
- [ ] 인증서 경고/CS error 재현 경로 확인
- [ ] 기존 확인 경로 스크린샷 준비
- [ ] 영어 통화 어려움으로 chat/screen sharing 중심 진행 요청 재확인
