# Robert VDI 유지보수 운영 템플릿

Citrix, Omnissa Horizon, VMware ESXi/vSphere 기반 공공기관 VDI 딜리버리·유지보수 업무를 체계화하기 위한 운영 문서 세트입니다.

## 빠른 사용법

1. 신규 고객/기관은 `customers/customer-profile-template.md`를 복사합니다.
2. 정기점검은 `templates/regular-maintenance-report.md`와 `checklists/monthly-vdi-checklist.md`를 사용합니다.
3. 장애 발생 시 `templates/incident-report.md`와 `logs/work-log.md`에 기록합니다.
4. 고객 메일은 `templates/email-templates.md`에서 상황별 문안을 복사해 사용합니다.
5. 변경 작업은 `templates/change-work-plan.md`로 사전 승인/사후 보고를 정리합니다.

## 구성

- `customers/` 고객/기관별 정보
- `templates/` 보고서, 메일, 작업계획 템플릿
- `checklists/` 정기점검 체크리스트
- `logs/` 작업 이력/장애 이력
- `reports/` 실제 제출 보고서 보관
- `scripts/` PowerShell/운영 스크립트 초안

## 운영 원칙

- 고객명, 계정, IP, 인증정보는 필요한 범위만 기록합니다.
- 패스워드/API 키/접속 토큰은 문서에 저장하지 않습니다.
- 장애/변경/점검은 날짜, 담당자, 영향도, 조치결과를 남깁니다.
- 공공기관 제출 문서는 객관적이고 간결한 문체를 사용합니다.
