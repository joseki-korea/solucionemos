---
id: "solucionemos/docs/MODEL-SESSION-RULES.md"
title: "Model Session Rules and Operational Placement"
repo: "joseki-korea/solucionemos"
device_scope: "all"
doc_type: "rules"
tags:
  - "rules"
  - "models"
  - "sessions"
  - "orchestration"
status: "DRAFT"
updated: "2026-11-08"
source_of_truth: "docs/MODEL-SESSION-RULES.md"
---

# 모델 세션 규칙 및 운영 배치 (Model Session Rules) — solucionemos

## 규칙 상속 체계 (Rules Inheritance)

- **GLOBAL (전역 정본)**: `solucionemos-vault/rules/INDEX.md` (Rule 00 · Rule 01 · Rule 02 · Rule 04).
  - 본 레포지토리는 vault 전역 정본 규칙을 상속하며, 전역 규칙은 절대 복사하지 않고 포인터로만 참조합니다.
  - 전역 규칙과 지역 규칙 충돌 시 **vault 전역 정본이 항상 우선**합니다.
- **LOCAL (지역 규칙)**: 본 레포지토리 전용 모델 배치 및 세션 운영 규칙 (하단 정의).
  - 지역 규칙은 전역 규칙을 보강(Add)할 수 있으나, 전역 규칙을 완화(Relax)하거나 배제할 수 없습니다.

## 1. 모델 배치 매트릭스 (Model Placement Matrix)

CEO 지침(2026-11-08)에 따른 모델 및 세션 역할 배치:

| 구분 | 전담 모델 | 역할 및 권한 범위 | 주요 금지 사항 |
|---|---|---|---|
| **Control / Persona / Telegram / Main** | Claude 3.5 / Opus 5.5 | 상위 지시 접수, 아키텍처 거버넌스, 태스크 디스패치 및 최종 감리/보고 | 비즈니스 코드 직접 구현 금지 |
| **PM Session** | Claude 3.5 / Opus 5.5 | 마일스톤 계획(Plan), 작업 분할(WBS), 디스패치, 품질 게이트 검수 및 인수(Acceptance) | 비즈니스 코드 직접 구현 및 수정 금지 |
| **Work Session (코드 구현)** | Codex Terra | 소스코드 구현, 리팩터링, 파일 이동(`git mv`), 빌드/테스트 스크립트 작성 | 동일 파일 동시 수정 금지 |
| **Work Session (검토 및 문서)** | Antigravity (AGY) | 풀스택 UI/UX 구현, 대시보드 뷰, 차트 렌더링, 교차 검토, 문서화 및 RAG 매니페스트 관리 | 추측성/상상 답변 금지, 증빙 필수 |
| **Work Session (조회 및 검증)** | Claude Haiku | 파일/문서 조회(Lookup), 디렉토리 정리(Cleanup), 문법/해시 검증(Verify) | 대규모 아키텍처 재설계 금지 |

### 파일 분할 원칙 (File-Split Principle)
- 복수의 작업 세션이 병렬 동작할 때, 동일한 파일에 동시 쓰기(Same-file writes)를 엄격히 금지합니다.
- 작업 대상 파일은 세션별로 명확히 분할 할당되어야 합니다.

## 2. 세션 명명 규칙 (Session Naming Convention)

Addendum 7 최신 규정에 따라 세션 식별자는 하이픈(`-`) 구분 형식을 준수합니다 (대괄호 사용 금지):

```text
device4-session4-model-role
```

- **구성 요소**:
  - `device4`: 기기 태그 4자리 (예: `gqfk`, `nwkw`, `96r0`, `hl95`)
  - `session4`: 고유 세션 ID 해시 4자리 (예: `48f7`, `567a`, `b1fe`, `0879`)
  - `model`: 실행 모델 식별자 (예: `opus55`, `terra`, `agy`, `haiku`)
  - `role`: 세션 역할 (예: `control`, `pm`, `worker`, `reviewer`, `lookup`)
- **실제 명명 예시**:
  - `gqfk-48f7-agy-worker`
  - `96r0-567a-opus55-control`
  - `gqfk-b1fe-haiku-lookup`
  - `nwkw-0879-terra-worker`

## 3. 컨텍스트 과적 방지 및 후속 인계 (Context Overload & Handoff)

- **과적 임계치 (Overload Threshold)**: 세션 컨텍스트 사용량이 약 **40%**에 도달하면 즉시 작업을 정리하고 후속 세션으로 인계합니다.
- **제자리 초기화 금지 (NO in-place `/clear`)**:
  - 실행 중인 세션에서 `/clear`를 직접 호출하여 컨텍스트를 지우는 행위를 일절 금지합니다.
  - 컨텍스트 소진 시 반드시 `handoffs/` 디렉토리에 정격 인계서(Handoff Note)를 작성한 후, 후속 세션(`v2`)을 인스턴스화하여 작업을 이어받습니다.
- **후속 세션 명명**: 기존 세션명 접미사에 판올림 버전을 부가합니다 (예: `gqfk-48f7-agy-worker-v2`).

## 4. 권한 모드 (Bypass-Only Seats)

- 모든 자율 작업 및 검토 세션은 비차단 파이프라인 운영을 위해 바이패스 모드(`--dangerously-skip-permissions` / bypass permissions on)로 동작합니다.
- 승인 대기로 인한 파이프라인 중단을 배제하고, 실시간 무결성 검증을 통해 품질을 담보합니다.
