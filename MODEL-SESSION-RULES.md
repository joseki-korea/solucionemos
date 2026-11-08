---
id: "solucionemos/MODEL-SESSION-RULES.md"
title: "Model Session Rules Pointer"
repo: "joseki-korea/solucionemos"
device_scope: "all"
doc_type: "rules"
tags:
  - "rules"
  - "models"
  - "pointer"
status: "DRAFT"
updated: "2026-11-08"
source_of_truth: "docs/MODEL-SESSION-RULES.md"
---

# Model Session Rules — solucionemos

본 문서는 `joseki-korea/solucionemos` 레포지토리의 모델 배치 및 세션 운영 규칙에 대한 상위 요약 및 포인터입니다.

## 규칙 상속 체계 (Rules Inheritance)

- **GLOBAL (전역 정본)**: `solucionemos-vault/rules/INDEX.md` (Rule 00 · Rule 01 · Rule 02 · Rule 04).
  - 본 레포지토리는 vault 전역 정본 규칙을 상속하며, 전역 규칙은 절대 복사하지 않고 포인터로만 참조합니다.
  - 전역 규칙과 지역 규칙 충돌 시 **vault 전역 정본이 항상 우선**합니다.
- **LOCAL (지역 규칙)**: 본 레포지토리 전용 모델 배치 및 세션 운영 규칙 (하단 정의).
  - 지역 규칙은 전역 규칙을 보강(Add)할 수 있으나, 전역 규칙을 완화(Relax)하거나 배제할 수 없습니다.

## 1. 핵심 세션 규칙 요약
1. **모델 배치**: Control/PM/Main = Opus 5.5, Work = Codex Terra (코드/이동/수정) + Antigravity (검토/문서) + Claude Haiku (조회/정리/검증).
2. **동시성 통제**: 세션 간 동일 파일 동시 수정 금지 (File-split 원칙 준수).
3. **세션 명명**: `device4-session4-model-role` (하이픈 구분, 괄호 금지).
4. **인계 원칙**: 컨텍스트 40% 도달 시 handoffs/ 작성 후 후속 세션(v2)으로 전환 (제자리 /clear 금지).
5. **권한 모드**: 무중단 파이프라인을 위해 바이패스(Bypass-only) 세션으로 구동.

## 2. 정본 문서 안내
상세한 모델 배치 매트릭스, 세션 역할 정의 및 과적 대응 수칙은 아래 정본 문서를 참고하십시오:
👉 **[docs/MODEL-SESSION-RULES.md](docs/MODEL-SESSION-RULES.md)**
