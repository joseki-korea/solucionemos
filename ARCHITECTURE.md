---
id: solucionemos/ARCHITECTURE
title: "Architecture"
summary: "This document describes the tracked repository at the time of the documentation update."
domain: solucionemos
tags: [repository, documentation, rag]
owner: repository maintainers
status: draft
created: 2026-11-08
updated: 2026-11-08
source: ARCHITECTURE.md
lang: en
sensitivity: public
related: [README.md, RULES.md]
repo: solucionemos
device_scope: all
doc_type: documentation
source_of_truth: ARCHITECTURE.md
---

# Architecture

This document describes the tracked repository at the time of the documentation update.

## Current components

- `home/` contains the product website HTML pages and images in `assets/` and `products/`.

## Flow and integrations

The root `index.html` is a browser dashboard using Supabase and ECharts client libraries. `wrangler.toml` configures the repository root as static assets. The repository is stored on GitHub. Its existing project documentation and code define any runtime data flows and external integrations; no new integration is introduced here.

## Asset migration

See [asset map](docs/ASSET-MAP.md). Proposed moves require review, reference updates and passing validation before execution. Roll back with a normal revert.
