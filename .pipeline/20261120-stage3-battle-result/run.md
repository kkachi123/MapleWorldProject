# 20261120-stage3-battle-result

- 요청·승인: 사용자 "3단계 진행하자"(2026-11-20). 로드맵 3단계(전투 한 방 완성: 전투 준비·시작·승패·종료, 처치 경험치 합산·전투 종료 정산, Level·EXP와 전투 피드백)의 계획 작성. 구현 승인은 아직 없음(Plan 확정·사용자 답변 뒤 별도 확인).
- 모드: 계획
- 상태: WAITING_USER
- 갱신: 2026-11-20 메인
- 현재 담당: 사용자 (회차 1 구현 지시)
- 다음 행동·대기 사유: 사용자 구현 지시 → 회차 1 coder(기준 = [BattleResult][plan] 커밋).
- 환경 가이드: 없음

## 원본 연결
- Plan: Docs/ProjectSkill/Engineering/Plans/3_BattleResult.md (FeatureKey BattleResult, R01~R14, Q1~Q14, 초안)
- Feature: 없음
- WorkRecord: 없음(구현 승인 뒤 생성)
- 기획 결과: 3_BattleResult.md 확정(Q1~Q16·스크린샷 상한)(회차 1 = R01~R09·R11 기본·R12·R13, 회차 2 = R10·R11 연출·R14 선택)
- 구현 결과: 없음
- 테스트 결과: 없음
- 리뷰 결과: 없음

## 실행·인계
- 대상 버전: 기준 198ce80(origin/main, 작업 트리 깨끗)
- 실행 주체: 메인 Opus 5.5(조율), planner = msw-planner 서브 에이전트(독립 실행)
- Maker: 사용 안 함(계획 단계)
- 전달·완료: planner 요청

## 기록
- 2026-11-20 사용자 "3단계 진행하자". 2단계 후속 처리 종료(f93a3c1), [ops] 90cde2b(V11 표기 규칙)·198ce80(map01 반영) 뒤. run 생성, planner 호출.
- 2026-11-20 planner 3단계 Plan 초안: 3_BattleResult.md. 막는 질문 Q1~Q7(동시 불능·사망 시 EXP·Level 유지 범위·EXP 표·다시 전투·패배 모습·결과 표시), 나중 질문 Q8~Q14. FU-18 적용, FU-22 포함(R13), FU-27·28 일부 포함. 로드맵 재개 지점·Plans README 갱신. 사용자 질문.
- 2026-11-20 사용자 답: Q1 패배 우선, Q2 그 판 EXP 전부 회수 + 후속 "회수는 4단계에서"(3단계는 죽은 전투 0, 판 전체 회수·레벨 되돌림은 Run이 생기는 4단계 구현, GameDesign 규칙은 지금 기록), Q3 Play 동안만, Q4 기본안대로(KillExp 열·PlayerLevelData·머쉬맘 120·100/150/200/250·최고 Lv5), Q5 결과의 버튼, Q6 쓰러진 채 유지, Q7 팝업+레벨업 토스트. planner Plan 확정 요청.
- 2026-11-20 planner Plan 확정(Q1~Q7): 3_BattleResult.md 회차 1 = R01~R09·R08a(4단계 회수용 정산 기록)·R11·R12·R13, coder 절차·시작 조건·스크린샷 상한(coder 4·tester 5). GameDesign §6·§8에 Q2 결정 문장, 로드맵 §2·§3·재개 지점, Plans README. 새 질문 Q15(패배 시 몬스터 복귀 방식)·Q16(결과 팝업 버튼). 제안: Q1을 GameDesign에 반영, 낡은 상태 줄 3곳.
- 2026-11-20 사용자 답: Q10~Q16 "모두 기본값", 스크린샷 상한 "coder 4·tester 5", GameDesign "둘 다 반영"(메소 문구 유지·Q1 패배 우선 기록), 구현 "Plan만 커밋"(회차 1 coder는 별도 지시 대기).
- 2026-11-20 planner 마무리: Plan 상태 Q1~Q16·스크린샷 상한 확정·구현 지시 대기, GameDesign §4.2·§8에 Q1(패배 우선) 반영, 로드맵·Plans README·ChatRoles README·CombatCore.md 상태 줄 정리. 메인 [BattleResult][plan] 커밋·push.
