# Echo — 제품 사이트

러닝 · 걷기 · 자전거 GPS 운동 기록 앱 **Echo**의 공식 사이트입니다.
빌드 과정 없는 정적 사이트이며 GitHub Pages로 서비스됩니다.

- **라이브** — <https://edwin-space.github.io/echo-space/>
- **App Store** — <https://apps.apple.com/kr/app/id6795827065>
- **운영** — [FunnySquare Inc.](https://funny-square.com)

> Return, not reaction. — 기록은 나에게 돌아옵니다.

## 구조

```
index.html            홈 (한국어)          en/index.html            홈 (영어)
features/             화면 가이드 (한국어)   features/en/             화면 가이드 (영어)
privacy/              개인정보처리방침       privacy/en/              Privacy Policy
terms/                이용약관              terms/en/                Terms of Use
support/              지원 및 문의          support/en/              Support
404.html              오류 페이지
assets/styles.css     디자인 시스템 (전 페이지 공용)
assets/site.js        테마 · 메뉴 · 스크롤 동작
assets/screens/       실제 앱 스크린샷
app-ads.txt           AdMob authorized sellers 선언
```

## 디자인

퍼니스퀘어 회사 사이트([funny-square.com](https://funny-square.com))와 같은 디자인 언어를 쓰되,
액센트 컬러만 Echo의 시안으로 바꾼 형태입니다.

- 다크 모드 기본, 우측 상단 버튼으로 라이트 모드 전환 (`localStorage`에 저장, 없으면 OS 설정을 따름)
- Pretendard Variable + JetBrains Mono
- 스크롤 리빌 · 섹션 하이라이트 · 진행바는 `IntersectionObserver` 기반, 미지원 시 즉시 최종 상태
- `prefers-reduced-motion` 존중
- 의존성 없는 순수 HTML/CSS/JS

`assets/styles.css` 또는 `assets/site.js`를 수정하면 각 HTML의 `?v=` 값을 함께 올려야
브라우저 캐시가 갱신됩니다.

## 손대면 안 되는 것

아래는 외부 시스템이 참조하고 있어, 지우거나 값을 바꾸면 즉시 문제가 생깁니다.

| 대상 | 이유 |
|---|---|
| `app-ads.txt` | AdMob authorized sellers 검증. 지우면 광고 수익 인증이 깨집니다 |
| `index.html`의 `google-site-verification` 메타 태그 | Search Console 소유 확인 |
| `privacy/`, `terms/`, `support/` 본문 | App Store 심사와 앱 내 링크가 참조하는 법적 고지. 버전·시행일 이력이 포함되어 있습니다 |
| `.nojekyll` | GitHub Pages의 Jekyll 처리 비활성화 |

이번 개편에서 위 네 가지는 **한 글자도 바꾸지 않았습니다.** 법적 고지 본문은 원본에서
그대로 옮겼고, 바깥 껍데기(내비게이션 · 푸터 · 스타일)만 교체했습니다.

## 로컬에서 보기

```bash
python3 -m http.server 4322
```

`http://localhost:4322/` 를 엽니다.

## 배포

`main`에 push하면 GitHub Pages가 1~2분 안에 반영합니다.

```bash
git push origin main
```

## 남은 작업

- [ ] 문의 주소가 `helper@gleam.com`입니다. 브랜드 표기(`gleaum.com`)와 철자가 달라 확인이 필요합니다
- [ ] 법적 고지의 운영자 표기가 "Edwin"입니다. 퍼니스퀘어 법인 명의로 바꿀지 검토가 필요합니다
- [ ] 영어 페이지가 한국어 앱 스크린샷을 그대로 씁니다. 영문 스크린샷이 준비되면 교체하세요
- [ ] Android 출시 시 `준비 중` 배지를 실제 Google Play 링크로 교체하세요

---

© Echo · FunnySquare Inc.
