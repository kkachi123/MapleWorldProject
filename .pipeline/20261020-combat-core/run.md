# 20261020-combat-core

- 요청·승인: 2026-10-20 사용자가 "v08 확인완료. 다음 단계 진행해줘."라고 보고. 1단계 V08 수락을 반영하고 로드맵 2단계를 진행한다. 결과를 바꾸는 미확정 규칙·수치는 사용자 결정 후 구현한다.
- 모드: 승인된 2단계 구현·검증 재개
- 상태: REVIEWING
- 갱신: 2026-10-29 / 메인 조율 채팅
- 현재 담당: reviewer /root/combat_core_reviewer_v2 (독립 실행)
- 다음 행동·대기 사유: 독립 QA2 실제 종료·동일 버전·Maker edit/사용종료 확인. reviewer가 승인 기준·actual source·새 QA 및 미실시를 대조하고 다음 담당/사용자 확인을 분류한다.

## 원본 연결
- 상위: [GameDesign](../../Docs/ProjectSkill/Engineering/GameDesign.md) · [로드맵](../../Docs/ProjectSkill/Engineering/DevelopmentRoadmap.md)
- 1단계 결과: [MovementInput Feature](../../Docs/ProjectSkill/Engineering/Features/1_MovementInput.md)
- 2단계 Plan: [2_CombatCore](../../Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md), D01~D04 / R01~R08 / P01~P06 / V01~V12.
- 2단계 WorkRecord: [CombatCoreWorkRecord](../../Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md).
- 구현 결과: WorkRecord의 P01b~P05와 2026-10-29 QA-F01 수정 개발절. 과거 독립 QA와 새 수정본의 QA를 구분하며 현재 리뷰 결과는 없음.

## 실행·인계
- 대상 버전: 2026-10-29 / 52파일 Bundle SHA-256 e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49. 최신 manifest는 WorkRecord 2026-10-29 개발절. 메인 byte 재확인 52/52 일치, 기존 대비 제품1파일 변경.
- 실행 주체: 메인 /root. 과거 독립 planner/coder_v3/tester 및 현재 coder_v4/tester_v2는 실제 collaboration 실행. reviewer 이전 전달 기록은 있으나 완료 결과 없음.
- Maker: 2026-10-29 tester_v2 actual Stop→다음Play baseline→최종Stop/map01-edit·사용종료 반환. reviewer와 메인은 제어하지 않는다.
- 전달·완료: 1단계 사용자 V08 수락·종료 정리 완료. 2단계 P01a 완료, 제품 구현·기본 검증 및 과거 QA 완료. 새 수정본 독립 QA 진행 중이며 리뷰·사용자 V11 미완료.

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
