# SPS Lab 홈페이지 업데이트 가이드 (학생용)

이 문서는 연구실 홈페이지에 **새 멤버 · 새 뉴스 · 새 논문**을 직접 추가하는 방법을 안내합니다.
프로그래밍을 몰라도 따라 할 수 있도록 단계별로 설명했습니다. 천천히 따라 하면 됩니다.

> 홈페이지는 GitHub Pages + Jekyll 로 만들어져 있습니다. 변경 사항을 저장소(repository)에 올리면, 1\~2분 뒤 실제 사이트(<https://spslab-ssu.github.io>)에 자동으로 반영됩니다.

---

## 목차

1. [무엇을 추가할 수 있나요?](#무엇을-추가할-수-있나요)
2. [시작하기 전에 (준비물)](#시작하기-전에-준비물)
3. [두 가지 작업 방식](#두-가지-작업-방식)
   - [방식 A — GitHub 웹에서 편집 (설치 불필요, 초보자 추천)](#방식-a--github-웹에서-편집-설치-불필요-초보자-추천)
   - [방식 B — 로컬 git으로 작업 (명령어 학습용)](#방식-b--로컬-git으로-작업-명령어-학습용)
4. [① 새 멤버 추가](#-새-멤버-추가)
5. [② 새 뉴스(소식) 추가](#-새-뉴스소식-추가)
6. [③ 새 논문 추가](#-새-논문-추가)
7. [사진(이미지) 추가 규칙](#사진이미지-추가-규칙)
8. [멤버 관리 — 졸업/퇴소, 숨기기](#멤버-관리--졸업퇴소-숨기기)
9. [로컬에서 미리보기 (방식 B 사용자)](#로컬에서-미리보기-방식-b-사용자)
10. [자주 하는 실수 & 최종 체크리스트](#자주-하는-실수--최종-체크리스트)

---

## 무엇을 추가할 수 있나요?

| 항목 | 편집하는 곳 | 자동 반영? |
|------|------------|-----------|
| **새 멤버** | `_members/` 에 파일 1개 추가 + 사진 | ✅ 파일만 추가하면 Members 페이지에 자동 표시 |
| **새 뉴스** | `_posts/` 에 파일 1개 추가 (+ 사진) | ✅ 파일만 추가하면 News·홈 "최근 소식"에 자동 표시 |
| **새 논문** | `pubs/index.md` 파일을 **직접 편집** | ⚠️ 직접 줄을 추가하고, 상단 개수도 같이 수정해야 함 |

각 항목의 **복붙용 템플릿**은 `_templates/` 폴더에 있습니다.

- `_templates/member.md` — 멤버 템플릿
- `_templates/post.md` — 뉴스 템플릿
- `_templates/publication.html` — 논문 템플릿

> 💡 멤버와 뉴스는 **새 파일 1개만 추가**하면 되므로 쉽습니다. 논문은 기존 파일을 직접 고쳐야 해서 조금 더 주의가 필요합니다.

---

## 시작하기 전에 (준비물)

1. **GitHub 계정** — 없으면 <https://github.com> 에서 무료로 가입하세요.
2. **저장소 접근 권한** — 교수님께 본인 GitHub 아이디를 알려 드리고 협업자(collaborator)로 추가해 달라고 요청하세요.
   저장소 주소: **`spslab-ssu/spslab-ssu.github.io`**
3. (방식 B 로컬 작업만 해당) **Git 설치** — <https://git-scm.com> 에서 설치. 로컬 미리보기까지 하려면 Ruby/Jekyll도 필요합니다(아래 9번 참고).

> **모든 변경은 곧바로 사이트에 반영되지 않고, 먼저 "Pull Request(PR)" 로 제안 → 교수님이 확인 후 병합(merge)** 하는 흐름을 권장합니다. 실수가 있어도 반영 전에 걸러낼 수 있어 안전합니다.

---

## 두 가지 작업 방식

두 방식 중 편한 것을 선택하면 됩니다. 결과물(PR)은 동일합니다.

- **방식 A (GitHub 웹):** 브라우저만 있으면 됩니다. 설치 불필요. **처음이라면 이 방식 추천.**
- **방식 B (로컬 git):** 컴퓨터에 저장소를 내려받아 작업. git 명령어를 익힐 수 있고, 올리기 전에 로컬에서 미리볼 수 있습니다.

### 방식 A — GitHub 웹에서 편집 (설치 불필요, 초보자 추천)

**새 파일을 만들 때 (멤버·뉴스 추가):**

1. 저장소 페이지(`spslab-ssu/spslab-ssu.github.io`)로 갑니다.
2. 오른쪽 위 **`Add file ▾` → `Create new file`** 클릭.
3. 파일 이름 칸에 **경로까지 포함**해 입력합니다. 예: `_members/gildong_hong.md`
   (`_members/` 처럼 폴더명을 슬래시와 함께 적으면 자동으로 그 폴더에 만들어집니다.)
4. 아래 내용 칸에 템플릿을 붙여넣고 값을 채웁니다.
5. 페이지 맨 아래 **`Commit changes...`** 클릭 → **"Create a new branch ... and start a pull request"** 선택 → **`Propose changes`** → **`Create pull request`**.

**기존 파일을 고칠 때 (논문 추가):**

1. 저장소에서 `pubs/index.md` 파일을 엽니다.
2. 오른쪽 위 **연필(✏️) 아이콘** 클릭 → 내용 수정.
3. 위와 동일하게 **새 브랜치로 커밋 → Pull Request 생성**.

**사진을 올릴 때:**

1. 저장소에서 사진을 넣을 폴더로 이동합니다 (멤버 사진은 `images/members/`, 뉴스 사진은 `images/posts/`).
2. **`Add file ▾` → `Upload files`** 로 사진을 끌어다 놓고, 동일하게 PR 로 제안합니다.

> 한 작업(예: 멤버 1명 추가)에 필요한 파일들(사진 + `.md`)은 **같은 브랜치/PR** 에 모아 두는 것이 좋습니다. 첫 파일을 새 브랜치로 만든 뒤, 나머지는 그 브랜치에서 이어서 추가하세요.

### 방식 B — 로컬 git으로 작업 (명령어 학습용)

처음 한 번만 저장소를 내려받습니다(클론):

```bash
git clone https://github.com/spslab-ssu/spslab-ssu.github.io.git
cd spslab-ssu.github.io
```

이후 작업할 때마다 다음을 반복합니다:

```bash
# 0) 항상 최신 상태에서 시작 (중요!)
git checkout main
git pull

# 1) 작업용 브랜치 생성 (이름은 작업 내용을 알 수 있게)
git checkout -b add-member-gildong

# 2) 파일 추가/수정 (에디터로 _members/, _posts/, pubs/index.md 등 편집, 사진 복사)

# 3) 변경 사항 저장
git add .
git commit -m "Add member: Gildong Hong"

# 4) GitHub에 올리기
git push -u origin add-member-gildong
```

`push` 후 터미널에 표시되는 링크를 누르거나, GitHub 저장소 페이지의 **"Compare & pull request"** 버튼으로 **Pull Request** 를 만듭니다. 교수님이 확인 후 병합합니다.

> ⚠️ `main` 브랜치에서 바로 작업하지 말고, 항상 **새 브랜치**를 만들어 작업하세요. 작업 전 `git pull` 로 최신 상태를 받는 것도 잊지 마세요.

---

## ① 새 멤버 추가

**필요한 것:** 멤버 파일 1개 + 프로필 사진 1장

### 1단계 — 사진 준비

- 정사각형에 가까운 사진을 준비합니다(얼굴이 중앙에 오도록). 권장: 가로세로 600×600px 내외, 1MB 이하.
- 파일명은 영문 소문자로: 예) `gildong_hong.jpg`
- `images/members/` 폴더에 올립니다.

### 2단계 — 멤버 파일 만들기

- 위치/이름: `_members/gildong_hong.md` (영문 소문자, 띄어쓰기 대신 `_` 사용)
- `_templates/member.md` 내용을 복사해 값을 채웁니다.

```markdown
---
name: Gildong Hong
image: images/members/gildong_hong.jpg
description:
role: ug
links:
  email: gildong@soongsil.ac.kr
---

### Research Interests
- **Optimization**
  - Mixed-Integer Programming

### Education
- **2026.03 - Present**: MS Student, Department of Industrial and Information Systems Engineering, Soongsil University
```

**`role` 값은 셋 중 하나입니다:**

| 값 | 의미 | Members 페이지 표시 위치 |
|----|------|------------------------|
| `prof` | 교수 | Professor |
| `grad` | 대학원생 | Graduate Students |
| `ug` | 학부연구생 | Undergraduate Researchers |

### 3단계 — 확인

파일을 올리면 **Members 페이지에 자동으로 추가**됩니다. 별도로 목록을 수정할 필요가 없습니다.

---

## ② 새 뉴스(소식) 추가

**필요한 것:** 포스트 파일 1개 (+ 사진은 선택)

### 1단계 — (사진이 있으면) 사진 준비

- `images/posts/` 폴더에 올립니다. 파일명 예: `2607-1.jpg`
- **확장자 대소문자를 정확히 기억하세요** (`.jpg` 와 `.JPG` 는 다릅니다).

### 2단계 — 포스트 파일 만들기

- 위치/이름: **`_posts/YYYY-MM-DD-제목.md`** 형식 (날짜 필수!)
  - 예: `_posts/2026-06-27-best-paper-award.md`
  - 날짜는 **오늘 날짜 또는 과거 날짜**로 적으세요. 미래 날짜면 사이트에 안 보일 수 있습니다.
  - 제목 부분(슬러그)은 영문 소문자 + `-` 권장.
- `_templates/post.md` 내용을 복사해 채웁니다.

```markdown
---
title: "이혁진 연구원, 우수논문상 수상"
---

SPS Lab 이혁진 연구원이 ... 우수논문상을 수상하였습니다. 축하합니다!

<div class="image-grid">
  <img src="/images/posts/2607-1.jpg" alt="수상 사진">
</div>
```

> 사진이 없으면 `<div class="image-grid"> ... </div>` 블록을 통째로 지우면 됩니다.

### 3단계 — 확인

파일을 올리면 **News 페이지와 홈 화면 "최근 소식"** 에 자동으로 추가됩니다.

---

## ③ 새 논문 추가

> ⚠️ 이 작업은 **`pubs/index.md` 파일을 직접 편집**하고, **상단의 개수도 같이 수정**해야 합니다. 천천히 따라 하세요. 템플릿은 `_templates/publication.html` 에 있습니다.

### 1단계 — 어느 섹션인지 정하기

`pubs/index.md` 에는 5개 섹션이 있고, 각각 `<ol class="pubs"> ... </ol>` 로 묶여 있습니다.

- Works in Progress (진행 중)
- International Publications (국제 저널)
- Domestic Publications (국내 저널)
- International Conferences (국제 학회)
- Domestic Conferences (국내 학회)

### 2단계 — 항목 추가

`_templates/publication.html` 에서 해당 유형의 블록을 복사해, 그 섹션의 `<ol class="pubs">` **바로 다음 줄(최신순이면 맨 위)** 에 붙여넣고 내용을 채웁니다.

**저널 논문 예시:**

```html
<li><div>
  <div class="pub_title">New Optimization Models for Smart Manufacturing</div>
  <div class="pub_meta">G. Hong, <span class="me">Y. Lee<sup>*</sup></span> · <span class="venue">Omega</span> 141, 103500, Jul. 2026</div>
  <a class="pub_link" href="https://doi.org/10.xxxx/xxxxx">on-line link <i class="fas fa-up-right-from-square"></i></a>
</div></li>
```

표기 규칙:
- `<span class="me">...</span>` → 우리 연구실 저자(교수님/연구원)를 감싸 강조합니다.
- `<sup>*</sup>` → 교신저자 표시.
- `<span class="venue">...</span>` → 저널/학회 이름.
- DOI 링크가 없으면 마지막 `<a class="pub_link">` 줄을 지웁니다.
- 학회 발표는 형식이 다릅니다(`pub_conf`). 템플릿의 3번 블록을 사용하세요.

### 3단계 — ★ 상단 개수 수정 (가장 중요) ★

파일 맨 위에 섹션별 개수가 적힌 부분이 있습니다:

```html
<nav class="jump-nav">
  <a class="jump" href="#wip">Works in Progress <span class="jump_count">5</span></a>
  <a class="jump" href="#intl">International <span class="jump_count">10</span></a>
  ...
</nav>
```

추가한 섹션의 숫자를 **1 늘려야** 합니다. 예: 국제 저널을 1편 추가했으면 `10` → `11`.
(이 숫자를 안 고치면 실제 목록과 표시된 개수가 어긋납니다.)

---

## 사진(이미지) 추가 규칙

- **멤버 사진:** `images/members/` 에 저장
- **뉴스 사진:** `images/posts/` 에 저장
- 본문/머리말에서 경로를 적을 때:
  - 멤버 파일 `image:` → `images/members/파일명` (맨 앞 `/` 없이)
  - 뉴스 본문 `<img src=...>` → `/images/posts/파일명` (맨 앞 `/` 있음)
- **파일명은 영문·숫자·`_`·`-` 만** 사용하고, 띄어쓰기·한글·특수문자는 피하세요.
- **확장자 대소문자까지 정확히 일치**시켜야 합니다 (`photo.JPG` 를 `photo.jpg` 로 적으면 안 보입니다).
- 용량은 가급적 1\~2MB 이하로 줄여서 올리세요(페이지 로딩 속도).

---

## 멤버 관리 — 졸업/퇴소, 숨기기

- **졸업·퇴소한 멤버:** 멤버 파일의 `role` 을 `alum_ug` 로 바꾸면 Members 목록에서 사라집니다.
  그런 다음, 보통 `members/index.md` 의 **"Past Members"** 부분에 이름을 추가합니다(기존 형식을 그대로 따라 하세요):

  ```html
  <div class="alumni-cohort">
    <span class="alumni-period">2026.01 – 2026.12</span>
    <span class="alumni-names">홍길동 · 김철수</span>
  </div>
  ```

- **임시로 숨기기:** 멤버 파일 머리말에 `published: false` 한 줄을 추가하면 사이트에 노출되지 않습니다.

---

## 로컬에서 미리보기 (방식 B 사용자)

올리기 전에 내 컴퓨터에서 사이트를 직접 확인할 수 있습니다(선택 사항이지만 추천).

```bash
# 처음 한 번 (Ruby가 설치되어 있어야 합니다)
bundle install

# 미리보기 서버 실행
bundle exec jekyll serve
```

실행 후 브라우저에서 <http://localhost:4000> 을 열면 됩니다. 파일을 수정하면 자동으로 새로고침됩니다.
종료는 터미널에서 `Ctrl + C`.

---

## 자주 하는 실수 & 최종 체크리스트

올리기 전에 확인하세요:

- [ ] **머리말(`---` ~ `---`) 형식**을 지켰나요? `---` 두 줄 사이에 설정이 들어갑니다.
- [ ] 멤버 `role` 이 `prof` / `grad` / `ug` 중 하나인가요? (오타 주의)
- [ ] 뉴스 파일명이 `_posts/YYYY-MM-DD-제목.md` 형식이고 날짜가 **미래가 아닌가요?**
- [ ] 사진을 먼저 올렸고, 파일 안의 경로/파일명이 **대소문자까지** 정확한가요?
- [ ] (논문) `pubs/index.md` 상단의 **개수(`jump_count`)** 를 같이 수정했나요?
- [ ] (논문) `<li>`, `<div>`, `</div>`, `</li>` **태그 짝이 맞나요?** 템플릿 블록을 통째로 복사하면 안전합니다.
- [ ] 한글 제목은 따옴표로 감쌌나요? 예: `title: "수상 소식"`

**문제가 생기면?**
- PR 화면에서 변경 내용(녹색=추가, 빨강=삭제)을 다시 확인하세요.
- 사이트가 깨졌다면 교수님이 GitHub에서 이전 상태로 되돌릴 수 있으니 너무 걱정하지 마세요.
- 막히면 교수님(<younsoo.lee@ssu.ac.kr>)께 어떤 작업을 하려 했는지와 함께 문의하세요.
