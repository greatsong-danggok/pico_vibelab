# GitHub Pages 배포 가이드

Pico VIBE.LAB 사이트를 깃헙 페이지로 올리는 전체 흐름입니다.

---

## 📦 준비된 파일 4개

다운로드한 파일들을 한 폴더(예: `vibelab-danggok`)에 모아둡니다.

```
vibelab-danggok/
├── index.html              ← 메인 페이지 (레슨 목록)
├── lesson01_led.html       ← Lesson 01
├── lesson02_mq2.html       ← Lesson 02
└── README.md
```

**중요**: 파일명은 절대 바꾸지 마세요. `index.html`이 메인 페이지로 자동 인식되고, 레슨 카드의 링크가 정확한 파일명을 가리킵니다.

---

## 🚀 배포 방법

가장 쉬운 방법부터 순서대로 안내드릴게요. 선생님 상황에 맞는 걸 고르세요.

### 방법 A — 웹 브라우저만으로 (제일 쉬움, 추천)

깃헙 사이트에서 직접 파일을 드래그&드롭하는 방식입니다. 명령줄 안 써도 돼요.

#### 1단계: GitHub 계정과 새 리포지토리

1. https://github.com 접속, 계정이 없으면 가입
2. 우상단 `+` → **New repository** 클릭
3. **Repository name**: `vibelab-danggok` (원하는 이름 아무거나)
4. **Public** 선택 (Pages 무료 사용 위해 필수)
5. **Add a README file** 체크 ✓
6. **Create repository** 클릭

#### 2단계: 파일 업로드

1. 만든 리포 페이지에서 **Add file** → **Upload files** 클릭
2. 준비한 4개 파일을 **드래그&드롭** (`index.html`, `lesson01_led.html`, `lesson02_mq2.html`, `README.md`)
3. 아래 **Commit changes** 버튼 클릭

> README.md는 이미 있으니 덮어쓸지 물어보면 **"Replace"** 선택

#### 3단계: GitHub Pages 활성화

1. 리포 페이지 상단 메뉴에서 **Settings** 클릭
2. 좌측 사이드바에서 **Pages** 클릭
3. **Source** 섹션에서 **Deploy from a branch** 선택
4. **Branch**: `main` 선택, 폴더는 `/ (root)` 그대로
5. **Save** 클릭

#### 4단계: 배포 완료 확인

- 보통 1~2분 정도 걸려요.
- 같은 Pages 페이지 위쪽에 초록 박스로 **"Your site is live at https://<your-id>.github.io/vibelab-danggok/"** 가 나타나면 완료
- 그 링크가 학생들에게 공유할 주소입니다 🎉

---

### 방법 B — 명령줄(터미널) 사용 (개발자용)

GitHub Code 작업에 익숙하시면 더 빠릅니다.

```bash
# 1. 폴더에서 git 초기화
cd vibelab-danggok
git init
git add .
git commit -m "Initial: Lesson 01 (LED) + Lesson 02 (MQ-2)"

# 2. 깃헙에 만든 빈 리포와 연결 (URL은 본인 것으로)
git remote add origin https://github.com/<your-id>/vibelab-danggok.git
git branch -M main
git push -u origin main
```

그 다음 **방법 A의 3단계**(Pages 활성화)부터 똑같이 진행.

---

## 🔄 새 레슨 추가/수정 흐름

### 웹에서 직접 (방법 A 후속)

1. 깃헙 리포 페이지에서 수정할 파일 클릭
2. 우상단 연필 아이콘(✏️) 클릭 → 편집
3. 또는 **Add file** → **Upload files**로 새 HTML 추가
4. 하단 **Commit changes**
5. **새 레슨 추가 시 `index.html`도 수정** — 새 카드를 추가해야 메인 페이지에 나타남
6. 1~2분 후 사이트에 자동 반영

### 로컬에서 (방법 B 후속)

```bash
# 파일 수정 후
git add .
git commit -m "Add Lesson 03: ..."
git push
```

---

## 🧪 학생들에게 공유하기 전 체크리스트

- [ ] `https://<your-id>.github.io/vibelab-danggok/` 접속해서 메인 페이지 보임?
- [ ] **LESSON 01** 카드 클릭 → LED 페이지 정상 표시?
- [ ] **LESSON 02** 카드 클릭 → MQ-2 페이지 정상 표시?
- [ ] 모바일에서 열어봤을 때 사이드바가 위로 접혀서 잘 보임?
- [ ] 코드 블록의 **Copy 버튼** 정상 작동?
- [ ] 접이식 코드 블록 펼침/접기 정상?

---

## ⚙️ 자주 발생하는 문제

**"404 — There isn't a GitHub Pages site here."**
→ Pages 설정에서 Branch가 `main`인지, 폴더가 `/ (root)`인지 확인. 저장 누른 뒤 1~2분 기다리기.

**카드 클릭하면 404**
→ 파일명 오타 가능성. 카드 링크 `lesson01_led.html`과 실제 파일명이 정확히 같아야 함. 대소문자도 구분.

**스타일이 깨져서 보임**
→ 페이지가 외부 폰트(Google Fonts, Pretendard)와 Prism CSS를 CDN에서 불러옵니다. 학교 망에서 CDN이 차단되어 있는지 확인. 차단된 경우 폰트 파일을 리포에 직접 넣거나 시스템 폰트로 폴백시키도록 CSS 수정 필요.

**수정했는데 반영이 안 됨**
→ 브라우저 강력 새로고침 (Mac: ⌘+Shift+R, Windows: Ctrl+Shift+R). 깃헙 Actions 탭에서 빌드 진행 상황 확인 가능.

---

## 📌 다음 단계 아이디어

레슨이 5개 이상 쌓이면 정적 사이트 제너레이터로 옮기는 게 편합니다.

- **MkDocs Material** — 마크다운으로 작성, 사이드바·검색 자동 (이전에 쓰셨던 도구)
- **Astro / 11ty** — HTML 그대로 쓰면서 공통 레이아웃 분리 가능
- 현재 단일 HTML 방식은 **5개까지** 추천. 그 이상은 레이아웃 중복 관리가 힘들어집니다.

---

© 2026 석리송 · 당곡고 × 수도여고 인공지능과 피지컬 컴퓨팅
