# 확보한 HTML의 역할

대상은 Site 소스 `0c396f9556499ed2a6143b5114d1cf05116ef0ec`의 dist/index.html이다. GitHub main에는 아직 이 소스가 없다.

| 구성 | 실제 동작 / 데이터 |
|---|---|
| 화면 | header, 마음/정보량 선택 aside, 5개 탐험 영역, reader, rest |
| 콘텐츠 | script의 worlds: 5개 영역과 각 3개 조각. 외부 검색이나 AI 생성 호출 없음 |
| 상태 | mood, pace, current, level 및 discovered Set. 메모리에만 존재 |
| paint() | 선택 버튼/영역 버튼을 다시 만들고 추천·발견 개수 갱신 |
| read() | 현재 조각·예시·이전/다음/쉬기 버튼 렌더링 |
| pause()/resume | 탐험·리더·휴식 영역의 hidden 클래스 전환. 현재 메모리 상태를 다시 표시 |
| 스타일 | inline CSS, 시스템 글꼴, 800px/440px 미디어쿼리 |
| 저장/서버 | 이 HTML에 DB·localStorage·백엔드·모델 API 연결 없음 |

“같은 자리에서 이어가기”는 현재 탭에서 쉬기→재개할 때의 상태 복원이다. 새로고침/탭 종료 뒤 영구 복구는 구현되지 않았다. 서버에 개인정보를 저장하는 기능이 있다고 해석하지 않는다.

현재 innerHTML에는 내장 문자열이 들어간다. innerHTML 사용만 보고 현재 사용자 입력 XSS를 확정할 수 없다. 향후 사용자·외부 콘텐츠를 연결한다면 그 경계에서 별도 검토해야 한다.
