---
{"id": "solucionemos/wiki/index", "title": "위키 색인", "summary": "위키 페이지 목록", "domain": "website", "tags": ["wiki"], "owner": "repository maintainers", "status": "DRAFT", "created": "2026-11-08", "updated": "2026-11-08", "source": ["README.md"], "lang": "ko", "sensitivity": "public", "related": []}
---

# 위키 색인

- [저장소 개요](pages/overview.md) — 이 저장소에는 제품 웹사이트와 브라우저 대시보드가 있다. [source: README.md#L27 @b40d55ea]
- [대시보드](pages/modules/dashboard.md) — 루트 index.html 대시보드는 Supabase와 ECharts 클라이언트 라이브러리를 사용한다. [source: ARCHITECTURE.md#L31 @6b28a705]
- [제품 웹사이트](pages/modules/product-site.md) — home 디렉토리는 제품 웹사이트 HTML 페이지와 이미지 경로를 포함한다. [source: ARCHITECTURE.md#L27 @6b28a705]
- [차트 초기화](pages/modules/charts.md) — 대시보드의 initCharts 함수는 여러 차트 영역을 초기화한다. [source: index.html#L314 @eff595eb]
- [환율 조회](pages/modules/currency.md) — 대시보드의 환율 로더는 외부 환율 API에 요청한다. [source: index.html#L348 @eff595eb]
- [제품 페이지](pages/entities/product-pages.md) — 홈 페이지는 제품 목록과 개별 제품 페이지로 연결한다. [source: home/index.html#L167 @c5d02759]
- [정적 호스팅](pages/concepts/static-hosting.md) — 배포 설정은 저장소 루트를 정적 자산 디렉토리로 지정한다. [source: wrangler.toml#L4 @96c35e09]
- [로컬 미리보기](pages/howto/local-preview.md) — 정적 HTTP 서버로 루트를 제공하고 index.html 또는 home/index.html을 열도록 안내한다. [source: README.md#L33 @b40d55ea]
- [자주 묻는 질문](pages/faq.md) — Q. 대시보드 실행에 추가 서비스가 필요한가? A. README는 외부 서비스가 필요할 수 있다고 설명한다. [source: README.md#L35 @b40d55ea]
