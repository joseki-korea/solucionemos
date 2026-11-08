---
id: solucionemos/RAG
title: "RAG guidance"
summary: "Index maintained Markdown as discrete source documents with stable paths and metadata. Exclude secrets, generated files, caches and binary assets; respect the source access controls. Consult `rag-manifest.json` for the tracked documentation inventory. Rebuild embeddings when source content changes."
domain: solucionemos
tags: [repository, documentation, rag]
owner: repository maintainers
status: draft
created: 2026-11-08
updated: 2026-11-08
source: RAG.md
lang: en
sensitivity: public
related: [README.md, RULES.md]
repo: solucionemos
device_scope: all
doc_type: documentation
source_of_truth: RAG.md
---

# RAG guidance

Index maintained Markdown as discrete source documents with stable paths and metadata. Exclude secrets, generated files, caches and binary assets; respect the source access controls. Consult `rag-manifest.json` for the tracked documentation inventory. Rebuild embeddings when source content changes.

## LLM Wiki

Repository sources remain in place; curated pages are in `docs/wiki/`. Follow `docs/wiki/SCHEMA.md`, run `python3 scripts/wiki-lint.py`, then regenerate `docs/_meta/rag-manifest.jsonl` with `python3 scripts/rag-manifest.py`. The manifest is a chunk inventory, not a vector index. Embeddings are built locally in the separate indexing phase; review material and access restrictions before indexing.
