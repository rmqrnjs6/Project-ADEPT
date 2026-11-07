# 원본 확보 및 검토 기준선

2026-11-08 KST.

| 항목 | 이번 확인 |
|---|---|
| GitHub 기준 | `7188aff41bed090224f651bc1207da40b1352d2e`, main, README 1개 |
| 다른 브랜치 / 열린 PR / Actions | 조회 시 main만 존재 / 없음 / 없음 |
| README의 사이트 | https://their-world.kiwoo-02.chatgpt.site |
| 일치한 사용자 소유 Site | 그들의 세계, `appgprj_6ac72e73f4c88191815f5c0a6b461893` |
| 확보한 소스 커밋 | `0c396f9556499ed2a6143b5114d1cf05116ef0ec` |
| 저장 버전 | 버전 1, source.commit_sha가 확보 커밋과 일치 |
| 추적 소스 | `.openai/hosting.json`, `dist/index.html` |
| HTML SHA-256 | `82a990bb0d1d760eda609ef8d2d53019e0a09a0a3c14e8843fdc75bc567fa3a7` |

사이트 소스 저장소를 읽기 위해 별도 체크아웃으로 확보했다. 체크아웃은 깨끗한 상태다. 원본을 GitHub에 임의 이식하거나 사이트를 수정·배포·공개 설정 변경하지 않았다. 이 감사 PR은 문서만 추가한다.

GitHub에 소스가 없다는 사실과 어디에도 원본이 없다는 판단은 다르다. 이번에는 연결된 소유 사이트와 README URL을 대조해 출처를 확보했으므로 그 HTML의 정적 검토는 가능하다. GitHub README 작성 시점의 제작본과 완전히 동일한 판본인지는 별도 이력 대조 전까지 확정하지 않는다.

## 검증

- HTML 전체의 구조·스크립트 정적 검토 완료. 사용자 입력/외부 데이터 연동은 없고 내장 콘텐츠로 DOM을 구성한다.
- script 부분 추출 후 Node 24.22.1의 `node --check`: 종료 코드 0.
- Playwright의 Chromium 실행을 실제 시도했으나 브라우저 실행 파일이 없어 실패했다. 브라우저 사용자 흐름·접근성·반응형 검증은 BLOCKED다. 구문 통과를 화면 동작 통과로 바꾸어 보고하지 않는다.
- 별도 테스트·CI는 확보한 소스에 없다. 코드 품질·UX 완성이나 테스트 통과 수를 가정하지 않는다.
