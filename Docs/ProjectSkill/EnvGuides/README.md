# 환경 오류 — 일시정지와 직접 해결 가이드

인증·연결·권한·Maker 상태처럼 **사용자가 직접 고쳐야 하는 실행 환경 오류**를 만났을 때의 처리 규칙이다. 메인 채팅과 ship의 모든 담당(planner·coder·tester·reviewer)에 적용한다.

## 1. 언제 멈추는가

다음에 해당하면 우회·반복 재시도 없이 작업을 멈춘다.

- 인증 실패: MCP 401/403, `AUTH_HEADER_REJECTED`, 토큰·API 키 만료.
- 연결 실패: MCP 서버 연결 실패, Maker 도구가 목록에 없음, `unavailable` 응답, 타임아웃이 두 번 연속 발생.
- Maker 상태 불일치: 다른 월드·맵이 열려 있음(기록된 ID와 다름), Stop이 실패해 Play에서 빠지지 못함.
- 권한 거절: "user rejected MCP tool call" 등 사용자가 도구 호출을 거절함. 거절은 사용자의 결정이므로 다시 호출하지 않는다.
- 설치·경로 문제: 실행 파일·bat 경로 없음, Node 등 필수 프로그램 없음.
- 설정 미적용: 새 에이전트·설정이 세션 재시작 전이라 보이지 않음.

일시적인 네트워크 오류로 보이면 **한 번만** 다시 시도한다. 그래도 실패하면 멈춘다.

## 2. 멈추는 순서

1. **안전 지점에서 정지한다.** Play 중이고 Stop이 가능하면 Stop하고, 편집 중이던 파일은 어디까지 바뀌었는지 기록한다. 새 제품 변경·Play·다음 담당 호출은 하지 않는다.
2. **담당 에이전트는 메인 채팅에 반환한다.** 상태 `WAITING_ENV`, 실제 오류 문구, 멈춘 지점, Maker 최종 모드, 남은 변경을 돌려준다. 가이드는 메인이 쓴다.
3. **메인 채팅이 가이드를 쓴다.** 이 폴더에 `{YYYYMMDD}-{짧은-영문-슬러그}.md`로 아래 양식을 채운다. 진행 중인 run이 있으면 run.md 상태를 `WAITING_ENV`로 바꾸고 가이드 링크를 남긴다.
4. **사용자에게 보고하고 기다린다.** 가이드 링크와 핵심 조치 1~3줄을 알려 준다. 사용자가 해결했다고 말하기 전에는 자동으로 재개하지 않는다.
5. **재개할 때 먼저 확인한다.** 가이드의 "해결 확인" 호출을 실제로 실행해 정상인지 본 뒤, 멈춘 지점부터 같은 run으로 이어 간다. 해결된 가이드는 아래 "알려진 사례"에 배운 점을 반영하고 삭제한다.

비밀값(토큰·API 키·비밀번호)은 가이드·run·채팅에 절대 적지 않는다. 길이나 "설정됨/비어 있음" 정도만 쓴다. 사용자를 대신해 새 토큰을 입력하거나 계정을 만들지 않는다.

## 3. 가이드 양식

```markdown
# {한 줄 제목} ({YYYY-MM-DD})

- 상태: 해결 대기
- 멈춘 작업: {run-id·담당·요구/결함 ID, 또는 "조회 중"}
- Maker 마지막 상태: {맵·모드·사용 종료 여부, 확인 못 했으면 "미확인"}
- 남은 변경: {편집 중이던 파일과 상태, 없으면 "없음"}

## 증상
{실제 오류 문구를 그대로. 비밀값은 지운다.}

## 원인
- 확인된 사실: {...}
- 추정: {...}

## 직접 해결 방법
1. {누르거나 열 메뉴·파일 경로·값을 구체적으로}
2. {...}

## 해결 확인
- 사용자 확인: {사용자가 화면에서 볼 수 있는 결과}
- 재개 시 AI 확인: {실제로 호출할 도구와 기대 응답}

## 재개 요청 문장
"{예: 환경 문제 해결했어. 확인하고 REV-F01 이어서 진행해줘.}"
```

## 4. 알려진 사례

### A. msw-mcp 인증 실패 (401 / AUTH_HEADER_REJECTED)
- 증상: 세션 시작 시 "msw-mcp ... failed to connect (AUTH_HEADER_REJECTED)", 문서·리소스 검색 도구가 없음.
- 영향: msw-search(API 문서, RUID 검색)와 `asset_*` 도구. Maker 조작에는 영향 없음.
- 해결: 프로젝트 루트 `.mcp.json` → `mcpServers.msw-mcp.headers.Authorization` 값을 새로 발급한 키로 교체한다. 발급·설정 방법은 https://maplestoryworlds-creators.nexon.com/ko/docs?postId=1368 을 따른다. 저장 후 새 세션을 시작하거나 앱의 커넥터 화면에서 다시 연결한다.
- 해결 확인: `mlua_api_retriever`로 짧은 검색(예: "AttackComponent")을 한 번 실행해 결과가 나오는지 본다. (2026-11-02 해결 확인)

### B. msw-maker-mcp 연결 안 됨 / 도구 없음 / `unavailable`
- 증상: Maker 도구가 목록에 없음, 호출이 연결 오류, `maker_get_current_map`이 `unavailable`.
- 해결: MapleStory Worlds Maker를 실행하고 이 프로젝트 월드를 연다. `.mcp.json`의 `msw-maker-mcp` 실행 경로(`D:\NexonGame\MapleStory Worlds\MakerMCP\msw-maker-mcp.bat`)가 실제로 있는지 확인한다. 그래도 안 되면 새 세션을 시작한다.
- 해결 확인: `maker_get_current_map` → `map01` / `0a0972ef-ad23-4e24-af63-afbd53120c1d` / `edit`, `maker_get_world_info` → worldId `970621b29ba945369d3dc8e90c301186`.

### C. 다른 월드·맵이 열려 있음
- 증상: `maker_get_current_map`·`maker_get_world_info`가 `ok`인데 ID가 위 B의 값과 다름.
- 해결: Maker에서 이 프로젝트 월드를 다시 연다. AI가 맵 이동으로 맞추지 않는다.
- 해결 확인: B와 같다.

### D. Play에서 빠지지 못함
- 증상: `maker_stop` 실패, 이후 refresh·편집이 막힘.
- 해결: Maker 화면에서 직접 Stop을 누른다. 응답이 없으면 Maker를 다시 시작한다.
- 해결 확인: `maker_get_current_map`의 mode가 `edit`.

### E. 도구 호출 거절 ("user rejected MCP tool call")
- 의미: 사용자가 그 호출을 허락하지 않았다. 환경 고장이 아니라 사용자의 결정이다.
- 처리: 다시 호출하지 않고 멈춘다. 가이드에는 어떤 도구를 왜 호출하려 했는지 적는다. 허용하려면 다음 호출을 승인하거나 `.claude/settings.local.json`의 `permissions.allow`에 해당 도구를 추가한다.

### F. 새 에이전트·설정이 보이지 않음
- 증상: `.claude/agents`의 msw-* 에이전트나 `.claude/settings.json` 변경이 적용되지 않음.
- 해결: 새 세션을 시작한다.
- 해결 확인: Agent 도구 목록에 msw-planner·msw-coder·msw-tester·msw-reviewer가 보인다.

### G. 사용량 한도로 작업자 중단
- 증상: 담당 에이전트가 결과 없이 종료되거나 한도 안내가 나옴.
- 처리: 멈춘 지점과 Maker 상태를 run에 기록하고 기다린다. 한도가 풀린 뒤 사용자가 재개를 요청하면 Maker 상태부터 다시 확인한다.
