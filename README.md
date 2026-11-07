---
id: joseki-korea-solucionemos/README.md
title: 정푸드코리아 발주 임원 대시보드 및 회사 소개 — 프로젝트 개요
repo: joseki-korea-solucionemos
device_scope: all
doc_type: readme
tags: ["dashboard", "jungfoodkorea", "cloudflare-pages", "echarts", "executive-dashboard"]
status: DRAFT
updated: 2026-11-07
source_of_truth: README.md
---

# 정푸드코리아 발주 임원 대시보드 및 회사 소개

## 프로젝트 설명

㈜솔루시오네모스 및 정푸드코리아 발주·재고 모니터링 임원 대시보드와 공식 제품 소개 정적 웹 애플리케이션 (Cloudflare Pages `jungfoodkorea_dashboard`).

## 실행 방법

- Cloudflare Pages 배포 또는 로컬 웹 서버 실행: `npx wrangler pages dev .` 또는 `python3 -m http.server 8000`.
- 브라우저에서 `index.html` (발주 대시보드) 및 `home/index.html` (소개 홈) 접속.

## 규칙 요약

- 규칙 단일 정본은 vault `main`의 `rules/INDEX.md`와 Rule 00·01·02·04이다. 이 레포 규칙은 `docs/RULES.md`에 있다.
- 세션 역할(PM·작업·janitor)은 `docs/ROLES.md`에 있다.
- 폴더 구조와 폴더별 목적은 `docs/ARCHITECTURE.md`에 있다.
- 비밀·토큰·개인정보는 어떤 파일에도 평문으로 기록하지 않는다. force push 금지, main 직접 push 금지.

## 문서 링크

| 문서 | 경로 | 내용 |
|---|---|---|
| 규칙 | [docs/RULES.md](docs/RULES.md) | 레포 규칙 + vault 정본 포인터 |
| 역할 | [docs/ROLES.md](docs/ROLES.md) | PM·작업·janitor 세션 |
| 구조 | [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | 폴더 트리와 목적 |
| 핸드오프 | [handoffs/README.md](handoffs/README.md) | 에이전트 세션 인계 노트 |
| 에셋 | [assets/](assets/) | images · src · components · binaries |
| RAG 목록 | [rag-manifest.json](rag-manifest.json) | 검색 대상 문서 목록 |
