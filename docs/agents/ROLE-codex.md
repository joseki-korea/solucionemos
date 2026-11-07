---
id: solucionemos/docs/agents/ROLE-codex
title: "Codex role"
summary: "Implement and validate assigned changes."
domain: solucionemos
tags: [repository, documentation, rag]
owner: repository maintainers
status: draft
created: 2026-11-08
updated: 2026-11-08
source: docs/agents/ROLE-codex.md
lang: en
sensitivity: public
related: [README.md, RULES.md]
repo: solucionemos
device_scope: all
doc_type: documentation
source_of_truth: docs/agents/ROLE-codex.md
---

# Codex role

Implement and validate assigned changes.

Input: assigned task and repository context.
Output: changes and validation evidence.
Follow [repository rules](../../RULES.md) and [architecture](../../ARCHITECTURE.md).
Do not expose secrets or change access settings.
Handoff: record status, evidence and remaining work.
