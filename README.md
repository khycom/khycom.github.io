# Hoyoung Kim — Academic Portfolio

영문·국문 2개 언어로 운영하는 학술 포트폴리오. 빌드 과정 없이 `cv/` 폴더를
GitHub Pages에 올리면 바로 공개됩니다.

## 폴더 구조

```
academic-site/
└── cv/
    ├── index.html        ← 영문 페이지 (기본 진입)
    ├── index_kr.html     ← 국문 페이지
    ├── style.css         ← 두 페이지가 공유하는 스타일
    ├── images/
    │   └── profile.jpg   ← 프로필 사진 (정사각형, 400×400px 이상 권장)
    ├── logos/            ← 협업 기관 로고 (투명 배경 PNG)
    │   ├── kriso.png     · nice.png        · kibo.png
    │   ├── mof.png       · AIVeNautics.png · cois-lab.png
    │   └── MG.png
    └── files/
        └── CV_Hoyoung_Kim.pdf   ← 영문 CV 다운로드용
```

## 두 언어판의 관계

- 스타일은 **`style.css` 한 곳**에만 있습니다. 색상·여백·폰트 크기를 바꾸면
  두 페이지에 동시에 반영됩니다.
- 한글 폰트(Noto Serif/Sans KR)는 `html[lang='ko']` 선택자로만 덮어씁니다.
  국문 전용 스타일을 추가할 때도 같은 블록에 넣으세요.
- 각 페이지 사이드바 하단에 **언어 전환 링크**가 있고, `<head>`에는
  검색엔진용 `hreflang` 태그가 들어 있습니다.
- **내용은 자동으로 동기화되지 않습니다.** 논문·발표·프로젝트를 추가할 때는
  `index.html`과 `index_kr.html` 양쪽을 모두 수정해야 합니다.

## 내용 수정

각 섹션은 `<section id="...">` 로 구분되어 있습니다.

| id             | 영문             | 국문             |
| -------------- | ---------------- | ---------------- |
| `about`        | About            | 소개             |
| `education`    | Education        | 학력             |
| `interests`    | Research Interests | 연구 관심 분야 |
| `publications` | Publications     | 국내 학술지 논문 |
| `talks`        | Conference Talks | 학술대회 발표    |
| `projects`     | Selected Projects | 주요 프로젝트   |
| `awards`       | Awards & Honors  | 수상 및 장학     |
| `skills`       | Skills           | 기술 역량        |

### 프로젝트 추가하기

1. 기관 로고를 `cv/logos/` 에 넣습니다 (투명 배경 PNG 권장).
2. `index.html` 의 `<section id="projects">` 안에서 기존 `<li class="proj-item">`
   하나를 복사해 로고 경로·제목·기관명·기간·설명을 바꿉니다.
3. `index_kr.html` 에서 같은 작업을 국문으로 반복합니다.
4. 프로젝트는 **최신순**으로 정렬합니다.
5. 푸터의 "최종 수정 / Last updated" 날짜를 양쪽 다 갱신합니다.

로고 파일이 없거나 경로가 틀리면 `onerror` 핸들러가 기관명 텍스트를 대신
보여주므로 페이지가 깨지지는 않습니다.

## 로컬에서 미리보기

`style.css` 를 외부 파일로 분리했기 때문에, 파일을 더블클릭해 여는 대신
간단한 로컬 서버로 확인하는 편이 안전합니다.

```bash
cd cv
python3 -m http.server 8000
# → http://localhost:8000/index.html   (영문)
# → http://localhost:8000/index_kr.html (국문)
```

## GitHub Pages 배포

저장소의 **Settings → Pages** 에서 Source 를 `Deploy from a branch`,
Branch 를 `main` / `/ (root)` 로 지정하면 `/cv/` 경로로 공개됩니다.

```bash
git add .
git commit -m "Update CV"
git push
```

## 남은 항목

- 국문·영문 페이지 모두 영문 CV(`files/CV_Hoyoung_Kim.pdf`) 하나를 공유합니다.
  국문 CV PDF를 따로 만들면 `index_kr.html` 의 다운로드 링크만 바꾸면 됩니다.
- 사이드바 소속 표기가 영문은 "M.S. Researcher", 국문은 "연구원" 으로
  달라 국문에만 석사과정이 드러나지 않습니다.
- 프로필 사진이 없을 때의 이니셜 폴백은 현재 동작하지 않습니다
  (`.profile-photo` div 가 비어 있음).
