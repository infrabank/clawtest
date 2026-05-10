---
id: srNNN
type: sr
customer: 고객사약칭
title: 한 줄 요약
target: 대상 시스템
severity: P2
status: open
opened: YYYY-MM-DD
related: [[entity-id]]
sources:
  - 기술지원_관리/SRNNN_제목/
tags: [sr]
---

# SRNNN — 제목

## 요청 / 증상

고객 요청 또는 발견 증상 기록.

## 분석

원인 분석, 진단 내용 기록.

## 조치

수행한 작업 기록.

## 결과 / 산출물

인도물, 검증 방법, 고객 확인 여부 기록.

## 관련

- [[entity-id]] — 관련 호스트/스토리지/결정

---

> SR 종료 시 frontmatter에 `closed: YYYY-MM-DD`, `effort_hours: 누적시간`, `status: closed` 갱신 필수.
> 표준 스키마는 `maint/Maint/_lib/SR_SCHEMA.md` 참조.
