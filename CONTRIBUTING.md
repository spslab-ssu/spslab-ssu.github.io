# SPS Lab 홈페이지 업데이트 가이드

| 항목    | 편집하는 곳                                          | 템플릿                 |
| ------- | ---------------------------------------------------- | ---------------------- |
| 새 멤버 | `_members/` 에 `.md` 추가 (+ `images/members/` 사진) | `_templates/member.md` |
| 새 뉴스 | `_posts/` 에 `.md` 추가 (+ `images/posts/` 사진)     | `_templates/post.md`   |

> HTML 을 직접 만질 필요가 없습니다. 목록과 개수는 자동으로 만들어집니다.

## 작업 방법

변경은 사이트에 바로 반영하지 않고, **새 브랜치(branch)에 올린 뒤 PR(Pull Request)로 제안 → 교수님이 확인 후 병합**하는 흐름입니다. 아래 두 방식 중 **편한 것 하나**를 고르세요. 결과는 같습니다.

### 방식 A — GitHub 웹에서 (설치 불필요, 처음이면 추천)

브라우저만 있으면 됩니다. 먼저 저장소 페이지 `spslab-ssu/spslab-ssu.github.io` 로 갑니다.

**새 파일을 추가할 때 (멤버·뉴스):**

1. 오른쪽 위 **`Add file ▾` → `Create new file`** 클릭.
2. 파일 이름 칸에 **폴더 경로까지** 입력합니다. 예: `_members/gildong_hong.md`
   (슬래시 `/` 를 넣으면 그 폴더 안에 자동으로 만들어집니다.)
3. 아래 큰 칸에 템플릿을 붙여넣고 값을 채웁니다.
4. 페이지 맨 아래 초록색 **`Commit changes…`** 버튼 클릭.
5. 뜨는 창에서 **"Create a new branch … and start a pull request"** 를 선택하고 **`Propose changes`** 클릭.
6. 다음 화면에서 **`Create pull request`** 클릭 → 끝. 교수님이 확인 후 병합합니다.

**사진을 올릴 때:**

1. 저장소에서 사진 폴더로 이동합니다 (멤버 `images/members/`, 뉴스 `images/posts/`).
2. **`Add file ▾` → `Upload files`** 로 사진을 끌어다 놓습니다.
3. 위와 똑같이 **새 브랜치로 커밋 → PR 생성**.

> 💡 한 작업에 필요한 파일(사진 + `.md`)은 **같은 브랜치/PR** 에 모으는 게 좋습니다. 첫 파일을 새 브랜치로 만든 뒤, 나머지는 그 브랜치를 골라 이어서 추가하세요.

### 방식 B — 내 컴퓨터에서 (로컬 git, 명령어 학습용)

**(처음 한 번만)** 저장소를 내려받습니다(clone):

```bash
git clone https://github.com/spslab-ssu/spslab-ssu.github.io.git
cd spslab-ssu.github.io
```

**(작업할 때마다)** 아래 순서를 반복합니다:

```bash
# 1) 항상 최신 상태에서 시작
git checkout main
git pull

# 2) 작업용 새 브랜치 만들기 (이름은 작업 내용을 알 수 있게)
git checkout -b add-member-gildong

# 3) 파일을 추가/수정하고 사진을 복사합니다
#    (_members/, _posts/, images/… 등)

# 4) 변경 사항 기록(commit)
git add .
git commit -m "Add member: Gildong Hong"

# 5) GitHub 에 올리기(push)
git push -u origin add-member-gildong
```

6. `push` 후 터미널에 나오는 링크를 누르거나, 저장소 페이지의 **"Compare & pull request"** 버튼으로 **PR** 을 만듭니다. 교수님이 확인 후 병합합니다.

> ⚠️ `main` 에서 바로 작업하지 말고 **항상 새 브랜치**(2번)를 만드세요. 시작 전 `git pull`(1번)도 잊지 마세요.
> 💡 올리기 전 내 컴퓨터에서 미리보려면(선택): `bundle install` 후 `bundle exec jekyll serve` → <http://localhost:4000> (종료는 `Ctrl+C`).

## ① 새 멤버

`_members/gildong_hong.md` 생성 (영문 소문자, 공백 대신 `_`):

```markdown
---
name: Gildong Hong
image: images/members/gildong_hong.jpg
role: ug # prof(교수) / grad(대학원생) / ug(학부연구생)
links:
  email: gildong@soongsil.ac.kr
---

### Research Interests

- **Optimization**

### Education

- **2026.03 - Present**: MS Student, Industrial and Information Systems Engineering, Soongsil University
```

사진(정사각형 권장)은 `images/members/` 에. 파일만 추가하면 Members 페이지에 자동 표시됩니다.
졸업 시에는 `role` 을 `alum_ug` 로 바꾸고, `members/index.md` 의 Past Members 에 이름을 옮겨 적습니다.

## ② 새 뉴스

`_posts/YYYY-MM-DD-slug.md` 생성 (날짜 필수, **미래 날짜는 안 보임**):

```markdown
---
title: "이혁진 연구원, 우수논문상 수상"
---

SPS Lab 이혁진 연구원이 … 수상하였습니다.

<div class="image-grid">
  <img src="/images/posts/2607-1.jpg" alt="수상 사진">
</div>
```

사진이 없으면 `<div class="image-grid">` 블록을 지웁니다. 사진은 `images/posts/` 에 올리고 **파일명·확장자 대소문자를 정확히** 맞춥니다. 파일만 추가하면 News·홈에 자동 표시됩니다.
