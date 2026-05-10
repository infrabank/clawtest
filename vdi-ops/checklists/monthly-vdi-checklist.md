# 월간 VDI 정기점검 체크리스트

## 1. 공통 인프라
- [ ] AD/DNS/NTP 정상 상태 확인
- [ ] 인증/로그온 지연 여부 확인
- [ ] 주요 서버 CPU/Memory/Disk 사용률 확인
- [ ] 이벤트 로그 Critical/Error 확인
- [ ] 백업 수행 여부 확인

## 2. Citrix 점검
- [ ] Delivery Controller 서비스 상태 확인
- [ ] StoreFront / Workspace 접속 확인
- [ ] Machine Catalog 상태 확인
- [ ] Delivery Group 등록/미등록 장비 확인
- [ ] 세션 접속/해제 테스트
- [ ] License 상태 확인
- [ ] 정책 변경 이력 확인

## 3. Omnissa Horizon 점검
- [ ] Connection Server 상태 확인
- [ ] UAG 사용 시 외부 접속 확인
- [ ] Desktop Pool 상태 확인
- [ ] Agent 상태 확인
- [ ] App Volumes / DEM 사용 시 상태 확인
- [ ] 세션 접속/해제 테스트

## 4. VMware vSphere / ESXi 점검
- [ ] vCenter 접속 및 알람 확인
- [ ] ESXi Host 연결 상태 확인
- [ ] Datastore 여유 공간 확인
- [ ] VM Snapshot 장기 보관 여부 확인
- [ ] HA/DRS 상태 확인
- [ ] 주요 VM Tools 상태 확인

## 5. 사용자 영향 확인
- [ ] 최근 장애/문의 내역 확인
- [ ] 로그인 지연/프로파일 오류 여부 확인
- [ ] 주요 업무 애플리케이션 실행 확인

## 6. 보고
- [ ] 점검 결과 요약 작성
- [ ] 이상 항목 및 조치 계획 작성
- [ ] 고객 전달 메일 발송
