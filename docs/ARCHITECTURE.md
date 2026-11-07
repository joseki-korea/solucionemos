---
id: joseki-korea-solucionemos/docs/ARCHITECTURE
title: 정푸드코리아 발주 임원 대시보드 및 회사 소개 — 폴더 구조
repo: joseki-korea-solucionemos
device_scope: all
doc_type: architecture
tags: [architecture, folders]
status: DRAFT
updated: 2026-11-07
source_of_truth: repo tree
---

# 폴더 구조

## 폴더 트리

기존 코드 폴더는 그대로 두고 아래 표준 폴더만 필요한 만큼 추가한다. 실제 트리로 채운다.

```text
.
./README.md
./assets
./assets/binaries
./assets/binaries/README.md
./assets/binaries/drive-manifest.json
./assets/components
./assets/components/README.md
./assets/images
./assets/images/README.md
./assets/images/drive-manifest.json
./assets/src
./assets/src/README.md
./docs
./docs/ARCHITECTURE.md
./docs/ROLES.md
./docs/RULES.md
./handoffs
./handoffs/README.md
./handoffs/_TEMPLATE.md
./home
./home/assets
./home/assets/food_golbaengi.jpg
./home/assets/hero_cans.png
./home/assets/prod_mango.jpg
./home/assets/prod_peach.jpg
./home/index.html
./home/mango.html
./home/products
./home/products.html
./home/products/깐포도.jpg
./home/products/백도.jpg
./home/products/애플망고.jpg
./home/products/자연산골뱅이.jpg
./home/products/큰구슬골뱅이.jpg
./home/products/황도.jpg
./index.html
./rag-manifest.json
./wrangler.toml
```

## 표준 폴더와 목적

| 폴더 | 목적 | 넣으면 안 되는 것 |
|---|---|---|
| `docs/` | 규칙·역할·구조 문서 | 비밀, 생성 산출물 |
| `handoffs/` | 에이전트 세션 핸드오프 노트(파일당 1건) | 비밀, 전체 로그 |
| `assets/images/` | 이미지 + alt-text/캡션 md | 개인정보 사진, 대용량 원본 |
| `assets/src/` | 소스코드 조각·스니펫 | 앱 본체 코드, 비밀 |
| `assets/components/` | 재사용 컴포넌트 | 빌드 산출물 |
| `assets/binaries/` | 바이너리 안내(실파일은 .gitignore 또는 LFS) | 비밀, 대용량 파일 커밋 |

## 기존 폴더 설명

| 폴더/경로 | 설명 |
|---|---|
| `index.html` | 정푸드코리아 발주 임원 대시보드 메인 화면 |
| `home/` | 정푸드코리아 회사 소개, 제품 카탈로그 및 상세 안내 페이지 |
| `wrangler.toml` | Cloudflare Pages 정적 에셋 배포 설정 |
