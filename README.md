# AidPage 패치 노트

[AidPage](https://5-jihwan.github.io/aidpage/)(재난 지원제도 안내)의 변경 기록 사이트. https://5-jihwan.github.io/aidpage-notes/

- `index.html` — 정적 페이지 한 장. `notes.json`을 읽어 날짜별 기록·마일스톤·태그 필터·검색·펼침 상세(왜/무엇이 어떻게/어디서/원 커밋)를 그린다.
- `notes.json` — 기록 본문. 앱 저장소 커밋에서 사람이 바꾼 것만 뽑아 사용자 말로 다시 적는다. 자동 수집 커밋(`live …`, `ref: …`)은 제외. 정부 지원 기준의 변경 이력은 앱 안 `rules/changelog.json`이 따로 담당한다.

항목 추가: `entries[]` 맨 앞에 `{date, version, title, items[], tags[], commits[], detail:{why, how[], where, commits:[{hash,msg}]}}`를 넣는다. `how`의 각 줄은 가능하면 `전: … → 후: …` 꼴.
