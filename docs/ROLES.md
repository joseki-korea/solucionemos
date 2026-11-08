---
id: "solucionemos/docs/ROLES.md"
title: "Repository Roles and Model Assignments"
repo: "joseki-korea/solucionemos"
device_scope: "all"
doc_type: "roles"
tags:
  - "roles"
  - "sessions"
  - "model-placement"
status: "DRAFT"
updated: "2026-11-08"
source_of_truth: "docs/MODEL-SESSION-RULES.md"
---

# 세션 역할 및 모델 배치 (Roles & Model Placement) — solucionemos

본 문서는 `joseki-korea/solucionemos` 레포지토리에서 11-08 최신 전역 규칙에 따른 세션 역할과 모델 배치를 정의합니다.

## 1. 관제 및 관리 세션 (Claude 3.5 / Opus 5.5 전용)

Claude는 관제, 기획 및 모니터링 전용 세션입니다. 비즈니스 코드를 직접 구현하지 않고 작업 분할, 디스패치 및 최종 감리를 담당합니다.

- **총괄 관제 세션 (Control / Persona / Telegram)**: 지시 접수, 아키텍처 거버넌스 및 최종 보고.
- **PM 세션 (Claude Opus 5.5)**: 마일스톤 기획(Plan), 작업 분할(WBS), 디스패치(Dispatch), 품질 게이트 검수 및 인수(Acceptance). 👉 **[docs/PM.md](PM.md)**
- **Janitor 세션**: 맥락 과적 방지 와치독 전용. 사용량 약 40% 도달 시 핸드오프 작성 및 후속 세션(v2) 인계를 유도합니다 (제자리 /clear 금지).

## 2. 작업 세션 (Work Sessions — Codex Terra / Antigravity / Claude Haiku)

작업 세션은 PM이 배정한 명확한 태스크를 격리된 워크트리에서 수행합니다. 복수 작업 세션 간 동일 파일 동시 수정을 금지합니다 (File-split 원칙).

| 실행기 / 모델 | 전담 업무 영역 | 작업 불변식 |
|---|---|---|
| **Codex Terra** | 소스코드 구현, 코어 계산 로직, 리팩터링, 파일 이동(`git mv`), 데이터 변환 | 격리 워크트리, 단독 커밋, 구체적 실행 증거 필수 |
| **Antigravity (AGY)** | 풀스택 UI/UX 구현, 대시보드 뷰, 차트 렌더링, 교차 검토(Review), 아키텍처 문서화, RAG 인덱싱 | Strict Mode 90점 이상 검증, 실시간 증빙 |
| **Claude Haiku** | 소스코드/문서 경로 조회(Lookup), 디렉토리 위생 정리(Cleanup), 문법 및 해시 무결성 검증(Verify) | 대규모 코드 재설계 금지, 빠른 조회 및 정리 전담 |

## 3. 세션 명명 및 인계 규칙

- **세션 명명**: `device4-session4-model-role` (하이픈 구분, 괄호 금지).
  - 예: `gqfk-48f7-agy-worker`, `96r0-567a-opus55-control`, `gqfk-b1fe-haiku-lookup`, `nwkw-0879-terra-worker`
- **컨텍스트 인계**: 40% 임계치 도달 시 `handoffs/`에 인계서를 작성하고 후속 세션(v2)으로 전환합니다 (NO `/clear`).
- **권한 모드**: 모든 자율 작업 세션은 바이패스 모드(Bypass-only)로 동작하여 파이프라인 중단을 배제합니다.
