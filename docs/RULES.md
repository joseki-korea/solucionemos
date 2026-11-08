---
id: joseki-korea-solucionemos/docs/RULES
title: "정푸드코리아 발주 임원 대시보드 및 회사 소개 — 규칙"
repo: joseki-korea-solucionemos
device_scope: all
doc_type: rules
tags: [rules, safety]
status: DRAFT
updated: "2026-11-08"
source_of_truth: vault main rules/INDEX.md
---

# 규칙

## 규칙 상속 체계 (Rules Inheritance)

- **GLOBAL (전역 정본)**: `solucionemos-vault/rules/INDEX.md` (Rule 00 · Rule 01 · Rule 02 · Rule 04).
  - 본 레포지토리는 vault 전역 정본 규칙을 상속하며, 전역 규칙은 절대 복사하지 않고 포인터로만 참조합니다.
  - 전역 규칙과 지역 규칙 충돌 시 **vault 전역 정본이 항상 우선**합니다.
- **LOCAL (지역 규칙)**: 본 레포지토리 전용 개발, 빌드, 테스트 및 에셋 관리 규칙 (하단 정의).
  - 지역 규칙은 전역 규칙을 보강(Add)할 수 있으나, 전역 규칙을 완화(Relax)하거나 배제할 수 없습니다.


## 정본 포인터

이 레포의 규칙 정본은 vault `main` 브랜치의 `rules/INDEX.md`와 Rule 00(안전·승인), Rule 01(토폴로지·소유권), Rule 02(수송·배차), Rule 04(표현·출처)이다. 이 문서는 정본을 복제하지 않고 레포 고유 규칙만 추가한다. 상태는 DRAFT이며 임의로 FINAL로 승격하지 않는다.

## 안전 불변식

- force push 금지. main 직접 push 금지. 변경은 작업 가지 + PR로만 한다.
- 기존 dirty·untracked 변경은 사용자 소유로 보존한다. 삭제·이동은 승인 없이 하지 않는다.
- 비밀·token·key·계정 ID·개인정보를 평문으로 기록하지 않는다.
- 신원·대상·권한이 불명확하면 중단하고 상향한다(fail-closed).

## 레포 고유 규칙

- 임원 대시보드 ECharts 시각화 및 다크/라이트 테마 전환 기능을 유지한다.
- 제품 소개 페이지(`home/products.html`, `home/mango.html`)의 정적 이미지 및 자산 경로를 보존한다.

## 보고와 증거

- 완료 보고에는 경로·sha8·판정·건수를 포함한다. 실측과 추정을 구분한다.
- 감사 기록·receipt는 append-only로 남긴다.
