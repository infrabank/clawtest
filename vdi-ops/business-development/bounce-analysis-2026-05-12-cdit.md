# 청담정보기술 메일 반송 원인 분석

분석일: 2026-05-12  
대상 메일: `(주)마이로켓 — 대전·세종권 VDI/가상화 기술지원 협력 문의드립니다`  
원 발송 Gmail message id: `19e1e40ba8c21559`  
반송 Gmail message id: `19e1e40e90d9a900`

## 결론

반송 원인은 **수신자 주소 중 `sales@cdit.co.kr`이 Microsoft 365 그룹이며, 외부 발신자 수신이 차단되어 있기 때문**이다.

- 반송 발신자: `postmaster@cdit.co.kr`
- 반송 제목: `Undeliverable: (주)마이로켓 — 대전·세종권 VDI/가상화 기술지원 협력 문의드립니다`
- SMTP 상태 코드: `550 5.7.193`
- 오류 메시지:
  - `The Microsoft 365 group, sales@cdit.co.kr, is configured to reject messages sent to it from outside its organization`
  - `Delivery failed because the sender isn't a group member or external senders aren't permitted to send to this group`

## 해석

- `sales@cdit.co.kr`은 일반 외부 수신용 메일박스가 아니라 Microsoft 365 그룹으로 보인다.
- 해당 그룹은 외부 발신자 수신을 허용하지 않도록 설정되어 있다.
- 발신 도메인 `mlkit.co.kr`의 SPF/DKIM/DMARC는 통과한 것으로 보이므로, 스팸/인증 실패가 아니라 **수신 그룹 정책 문제**다.
- 원문 반송 상세의 `Original Message Details`에는 `Recipient Address: sales@cdit.co.kr`만 명시되어 있다. 같은 메일에 포함된 `service@cdit.co.kr`까지 반송되었는지는 반송 원문만으로 확정하기 어렵지만, 최소한 `sales@cdit.co.kr`은 실패했다.

## 권장 조치

1. 청담정보기술 재발송 시 `sales@cdit.co.kr`은 제외한다.
2. `service@cdit.co.kr` 단독으로 보내거나, 홈페이지 문의폼/대표전화로 영업 담당 연결을 요청한다.
3. 재발송한다면 제목을 짧게 바꾸고, 이미 보낸 메일이 일부 수신되었을 가능성을 고려해 “혹시 중복 수신이면 양해 부탁드립니다” 문구를 넣는다.

## 재발송 후보 문구

수신: `service@cdit.co.kr`  
제목: `(주)마이로켓 — VDI/가상화 기술지원 협력 문의`

본문 첫 문장:

> 안녕하세요. 앞서 sales@cdit.co.kr로 함께 발송한 메일이 Microsoft 365 그룹 외부수신 제한으로 반송되어, 기술지원 문의 주소로 다시 연락드립니다.
