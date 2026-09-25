# Logos

프로젝트 섹션에 쓰이는 협업 기관 로고입니다. 투명 배경 PNG 를 권장합니다.

## 현재 파일

| 파일               | 기관                                          |
| ------------------ | --------------------------------------------- |
| `MG.png`           | 새마을금고중앙회 (KFCC)                       |
| `kriso.png`        | 선박해양플랜트연구소 (KRISO)                  |
| `nice.png`         | NICE평가정보                                  |
| `kibo.png`         | 기술보증기금 (KOTEC)                          |
| `mof.png`          | 해양수산부                                    |
| `AIVeNautics.png`  | 에이브노틱스                                  |
| `cois-lab.png`     | COIS Lab / 단국대학교                         |

파일명 대소문자까지 HTML 의 `src` 와 정확히 일치해야 합니다
(`AIVeNautics.png` 는 대문자가 섞여 있으니 주의).

## 로고 추가하기

1. PNG 파일을 이 폴더에 넣습니다.
2. `index.html` 과 `index_kr.html` 의 `<section id="projects">` 안
   `.proj-logo` 블록에서 `src` 와 `alt` 를 지정합니다.
3. `.logo-fallback` div 에 기관 약칭을 적어둡니다.

로고 파일이 없거나 경로가 틀리면 `onerror` 핸들러가 이미지를 숨기고
`.logo-fallback` 텍스트를 대신 보여주므로 페이지는 깨지지 않습니다.
