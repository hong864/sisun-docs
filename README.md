# sisun-docs

시선닷컴 서비스 기획팀 **기획 문서(PRD·요구사항 정의서 등) 전용 레포**.
Notion에서 정리한 내용을 HTML로 구성 → 이 레포에 커밋 → GitHub Pages URL을 Notion에 임베드해서 사용한다.

---

## 1. 시작 설정 (최초 1회)

1. 이 폴더 전체를 GitHub 레포(`sisun-docs`)에 업로드.
2. **Settings → Pages → Source: `main` 브랜치 / `/ (root)`** 선택 후 저장.
3. 몇 분 뒤 `https://hong864.github.io/sisun-docs/` 접속 확인.

> ⚠️ **public / private 확인**: public 레포면 URL을 아는 누구나 문서를 볼 수 있다.
> 대외비 기획 문서는 private 레포 + GitHub Pro/Team(유료) 조합이 필요하다.

---

## 2. 폴더 구조

```
sisun-docs/
├── index.html                  ← 전체 문서 허브(목차). Notion 최상단에 임베드.
├── README.md                   ← 이 파일
├── assets/
│   └── style.css               ← 모든 문서 공통 스타일
└── docs/
    └── 연도/월/일감-슬러그/
        ├── prd.html
        ├── requirements.html   ← 요구사항 정의서
        └── assets/             ← 이 문서 전용 이미지(필요 시)
```

신규 일감이 생기면 `docs/2026/06/일감이름/` 폴더를 만들고 `_template.html`을 복사해 작성한다.

---

## 3. 네이밍 규칙 (★ 변경 금지)

URL이 바뀌면 Notion 임베드가 전부 깨진다. **한번 정한 폴더·파일명은 바꾸지 않는다.**

- 폴더: `docs/<연도>/<월 2자리>/<일감-슬러그>/`
  - 예: `docs/2026/06/pdp-improvement/`
- 일감 슬러그: 영문 소문자 + 하이픈만. 한글·공백·대문자 금지.
  - 좋음: `cart-redesign`, `search-filter-v2`
  - 나쁨: `장바구니개편`, `Cart Redesign`, `cart_redesign`
- 문서 파일: `prd.html`, `requirements.html`, `flow.html` 등 종류명으로 통일.

---

## 4. 버전 관리

- 파일명에 `v1`, `v2`, `최종`, `진짜최종`을 붙이지 **않는다**.
- 같은 파일을 수정·커밋하면 git 히스토리가 버전을 자동 보관한다.
- 큰 개정이면 커밋 메시지에 남긴다. 예: `requirements: 결제 정책 v2 반영`

---

## 5. 작성 → 게시 플로우

1. Notion에서 PRD/요구사항 확정.
2. `_template.html` 복사 → 해당 일감 폴더에 `requirements.html`로 저장 → 내용 작성.
3. `index.html` 목차에 새 문서 링크 한 줄 추가.
4. 커밋 & 푸시.
5. Pages URL을 복사해 Notion에 `/embed` 블록으로 붙여넣기.
6. 이후 수정은 같은 파일 갱신 → URL 그대로라 Notion에 자동 반영.

---

## 6. 임베드 URL 형식

```
https://hong864.github.io/sisun-docs/docs/2026/06/pdp-improvement/requirements.html
```
