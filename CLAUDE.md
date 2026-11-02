<!-- >>> managed by mswai >>> -->
@AGENTS.md
<!-- <<< managed by mswai <<< -->

# ship 역할 에이전트 매핑

ship 스킬은 네 담당을 아래 프로젝트 에이전트(`.claude/agents/`)로 한 번에 하나씩 순차 호출한다. 앞 담당이 실제로 끝나고 산출물을 확인한 뒤 다음 담당을 부른다.

| 순서 | 담당 | Agent `subagent_type` | 모델 / effort (에이전트 정의) |
| --- | --- | --- | --- |
| 1 | planner | `msw-planner` | Opus 5.5 / high |
| 2 | coder | `msw-coder` | Sonnet 5.5 / high |
| 3 | tester | `msw-tester` | Sonnet 5.5 / high |
| 4 | reviewer | `msw-reviewer` | Opus 5.5 / high |

- 메인 채팅은 Opus 5.5 / high(`.claude/settings.json`)로 조율만 한다.
- Agent 호출에 `model`·`effort`를 넘기지 않는다. 모델과 effort는 각 에이전트 정의만 따른다.
- 역할 계약 원본은 `.agents/skills/ship/references/`다. 각 에이전트가 시작할 때 해당 파일을 읽는다.
- CHANGES_REQUIRED면 같은 승인 범위에서 `msw-coder` → `msw-tester` → `msw-reviewer` 순서로 다시 돈다. 기존 승인 Plan이 있으면 planner는 범위 확인만 한다.
- 에이전트는 다른 에이전트를 호출하지 않고 결과를 메인 채팅에만 돌려준다. Maker MCP는 coder와 tester만 순차 사용한다.

# 환경 오류 시 일시정지

인증 실패(MCP 401 등)·연결 실패·도구 없음·다른 월드가 열림·Stop 실패·도구 호출 거절처럼 사용자가 직접 고쳐야 하는 환경 오류를 만나면, 메인 채팅과 모든 담당은 [EnvGuides 규칙](Docs/ProjectSkill/EnvGuides/README.md)을 따른다.

- 우회·반복 재시도를 하지 않는다. 일시적 오류로 보이면 한 번만 다시 시도한다.
- 안전 지점에서 멈추고 담당은 `WAITING_ENV`로 메인에 반환한다. 메인은 `Docs/ProjectSkill/EnvGuides/`에 직접 해결 가이드를 쓰고, run이 있으면 상태를 `WAITING_ENV`로 바꾼 뒤 사용자에게 알린다.
- 사용자가 해결했다고 말하기 전에는 재개하지 않는다. 재개할 때는 가이드의 해결 확인 호출을 먼저 실행한다.
- 토큰·키 같은 비밀값은 가이드·run·채팅에 적지 않는다.
