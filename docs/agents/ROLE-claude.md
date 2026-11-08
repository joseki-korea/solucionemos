---
id: solucionemos/docs/agents/ROLE-claude
title: "Claude role"
summary: "Monitor and coordinate work."
domain: solucionemos
tags: [repository, documentation, rag]
owner: repository maintainers
status: draft
created: 2026-11-08
updated: 2026-11-08
source: docs/agents/ROLE-claude.md
lang: en
sensitivity: public
related: [README.md, RULES.md]
repo: solucionemos
device_scope: all
doc_type: documentation
source_of_truth: docs/agents/ROLE-claude.md
---

# Claude role

Monitor and coordinate work.

Input: assigned task and repository context.
Output: changes and validation evidence.
Follow [repository rules](../../RULES.md) and [architecture](../../ARCHITECTURE.md).
Do not expose secrets or change access settings.
Handoff: record status, evidence and remaining work.
