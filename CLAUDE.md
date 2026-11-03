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

# git 커밋·push 기준

원격: `origin` = https://github.com/kkachi123/MapleWorldProject (Public), 브랜치 `main` 하나. 사용자가 2026-11-02 아래 기준의 커밋·push를 상시 승인했고, 2026-11-03 담당마다 커밋하던 방식을 회차 단위로 바꿨다.

- **커밋은 메인 채팅만 한다.** 서브 에이전트(msw-*)는 commit·push를 하지 않는다. 메인이 담당의 실제 종료와 산출물을 확인한 뒤 커밋한다.
- **커밋 단위는 승인된 요구·결함 한 회차다**(예: V11-F08·F09). 회차는 planner 범위 확인부터 reviewer 판정까지다.

  | 시점 | 포함 | 메시지 머리 | push |
  | --- | --- | --- | --- |
  | coder 종료(Maker 편집 모드 인계 확인 후) | 제품 파일(.mlua·Maker 생성 .codeblock/.directory·빌더로 만든 .model/.map/.ui·DataSet)과 그 시점까지의 Plan·WorkRecord 변경 | `[{FeatureKey}][code]` | 하지 않음(로컬 버전 고정용) |
  | CHANGES_REQUIRED 뒤 coder 재수정 종료 | 같은 범위 | `[{FeatureKey}][code]` | 하지 않음 |
  | 회차 종료(reviewer 판정 확인 후) | QA·리뷰 절, Plan·GameDesign·로드맵, run.md 등 회차의 나머지 문서 | `[{FeatureKey}][review] {판정}` | 회차 커밋 전체를 한 번에 |

- **따로 커밋하는 경우만 `[ops]`:** EnvGuides·에이전트 정의·설정·CLAUDE.md 같은 운영 규칙 변경, 사용자의 일시정지·중단 요청, `WAITING_ENV` 전환. run.md만 바뀐 상태 갱신은 따로 커밋하지 않고 회차 커밋에 넣는다. 회차 밖 planner 단독 문서 작업은 끝날 때 `[{FeatureKey}][plan]` 한 커밋으로 한다.
- **버전 고정:** coder 로컬 커밋 해시를 tester·reviewer의 대상 버전으로 쓰고, WorkRecord와 run에 기존 바이트 지문과 함께 적는다.
- **커밋하지 않는 상태:** Play 중, 편집이 반쯤 된 상태, `WAITING_ENV` 중의 미완성 제품 변경. run에만 기록하고 다음 정상 종료 시점에 커밋한다. 사용자가 직접 바꾼 파일은 해당 범위가 아니면 커밋에 섞지 않고 알린다.
- **메시지 본문:** run-id, 요구/결함 ID, 실제 실행한 검증과 미실시를 짧게 적고 마지막 줄에 Co-Authored-By 서명을 붙인다.
- **push:** 회차 종료 커밋과 `[ops]`·`[plan]` 커밋 때 `origin main`에 push한다. 공개 저장소이므로 push 전마다 아직 push하지 않은 커밋 전체에서 토큰·키·개인정보(이메일·로컬 사용자 경로)를 검사하고, 하나라도 걸리면 push하지 않고 멈춘다. 강제 push·이력 재작성·다른 브랜치 push는 사용자 요청 없이 하지 않는다.
- `.gitignore`의 비밀값·개인 설정·런타임 제외와 `.gitattributes`의 `* -text`(바이트 보존)를 유지한다.
