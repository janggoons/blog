# 장윤재 블로그 (janggoons.github.io/blog)

연구 사이트(https://janggoons.github.io, 저장소 `janggoons.github.io`)와 **분리된 블로그**입니다.
Jekyll + [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) 테마를 글 읽기 중심 레이아웃으로 바꿔 씁니다.

- 주소: https://janggoons.github.io/blog/
- 저장소: https://github.com/janggoons/blog
- 로컬 폴더: `C:\Users\owner\Dropbox\blog\`

## 새 글 쓰기

1. `_drafts/글-템플릿.md`를 복사해 `_posts/` 폴더에 넣습니다.
2. 파일 이름을 `2026-10-05-paper-reading-ct.md`처럼 **날짜-영문제목.md**로 바꿉니다.
3. 맨 위 `---` 사이의 제목 · 카테고리 · 태그를 고치고, 아래에 본문을 씁니다.
4. 올리기 (PowerShell):
   ```powershell
   cd C:\Users\owner\Dropbox\blog
   git add . ; git commit -m "글 추가" ; git push
   ```
   1~2분 뒤 블로그에 반영됩니다.

### 카테고리

| 카테고리 | 용도 |
|----------|------|
| 논문 읽기 | 진행 중인 연구와 관련된 논문을 읽고 생각 · 질문 남기기 |
| 강의 준비 | 수업 설계와 수업 후 돌아보기 |
| 기타 | 그 밖의 기록 |
| 공지 | 블로그 소식 |

카테고리 이름을 새로 쓰면 자동으로 카테고리 페이지와 첫 화면 칩에 추가됩니다.

### 알아 두면 좋은 것

- **첫 문단 = 목록 요약**: 첫 화면 글 목록에 첫 문단이 요약으로 나옵니다.
- **목차**: 긴 글은 머리말에 `toc: true`를 넣으면 오른쪽에 목차가 생깁니다.
- **그림**: `assets/images/`에 넣고 `![설명]({{ '/assets/images/파일명.png' | relative_url }})`로 넣습니다.
  이 블로그는 `/blog` 하위 주소라서 `/assets/...`로 바로 쓰면 그림이 깨집니다. 꼭 `relative_url`을 붙이세요.
- **임시 저장**: `_drafts/`에 둔 글이나 `published: false`인 글은 공개되지 않습니다.

## 설정 파일

| 파일 | 내용 |
|------|------|
| `_config.yml` | 블로그 제목 · 설명 · 댓글 · 검색 |
| `_data/navigation.yml` | 상단 메뉴 |
| `assets/css/main.scss` | 디자인 (연구 사이트와 같은 색 · 글꼴) |
| `_includes/archive-single.html` | 글 목록 카드 모양 |

## 댓글 켜기 (giscus, 선택)

1. 저장소 **Settings → General → Features**에서 **Discussions**를 켭니다.
2. https://github.com/apps/giscus 에서 앱을 설치하고 `blog` 저장소에 권한을 줍니다.
3. https://giscus.app/ko 에 `janggoons/blog`를 넣어 `repo_id` · `category_id`를 받습니다.
4. `_config.yml`의 `comments:`에서 `provider: false`를 지우고 giscus 설정 주석을 풀어 값을 채웁니다.
