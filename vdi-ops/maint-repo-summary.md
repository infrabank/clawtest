# infrabank/maint 핵심 정보 요약

원본 저장소: `https://github.com/infrabank/maint`
로컬 경로: `maint/`

## 목적
다수 고객사의 Windows 클라이언트 VDI 유지보수 기술지원 프로젝트를 관리하는 저장소.
VMware vSphere + Omnissa Horizon 및 Citrix Virtual Desktop + XenServer 환경을 대상으로 SR 단위 산출물, 절차서, 가이드, 보고서, 대시보드 등을 생성·관리한다.

## 고객사 목록
| 약칭 | 고객사/비고 |
|---|---|
| MODS | 국가데이터처 + 통계정보원(Kosii), SDC통계데이터센터 VDI 서비스 |
| KIEP | 대외경제정책연구원 |
| KRIHS | 국토연구원 |
| KISTI | 한국과학기술정보연구원 |
| MPM | 인사혁신처, Citrix Virtual Desktop/XenServer 기반 VDI |
| KLRI | 한국법제연구원, 분기 점검 |
| KRISO | 선박해양플랜트연구소 |
| SFD | 세종소방 |
| KINS | 한국원자력안전기술원 |
| KINAC | 한국원자력통제기술원 |
| DJGLASS | 대진글라스 |

## 주요 구조
- `KB/` — 기술 지식베이스, SW사업 대가산정 가이드, VMware 자료 등
- `Maint/{고객사}/기술지원_요청내역.md` — 고객사별 SR 마스터 추적 문서
- `Maint/{고객사}/환경정보.md` — 고객사별 인프라 환경 요약
- `Maint/{고객사}/기술지원_관리/` — SR별 산출물/스크립트/자료
- `Maint/_templates/` — 신규 고객사/SR/환경정보 템플릿
- `Maint/_lib/` — docx 생성, KB 검색, SR lint, 마이그레이션 유틸리티

## 운영 규칙
1. 고객사별 `기술지원_요청내역.md`가 SR 마스터 문서다.
2. 새 SR은 `SR{번호}_{한글_설명}` 구조를 사용한다.
3. SR 위키 파일은 YAML frontmatter + `[[wiki-link]]` 백링크를 사용한다.
4. SR 상태/긴급도는 표준 스키마를 따른다.
5. 고객사 환경정보, IP, 담당자 연락처 등은 민감정보일 수 있으므로 외부 공유 시 반드시 마스킹한다.

## SR 표준
필수 필드:
- `id`
- `type: sr`
- `customer`
- `title`
- `severity`: `P1` / `P2` / `P3`
- `status`: `open` / `in_progress` / `resolved` / `closed` / `cancelled`
- `opened`: `YYYY-MM-DD`

조건부 필수:
- `status`가 `resolved`/`closed`/`cancelled`면 `closed` 필요
- `status`가 `resolved`/`closed`면 `effort_hours` 필요

## severity 기준
- `P1`: 운영 중단/사용자 영향, 즉시 조치 필요
- `P2`: 영향 있으나 우회 가능, 단기 조치
- `P3`: 영향 없음, 중장기 개선/계획

## 대가산정/견적 주의사항
유지관리 비용, 견적, 요율, 대가 산정 작업 시 반드시 아래 자료를 참조한다.
- `maint/KB/SW사업_대가산정_가이드_2025/04_운영단계.md`
- `maint/KB/SW사업_대가산정_가이드.md`
- `maint/KB/SW사업대가_산정양식(2026년_1월)/`

상용SW 유지관리 요율은 5등급 체계 `12% / 14% / 16% / 18% / 20%`를 적용하며, 임의 요율을 사용하지 않는다.
등급은 7개 서비스 항목의 최저 점수 기준으로 산정한다.

## 점검/보고 자동화 패턴
- DOCX 산출물은 Python `python-docx` 또는 JS `docx-js`로 생성한다.
- 한글 문서 폰트는 `맑은 고딕` 및 `w:eastAsia` 속성을 적용한다.
- 고객사별 점검 보고서는 `_lib/report_framework/`의 설정 JSON 기반 자동 생성 구조를 따른다.
- PowerCLI 기반 데이터 수집 시 `Collect-Data.ps1` / `Get-ThinProvisioningReport.ps1` 패턴을 참고한다.

## 현재 확인된 진행 SR 요약
- MODS: 방화벽 정책 변경 승인 추적, 스토리지 운영방안 PM 회의, 유지관리 비용 산정 등
- KRIHS: Horizon Support Bundle 분석 및 CS/UAG 경미 이슈
- KISTI: Horizon Client 인증서 및 접속 오류
- SFD: VDI 공유 스토리지 증설, 제로클라이언트 전원 불량
- DJGLASS: 인터넷 장애/방화벽 재부팅 복구 건

상세 내용은 각 고객사 `기술지원_요청내역.md` 및 `환경정보.md`를 확인한다.
