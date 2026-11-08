---
id: solucionemos/RULES
title: "Repository rules"
summary: "Follow these repository rules and existing project policies."
domain: solucionemos
tags: [repository, documentation, rag]
owner: repository maintainers
status: draft
created: 2026-11-08
updated: 2026-11-08
source: RULES.md
lang: en
sensitivity: public
related: [README.md, RULES.md]
repo: solucionemos
device_scope: all
doc_type: documentation
source_of_truth: RULES.md
---

# Repository rules

Follow these repository rules and existing project policies.

- Work on a branch and request review; do not force push.
- Keep secrets, credentials, private data and large binary assets out of commits.
- Preserve existing documents and verify changes before sharing.
- Review asset moves and update references and tests before moving.
- GitHub contains source and documentation; Drive sharing settings require separate authorization.

## 핸드오프 절차 (멀티에이전트)
1. 인수인계는 `docs/agents/handoffs/active/`에 `YYYYMMDD-HHMM-<from>-to-<to>-<topic>.md` 이름으로 씁니다.
2. 양식은 `docs/agents/handoffs/TEMPLATE.md`를 따릅니다.
3. 받은 쪽은 `ACK: <역할> <YYYYMMDD-HHMM>` 줄을 추가합니다. 기존 내용은 고치지 않습니다 (append-only).
4. 끝난 파일은 `archive/`로 옮깁니다.
5. 자세한 규칙: [docs/agents/handoffs/README.md](docs/agents/handoffs/README.md)
