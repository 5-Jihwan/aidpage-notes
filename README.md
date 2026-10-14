# AidPage 패치 노트

세 프로젝트 — [AidPage](https://5-jihwan.github.io/aidpage/)(재난 지원제도 안내), [AidPage Atlas](https://5-jihwan.github.io/aidpage/atlas.html)(시군구 재난 프로파일 도감), AidPage Simulator(대피 접근 계산, 연구 트랙) — 의 변경 기록을 한 사이트에서 프로젝트별로 나눠 보여 준다. https://5-jihwan.github.io/aidpage-notes/

- `index.html` — 정적 페이지 한 장. `notes.json`을 읽어 날짜별 기록·마일스톤·태그 필터·검색·펼침 상세(왜/무엇이 어떻게/어디서/원 커밋)를 그린다.
- `notes.json` — 기록 본문. 앱 저장소 커밋에서 사람이 바꾼 것만 뽑아 사용자 말로 다시 적는다. 자동 수집 커밋(`live …`, `ref: …`)은 제외. 정부 지원 기준의 변경 이력은 앱 안 `rules/changelog.json`이 따로 담당한다.

항목 추가: `entries[]` 맨 앞에 `{date, project, version, title, items[], tags[], commits[], detail:{why, how[], where, commits:[{hash,msg}]}}`를 넣는다. `how`의 각 줄은 가능하면 `전: … → 후: …` 꼴.

`project`는 `aidpage` · `atlas` · `sim` 중 하나(`projects[]`에 이름·설명·색). 한 배포가 두 프로젝트에 걸치면 항목을 프로젝트별로 나눠 따로 적는다(같은 커밋을 양쪽에 적어도 됨). 주소 `?p=atlas`로 프로젝트 하나만 연다. 마일스톤에도 `project`.
