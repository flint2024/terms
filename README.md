# Filty — Privacy Policy (개인정보처리방침)

Filty 앱의 **개인정보처리방침 정적 페이지**입니다. App Store 등록과 앱 내 링크에서 요구하는 "외부에서 접근 가능한 약관 URL"을 제공하기 위해, GitHub Pages로 호스팅하는 단일 HTML 페이지입니다.

- **공개 주소: https://flint2024.github.io/terms/**
- 한국어 / English **이중 언어** (상단 토글, 기기 언어가 영어면 자동으로 English 시작)
- **빌드·의존성 없음** — `index.html` 하나로 끝나는 순수 정적 페이지
- 호스팅: GitHub Pages (public repository `flint2024/terms`)

---

## 구성

```
.
├── index.html   # 약관 전문 (KO/EN) + 스타일 + 언어 토글 스크립트가 모두 인라인
└── README.md
```

`index.html` 한 파일에 모든 것이 들어 있습니다.
- CSS는 `<style>`에 인라인 — 외부 스타일시트/폰트 요청 없음
- 언어 전환은 `<script>`의 `setLang()` — 프레임워크 없음
- CSS 변수(`--fg`, `--accent` 등)로 색상 관리

---

## 배포 (GitHub Pages)

이 페이지는 `flint2024/terms` 저장소에서 GitHub Pages로 이미 서비스 중입니다.

- **라이브 URL: https://flint2024.github.io/terms/**
- 저장소: `github.com/flint2024/terms` (public)

빌드 과정이 없으므로, `index.html`을 저장소 루트에 커밋하면 됩니다(파일명은 반드시 `index.html` — Pages 기본 문서). `main`에 push하면 별도 Action 없이 자동으로 재배포됩니다.

### 공개 URL 확인하는 법

GitHub에 접속 → **`terms` 저장소 → Settings → Pages** 페이지로 들어가면, **상단에 현재 게시된 주소**가 표시됩니다.

- "Your site is live at **https://flint2024.github.io/terms/**" 형태로 뜨며, 옆의 **Visit site** 버튼으로 바로 열 수 있습니다.
- 같은 화면에서 배포에 사용하는 **Branch / 폴더 설정**(`Deploy from a branch` → `main` `/ (root)`)도 확인·변경할 수 있습니다.
- 방금 push한 변경이 반영 중이면 잠깐 빌드 표시가 나타났다가 완료되면 위 주소가 갱신됩니다.

> 최초 설정 시에는 Settings → Pages에서 Source를 `Deploy from a branch`, Branch를 `main` `/ (root)`로 지정하면 됩니다. 커스텀 도메인이 필요하면 같은 화면의 Custom domain에 등록하고 저장소 루트에 `CNAME` 파일을 둡니다.

---

## 배포 전 교체 항목 (중요)

`index.html`에는 출시 전 실제 값으로 바꿔야 하는 **플레이스홀더**가 있습니다. 노란색으로 강조되어 있고, CSS 클래스 `.ph` / `.ph-note`로 표시됩니다.

- [ ] `<span class="ph">"가명"</span>` → 실제 **개발자명**(KO·EN 양쪽)
- [ ] `<span class="ph">example@gmail.com</span>` → 실제 **문의 이메일**(KO·EN 양쪽, 8. 문의 / 8. Contact)
- [ ] 상단 **안내 박스**(`.ph-note`, "배포 전 교체 필요") 삭제
- [ ] 필요 없으면 `.ph` / `.ph-note` **스타일 정의도 삭제**
- [ ] 내용 변경 시 **최종 수정일 / Last Updated** 날짜 갱신

교체가 끝났는지 빠르게 확인:

```bash
grep -n "ph-note\|class=\"ph\"\|가명\|example@gmail.com" index.html
# 아무것도 안 나오면 교체 완료
```

---

## 이 URL을 사용하는 곳

배포된 Pages 주소(**https://flint2024.github.io/terms/**)는 다음에 등록합니다.
- **App Store Connect** → 앱 정보의 개인정보처리방침 URL
- **앱 내 설정/약관 링크** (해당 화면이 있는 경우)
- AdMob 등 심사에서 약관 URL을 요구할 때

---

## 수정 방법

에디터로 `index.html`을 직접 편집하면 됩니다. 로컬 확인은 브라우저로 파일을 여는 것만으로 충분합니다.

```bash
# macOS
open index.html
# 또는 아무 정적 서버로
python3 -m http.server 8000   # http://localhost:8000
```

약관 문구는 `<section id="ko">`(한국어)와 `<section id="en">`(English) **양쪽을 함께** 수정해야 두 언어가 일치합니다.

---

## 참고

- 이 페이지 자체는 **어떤 개인정보도 수집·전송하지 않습니다**(정적 HTML, 분석 스크립트 없음).
- 약관 본문 기준: 사진·동영상 등 콘텐츠는 기기 내 처리, 무료 사용자에 한해 Google AdMob(앱 오프닝 광고) 식별자 수집, 결제는 Apple App Store 처리, 프리미엄 구독 시 광고·광고용 수집 없음.
- 약관 내용이 실제 앱 동작(수집 항목·광고·구독)과 어긋나지 않도록, 앱 스펙 변경 시 이 문서도 함께 갱신하세요.