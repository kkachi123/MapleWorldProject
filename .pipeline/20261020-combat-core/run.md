# 20261020-combat-core

- 요청·승인: 2026-10-20 사용자가 "v08 확인완료. 다음 단계 진행해줘."라고 보고. 1단계 V08 수락을 반영하고 로드맵 2단계를 진행한다. 결과를 바꾸는 미확정 규칙·수치는 사용자 결정 후 구현한다. 2026-11-02 사용자가 일시정지 해제·REV-F01 수정 회차 재개를 승인(아래 절).
- 모드: 승인된 2단계 V11 피드백 회차(F05 원인 확인 + F01~F04 구현·검증·재검토)
- 상태: PLANNING
- 갱신: 2026-11-03 / 메인 조율 채팅(Claude Code)
- 현재 담당: planner msw-planner (Plan §15 범위 반영, Maker 제어 없음)
- 다음 행동·대기 사유: 2026-11-03 사용자 V11 추가 결정(V11-F06 착지점·가드형 제외·1칸 공격·가중치) Plan 반영 → coder → tester(QA5) → reviewer(1447ff8 리뷰는 중단, 새 버전으로 한 번에) → 사용자 V11 재확인.
- 환경 가이드: 없음
## 원본 연결
- 상위: [GameDesign](../../Docs/ProjectSkill/Engineering/GameDesign.md) · [로드맵](../../Docs/ProjectSkill/Engineering/DevelopmentRoadmap.md)
- 1단계 결과: [MovementInput Feature](../../Docs/ProjectSkill/Engineering/Features/1_MovementInput.md)
- 2단계 Plan: [2_CombatCore](../../Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md), D01~D04 / R01~R08 / P01~P06 / V01~V12.
- 2단계 WorkRecord: [CombatCoreWorkRecord](../../Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md).
- 구현 결과: WorkRecord의 P01b~P05, 2026-10-29 QA-F01 수정 개발절, 2026-11-02 coder REV-F01 수정·기본 검증 인계 절.
- 테스트 결과: WorkRecord "2026-11-02 독립 QA 3회차 — REV-F01"(대상 6614b20). QA1·QA2는 이전 버전 근거.
- 리뷰 결과: WorkRecord "2026-11-02 독립 리뷰 — WAITING"(대상 6614b20). 2026-10-29 CHANGES_REQUIRED는 이전 버전 근거.

## 실행·인계
- 대상 버전: 2026-11-02 coder 커밋 6614b20 / 52파일 Bundle SHA-256 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4. manifest는 WorkRecord 2026-11-02 개발절. tester·reviewer 52/52 재계산 일치, 이전 e8a20728…a49 대비 제품 2파일 변경.
- 실행 주체: 2026-11-02부터 메인 Claude Code(Opus 5.5) + Agent 도구의 msw-planner·msw-coder·msw-tester·msw-reviewer 독립 실행. 2026-10-29까지의 /root/... 작업자는 Codex collaboration 실행 근거.
- Maker: 2026-11-02 msw-tester 최종 Stop→다음Play baseline→Stop/map01-edit·사용종료 반환, 메인 읽기 전용 재조회 edit 확인. reviewer·planner·메인은 제어하지 않는다.
- 전달·완료: 1단계 사용자 V08 수락·종료 정리 완료. 2단계 REV-F01 수정·독립 QA3·독립 리뷰(WAITING) 결과 확인. DOC-01 완료, 사용자 V11·CF-F07 연출·V12 외부 미완료.

## 사용자 규칙 응답
- Gate: combat-core-rules-20261020-01 (선택 화면은 표시용, 결정 원본은 사용자 답변과 Plan).
- Q1 / D01: A. 패링 실패 시 가드 피해 경감 허용.
- Q2 / D02 시간: A. 저스트 회피·패링 직전 0.20초.
- Q3 / D02 가드: A. 잔여 40%·경감 60%, 저스트/패링 성공 피해 0.
- Q4 / D03: A. 모든 유효한 저스트 회피·패링 성공 후 2초·다음 직접 공격 1회 전체 타격 ×2.2, 유효 시전 시작 소비·빗나가도 소비.
- Q5 / D04: 사용자 직접 답변 "전투하는 몬스터. 애초에 상대 몬스터는 1개체 고정(1:1대결)". 전투는 상대 1개체 고정, 슬로우/그로기는 그 상대 대상. 제시한 슬로우 2초 ×0.5·그로기 1.5초를 기준으로 대상 명확화.
- 선택 화면: 모든 답변 수신·사용자 요청 반영 인계 후 decision-data.json 제거, gate 종료.

- coder 전달: collaboration.spawn_agent /root/combat_core_coder, 독립 실행. 현재 Maker·제품 편집 담당은 coder 한 명. tester/reviewer 미호출.

## 사용자 요청으로 중단
- 2026-10-20 사용자 요청: "나머지 작업은 이후 내가 명령하면 진행해줘."
- /root/combat_core_coder 상태는 interrupted, planner는 완료. tester/reviewer 미호출.
- coder 최종 보고: 제품 편집 전 Maker 사전 조회 maker_get_current_map이 "user rejected MCP tool call"로 거절됨. 재호출·우회·Play 없음. MapBuilder 읽기는 map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / TileMapMode=0 확인. 이 파일 읽기를 현재 Maker 연결·모드 확인으로 간주하지 않음.
- 인계 상태: 1단계 종료 및 2단계 규칙·1:1 기획 동기화 완료. 구현 원장은 아직 생성되지 않았고 제품 구현·새 QA·독립 리뷰 완료 근거 없음.
- 이후 사용자 재개 명령이 있을 때 같은 run을 재개하고 실제 변경 범위·Maker 접근/모드부터 확인한다.

## 2026-10-24 사용자 명령으로 재개
- 승인: "2단계 중단 시점 부터 작업 재개해줘." 기존 중단 요청을 해제하고 같은 run/P01b부터 이어간다.
- 사전 대조: 이동 소스 3개 SHA-256은 기존 수락본과 일치. 2단계 구현 원장 부재·제품 완료/QA/리뷰 근거 없음.
- 환경: msw-maker-mcp 등록·enabled=true, 기존 브리지 127.0.0.1:11192 TCP 연결 성공. 메인 세션의 Maker 도구 노출은 없음. TCP 연결만으로 Maker 실제 맵·편집 모드나 런타임 검증을 확인한 것으로 보지 않는다.
- 위임: 이전 coder는 활성 상태가 아니므로 새 독립 coder에게 같은 원본과 중단 지점을 인계한다. 다음 역할은 coder의 실제 변경·기본 검증·버전·Maker 사용 종료 확인 후 호출한다.

- 재개 coder 전달: 2026-10-24 collaboration.spawn_agent로 /root/combat_core_coder_v2 호출. P01b 사전 점검·현재 Maker 도구/맵/모드 확인 후 승인된 구현·기본 검증을 담당한다. tester/reviewer는 아직 호출하지 않았다.

- coder 환경 확인(실제 독립 실행 보고): /root/combat_core_coder_v2의 maker_get_current_map 성공, map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / mode=edit. 새 coder 문맥에는 Maker 도구가 노출됨. 메인은 Maker를 제어하지 않으며 coder가 단독으로 P01b부터 진행한다. 이는 신규 Play/QA 결과가 아니다.

- 진행 대조: Plan P01b/P02/P03 🟡(제품 작성·확인 대기), P04 이후 진행 중. 새 런타임 PASS·독립 QA·리뷰 완료 근거로 표시하지 않는다. 상세 구현/검증 상태는 Plan과 WorkRecord만 원본으로 유지한다.

- 기본 검증 진행: coder가 첫 실제 Refresh/Play와 일부 판정 결과를 수집했으며 슬로우 진입의 재생률 보관값 오류를 발견해 수정 중이다. 최종 통합 PASS와 독립 QA/리뷰는 아직 없음. 상세 근거는 WorkRecord 개발 절로 인계한다.

## 2026-10-25 연결 확인·작업 재개
- 승인: 사용자 "프로젝트 연결 확인하고 작업 재개해줘". 2단계 동일 범위의 남은 기본 검증·독립 테스트·리뷰를 진행하고 단계 경계에서 정리·종료한다. 3단계는 시작하지 않는다.
- 중단 대조: coder_v2는 사용량 한도로 종료됐고 최종 버전·Maker 종료 인계가 없다. 현재 collaboration 활성 목록에는 이전 작업자가 없다.
- 위임: collaboration.spawn_agent로 /root/combat_core_coder_v3 실제 독립 호출. 기존 소스·데이터·검증 기록을 보존하고 현재 연결부터 확인한다. 메인은 Maker/제품을 제어하지 않는다.
- Maker: coder_v3의 실제 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186 성공. MapBuilder mode=0과 일치. 해당 관찰 당시 제품 쓰기/Play 전이며 이후 단독 기본 검증 담당은 coder_v3.

- coder_v3 인계 완료: WorkRecord 2026-10-25 개발절·부분 결과/미실시·최종 지문 확인. 실제 CSV값 반영/오류거부/원본복원·Stop재진입 확인, 최종 build 오류0/경고0. 독립 QA·리뷰·V11 미완료이므로 전체 단계 완료로 처리하지 않는다.

- tester 전달: coder_v3 실제 종료·메인 지문 대조 후 collaboration.spawn_agent /root/combat_core_tester 호출. 제품/DataSet 수정 금지, 동일 버전의 독립 Maker 시험·QA절 기록 담당. reviewer는 아직 호출하지 않았다.

- 독립 QA 종료: /root/combat_core_tester, 동일 Bundle 8be49440…e21·제품 무수정·최종 map01/edit·사용 종료 확인. 상세 PASS/NOT_RUN와 확정 FAIL CombatCore-QA-F01은 WorkRecord QA절. CF-F07 미완료, V11 사용자 확인 미실시.

- reviewer 전달: 독립 tester 종료 후 collaboration.spawn_agent /root/combat_core_reviewer 호출. 동일 버전 actual source·승인 요구·개발/QA·QA-F01 및 미실시 검토, Maker 제어·제품수정 없음.

## 2026-10-29 연결 확인·재작업 재개
- 승인: 사용자 “프로젝트 연결 확인하고 작업 재개해줘”. 동일 2단계 범위의 남은 수정·검증·리뷰를 이어간다.
- 중단 대조: 현재 활성 역할 없음. WorkRecord는 독립 QA까지 있으며 리뷰 결과는 미실시다. 요청만 있던 reviewer를 완료로 세지 않는다.
- 버전: 메인 byte 대조 52/52 일치·기존 Bundle 8be49440…e21.
- 위임: collaboration.spawn_agent /root/combat_core_coder_v4 실제 호출. 현재 연결부터 확인 후 QA-F01 최소 수정·기본 검증. 결과 전 tester/reviewer는 호출하지 않는다.

- 새 연결 확인: coder_v4의 실제 Maker 두 조회 성공, 기록된 map/world ID 일치·edit. 이 관찰은 수정/Play 전에 이뤄졌으며 새 런타임 PASS가 아니다.

- coder_v4 실제 종료: QA-F01 최소 패치·기본 native 회귀·Stop재진입·edit/사용종료와 새manifest 확인. 사용자평가/독립QA 전 단계완료 아님.
- tester_v2 전달: 메인 새버전 byte대조 52/52 일치 후 collaboration.spawn_agent /root/combat_core_tester_v2 실제호출. 제품무수정 독립QA2회차.

- 독립 QA2 종료: 실제 변경·회귀 수치 PASS와 대표 입력/시간경계 보완·최종edit/사용종료 반환 확인. 제품52/52일치·V11/연출/외부환경미완료. 원문은WorkRecord QA2.
- reviewer_v2 전달: tester 종료 및 메인 지문재대조 후 collaboration.spawn_agent /root/combat_core_reviewer_v2 실제호출. actual source/요구/QA/미실시 검토만, Maker제어없음.

- 2026-10-29 reviewer_v2 실제 종료: WorkRecord 리뷰 절 CHANGES_REQUIRED — CombatCore-REV-F01, 별도 CombatCore-DOC-01(planner). 이후 사용자가 개발을 일시정지했고(ClaudeSetup.md), 실행 환경을 Claude Code로 옮겼다.

## 2026-11-02 일시정지 해제·REV-F01 수정 회차 재개
- 승인: 사용자 "/ship 2단계 CombatCore 일시정지를 해제하고 REV-F01 수정 회차를 재개해줘." 기준은 Plan D02/R02/V02와 WorkRecord 2026-10-29 리뷰의 REV-F01 최소 수정 범위. 순서 planner(범위 확인만)→msw-coder→msw-tester→msw-reviewer, 리뷰 확정 뒤 DOC-01은 msw-planner. 규칙·수치 변경·3단계 진행 금지, V11은 사용자 직접 확인으로 남긴다.
- 실행 환경: Claude Code 데스크톱 Code 탭, 메인 Opus 5.5/high. 담당은 .claude/agents의 msw-planner·msw-coder·msw-tester·msw-reviewer를 Agent 도구로 순차 호출(각각 독립 실행). 이전 /root/... collaboration 작업자는 Codex 실행 근거로만 보존.
- 연결 확인(메인, 읽기 전용): maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186 일치. msw-mcp mlua_api_retriever("AttackComponent") 결과 정상. 메인은 이후 Maker를 제어하지 않는다. 새 Play/QA 결과가 아니다.
- 기준 버전: 2026-10-29 52파일 Bundle e8a20728…a49(리뷰 대상). 저장소 기준 커밋 ad89cf3.
- planner 범위 확인(msw-planner 실제 종료, 문서 무수정): REV-F01은 D02 "합성 뒤 정수 내림" 미구현으로 승인 범위 안, 새 규칙·수치·사용자 결정 불필요. 편집 범위 MonsterAttackComponent.mlua:134 호출의 선내림 제거, PlayerHealthComponent.mlua:38 인자 number화(:45 유일 최종 floor 유지). 플레이어 쪽 HP 상한 부재는 이번 범위 밖 관찰로 reviewer 판단에 남김.
- coder 전달: msw-coder 호출. tester/reviewer 미호출.
- coder 실제 종료(msw-coder): REV-F01 제품 .mlua 2파일 각 1줄 수정, WorkRecord 2026-11-02 개발절·Plan §13 기록. build 오류0/경고0, Play 프로브 기본 검증 결과는 WorkRecord. 메인 diff·두 파일 SHA-256 대조 일치, maker_get_current_map=map01/edit 확인(읽기 전용).
- 대상 버전: coder 커밋 6614b20 / 52파일 Bundle 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4 (이전 e8a20728…a49 대비 2파일 변경). 이전 QA2·리뷰는 이전 버전 근거로만 취급.
- tester 전달: msw-tester 호출. reviewer 미호출.
- tester 실제 종료(msw-tester): 같은 Bundle 1ac324e6…9de4 전후 52/52 일치, 제품 무수정. 4개 기준 수치 PASS·FAIL 없음, 상세는 WorkRecord "2026-11-02 독립 QA 3회차 — REV-F01". QA 커밋 13fe548. 메인 두 파일 해시 재대조 일치, maker_get_current_map=map01/edit 확인(읽기 전용). Maker 사용 종료.
- reviewer 전달: msw-reviewer 호출. Maker 제어·제품 수정 없음.
- reviewer 실제 종료(msw-reviewer): WAITING. REV-F01 해소, 범위 밖 변경 없음. 플레이어 HP 상한 부재는 범위 밖 관찰(새 ID 없음). 리뷰 커밋 0c1717b.
- planner 전달: msw-planner DOC-01. 제품·Maker 무관.
- planner 실제 종료(msw-planner): DOC-01 문서만 동기화, 규칙·수치·기준·P 상태 무변경. 커밋 아래 [plan]. 남은 메인 확인: Plans/CombatFoundation.md 19행 F07 "미실시" 표시(대상 목록 밖이라 미수정, 사용자에게 보고).
- 이번 회차 AI 담당 종료. Maker는 map01/edit, 사용 중인 담당 없음.

## 2026-11-02 사용자 V11 직접 확인 피드백
- 사용자 원문 요지(전문·판정은 Plan에 planner가 반영):
  1. 예고 구별은 되나 설명만으로는 한계. battlepos에 빨간 영역으로 공격 범위를 사전 표시하면 좋겠음.
  2. 키보드·UI 버튼 입력에 딜레이 체감. UI는 0.2초 저스트가 대체로 맞으나 키보드는 반응이 느림(원인 미상).
  3. 슬로우 연출 OK. 패링 성공 시 몬스터가 플레이어 위치에 고정된 뒤 다음 공격을 그 자리에서 함. 처음 위치로 복귀 후 그로기를 원함.
  4. 패링 성공 이펙트는 좋으나 잘 안 보임. 가시성 개선 원함.
  5. 어지러움(패링 성공) 애니메이션이 idle과 동일. 애니메이션 존재 확인, 후속 작업이면 미뤄도 됨.
  6. 미리 왼쪽으로 이동(좌키 홀드)해 있었는데 몬스터 중앙 공격에 피격 판정. 확인 필요.
- 2026-11-02 사용자 정정: 2번 입력 지연은 "이부분 취소. 밑에 피격판정 관련 문제로 통일해줘" → 별도 항목 없이 6번 피격 판정 문제로 통일. planner에 전달.
- 미언급 V11 항목(모바일·터치·화면 잘림·음향·사망 직후 HP 문자 등)은 미확인으로 유지.
- planner 전달: msw-planner로 결함/새 요구/후속 분류와 사용자 결정 질문 정리. 제품·Maker 작업 없음.

## 2026-11-02 사용자 요청으로 일시정지
- 사용자: "전체 작업 일시정지해줘."
- msw-planner(V11 피드백 분류)를 메인이 중단. 중단 시점 문서 변경 없음(git status상 run.md만 변경). Plan에 V11 피드백 절은 아직 없음.
- Maker: 이번 회차 마지막 확인 map01/edit, 사용 중 담당 없음. 메인은 제어하지 않았다.
- 재개 지점: 사용자 V11 피드백 5항목(빨간 공격 범위 표시, 패링 성공 후 처음 위치 복귀 뒤 그로기, 패링 이펙트 가시성, 어지러움 애니메이션, 좌키 홀드 중 중앙 공격 피격 판정[입력 지연 항목 통합])의 planner 분류·사용자 결정 질문 정리부터.

## 2026-11-02 사용자 명령으로 재개
- 사용자: "작업 재개해줘." 일시정지 해제, 재개 지점(V11 피드백 planner 분류)부터 이어간다.
- 재개 확인(메인, 읽기 전용): git status 깨끗·origin/main과 동일(234ade1), 미완성 변경 없음. maker_get_current_map=map01/0a0972ef-ad23-4e24-af63-afbd53120c1d/edit, worldId 970621b29ba945369d3dc8e90c301186 일치.
- planner 전달: 새 msw-planner 호출(이전 호출은 중단됨, 문서 변경 없었음).
- planner 실제 종료(msw-planner): Plan §14에 V11-F01~F05 분류·F05 재현 조건·Q1~Q4 기록, 규칙·수치·기준 무변경. 커밋 아래 [plan].
- 사용자 결정(2026-11-02, 선택 화면 답변):
  - Q1/F01: 맞는 BattlePos 칸만 예고 시작부터 판정까지 반투명 빨강(판정 불변).
  - Q2/F02: 복귀 후 그로기(사용자 원문 방식). D04·§5의 순서 변경을 사용자가 선택.
  - Q3/F03: 별 파티클 확대·위치 조정 + 패링 순간 별도 강조 둘 다.
  - Q4: F04 어지러움 애니메이션 자원 존재를 지금 읽기 확인한 뒤 처리 시점을 함께 판단. 아직 구현 승인 아님.
- planner 전달: 결정 반영·F04 읽기 확인.
- planner 실제 종료(msw-planner): Q1~Q3 결정·D04/§5 순서 변경 반영, F04 자원 없음 확인(읽기 전용, 런타임 미확인). Q5·Q6 추가. 커밋 아래 [plan].
- 사용자 결정(2026-11-02, 선택 화면 답변):
  - Q5: "StateAnimationComponent보면 hit 애니메이션 존재. 이걸 사용해줘. 확인하고 성공하면 추가로 애니메이션 세팅이 필요할때는 지금처럼 세팅된 animation 확인하고 뭘 쓸지 물어봐." → F04는 기존 hit 애니메이션을 그로기(STUN) 모션으로 사용, 런타임 확인 필요. 이에 따라 F05·F01~F04를 2단계에서 구현·검증하기로 승인(F04 포함 범위). 앞으로 추가 애니메이션 설정은 기존 세팅 확인 후 사용자에게 선택을 묻는다.
  - Q6: 접촉 지점 이펙트(네이티브 파티클).
- planner 전달: Q5·Q6 반영·구현 범위 확정.
- planner 실제 종료(msw-planner): Q5·Q6 반영, Plan §14 coder 인계 범위 확정, 미결정 없음. 커밋 아래 [plan].
- coder 전달: msw-coder 호출(기준 6614b20 / Bundle 1ac324e6…9de4). tester/reviewer 미호출.
- coder 실제 종료(msw-coder): F05 규칙상 정상(제품 무수정), F01~F04 구현, build 오류0/경고0, 기본 검증은 WorkRecord 2026-11-02 V11 개발절. 메인 mlua diff 검토 일치, maker_get_current_map=map01/edit 확인(읽기 전용).
- 대상 버전: coder 커밋 1447ff8 / 54경로 Bundle d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb. 빌더 재작성으로 모델·맵 줄 끝 CRLF→LF·형식 버전 문자열 변경 — 의미 차이가 의도 범위뿐인지 reviewer가 빌더 읽기로 확인 예정(메인 shell 읽기는 프로젝트 훅이 차단).
- tester 전달: msw-tester 호출. reviewer 미호출.
- tester 실제 종료(msw-tester): 같은 Bundle d2b57802…0fbb 전후 54/54 일치, 제품 무수정, FAIL 없음, 별·접촉 파티클 육안 NOT_RUN. QA 커밋 f7b3244. 메인 maker_get_current_map=map01/edit 확인(읽기 전용).
- 계약 위반 기록: tester가 시작 직후 maker_clear_logs로 이전 Play normal 로그 36건을 보존 확인 없이 지웠고 회차 사이에도 호출함(build 로그는 유지). 사용자 로그 무단 삭제 금지 계약 위반으로 사용자에게 보고. 다음 tester 지시에 clear_logs 금지 명시.
- reviewer 전달: msw-reviewer 호출.
- reviewer 중단: 이전 세션 종료로 msw-reviewer가 완료 기록 없이 멈춤. WorkRecord 변경 없음(리뷰 절 미작성). 1447ff8 단독 리뷰는 하지 않고 아래 추가 범위 구현 뒤 새 버전으로 한 번에 리뷰한다.

## 2026-11-03 사용자 추가 결정 (V11 공격 범위·데이터)
- 재개 확인(메인, 읽기 전용): git status에 1447ff8 이후 미커밋 3파일(map01.map, AttackAreaMark 모델, MapObjects.directory). 줄 끝 무시 diff는 숫자 표기(1→1.0)·StudioVersion ""→"0.1.0.0"·일부 키 순서뿐이라 Maker 재저장 형식 차이로 판단, 에이전트 작성 아님. 되돌리지 않고 coder가 시작 시 빌더 의미 비교로 확인한 뒤 새 커밋에 포함한다.
- 사용자 제안 1: 주황버섯은 점프 공격에 맞는 범위만. 3위치 전체 공격은 다른 보스용. 2위치 공격이면 두 칸 중간에 착지.
- 사용자 제안 2: 몬스터 관련 수치(점프 속도, 공격·HP 등)를 DataSet에서 조절, 공통/개별 구분.
- 메인 의견: 2칸 패턴은 착지점을 영역 중앙에서 도출, 가드형(3칸) 2패턴은 주황버섯 데이터에서 제외(코드·규칙 유지). 1칸 공격은 방향 예고와 충돌해 새 대응 유형 필요. 수치 DataSet화는 V11 뒤 별도 회차 권장.
- 사용자 답변: "이거는 그런 공격도 있어야됨. 안그럼 난이도가 너무 올라" / "1번안은 1위치 공격은 필요함. 나머지는 추천안대로 진행해도 됨. 또 일반 몬스터들도 필요하니까 1위치 공격은 필수야."
- 사용자 선택(2026-11-03, 선택 화면):
  - 1칸 대상: 플레이어 칸 조준 — 예고 시작 순간 플레이어와 가장 가까운 칸을 고정, 이후 추적 없음.
  - 1칸 저스트 회피: 범위를 벗어나는 방향이면 어느 쪽이든 성공(슬로우·반격 보너스).
  - 1칸 허용 속성: 일반·특수·패링 모두.
  - 출현 비율: DataSet 가중치 열(기본 모두 1).
- 범위: V11-F06으로 2단계 V11 회차에 포함. 몬스터 수치 DataSet화(제안 2)는 V11 종료 뒤 별도 승인 회차.
- planner 전달: msw-planner로 Plan §15 작성(D01 새 대응 유형 반영, 패턴 표, 검증 기준).
