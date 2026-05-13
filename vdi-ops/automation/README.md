# 현우봇 업무 자동화 확장

목적: 현우님의 Gmail/Calendar/maint/vdi-ops/Manus 연동을 기반으로 VDI 유지보수 업무, 협력사 CRM, AI 뉴스 브리핑, 보고서 초안 생성을 자동화한다.

## 현재 바로 가능한 연동

- Gmail: 메일 조회/발송/삭제/스레드 답장
- Google Calendar: 일정 조회/등록/반복 알림
- Manus: 긴 리서치/문서/디자인 작업 위임
- OpenClaw workspace: `maint/`, `vdi-ops/`, `memory/` 문서 기반 업무 맥락 유지

## 추가 연동 후 확장 가능 영역

- Google Drive/Docs/Sheets: 보고서/관리대장 클라우드 문서화
- Google Contacts: 협력사/담당자 연락처 관리
- Notion/Airtable: CRM DB화
- Slack/Teams: 외부 협업 채널 자동화

## 우선 자동화 구성

1. Gmail 기반 VDI 업무 인박스 트리아지
2. 협력사 CRM 자동 기록
3. 점검/장애 보고서 초안 템플릿
4. AI/VDI 뉴스 브리핑
5. Manus 장시간 작업 위임

## 민감정보 기준

- 민감정보 저장/공유 기준: `vdi-ops/automation/sensitive-info-policy.md`
- 실제 CRM Sheet URL, 담당자 연락처, 고객사 상세정보는 public repo에 커밋하지 않는다.
