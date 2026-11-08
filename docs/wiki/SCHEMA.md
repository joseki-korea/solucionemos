---
{"id": "solucionemos/wiki/schema", "title": "위키 작성 규칙", "summary": "수집, 질의 및 검증 절차", "domain": "website", "tags": ["wiki"], "owner": "repository maintainers", "status": "DRAFT", "created": "2026-11-08", "updated": "2026-11-08", "source": ["README.md"], "lang": "ko", "sensitivity": "public", "related": []}
---

# 위키 작성 규칙

## Ingest

원본을 읽고 한 주제에 한 페이지를 작성한다. 사실에는 `[source: 경로#L줄 @sha8]`를 붙인다. sha8은 원본 파일의 SHA-256 앞 8자리다. 비밀, 개인정보와 회사 내부 수치는 적지 않는다. 파일명은 영문 소문자 kebab-case를 쓴다. id, title, summary, domain, tags, owner, status, created, updated, source, lang, sensitivity, related 정보칸을 채운다. index와 append-only log를 갱신한다.

## Query

색인에서 관련 페이지를 찾고 인용된 원본 줄과 해시를 확인한다. 근거가 없거나 오래된 사실은 답변하지 않는다.

## Lint

`python3 scripts/wiki-lint.py`를 실행하고 `python3 scripts/rag-manifest.py`로 청크 목록을 갱신한다. 자동 검사는 의미적 정확성이나 비밀의 부재를 보장하지 않으므로 원문과 변경분을 별도 검토한다.

## 페이지 종류

개요, 모듈, 개념, 엔터티, 실행 방법과 FAQ로 구분한다. 한 절은 A4 한 장 이내로 유지하고 표에는 머리글, 그림에는 1~3줄 설명을 쓴다.
