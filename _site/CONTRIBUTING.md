# SPS Lab 홈페이지 업데이트 가이드

**새 멤버 · 뉴스 · 논문**을 추가하는 방법입니다. 변경은 PR(Pull Request)로 제안하면 교수님이 확인 후 반영하고, 반영되면 1\~2분 뒤 <https://spslab-ssu.github.io> 에 나타납니다.

| 항목 | 편집하는 곳 | 템플릿 |
|------|------------|--------|
| 새 멤버 | `_members/` 에 `.md` 추가 (+ `images/members/` 사진) | `_templates/member.md` |
| 새 뉴스 | `_posts/` 에 `.md` 추가 (+ `images/posts/` 사진) | `_templates/post.md` |
| 새 논문 | `_data/publications.yaml` 에 항목 추가 | `_templates/publication.yaml` |

> HTML 을 직접 만질 필요가 없습니다. 목록과 개수는 자동으로 만들어집니다.

## 작업 방법

변경은 사이트에 바로 반영하지 않고, **새 브랜치(branch)에 올린 뒤 PR(Pull Request)로 제안 → 교수님이 확인 후 병합**하는 흐름입니다. 아래 두 방식 중 **편한 것 하나**를 고르세요. 결과(PR)는 같습니다.

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

**기존 파일을 고칠 때 (논문):**

1. 저장소에서 `_data/publications.yaml` 파일을 엽니다.
2. 오른쪽 위 **연필(✏️) 아이콘** 클릭 → 항목을 추가/수정합니다.
3. 위 4\~6번과 똑같이 **새 브랜치로 커밋 → PR 생성**.

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
#    (_members/, _posts/, _data/publications.yaml, images/… 등)

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
role: ug            # prof(교수) / grad(대학원생) / ug(학부연구생)
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

## ③ 새 논문

`_data/publications.yaml` 의 알맞은 목록에 항목을 추가합니다. **개수는 자동 계산**되므로 따로 고치지 않습니다.

목록: `wip`(진행중) · `journal_intl`(국제저널) · `journal_dom`(국내저널) · `conf_intl`(국제학회) · `conf_dom`(국내학회)
```yaml
journal_intl:
  - title: "New Optimization Models for Smart Manufacturing"
    authors:
      - G. Hong
      - { name: Y. Lee, me: true, corr: true }   # me=우리 연구실(굵게), corr=교신저자(*)
    venue: "Omega"
    detail: "141, 103500, Jul. 2026"
    doi: "10.xxxx/xxxxx"                          # 없으면 이 줄 삭제
  # 기존 논문은 아래에 그대로 둡니다
```
- 학회(`conf_*`)는 `doi` 없이 `venue`(학회명) · `detail`(도시, 연도)만 적습니다. 국내 학회는 한글 가능.
- 진행중(`wip`)은 `title` + `status: accepted`(게재확정) 또는 `review`(심사중) — 없으면 `status` 줄 삭제.

## 올리기 전 체크리스트
- [ ] 머리말(`---` 사이) 형식과 들여쓰기를 지켰나요? *헷갈리면 기존 항목을 복사해 값만 바꾸세요.*
- [ ] 멤버 `role` 이 `prof`/`grad`/`ug` 중 하나인가요?
- [ ] 뉴스 날짜가 미래가 아니고, 사진 파일명·확장자가 대소문자까지 맞나요?
- [ ] 제목·저널명에 `:` 나 특수문자가 있으면 `"따옴표"` 로 감쌌나요?

막히면 교수님(<younsoo.lee@ssu.ac.kr>)께 문의하세요.
