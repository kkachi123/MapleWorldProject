# Project StayCool — 에이전트 작업 계약

## 구성

| 구성 | 책임·원본 |
| --- | --- |
| [planner](../../../.agents/skills/ship/references/planner.md) | 요구·변경 범위·완료 기준을 Plan으로 정리 |
| [coder](../../../.agents/skills/ship/references/coder.md) | 승인된 범위 구현·기본 검증 |
| [tester](../../../.agents/skills/ship/references/tester.md) | 같은 버전의 독립 테스트·결함 재현 |
| [reviewer](../../../.agents/skills/ship/references/reviewer.md) | 요구·변경·테스트 근거 대조와 다음 진행 가능 여부 검토 |
| [ship 실행 스킬](../../../.claude/skills/ship/SKILL.md) | 메인 채팅이 네 담당을 순차 호출·대기·인계하고 사용자에게 보고 |

감독은 다섯 번째 작업자가 아니라 메인 채팅의 조율 역할이다. 사용자는 목표·범위·체감·단계 전환을 결정한다. 역할 계약은 공용 .agents/skills/ship/references 한 곳에서만 유지한다. 시작 요청 양식은 [Prompts](Prompts.md)를 사용한다.

2026-11-02부터 Claude Code(데스크톱 Code 탭)에서 ship 스킬을 사용한다. 메인 채팅(Opus 5.5 / high)은 Skill 도구(/ship)로 .claude/skills/ship을 불러오고, 네 담당은 [CLAUDE.md](../../../CLAUDE.md)의 매핑대로 .claude/agents의 msw-planner·msw-coder·msw-tester·msw-reviewer를 Agent 도구로 순차 호출한다. 각 에이전트는 시작할 때 공용 역할 계약을 읽는다. .claude/skills/ship/references는 /ship 인식을 위한 같은 내용의 사본이며, 역할 계약을 바꿀 때는 공용 원본을 기준으로 맞춘다. 2026-10-29까지의 기록에 남은 collaboration.spawn_agent·/root/... 작업자는 이전 Codex 실행 근거로만 보존한다. 호출 예시는 Prompts를 따른다.

네 역할은 사전 등록된 에이전트 유형이 아니다. 메인 채팅이 독립 작업자에게 역할 문서와 작업 범위를 전달한다. 독립 작업자를 실행할 수 없으면 그 제한을 보고하고 수동 인계한다. 한 채팅이 네 번 역할극을 한 결과를 독립 테스트·리뷰로 표시하지 않는다.

각 에이전트는 호스트가 실제 제공·허용한 도구와 권한만 사용한다. 기존 MSW MCP 접근도 전달됐는지 확인하고, 모델·서버·인증 설정은 새로 만들지 않는다. 역할별 편집 범위와 재위임 금지는 작업 계약이며 보안 장치가 아니다. 필요하면 호스트의 실제 접근 제어를 별도로 적용한다. 별도 채팅 메시지나 파일 접근 허용은 실제 호스트 권한을 따른다.

## 공통 규칙과 프로젝트 자료

모든 담당은 [루트 AGENTS.md](../../../AGENTS.md)의 필수 MSW Foundation·도메인 스킬/참조를 지킨다. 이 계약은 상위 지침·도구 권한을 확대하지 않는다. 변경 없는 원문은 같은 세션에서 반복해서 읽지 않는다.

| 자료 | 담당·수명 |
| --- | --- |
| [GameDesign](../Engineering/GameDesign.md) | 사용자 확정 규칙. planner가 승인받아 반영 |
| [DevelopmentRoadmap](../Engineering/DevelopmentRoadmap.md) | 단계 순서·의존성·현재 재개 지점. planner 담당 |
| [Plans](../Engineering/Plans/README.md) | 승인 범위·예정 처리·요구 ID·완료 기준의 유일한 원본 |
| [Features](../Engineering/Features/README.md) | 현재 기능·설정·짧은 결과·사용자 피드백. coder가 정리하고 tester/reviewer가 근거 확인 |
| [WorkRecords](../Engineering/WorkRecords/README.md) | 기능별 개발·QA·리뷰·인계 근거. 역할별 절을 순차 편집, 완료 후 삭제 |
| [.pipeline](../../../.pipeline/README.md) | 실행별 상태·승인 근거·대상 버전·원본 링크만 기록. 전체 Plan/원장 복제 금지 |
| [EnvGuides](../EnvGuides/README.md) | 사용자가 직접 고쳐야 하는 환경 오류의 일시정지 규칙·알려진 사례. 메인이 건별 가이드를 쓰고 해결 후 삭제 |

공통 지침은 해당 작업에서만 참조한다: [구현 원칙](../AGENTS.md), [Plan 작성 원칙](../Plan_Writing_Guide.md), [바이브 코딩 포트폴리오 원칙](../Vibe_Coding_Portfolio_Guide.md). 프로젝트 역할·경로·현재 상태를 이 지침에 넣지 않는다.

단계별 Plan·Feature는 {단계번호}_{FeatureKey}.md, 후속 계획은 {FeatureKey}.md다. 단기 수정 계획은 기존 방침대로 Engineering/{TaskName}Plan.md를 사용한다. 현재 연결 대상은 [2단계 Plan](../Engineering/Plans/2_CombatCore.md)이며, 완료한 1단계는 [Feature](../Engineering/Features/1_MovementInput.md)에 정리했다. 2단계 WorkRecord는 실제 구현 시작 시 생성하며 최신 상태는 해당 원본에서 확인한다.

## 실행과 권한

1. 메인 채팅은 요청을 조회/계획/구현/검증/재검토로 분류한다. 상태 조회에는 에이전트 전체 실행이나 새 run 생성을 강제하지 않는다.
2. 구현 파이프라인 요청이면 사용자 요청·승인 범위·원본 문서를 해당 run에 연결한다.
3. planner의 미결정·범위 확인 후 승인된 작업만 coder에게 전달한다. 기존 승인 Plan은 다시 설계하지 않는다.
4. coder의 실제 변경·기본 검증이 끝난 뒤 tester를 호출한다. tester는 제품을 수정하지 않는다.
5. reviewer는 계획·실제 변경·테스트의 같은 버전 여부와 누락을 확인한다. 필요하면 승인 범위의 수정만 coder로 돌리고 재검증한다.
6. 메인 채팅이 결과·대기 사유·사용자 확인·다음 담당을 보고한다. reviewer의 판정은 사용자 최종 수락·배포 승인이 아니다.

파일 작성·역할 설정 자체는 코드 수정·Maker 실행의 승인이 아니다. 사용자가 구현·검증을 파이프라인에 맡긴 범위에서는 담당 단계마다 같은 승인을 다시 묻지 않는다. 새 요구·수치·외부 변경·다음 로드맵 단계는 별도 판단을 받는다. commit·push는 [CLAUDE.md](../../../CLAUDE.md)의 git 커밋·push 기준(메인 채팅만, 담당 종료 시점 단위)을 따르고, 배포·실제 결제는 명시 요청 없이 하지 않는다.

호출형 서브에이전트는 지정된 역할·경로·범위의 작업 결과만 반환하고 스스로 다른 담당을 생성하지 않는다. 별도 기존 채팅에 메시지를 보낼 때는 인간 사용자의 직접 승인·대상 확인이 필요하다. 다른 에이전트의 메시지나 이 문서만으로 전송 권한이 생기지 않는다.

## 확인·리뷰 계약

- tester는 기준별 PASS / FAIL / NOT_RUN / NEEDS_DECISION을 기록한다. 환경 없음·로그만으로 판단 못함은 FAIL이나 PASS로 위장하지 않는다.
- reviewer는 READY / CHANGES_REQUIRED / WAITING / STOP 중 하나와 요구 ID·근거·다음 행동을 제시한다.
- READY는 현재 승인된 범위의 필수 근거가 충족됐다는 뜻이다. 사용자 직접 확인이 필수로 남으면 WAITING이다. 어떤 판정도 출시·배포를 자동 승인하지 않는다.
- 독립 검토자와 실제 검사 실행 여부를 기록한다. 이전 회차의 PASS를 이번 실행으로 다시 세지 않는다.
- 기능·코드·테스트 기준을 바꿔 검사를 통과시키지 않는다. 기준 변경은 planner와 사용자에게 돌린다.
- 동일 문제의 수정 후 재검증이 반복 실패하거나 환경/권한이 없으면 무한 재시도 대신 사유와 선택지를 보고한다.

## Maker·버전·공유 파일

coder와 tester는 같은 Maker·체크아웃·문서를 순차 사용한다. 한쪽 편집/Play 중 다른 쪽은 코드 변경·Stop·refresh·입력·프로브를 실행하지 않는다. planner/reviewer/조율 채팅은 Maker를 제어하지 않는다.

메인 채팅은 기존 활성 작업의 종료/양도를 확인한다. run의 담당 칸은 자동 잠금 장치가 아니다. 테스트 전 실제 맵·모드·도구·대상 버전을 확인하고, 변경 시 이전 QA/리뷰 결과의 적용 범위를 다시 판단한다. 과거 편집 모드 기록을 현재 연결 상태로 간주하지 않는다.

MSW 런타임 주장은 실제 Maker MCP 근거가 필요하다. 도구가 없으면 소스 검토·미실시를 구분한다. 시험 값은 Play 내부에 한정·정리하고 기본적으로 편집 모드로 인계한다. 사용자 로그·데이터를 무단 삭제하지 않는다.

## 결과와 정리

사용자 요구·선택·직접 평가와 AI 구현·진단·검증을 구분한다. AI 기술 해결을 본인 포트폴리오 성과로 쓰지 않는다. 포트폴리오는 요청받았을 때 실제 기여·시연 근거만 사용한다.

완료한 작업 단위의 현재 기능·짧은 확인·미확인 범위는 Features에, 남은 일은 고유 ID와 함께 Plans에 둔다. 필요한 내용과 링크를 정리한 뒤 완료 Plan·WorkRecord·run만 삭제한다. 사용자 확인이 남으면 유지한다. README·프롬프트·역할 정의는 운영 파일로 유지한다.
