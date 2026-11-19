# CombatCore — 임시 작업 기록

- 연결 Plan: [2_CombatCore](../Plans/2_CombatCore.md).
- 상태·갱신일: 2026-11-19 / 최신: **2단계 완료**(사용자 "모바일연결이나 멀티환경 테스트는 하지는 않음. 그래도 2단계 완료는 해도 될것 같음.", Plan P01b~P06 ✅). 결과는 [2단계 Feature](../Features/2_CombatCore.md)로 이관했고 남은 확인·부채·사용자 결정은 [2단계 후속 계획](../Plans/CombatCore.md)에서 추적한다. V11 모바일·실기기 터치와 V12 실제 외부 환경은 NOT_RUN(사용자가 하지 않기로 함). CombatFoundation-F07은 같은 날 사용자 "기존 수락으로 닫기"로 완료했다(PC Maker 기준, 모바일은 CombatCore-V11 NOT_RUN). 이 기록의 삭제 여부는 사용자가 정한다. 그 전: 회차 E(Plan §24, CombatCore-UX-01·UX-02) **사용자 V11 수락으로 완료**("다른 건 다 좋음", Maker 26.11에서 확인, 바꿀 점 없음, O-1·O-3 수락 범위). 근거: coder 3e29a35(맨 아래 2026-11-16 개발절) + QA15(QA 기록 첫 절, §24.7 1~7 PASS) + 리뷰 WAITING(리뷰 기록 첫 절, [review] a81afcf, 결함·지적 없음). 회차 종료 planner 정리(2026-11-19) 완료, 회차 종료 커밋은 메인. 일시정지 중 작업 트리 변경은 [ops] d0d095b(회차 밖). 다음 회차는 정해지지 않았고 사용자 결정 대기 항목은 Plan §24.9 아래 목록이다. 그 전(2026-11-16): 회차 D(Plan §22, CombatCore-MM-07~11)와 V11 후속 D2(Plan §22.17, MM-13~15) **사용자 V11 수락으로 완료**("다른 건 다 좋은 데 1칸 점프음을 player가 사용하는 점프음으로 바꿔줘." → coder 5ce65d6 → "점프음 확인 완료"). 근거: coder e5f7249 → a5efe69 + QA12 + 리뷰 WAITING → 8428a05(REV-D-O1) + QA13 + 리뷰 WAITING → 1b41f29·e710907 + QA14 + 리뷰 WAITING → 5ce65d6(D-Q13, coder 기본 검증). 회차 종료 planner 정리(2026-11-16) 완료, 회차 종료 커밋은 메인. 다음 후보는 회차 E(Plan §24, 사용자 시작 지시 필요). 범위 밖 남은 사항: 원장의 낡은 castleenemy 문구. 그 전(2026-11-08): 회차 C2(Plan §23, CombatCore-MM-12) **사용자 V11 수락으로 완료**(사용자 "V11 확인 완료", 회차 종료 커밋 7a796aa). coder 163fc37(사용자 Maker 파일 이름·Name 변경 반영, 모델 재기록 없음, 원장 23행 경로만 갱신) → 독립 QA11(대상 163fc37, 55경로 Bundle 8ef9c6f1…e080, §23.3 기준 전부 PASS) → 독립 리뷰 **WAITING**(2026-11-08, 결함 없음) → 사용자 V11 수락. 다음은 회차 D(Plan §22, 기준 7a796aa) → 회차 E(Plan §24)이며 각 회차는 사용자 시작 지시 뒤. 범위 밖 남은 사항: 원장의 낡은 castleenemy 문구(정리 시점 사용자 결정). 그 전: 회차 C(Plan §21, CombatCore-MM-01~06·V11-F15) **사용자 V11 수락으로 완료**(회차 종료 커밋 b93e2ac). 사용자 답: 1~6 확인, 8 이상 없음(사운드 실청취는 회차 D), 7 키 이름은 영어 이름 정리로 결정해 Plan §23 회차 C2(파일·모델 Name OrangeMushroom, 키 orangemushroom 유지)로 분리. 주황버섯 MonsterData·MonsterStatData·패턴 행은 6단계. 다음은 회차 C2 → 회차 D(Plan §22) → 회차 E(Plan §24, 조작 버튼 테마·가드 모션/이펙트, 설계·후보만)이며 각 회차는 사용자 시작 지시 뒤. 그 전: 회차 C **사용자 V11 대기**. coder 구현·기본 검증(로컬 커밋 5a605ba, STOPPED 중단 조건 3 → 사용자 월드 재로드로 해소, Maker 재저장분 [ops] b4adbdd) → 독립 QA 10회차(대상 b4adbdd, 55경로 Bundle 222e7a04…476d, 실행 기준 전부 PASS) → 독립 리뷰 **WAITING**(리뷰 기록 첫 절, 결함 없음). 회차 D(Plan §22)는 회차 C 사용자 V11 수락과 사용자 시작 지시 뒤이며, 리뷰가 넘긴 재스폰 프레임 범위 확인은 Plan §22.15에 있다. 그 전: 머쉬맘 모션·사운드 사용자 지시 반영(Plan §21 애니메이션 연결 확인 완료·기준 eca1903, coder 시작 조건은 사용자 재개 지시뿐 / Plan §22 회차 D CombatCore-MM-07~11 구현 승인, 회차 C 사용자 V11 수락 뒤 시작). 그 전: 회차 C Plan 작성(Plan §21, CombatCore-MM-01~06·V11-F15 구현 승인, 사용자 재개 지시 전 정리 단계, coder 전 애니메이션 연결 확인 1건 대기, 기준 8f16a81). 그 전: 회차 B(Plan §20, CombatCore-V11-F14·V11-F07) **사용자 V11 수락**(메인이 물은 4항목에 "전부 ok", run "2026-11-05 회차 B 사용자 V11 수락" 절, Plan §20 상태 표 ✅). 이동·복귀 체감 동일, AttackInterval 의미(공격 종료 뒤 IDLE 대기 3.0초, 시작~다음 시작 약 4.0초) 사용자 기대와 같음, HP 바 현재/최대 숫자 정상(HP 바 자릿수 육안 NOT_RUN 해소). CSV 직접 수정은 조건 질문이라 사용자 실시 여부 미확정(AI 근거 QA9·보충 시험 1). 그 전: 회차 B 독립 리뷰 **WAITING**(리뷰 기록 첫 절과 그 "보충 확인" 소절, 결함 0, 사용자 V11 대기). 대상 coder 로컬 커밋 1b4f4ee(기준 9eed765) / 59경로 Bundle 9325c33a…cd19. 독립 QA 9회차(QA 기록 첫 절) 실행 기준 PASS·FAIL 없음, "QA9 보충 시험 1"로 플레이어 MaxHp DataSet 적용 PASS. 문서 정정(planner, 2026-11-05): coder 개발절의 "IDLE→ATTACK 전환 간격 2.96~3.01초"와 Plan의 옛 "시작 간격 3.0" 표현은 실제로 공격 종료 뒤 IDLE 대기 3.0초(시작~다음 시작 약 4.0초)를 뜻한다. Plan §5·§20 문구만 고쳤고 값·동작은 그대로이며 개발절 본문은 당시 기록대로 둔다. 그 전: 회차 B Plan 작성(Plan §20, CombatCore-V11-F14·V11-F07 구현 승인, coder 대기, 기준 9eed765). 그 전: 회차 A(V11-F12·V11-F13) **사용자 V11 수락**(메인이 물은 4항목에 "전부 ok", run "2026-11-04 회차 A 사용자 V11 수락" 절, Plan §19 상태 표 ✅. 사람 손 0.20초 타이밍 NOT_RUN 해소, 모바일·실기기는 기존 V11 미확인 유지). 그 전: 회차 A 독립 리뷰 **WAITING**(리뷰 기록 첫 절, 사용자 V11 대기, 고칠 결함 없음, 7f2d0b4 커밋 트리 Bundle 7f32ae45…e21e3 / 작업 트리 b321d71c…040f 재계산 일치). 그 전: 독립 QA 8회차 회차 A(QA 기록 첫 절, 사용자 일시정지로 중단 뒤 같은 날 "QA8 재개" 소절에서 남은 NOT_RUN 실행, 같은 Bundle 54/54 전후 일치, 실행 기준 PASS·FAIL 없음, 사람 손 0.20초 타이밍·HP 0 실제 플레이어 사망·실제 맵 전환·CSV 변경 반영·실기기 NOT_RUN). 그 전: coder 회차 A 구현·기본 검증(로컬 커밋 7f2d0b4, 맨 아래 2026-11-04 개발절). 그 전(2026-11-03): 독립 리뷰 REV-F02·V11-F10·V11-F11 **WAITING**(리뷰 기록 둘째 절, 5c4eda3 커밋 트리 Bundle 9208e0aa…da79 / 작업 트리 fdca556d…ee80 재계산 일치, 제품 변경 6경로, 고칠 결함 없음, H1 규칙상 정상, 사용자 V11 대기). 그 전: 독립 QA 7회차 REV-F02·V11-F10·V11-F11·H1(QA 기록 첫 절, 커밋 5c4eda3 / 작업 트리 Bundle fdca556d…ee80 54/54 전후 일치, 전부 PASS·FAIL 없음·결함 후보 없음, 육안·0.20초 손 타이밍·CSV 파일 변경 반영·실제 키 해제 타이밍 NOT_RUN, 독립 reviewer 대기). 그 전: 독립 리뷰 V11-F08·F09 **WAITING**(리뷰 기록 첫 절, a921c76 / 작업 트리 Bundle 377a5ccc…0363 재계산 일치, 수정 필요 결함 없음, 범위 밖 결함 후보 CombatCore-REV-F02 일반 사망 die 미유지는 사용자 범위 결정 대기, 사용자 V11 육안 대기). 그 전: 독립 QA 6회차 V11-F08·F09(QA 기록 첫 절, 커밋 a921c76 / Bundle 377a5ccc…0363 54/54 전후 일치, F08 세 조건 그로기 전체 hit·종료 뒤 stand·복귀 jump·그로기 중 사망 die·정리 경로, F09 9패턴 문구 없음·칸 속성색, Plan §16 필수 2칸 패턴 F02 복귀 조합 V07·V08 PASS·FAIL 없음, 육안·0.20초 손 타이밍·CSV 변경 반영·실기기·플레이어 사망 중 칸·실제 맵 이동 NOT_RUN, 범위 밖 관찰 일반 사망 stand 표시 재현, 독립 reviewer 대기). 그 전: 독립 리뷰 V11-F01~F06 **WAITING**(리뷰 기록 첫 절, b89de46 / Bundle b985aa4b…74dbf 54/54 재계산 일치, 새 결함 없음, 사용자 V11·CF-F07 연출·V12 대기). 그 전: 독립 QA 5회차 V11-F01~F06(QA 기록 첫 절, Bundle b985aa4b…74dbf 54/54 전후 일치, F06 수치·로그 PASS·FAIL 없음·육안/창 0.20 손 타이밍/CSV 변경/F04 클립 재계측 NOT_RUN, 독립 reviewer F01~F06 일괄 리뷰 대기). 그 전: coder V11-F06 구현·기본 검증 인계(맨 아래 절, 새 Bundle b985aa4b…74dbf 54경로). 그 전(2026-11-02): 독립 QA 4회차 V11-F01~F05(QA 기록 첫 절, Bundle d2b57802…0fbb 54/54 전후 일치, 수치·로그 PASS·육안 일부 NOT_RUN, 독립 reviewer 대기). 그 전: coder V11-F01~F05 구현·기본 검증 인계(맨 아래 절, 새 Bundle d2b57802…0fbb 54경로). 아래는 그 이전 상태 — coder REV-F01 수정·기본 검증(커밋 6614b20 / Bundle 1ac324e6…9de4), 독립 tester 3회차 수치 PASS, 독립 리뷰 WAITING. 사용자 V11 대기. 2026-10-29 QA2·리뷰와 그 이전 기록은 이전 버전 근거.
- 실행: [20261020-combat-core](../../../../.pipeline/20261020-combat-core/run.md).
- 삭제 조건: 승인된 범위 구현·필수 확인·결과/미완료 추적 이관·링크 정리 완료 후 삭제. 사용자 직접 확인이 남으면 유지한다. 2026-11-19: 결과·미완료 추적 이관은 끝났다. CombatFoundation-F07도 같은 날 사용자 결정으로 닫혀 남은 사용자 확인이 없다. 삭제 여부는 사용자가 Plan·run과 함께 정한다. 삭제할 때 Feature·후속 계획·로드맵·README의 이 기록 링크를 함께 정리한다.

## 현재 재개 지점

2026-11-19 CombatFoundation-F07 닫기(planner, 문서만): 사용자가 "기존 수락으로 닫기"로 답했다. 회차 C V11 8번(모바일·터치·사운드·CF-F07) "이상 없음"과 회차 D·E PC 수락을 F07 실제 연출 평가(피해 숫자 가시성·피격·die 연출) 완료로 인정했다. 수치 근거는 아래 QA 기록의 QA2(2026-10-29)·QA3(2026-11-02)이다. 평가 기준은 PC Maker이고, 모바일·실기기는 F07을 다시 열지 않고 [2단계 후속 계획](../Plans/CombatCore.md) CombatCore-V11 NOT_RUN으로 추적한다. CombatFoundation·Feature·후속 계획·Plan·로드맵·README 연결을 맞췄다. 제품 파일·run은 바꾸지 않았다. 이 기록을 남길 사용자 확인은 더 없고, 삭제 여부는 사용자가 정한다. 아래 문단은 이전 기록이다.

2026-11-19 2단계 완료 정리(planner, 문서만): 사용자가 "모바일연결이나 멀티환경 테스트는 하지는 않음. 그래도 2단계 완료는 해도 될것 같음."으로 2단계 완료를 결정했다. Plan §6 P01b~P06을 ✅로 바꾸고 결과를 [2단계 Feature](../Features/2_CombatCore.md)로 이관했다. V11 모바일·실기기 터치 부분과 V12 실제 외부 환경 부분은 NOT_RUN(PASS 아님)이며, 이 기록의 QA·리뷰 절에 남은 다른 NOT_RUN(실접속 지연 위치 동기화, 맵 이동 뒤 최대 HP, 열 누락 경고 줄 등)과 부채는 [2단계 후속 계획](../Plans/CombatCore.md) ID로 옮겼다. CombatFoundation-F07은 근거를 붙여 사용자 확인 대기로 바꿨다. 제품 파일·run은 바꾸지 않았다. 현재 AI 담당 작업은 없고 3단계는 사용자 시작 지시 대기다. 아래 문단은 이전 기록이다.

2026-11-19 회차 E 종료(planner, 문서만): [Plan §24](../Plans/2_CombatCore.md) 회차 E(CombatCore-UX-01 조작 버튼 메이플 테마, UX-02 가드 alert·가드 시작 이펙트·효과음, PlayerActionFxData)는 사용자 V11 수락으로 완료했다. 사용자는 Maker 26.11에서 §24.8을 확인하고 "다른 건 다 좋음"으로 답했다. 바꿀 점은 없고, 무기 없을 때 공격·가드가 같은 모습(QA15 O-1)과 이펙트 첫 프레임 흰 세로선(O-3)도 수락했다. 26.11 tester 연기 시험은 하지 않았다(사용자 "바로 V11 확인", V11이 26.11 확인을 겸함). 아래 리뷰 기록 첫 절의 "회차 종료 planner 정리 목록"은 이번에 반영했다. Plan §24.7(O-6 패턴 5행, O-2 경고 문구 키 단위, O-5 입력 게이트 근거, 스크린샷 허용 범위 충돌 주석), §24.9 ✅와 사용자 결정 대기 목록, 새 §24.12 남은 과제(스크린샷 허용 범위 명시, SetGuarding 연출 호출 순서 등), §24.10 CoreVersion 메모, GameDesign §7.4·§8, AssetList(회차 E 에셋 "사용 중", 교체된 버튼 이미지 4개), FileStructure §2·§4, 로드맵 재개 지점이다. 일시정지 중 작업 트리 변경(CoreVersion 26.11, 스킬·NativeScripts·AGENTS.md·skills-lock, CombatScreen 형식 재저장)은 사용자 지시로 [ops] d0d095b에 커밋됐고 회차 E 문서가 아니다. 현재 AI 담당 작업은 없고 다음 회차는 정해지지 않았다. 남은 NOT_RUN(모바일·실기기 터치, 정상 0.20초 창 사람 손 JUST, 열 누락 경고 줄 직접 실행)은 PASS로 세지 않는다. P01b~P06 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다. 아래 문단은 이전 기록이다.

2026-11-16 회차 D·D2 종료(planner, 문서만): [Plan §22](../Plans/2_CombatCore.md) 회차 D(MM-07~11, 22.16 재설계 포함)와 22.17 D2(MM-13~15)는 사용자 V11 수락으로 완료했다. 사용자가 V11에서 바꾼 값은 1칸 두 행 AttackSound(35ee15e5… → player 점프음 a49c4b39…, D-Q13, 5ce65d6)뿐이며, 나머지는 Plan 22.16.9 표의 값(0.7배, TelegraphLeadSec 1.571429/1.571429/0.5/0.5/1.571429, 도약 조절 항목 기본값 등) 그대로다. MM-14 "버벅임"은 원인을 측정으로 확정하지 못한 채 조절 항목 기본값 수락으로 닫았다(Plan 22.17.9). 아래 리뷰 절들의 "회차 종료 planner 정리 목록"은 이번에 Plan·GameDesign·AssetList·FileStructure·로드맵·이 기록에 반영했다(원장 castleenemy 문구는 범위 밖으로 남김, E-Q1 반영은 회차 E 시작 때). 날짜 정정: REV-D-O1 수정(8428a05)·QA13·그 리뷰(7cbf14e)는 git 기록상 2026-11-10이고, MM-14 2차 구현(e710907)은 2026-11-16이라 해당 절 제목을 고쳤다(본문은 당시 기록 그대로). 현재 AI 담당 작업은 없다. 다음 후보는 회차 E([Plan §24](../Plans/2_CombatCore.md))이며 사용자 시작 지시가 있어야 시작한다. 남은 NOT_RUN(실접속 위치 동기화·모바일·실기기·사람 손 JUST 등)은 PASS로 세지 않는다. P01b~P06 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다. 아래 문단은 이전 기록이다.

2026-11-09 회차 D 재개(planner, 문서만): coder 구현 e5f7249(57경로 Bundle a7bc3d73…539d) 뒤 사용자 새 요구 "눈빛 중에는 점프 시작이 아니므로 점프 상태이면 안 됨"으로 [Plan §22.16](../Plans/2_CombatCore.md)에 2칸·3칸 접근 재설계(제자리 → 도약 프레임에서 점프 → 착지 = 판정, `JumpStartFrame` 열, 이펙트 2단계 분할 재생, V11 속도 조절 안내)를 적었다. 22.4·22.6·22.7·22.8·22.10·22.12·22.13·22.14에는 대체 표시만 달았다. ~~사용자 질문 D-Q3(시간 구조)·D-Q4(제자리 피격)·D-Q5(접근 점프 높이)·D-Q6(미결 (A))·D-Q7(미결 (B) 로그 버퍼)이 메인에 있다.~~ → 같은 날 사용자 답(Plan 22.16.11): D-Q3 원작 속도 1배(2·3칸 판정 1.1초·배율 1), D-Q4 제자리 피격 가능, D-Q5 수평 이동만, D-Q6 지금 고침(계약 22.16.12), D-Q7 이번 회차 한정 로그 비우기 허용. 답 뒤 coder가 22.16.10 순서로 재작업하고 이 기록 맨 아래 회차 D 개발절에 이어 적는다. 아래 2026-11-08 문단은 이전 기록이다.

2026-11-08 회차 D 시작: 사용자 "회차 D 시작"(기준 7a796aa). planner가 [Plan §22](../Plans/2_CombatCore.md) 범위만 확인했다(22.14 "2026-11-08 회차 D 시작 범위 확인", 22.7 OrangeMushroomAttack 명시, 22.15 재스폰 프레임 범위 처리 원칙, 선택 항목 `_T.resolveIndex` 제외 → 22.13 부채). 규칙·수치 변경 없음. ~~시작 전 확인 1건 D-Q1(MonsterSoundData 생성 방법)이 메인에 있다.~~ → D-Q1 사용자 답 "AI 수동 작성"(Plan 22.5·22.9·22.10 반영). 회차 D coder는 이 기록 맨 아래에 새 개발절을 만든다.

이전 재개 지점 — 2026-11-08(회차 C2 사용자 V11 수락 뒤) 기준: [Plan §23](../Plans/2_CombatCore.md) 회차 C2(CombatCore-MM-12)는 사용자 V11 수락으로 완료했다(회차 종료 커밋 7a796aa). 사용자는 Plan §23.4 두 항목(Maker 작업 공간에 주황버섯 모델이 OrangeMushroom 하나로만 보임, 플레이 화면이 회차 C와 같음)을 확인했다. 파일 이름과 Name은 사용자가 Maker에서 바꿨고 coder는 모델을 다시 쓰지 않았다. 근거는 아래 C2 coder 절, QA 기록 첫 절(QA11), 리뷰 기록 첫 절이다. 현재 AI 담당 작업은 없다. 다음은 회차 D([Plan §22](../Plans/2_CombatCore.md), CombatCore-MM-07~11, 기준 7a796aa, 재스폰 프레임 범위 확인 §22.15 포함)이며 **사용자 시작 지시를 기다린다**. 그 뒤 회차 E([Plan §24](../Plans/2_CombatCore.md))도 사용자 시작 지시 뒤다. 회차 D coder는 이 기록 맨 아래에 새 개발절을 만든다. 범위 밖 남은 사항: `.maplestory-skill-maker-ledger.md`의 낡은 castleenemy 문구(원장 규칙에 정리 조항 없음, 정리 시점은 사용자 결정, Plan §23.6). 남은 NOT_RUN은 QA11 기록 그대로이며 PASS로 세지 않는다. P01b~P06 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다.

이전 재개 지점(2026-11-06, 회차 C 사용자 V11 수락 뒤) 기준: [Plan §21](../Plans/2_CombatCore.md) 회차 C(CombatCore-MM-01~06·V11-F15)는 사용자 V11 수락으로 완료했다(회차 종료 커밋 b93e2ac). 리뷰 기록 첫 절의 "남은 사용자 V11" 1~6은 확인, 8은 이상 없음(사운드 실청취는 회차 D)이다. 7은 영어 이름 정리로 답해 [Plan §23](../Plans/2_CombatCore.md) 회차 C2로 넘겼다. 키 orangemushroom은 그대로 두고 파일 이름과 모델 Name만 OrangeMushroom으로 바꾼다. 주황버섯 MonsterData·MonsterStatData·패턴 행은 6단계다(사용자 "6단계로 미루기"). 현재 AI 담당 작업은 없다. 다음은 사용자 시작 지시 뒤 회차 C2 → 회차 D([Plan §22](../Plans/2_CombatCore.md), 재스폰 프레임 범위 확인 §22.15 포함) → 회차 E([Plan §24](../Plans/2_CombatCore.md))다. 회차 E는 사용자 선택(§24.6) 전에는 구현 범위가 정해지지 않는다. 회차 C2 coder는 이 기록 맨 아래에 새 개발절을 만든다.

2026-11-06 추가(회차 E 선택 확정): 사용자가 [Plan §24.6](../Plans/2_CombatCore.md) 질문 6개에 모두 추천안으로 답했다(simplefantasy, ↑ 칼·↓ 아래 화살표·←→ 화살표, 눌림 ColorTint 유지, 가드 alert·찌르기 없음, 로얄 가드 effect 가드 시작 1회·기존 패링 성공 이펙트 유지, 가드 시작 때 로얄 가드 _audio/Use만·버튼 소리 없음). 범위는 §24.2~24.4·24.7에 확정했고 남은 사용자 확인은 §24.10 E-Q1(가드 이펙트·소리 RUID 저장 위치) 1건이다. 구현 승인 아님, 순서 C2 → D → E는 그대로이며 회차 시작은 사용자 지시다.

이전 재개 지점(2026-11-06, 회차 C 리뷰 뒤) 기준: [Plan §21](../Plans/2_CombatCore.md) 회차 C(CombatCore-MM-01~06·V11-F15)는 msw-coder 구현·기본 검증(로컬 커밋 5a605ba, 맨 아래 2026-11-05 개발절) → 중단 조건 3(Maker에 옛 castleenemy 항목 잔존)으로 STOPPED → 사용자가 월드를 다시 열고 주황버섯 모델을 원래 경로로 되돌려 해소, Maker 재저장분은 [ops] b4adbdd(제품 의미 동일) → 별도 msw-tester 독립 QA 10회차(대상 b4adbdd, 55경로 Bundle 222e7a04…476d, castleenemy 스폰 nil 확인, 실행 기준 전부 PASS·FAIL 없음) → 별도 msw-reviewer 독립 리뷰 **WAITING**(리뷰 기록 첫 절, 결함 없음)까지 마쳤다. 현재 AI 담당 작업은 없고 다음은 사용자 V11이다(확인 항목은 Plan §21 "사용자 V11 직접 확인"과 리뷰 기록 첫 절 "남은 사용자 V11" 1~8). 회차 D([Plan §22](../Plans/2_CombatCore.md), CombatCore-MM-07~11)는 회차 C 사용자 V11 수락과 사용자 시작 지시 뒤에 시작한다. 리뷰가 회차 D로 넘긴 재스폰 개체 프레임 범위 0-0 확인(필수)과 `_T.resolveIndex` 정리(선택)는 Plan §22.15에 적었다. GameDesign §4.2·§5의 예정형 문구는 사용자 V11 수락 뒤 완료형으로 고친다. 남은 NOT_RUN은 QA10 기록 그대로다. 아래 QA·리뷰 절 본문은 당시 근거 그대로 둔다. P01b~P06 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다.

이전 재개 지점(2026-11-05, 머쉬맘 모션·사운드 지시 뒤) 기준: 회차 C([Plan §21](../Plans/2_CombatCore.md))의 머쉬맘 애니메이션 연결은 사용자 확인 완료다(stand←stand, move←move 기본값, jump←jump, hit←hit1, die←die1). 회차 C에서는 모든 공격이 jump 모습이고 ActionSheet 키는 5개다. 기준 커밋 eca1903(제품 파일은 8f16a81과 같음), 예상 작업 트리 변경은 PlayerBaseStatData.csv(V11-F15)·run.md다. coder 시작 조건은 사용자 재개 지시뿐이고 그 전까지 정리 단계만 한다. 회차 D([Plan §22](../Plans/2_CombatCore.md), CombatCore-MM-07 패턴별 모션·MM-08 3칸 parry.guard·Pos2 착지·MM-09 비중 4/4/5/3/4와 사용자 Weight 표·MM-10 3칸 이펙트·MM-11 효과음)는 구현 승인 범위이며 회차 C 사용자 V11 수락과 시작 지시 뒤에 시작한다. 이 문서 아래 기존 회차 C 기준 문단은 이전 기록이다.

이전 재개 지점(2026-11-05, 회차 C Plan 뒤) 기준: [Plan §21](../Plans/2_CombatCore.md) 회차 C가 구현 승인 범위다. MM-01 머쉬맘 리소스 모델(Models/Monsters/Mushmom.model, model://mushmom, 1배), MM-02 키 mushmom(MonsterData·패턴 4행·MonsterStatData), MM-03 규칙 충족형 플레이어→몬스터 피격과 공격 점프 구간 피격 불가 선언, MM-04 공격 범위 도구·AssistModel·범위 열 삭제, MM-05 주황버섯 모델 1배·키 orangemushroom(패턴·스폰 없음), MM-06 stun 키 제거·그로기 hit 직접 지정, V11-F15 사용자 직접 변경 플레이어 수치 100·12·12다. 공격 위치 조건은 규칙에 넣지 않는다(사용자 결정). 새 파일 위치는 [파일 구조 기준](../FileStructure.md)을 따르고 기존 파일 이동은 회차 C 뒤 별도 회차다. 사용자 재개 지시 전까지 정리 단계만 하며, coder 전 사용자 확인 1건(애니메이션 연결 기본안 stand·move·jump·hit1·die1)이 남았다. 그다음 msw-coder 한 회차(기준 8f16a81, 이 기록 맨 아래 새 개발절) → 같은 버전 msw-tester → msw-reviewer → 사용자 V11이다. P01b~P06 🟡 유지.

이전 재개 지점(2026-11-05, 회차 B 사용자 V11 수락 뒤) 기준: [Plan §20](../Plans/2_CombatCore.md) 회차 B(CombatCore-V11-F14·V11-F07)는 아래 "이전 재개 지점(회차 B 리뷰 뒤)"의 coder·QA9(보충 시험 1 포함)·리뷰 WAITING에 이어 사용자 V11 직접 확인까지 마쳐 완료다. 메인이 물은 4항목(이동·복귀 체감이 회차 A와 같은지 / 해 보셨다면 PlayerBaseStatData.csv·MonsterStatData.csv 직접 수정이 Refresh→Play에 반영되는지와 표·열 이름 / AttackInterval 3.0 = 공격 종료 뒤 IDLE 대기 3.0초·시작~다음 시작 약 4.0초가 생각한 공격 간격과 같은지 / 플레이어 HP 바 현재/최대 숫자)에 사용자가 "전부 ok"로 답했다(근거: [run](../../../../.pipeline/20261020-combat-core/run.md) "2026-11-05 회차 B 사용자 V11 수락" 절). 새 요구·재현 결함은 없다. HP 바 자릿수 육안 NOT_RUN은 이 확인으로 해소했고 AttackInterval 의미는 확정됐다(변경 없음). CSV 직접 수정은 "해 보셨다면" 조건 질문이라 사용자 실시 여부가 확정되지 않았으므로 사용자 실시 기록으로 세지 않는다. 반영 근거는 AI 측 QA9 "CSV 실제 변경 반영" 사례와 보충 시험 1이다. 현재 AI 담당 작업은 없고, 다음은 회차 C(Plan §18 머쉬맘 전환, CombatCore-MM-01·MM-02) 시작 여부 사용자 결정이다(시작 지시 필요, 시작 전 §18 질문 답 필요). 남은 것: 맵 이동 뒤 복귀·재접속 때 플레이어 MaxHp(맵 추가 단계), 실기기·다중 접속, V12, 기존 V11 미확인(모바일·터치·음향·반격 체감·CF-F07), 그 밖의 아래 NOT_RUN(사람 손 0.20초 타이밍 기본 창, V07 예고 중 팝업 전수, F06 `parry.right` 대칭 착지·F10 출현 빈도, 실제 다른 맵 전환에서의 위치 기록 삭제, 표 실패 비대칭, Maker UI DataSet 편집). 아래 QA·리뷰 절 본문은 당시 근거 그대로 둔다. P01b~P06은 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다.

이전 재개 지점(2026-11-05, 회차 B 리뷰 뒤): [Plan §20](../Plans/2_CombatCore.md) 회차 B(CombatCore-V11-F14 플레이어 최대 HP·이동·복귀 속도 DataSet, V11-F07 몬스터 HP·공격력·공격 간격 DataSet)는 msw-coder 구현·기본 검증(로컬 커밋 1b4f4ee, 기준 9eed765, 맨 아래 2026-11-04 개발절) → 별도 msw-tester 독립 QA 9회차(QA 기록 첫 절, 59경로 Bundle 9325c33a…cd19 시작·재개·끝 일치, 실행 기준 PASS·FAIL 없음)와 "QA9 보충 시험 1"(플레이어 `default` MaxHp 800에서 서버·클라이언트·부활 모두 800, PASS) → 별도 msw-reviewer 독립 리뷰 **WAITING**(리뷰 기록 첫 절과 "보충 확인" 소절, 결함 0, MaxHp 근거 공백 해소)까지 마쳤다. 현재 AI 담당 작업은 없고 다음은 사용자 V11이다(확인 항목은 Plan §20 "사용자 V11 직접 확인": 이동·복귀 체감, CSV 직접 수정과 표·열 이름, 몬스터 행 수정, AttackInterval 의미, HP 바 자릿수 육안). tester 비차단 후속은 정리됐다: (a) 예고 없는 ↓ 홀드 가드 시작 기록은 재현 안 됨·종결(결함 후보 아님), (b) 실제 HP 0 사망 뒤 기록 삭제·부활 Hp는 PASS. AttackInterval 표현 정정: coder 개발절 "IDLE→ATTACK 전환 간격 2.96~3.01초"와 Plan의 옛 "자연 공격 시작 간격 3.0초"는 공격 종료 뒤 IDLE 대기 3.0초(시작~다음 시작 약 4.0초)를 뜻한다. 값·동작은 바뀌지 않았고 Plan §5·§20 문구만 고쳤다(개발절 본문은 그대로). 이 의미가 사용자가 생각한 "공격 간격"과 다르면 새 요구로 planner를 거친다. 남은 NOT_RUN: 맵 이동 뒤 복귀·재접속 때 플레이어 MaxHp, HP 바 자릿수 육안, 사람 손 0.20초 타이밍, 모바일·실기기·터치·다중 접속, V07 예고 중 팝업 전수, F06 `parry.right` 대칭 착지·F10 출현 빈도, 실제 다른 맵 전환에서의 위치 기록 삭제, 표 실패 비대칭, Maker UI DataSet 편집, V12·CF-F07(Plan §20 상태 절). 작업 트리의 Stat.directory 재저장 한 줄은 범위 밖(메인 결정). V11 결과에 따라 Plan §18(회차 C, 시작 전 애니메이션 선택 등 사용자 질문 필요) 순서는 그대로다. 아래 QA·리뷰 절 본문은 당시 근거 그대로 둔다. P01b~P06은 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다.

이전 재개 지점(2026-11-04, 회차 B Plan 뒤): 사용자 "기본안으로 시작"으로 [Plan §20](../Plans/2_CombatCore.md) 회차 B(CombatCore-V11-F14 플레이어 최대 HP·이동·복귀 속도 DataSet, V11-F07 몬스터 HP·공격력·공격 간격 DataSet)가 구현 승인 상태다. 현재 값(1000·6·6, 100·12·3.0)을 그대로 새 표(PlayerBaseStatData·MonsterStatData, 설계안)로 옮기며 결과가 이전과 같아야 한다. coder 시작 전 조건(Maker 재저장 3파일)은 [ops] 9eed765로 해소됐다. 다음은 msw-coder 한 회차(기준 9eed765, 이 기록 맨 아래에 새 개발절, 첫 단계로 모델 Values 고정 수치 확인) → 같은 버전 msw-tester(아래 비차단 후속 2건 포함) → msw-reviewer → 사용자 V11이다. 그 뒤 Plan §18(회차 C). P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-04, 회차 A 사용자 V11 수락 뒤): [Plan §19](../Plans/2_CombatCore.md) 회차 A(CombatCore-V11-F12·V11-F13)는 아래 "이전 재개 지점(회차 A 리뷰 뒤)"의 coder·QA8·리뷰 WAITING에 이어 사용자 V11 직접 확인까지 마쳐 완료다. 메인이 물은 4항목(die 1회 재생 후 끝 모습 정지·그로기 중 처치·팝업 열고 닫은 뒤 / Pos2에서 가운데 칸이 켜진 공격에서만 JUST·PARRY, 정상 입력 실패 여부 / 0.20초 판정 창 손 타이밍 / 끝 칸 1칸 공격·특수 무작위 무보상 난이도)에 사용자가 "전부 ok"로 답했다(근거: [run](../../../../.pipeline/20261020-combat-core/run.md) "2026-11-04 회차 A 사용자 V11 수락" 절). 새 요구·재현 결함은 없다. 사람 손 기본 0.20초 타이밍 성공 NOT_RUN은 이 확인으로 해소했다. 모바일은 "해 보셨다면" 조건 질문이라 실시 여부가 확정되지 않았으므로 모바일·실기기는 기존 V11 미확인 항목으로 남긴다. 현재 AI 담당 작업은 없고, 다음은 회차 B(플레이어 기본 능력치 DataSet·V11-F07, Plan 미작성) 시작 여부 사용자 결정이다. 그 뒤 Plan §18(회차 C) 순서는 그대로다. 남은 것: 기존 V11 미확인(모바일·터치·음향·반격 체감·CF-F07), 비차단 후속 2건(회차 B tester: 예고 없을 때 ↓ 홀드 `[VRF] PlayerGuard start` 미발생 관찰 재현, 실제 HP 0 플레이어 사망 뒤 위치 기록 삭제 1건), 실제 다른 맵 전환에서의 위치 기록 삭제, 재생 중 die AI 화면 캡처, CSV 파일 변경 반영, 다중 접속 위치 오차·V12. 아래 QA·리뷰 절 본문은 당시 근거 그대로 둔다. P01b~P06은 🟡 유지, 2단계 완료·3단계 진행은 사용자 결정이며 이 기록이 승인하지 않는다.

이전 재개 지점(2026-11-04, 회차 A 리뷰 뒤): [Plan §19](../Plans/2_CombatCore.md) 회차 A(CombatCore-V11-F12·V11-F13)는 msw-coder 구현·기본 검증(로컬 커밋 7f2d0b4, 기준 5c4eda3, 맨 아래 2026-11-04 개발절) → 별도 msw-tester 독립 QA 8회차(사용자 일시정지로 중단 뒤 같은 날 재개, QA 기록 첫 절과 "QA8 재개" 소절, 작업 트리 Bundle b321d71c…040f 54/54 전후 일치, 실행 기준 PASS·FAIL 없음) → 별도 msw-reviewer 독립 리뷰 **WAITING**(리뷰 기록 첫 절, 고칠 결함 없음, 커밋 트리 7f32ae45…e21e3 재계산 일치, QA8 근거가 커밋 트리에도 적용)까지 마쳤다. 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다(확인 항목은 Plan §19 "사용자 V11 직접 확인"과 리뷰 기록 첫 절). 남은 NOT_RUN: 사람 손 기본 0.20초 타이밍 성공, HP 0 실제 플레이어 사망과 실제 다른 맵 전환에서의 위치 기록 삭제, 재생 중 die 화면 캡처·육안, CSV 파일 변경 반영, 실기기·터치·모바일, 다중 접속 위치 오차, V12, CF-F07. V11 결과에 따라 회차 B(플레이어 기본 능력치 DataSet·V11-F07, Plan 미작성) → Plan §18(회차 C) 순서로 사용자 재개 지시 뒤 진행한다. V11에서 새 요구나 재현 결함이 나오면 해당 ID만 다시 돈다. 비차단 후속(회차 B tester): (1) 예고가 없을 때 DownArrow 홀드가 `[VRF] PlayerGuard start`를 남기지 않은 관찰의 재현(클라이언트·서버 CurrentStateName, isGuarding, 시작 기록 유무, 기존 GUARD 상태 재홀드 여부를 함께 기록, 재현되면 새 결함 후보로 planner에 넘김), (2) 가능하면 HP 0 실제 플레이어 사망 뒤 위치 기록 삭제 1건. 서버 기록 위치·클라이언트 위치 차이 재기록은 V12 외부 환경 또는 실기기 회차 후속이다. P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-04, 회차 A Plan 뒤): 2026-11-03 사용자 V11에서 §17의 F10 4패턴과 F11 "가드 불가" 문구는 통과했다. REV-F02는 die가 반복 재생된다는 보고로, 범위 밖 저스트는 "너무 쉬움" 보고와 Pos2 규칙 확정으로 이어진다. planner가 [Plan §19](../Plans/2_CombatCore.md)에 CombatCore-V11-F12(die 1회 재생 후 마지막 프레임 정지)와 V11-F13(JUST·PARRY 성공은 입력 시작 위치 Pos2 칸 ±0.75, 공격 영역 Pos2 포함 조건)을 정리했고, 2026-11-04 사용자 "A 회차 시작"으로 구현 승인 상태다. 다음은 msw-coder 한 회차(기준 5c4eda3, 이 기록 맨 아래에 새 개발절) → 같은 버전 msw-tester(QA 8회차) → msw-reviewer → 사용자 V11이다. 회귀로 다시 볼 기존 근거는 QA 7회차 REV-F02 사망 경로·E1 계열, QA 5회차 K3b·ANY 끝 칸 저스트(기대가 JUST 아님으로 바뀜)다(Plan §19 "다시 확인할 기존 근거"). 회차 B(플레이어 기본 능력치 DataSet·V11-F07)와 Plan §18(회차 C)은 그 뒤다. P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-03, 5c4eda3 리뷰 뒤): Plan §17 회차(REV-F02·V11-F10·V11-F11)는 msw-coder 구현·기본 검증(로컬 커밋 5c4eda3, 맨 아래 2026-11-03 개발절) → 별도 msw-tester 독립 QA 7회차(작업 트리 Bundle fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80, 54/54 전후 일치, H1 포함 전부 PASS) → 별도 msw-reviewer 독립 리뷰 **WAITING**(결함 없음, 5c4eda3 커밋 트리 Bundle 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79 / 작업 트리 fdca556d…ee80 재계산 일치, QA7 근거가 커밋 트리에도 적용)까지 마쳤다(각각 QA 기록·리뷰 기록 첫 절). 현재 AI 담당 작업은 없고 다음은 사용자 V11 확인이다. 확인 항목 5개는 리뷰 기록 첫 절 "사용자 V11 확인 항목"에 있고 [Plan §17 끝 "사용자 V11 확인 항목"](../Plans/2_CombatCore.md)에 연결했다. 그 뒤 Plan §18(머쉬맘 전환, MM-01·MM-02)은 사용자 재개 지시와 §18 질문 답을 받은 다음 시작한다. 남은 필수: V11, CF-F07 실제 연출 평가, V12 외부 환경과 기존 외부 후속 ID. P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-03, b89de46 기준): msw-coder가 V11-F06을 구현·기본 검증했고(커밋 b89de46 / 54경로 Bundle b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf, 맨 아래 2026-11-03 개발절), 별도 msw-tester가 같은 Bundle에서 독립 QA 5회차(커밋 a43b1b5, F01~F06 수치·로그 PASS·FAIL 없음, 육안·창 0.20 손 타이밍·CSV 변경 반영·F04 클립 재계측 NOT_RUN), 별도 msw-reviewer가 F01~F06 일괄 리뷰 **WAITING**(커밋 2dbaa07, 새 결함 없음)을 판정했다(각각 QA 기록·리뷰 기록 첫 절). 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다. 확인 항목 7개는 리뷰 기록 첫 절 "다음 행동" 4번에, 비차단 재확인 공백(2칸 패턴 패링 → 복귀 중 팝업 정지·재개, 복귀 중 Stop → 재Play 기본값)은 같은 절 "같은 버전 확인"에 있으며, 둘 다 [Plan §15 끝 "사용자 V11 확인 항목"](../Plans/2_CombatCore.md)에 연결했다. 남은 필수: V11, CF-F07 실제 연출 평가(수치 근거만 확보), V12 외부 환경과 기존 외부 후속 ID. V11에서 새 요구나 실기기 재현 결함이 나오면 해당 ID만 다시 돈다. P01b~P06은 🟡 유지, 3단계 미시작. 범위 밖 관찰인 플레이어 사망 직후 HP 문자 음수 표시 가능성은 V11 확인 항목 7번에 포함됐다(처리 여부는 3단계 계획 후보).

이전 재개 지점(2026-11-02, 6614b20 기준): 2026-11-02 사용자 재개 명령에 따라 msw-coder가 REV-F01을 최소 수정·기본 검증했고(커밋 6614b20 / 52파일 Bundle 1ac324e6…9de4, 아래 2026-11-02 개발절), 별도 msw-tester가 같은 Bundle에서 독립 QA 3회차 수치 PASS, 별도 msw-reviewer가 WAITING을 판정했다(각각 QA 기록·리뷰 기록 첫 절). 최종 map01/edit·Maker 사용 종료·제품 지문 전후 동일 확인. DOC-01 현황·링크 동기화는 2026-11-02 planner가 정리했다. 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다. 남은 필수: V11, CF-F07 실제 연출 평가(수치 근거만 확보), V12 외부 환경과 기존 외부 후속 ID. 결함 경과: QA-F01은 QA1 FAIL→QA2 수치 PASS, REV-F01은 2026-10-29 리뷰 지적→QA3 수치 PASS·리뷰 해소. 과거 FAIL과 이전 버전 QA/리뷰는 당시 근거로 보존한다. P01b~P06은 🟡 유지, 3단계 미시작. V11 때 함께 볼 범위 밖 관찰: 플레이어 사망 직후 HP 문자 음수 표시 가능성(새 규칙 아님, 처리 여부는 3단계 계획 후보).

### 과거 중단 기록 (2026-10-20)

사용자가 1단계 V08을 완료하고 2단계 진행을 승인했다. D01~D03은 제시한 A안, D04는 “전투하는 몬스터. 애초에 상대 몬스터는 1개체 고정(1:1대결)”로 답했다. 실제 확정 규칙·구현 범위는 Plan을 따른다. 기획 반영과 Plan 연결 확인 후 coder를 호출했으나 사용자가 남은 작업의 중단을 요청했다. 자동 재개하지 않는다.

## 과거 감독·인계 기록 (2026-10-20)

- 메인: /root. 독립 planner /root/combat_core_planner가 1단계 종료 정리·2단계 Plan 작성 후 사용자 답변을 반영 완료.
- coder /root/combat_core_coder: 사전 준비 중 사용자 요청으로 interrupt, 현재 interrupted. tester/reviewer는 미호출.
- Maker: coder의 사전 조회가 "user rejected MCP tool call"로 거절됐다. 재시도·우회·Play 없음. 직전 map01·edit은 과거 관찰이며 현재 상태로 간주하지 않는다.
- 새 QA/리뷰 결과: 아직 없음.

## 개발 기록

아래 문단은 2026-10-20 당시 중단 이력이다. 최신 재개·구현·검증은 뒤의 2026-10-24 절을 따른다.

제품 구현 완료 기록 없음. coder는 제품 편집 전 사전 문맥·소유자 점검 단계에서 중단됐다. 구현 ledger도 아직 생성되지 않았다. MapBuilder 읽기는 map01 id=0a0972ef-ad23-4e24-af63-afbd53120c1d, TileMapMode=0을 확인했다. 실제 Maker 연결/모드·런타임 검증은 조회 거절로 미확인이다. 사용자 재개 명령 후 실제 변경 범위와 환경을 확인해 이어간다.

## QA 기록

### 2026-11-16 독립 QA 15회차 — 회차 E(CombatCore-UX-01·UX-02, 대상 3e29a35)
- 상태: **실행 완료.** Plan §24.7 기준 1~7 전부 PASS(아래 예외 표기), FAIL·NEEDS_DECISION·새 결함 없음. 관찰 6건과 NOT_RUN은 PASS로 세지 않았다. 독립 reviewer 대기, 사용자 V11(§24.8) 남음.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push·run.md·Plan 수정 없음. coder 절의 PASS는 이번 실행으로 세지 않았다. 바꾼 파일은 이 QA 절뿐이다.
- 대상 버전: 로컬 커밋 **3e29a35**(3e29a352e803665c00267049492f101afad53643, push 전, 기준 de6e6aa). 작업 트리는 `M map/map01.map`(사용자 변경) 하나뿐이라 나머지 제품 파일은 커밋과 같다.
- **Bundle 지문**: map01.map을 뺀 58경로(경로 바이트순, `경로 TAB 파일 sha256 LF`, 확장자 9종, Global·RootDesk·map·ui, 새로 작성한 node 스크립트로 계산) **`1d70bc71a65ddd70d8f29c377065b4058e7e60d71f0690ffcab48618e23975dd` — coder 값과 시작 전·Stop 뒤 모두 일치(58/58, manifest 파일 byte 비교도 동일).** map01 포함 59경로도 `7f6a703b237f07837ea642bf548c3bc749ac012785fbd76721af88e69a308940`로 coder 끝값과 같고 시험 전후 동일하다. **map/map01.map SHA-256 `3e60c21d6bd2328e1119f9566beb55901b13da64a99400c3d3ce68a0be5c2094`: 시험 전·후 동일**(Maker 저장·Play가 다시 쓰지 않음). 커밋 트리를 따로 해시 계산하지는 않았다(작업 트리 해시 + `git status`로 대신).
- 환경: Maker map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit로 시작, worldId 970621b29ba945369d3dc8e90c301186. build 로그 편집 모드 93건 전부 Info(LIA 노이즈), 오류 0 — Stop 뒤 다시 읽어도 93건 Info. Play 1회(16:01~16:10). **`maker_clear_logs` 호출 0회**, 로그는 저장 파일에서 `[VRF`·`[VRF TE` 줄과 Warning·Error만 걸러 읽었다(시험 전 버퍼에 coder 세션 줄이 남아 있음). 마지막 `maker_stop` 성공(play_to_edit) 뒤 `maker_get_current_map` = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit.
- 방법 구분: **(A)** 서버·클라이언트 프로브(`maker_execute_script`, `[VRF TE]` 접두어), **(B)** 실제 키 입력(`maker_keyboard_input`), **(C)** 실제 마우스(`maker_mouse_input`, 800×450 스크린샷 → 1920×1080 좌표 BtnAttack (960,343)·BtnGuard (960,180)·BtnBack (790,180)·BtnForward (1130,180)), **(D)** UIBuilder 읽기(node 스크립트, 읽기만), **(E)** 소스 diff(`git diff de6e6aa 3e29a35`). 시험 값은 모두 Play 메모리에서만 바꿨다(몬스터 AttackInterval 9999, 플레이어 HP, `_CombatRuleCatalog.playerActionFx`·`fxReady`·`patterns`·`rules.default.JustWindowSec`, 클라이언트 시간 배율) — 카탈로그는 `_T.attempted`/`fxAttempted` 해제 + 재초기화로 복원했고 복원 뒤 로드 [VRF]가 부팅 때와 같다(패턴 5행 가중치 20·20·25·15·20%, 사운드·수치 행 동일). Stop으로 폐기.

**기준별 결과 (Plan §24.7)**

| 기준 | 방식 | 이번 독립 실행 결과 | 판정 |
| --- | --- | --- | --- |
| 1 UI 정적(UX-01) | D + 스크린샷 | UIBuilder.load(23개 엔티티)로 직접 검사: 버튼 4개 UUID가 §24.1 표와 같고 Highlight 3개(93225eff·f486d930·c7d65fee) UUID·소속 같음. 4개 모두 SpriteGUIRenderer ImageRUID `e314c09b…`·Type 1·Color (1,1,1,1)·PreserveSprite 1·RaycastTarget true. `{버튼}/Icon` 정확히 1개씩, RUID ↑3119d280…·↓a714a1ea…·←002ca90c…·→740aba24…, Color (1,1,1,1)·Type 0·Raycast false·PreserveSprite 1, 앵커 (0.5,0.5)·위치 (0,0)·60×60. BtnBack·BtnGuard·BtnForward는 Icon displayOrder 0 < Highlight 1, BtnAttack은 Highlight 없음. ButtonComponent 4개 Transition 1·PressedColor 0.7843·상태 스프라이트 5종 null. 크기 140×140·위치 (0,270)/(-170,110)/(0,110)/(170,110) 그대로. CombatInputController의 `.mlua` 바인딩 12개 UUID가 전부 새 `.ui`의 엔티티로 풀린다. **화면 존재**: Play 800×450 스크린샷에서 버튼 4개가 원형 배경 + 흰 아이콘(칼·← · ↓ · →)으로 가운데 정렬돼 보임(UI RUID 5개가 실제로 표시됨). 어울림은 판정하지 않음(V11) | PASS |
| 2 데이터 로드 | A(Play 부팅 [VRF]) | `[VRF] PlayerActionFxData id=guard effect=318a4662 sound=605da1fc` 1회(16:01:19). 같은 부팅의 `catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`, 패턴 5행(parry.left·right·any·special.random·guard) lead·rate·jumpFrame·sound(f135fc39·a49c4b39·5da7bb48)·effect=05113e9d, MonsterSoundData mushmom 3개, MonsterStatData 100/12/3.0, 머쉬맘 스폰 x=3.0이 coder 기록·회차 D 값과 같다. Ready true, 경고 0 | PASS |
| 3 오류 동작 | A(CSV 무수정, 캐시·검증 함수 프로브) | **빈 칸**: EffectClip 빈 칸 → `guard fx effect=-` + `sfx kind=guard` 1, EffectSound 빈 칸 → `guard fx effect=318a4662` + sfx 0, 둘 다 빈 칸 → 둘 다 없음, 경고 0. 시작 분기를 `SetGuarding(true)` 두 번 연속 호출해도 시작·fx·sfx 각 1회. **형식 오류**(`ValidatePlayerFxRows` 직접 호출): 대문자·31자·공백 끼움·16진 아님·소리 칸 오류 5건 모두 REJECT, 경고 `PlayerActionFxData invalid ruid` **1회만**(같은 문구 키 공유, O-2), 중복 id(앞뒤 공백 제거 뒤) REJECT + `duplicate id` 1회, 빈 id REJECT + `invalid id` 1회. 정상·둘 다 빈 칸·행 0개는 ACCEPT. **표 무효(`fxReady=false`)**: 가드 시작마다 `guard fx off`, sfx 0, 두 번째도 동일, 추가 경고 없음. **guard 행 없음**: `[CombatRuleCatalog] player action fx row missing: guard` 경고 **정확히 1회**, 두 번째 가드 시작은 경고 없이 `guard fx off`. 이 모든 경우 `Ready=true`·`GetMonsterStats("mushmom")`·`GetMonsterSounds` 정상. `ReadRows(MonsterSoundData, 연출 열)`·`ReadRows(nil, …)`·`ReadRows(PlayerActionFxData, …+NoSuchColumn)` 모두 nil(필수 열 누락 경로), 실제 표는 rows=1. **표 무효 상태에서의 전투**: 아래 7번 루프 1~8번(`fxReady=false`) 8회 공격 모두 가드 상태 진입·판정 정상(GUARD 0.4 등), 스폰·몬스터 순환 정상 | PASS(필수 열 누락 때 `EnsurePlayerActionFx`가 내는 경고 줄을 직접 실행한 것은 NOT_RUN — 아래) |
| 4 입력 회귀(UX-01) | B + C | **실제 키**: ← → 탭 각 1회: `MovementInput OUTBOUND→RETURNING→complete state=IDLE`·`PlayerEvade start`, `sfx` 0건. ↑ 탭 1회 + **실제 마우스 클릭**(BtnAttack): IDLE→ATTACK, `manual cast count=10`, HitRule pass 10, 몬스터 피격음 `sfx kind=damaged` 1건뿐(버튼 누름음 없음). ← → **마우스 클릭**: OUTBOUND→RETURNING 동일, sfx 0. ↓ **키 탭 1.5초·키 down/up·마우스 홀드 1초**: 매번 IDLE→GUARD→IDLE, `PlayerGuard start` 1·`guard fx` 1·`sfx kind=guard` 1(홀드 유지 중 추가 없음). **터치(마우스)+키 동시**: 마우스 down + 키 down 동시 → GUARD 진입 1회, 시작·fx·sfx 각 1건, 마우스만 떼도 GUARD 유지(`isGuarding=true`), 키까지 떼면 IDLE | PASS(모바일·실기기 터치는 NOT_RUN) |
| 5 가드 모션 | A + B/C | 서버 `StateToAvatarBodyActionSheet` GUARD=`alert`·ATTACK=`attack`·MOVE=`walk`·IDLE=`stand`. 실제 ↓ 입력: 클라이언트 `StateChangeEvent IDLE→GUARD`, `BodyActionStateChangeEvent Alert`, Body 엔티티 `ActionStateChangedEvent core=alert parts=alert`. 떼면 `GUARD→IDLE`·`Stand`·`core=stand1`. 패링 성공 찌르기 모션 호출 없음(소스 diff에 없음, PARRY 시험 중에도 모션 이벤트 없음) | PASS |
| 6 이펙트·소리 | A + B/C + 스크린샷 | 가드 시작 1회마다 `[VRF] guard fx effect=318a4662` 정확히 1줄 + `[VRF] sfx kind=guard ruid=605da1fc user=있음` 정확히 1줄. 홀드 유지(1.5초·1초) 중 추가 없음, 떼었다 다시 누르면 새 가드 시작이라 다시 1회(키 4번·마우스 1번·논리 경로 포함 모두 1:1). 가드 상태에서의 부정 대조(아래 7): 이미 GUARD인 채 공격이 와도 새 `guard fx`·sfx 없음. **클라이언트 표시**: 클라이언트 시간 배율 0.03에서 가드 시작 직후 가는 흰 세로선(첫 프레임), 약 3초 뒤 스크린샷에 **금색 방패가 플레이어 오른쪽에 나타남**(서버 `PlayEffect`가 클라이언트에 보임, @Sync 대체 경로 불필요). 방향·크기·위치 어울림은 V11 | PASS |
| 7 다른 회귀 | A + B + 스크린샷 | **가드 판정 40%**: 가드 상태 25회 강제·자연 공격 루프에서 `defense kind=GUARD rate=0.4`(parry.guard·left·right·any 모두), `sfx kind=hitplayer ruid=7c8e5f1e` 동반(`kind=hitplayer` 그대로), special.random은 `UNGUARDABLE rate=1`. 가드 없을 때 `kind=HIT rate=1`. **Pos2 PARRY(0.2초 정상 창, 논리 경로)**: parry.any 단일 행 시험에서 서버 타이머로 공격 시작 +0.38초(판정 0.119초 전)에 GUARD 진입 → `PlayerHealth guard eval x=0.000 cellOk=true areaOk=true attr=PARRY` → `defense kind=PARRY rate=0`, HP 변화 없음, `groggy applied deadline=…`, 피격음 없음(2회 재현). +0.10초(0.4초 전, 창 밖)에 진입하면 `kind=GUARD rate=0.4`. **JUST**: `JustWindowSec`를 Play 안에서 30으로 늘린 시험 값 + 실제 ← 탭 후 공격 → `evade eval cellOk=true areaOk=true dir=LEFT` → `defense kind=JUST rate=0`, `HUD feedback=JUST`(정상 0.2초 창은 도구 지연 때문에 사람 손 타이밍으로 못 맞춤). **스파크·그로기 화면**: 클라이언트 시간 배율 0.15의 PARRY 직후 스크린샷에 "패링 성공 / 반격 준비 · 다음 직접 공격 강화 / 상태 그로기" 텍스트, 플레이어 주변 하늘색 스파크 입자, 머쉬맘의 소용돌이 눈(그로기), 가드 방패 이펙트가 함께 보임(`groggy visual serial` 클라이언트 로그). 모양 판정 아님. **팝업 정지**: 클라이언트에서 `_UIPopup:Open`(실제 팝업 UI) → `CombatPause server/client paused=true`, 정지 중 ↓ 키 1.2초 → `PlayerGuard start`·`guard fx`·`sfx kind=guard` 0건, '취소' 마우스 클릭 → `paused=false`·`popup closed session=1`, 재개 뒤 `FINAL plState=IDLE isGuarding=false`. **회차 D 대표 회귀**: 머쉬맘 스폰 x=3.0, 패턴 5행 값, 1칸 점프음 `sfx kind=attack ruid=a49c4b39`(parry.any·special.random 공격 각 1줄), 2칸 f135fc39·3칸 5da7bb48 공격음, die: 몬스터 Hp 5에서 ↑ 탭 → `sfx kind=damaged`·`sfx kind=die`, `MonsterDie start frames=6 total=1.100 freezeAfter=0.800` 1회·`freeze frame=5` 1회. **몬스터 공격 5종 순환**: 강제 공격 25회에서 parry.left·right·any·special.random·guard 5종 모두 나타남. build 오류 0, 제품 경고·오류 0(의도한 시험 경고 제외) | PASS(JUST 정상 창은 NOT_RUN, 정상 창 PARRY는 서버 타이머 논리 경로) |

**coder NOT_RUN 처리 결과**

| coder NOT_RUN 항목 | 이번 시도 | 결과 |
| --- | --- | --- |
| Pos2 패링·저스트 | 위 7번 | PARRY는 정상 창 논리 경로 PASS, JUST는 확대 창 시험 값 PASS, 정상 JUST 창은 NOT_RUN |
| 스파크·그로기 화면 | 시간 배율 0.15 스크린샷 | 요소 존재 확인(모양 판정 아님) |
| 팝업 일시정지 중 가드 | `_UIPopup:Open` + ↓ 키 | 정지 중 가드 시작·연출 0건, 취소로 재개 정상. 정지 중 입력이 막힌 원인(팝업 UI가 입력을 가림 vs 서버 정지 규칙)은 구분 못 함(O-5) |
| 터치+키 동시 입력 | 마우스 down + 키 down | PASS(위 4) |
| 열 누락 경고 줄 직접 실행 | `_CombatRuleCatalog.ReadRows`를 Play 안에서 교체해 `EnsurePlayerActionFx`가 `missing or required columns missing` 경고를 내게 하려 함 | **NOT_RUN** — 메서드 대입이 `An error occurred while assigning a value to variable <ReadRows>`로 거부됨(회차 D2 QA의 `OnUpdate` 대입 거부와 같은 제한). 제품 CSV를 바꾸지 않는다는 조건이라 실제 열 누락 표는 만들 수 없음. 대신 `ReadRows(MonsterSoundData, …)`·`ReadRows(nil, …)`·`ReadRows(PlayerActionFxData, …+NoSuchColumn)`이 nil이 되는 것과 소스 읽기(`EnsurePlayerActionFx`: nil이면 `WarnOnce("PlayerActionFxData missing or required columns missing")` 후 return)로 판단. 이건 코드 리뷰·논리 경로이지 런타임 줄 증거가 아니다 |
| 모바일·실기기 터치 | 시도 불가(Maker 마우스 시뮬레이터만 있음) | NOT_RUN |

**.ui 비교 (요청 범위 5)**
- 방법: UIBuilder.load로 3e29a35 작업 트리의 `ui/CombatScreen.ui`와 `git show de6e6aa:ui/CombatScreen.ui`를 읽어(`build()` 결과의 `ContentProto.Entities`) 엔티티 id 기준으로 필드·컴포넌트 단위 깊은 비교를 했다. **de6e6aa 판과 비교 가능했다.**
- 결과: 엔티티 19 → 23개. 삭제 0, 추가 4(`BtnAttack/Icon` c208d754…·`BtnGuard/Icon` 4a770505…·`BtnBack/Icon` 8f4dd28a…·`BtnForward/Icon` 2f1c31a3…). 기존 19개 중 변경 7개뿐: 버튼 4개의 SpriteGUIRenderer `ImageRUID.DataId`(fa75318d/b5c63f01/9eff8b12/83feab30 → e314c09b…)와 `Type` 0→1, Highlight 3개의 `displayOrder` 0→1. 나머지 12개 엔티티의 노드·컴포넌트·UUID·값은 차이 없음(ButtonComponent·Transform·색·바인딩 대상 포함). +3995/-3415줄은 재직렬화 형식 차이로 보이며 줄 단위 diff는 셸 가드로 볼 수 없어 보지 않았다. 한계: UIBuilder의 `build()`가 정규화한 값을 비교한 것이라 빌더가 읽을 때 흡수하는 필드는 구분하지 못한다.

**관찰 (판정에 쓰지 않음, reviewer·사용자 참고)**
- **O-1 무기 없는 계정의 모습 같음**: ATTACK(`attack`)도 `core=alert`로 재생돼 공격과 가드가 같아 보인다(↑ 입력 때 Body `ActionStateChangedEvent core=alert`, ↓ 때도 `core=alert`). coder 관찰과 같다. 규칙 변경 없음. V11 항목.
- **O-2 경고 문구 공유**: 형식 오류 5종(대문자·31자·공백·비16진수·소리 칸 오류)은 모두 한 문구 `PlayerActionFxData invalid ruid`라 표 로드 시 경고가 하나로 합쳐진다. Plan §24.7-3의 "원인당 1회"를 문구 단위로 읽으면 충족, 어느 칸·어느 값인지는 경고에 없다.
- **O-3 이펙트 첫 프레임**: 정상 속도에서는 가드 시작의 첫 프레임이 가는 흰 세로선이고 금색 방패는 그 뒤에 나타난다(시간 배율 0.03에서 확인). 방패는 플레이어 오른쪽에서 몸과 일부 겹쳐 보인다. 모양·위치·방향(좌우 반전 필요 여부)은 V11.
- **O-4 이벤트 위치**: `ActionStateChangedEvent`는 플레이어 엔티티가 아니라 `AvatarRoot/Body` 자식에서만 온다(프로브 요령, 제품 이슈 아님).
- **O-5 정지 중 입력**: 팝업 정지 중 ↓ 키가 서버에 도달했는지는 알 수 없다(도달했어도 정지 규칙이 막았는지, 팝업 UI가 입력을 막았는지 구분 못 함). 결과(가드 시작·연출 0건, 재개 뒤 IDLE)만 확인.
- **O-6 Plan 표현**: §24.7-2의 "패턴 4행"은 낡았다(de6e6aa 기준 5행, coder도 지적).
- 시험 오류(제품 오류 아님): ① 첫 클라이언트 프로브가 `StateChangeEvent`의 속성 이름(`CurrentStateName`)을 틀려 `nil`을 찍었다(다시 연결). ② `_CombatRuleCatalog.ReadRows` 대입이 거부돼 `[LEA]` 아닌 일반 Error 1건. ③ 팝업 시험의 `CombatPauseComponent` 조회가 nil이라 `[LEA-2007] AttemptToIndex 'cp'` Error 2건(내 프로브의 조회 경로 오류, 정지 자체는 [VRF] 로그로 확인). ④ J 시험에서 `patterns` 복원용 사본을 만들지 않아 카탈로그 재초기화로 복원(결과 동일 확인). 로그 Warning 8건 중 4건은 시험 전 coder 세션(15:53)에서 남은 것이고 4건은 내 오류 시험의 의도한 경고(`invalid ruid`·`duplicate id`·`invalid id`·`row missing: guard`)다. 제품 Warning·Error 0.

#### NOT_RUN (PASS로 세지 않음)
1. 버튼 모양·아이콘·눌림·Highlight와의 어울림, 흰 아이콘 가독성, alert 모습·무기 있는 계정의 구분, 이펙트 크기·위치·방향, 소리 청취, 스파크·그로기의 모양: 사용자 V11(§24.8).
2. 모바일·실기기 터치, 실접속, 다중 접속.
3. JUST의 정상 0.2초 창을 사람 손으로 맞추는 시험(확대 창 시험 값만).
4. 필수 열 누락 때 `EnsurePlayerActionFx`가 내는 경고 줄의 런타임 실행(메서드 교체 제한 + CSV 무수정 조건).
5. 팝업 정지 중 입력이 막히는 원인 분리.
6. 커밋 트리(`git ls-tree`/`show`)를 직접 해시 계산한 Bundle 대조.
7. `.ui` 줄 단위 diff(셸 가드로 읽을 수 없음).

#### 사용자 V11 직접 확인 항목 (§24.8 그대로)
- 버튼 모양·아이콘 메이플 분위기, 눌림 표시, 모바일 터치, 노란 Highlight와의 어울림, ↓ 아이콘이 ← → ↑와 어울리는지, 흰 아이콘 가독성.
- 가드 모습(alert와 대기 stand 구분, 무기 없는 계정에서 공격 모습과 구분 — O-1), 이펙트 크기·위치·방향(첫 프레임 가는 선, 오른쪽 위 방패 — O-3), 소리 크기, 팝업 정지 중 모습.
- (선택) `PlayerActionFxData.csv` guard 행 칸을 비워 그 연출만 끄기(CSV 수정 → Refresh → Play).

#### 재현 방법
1. 시작: 58경로 Bundle 계산(node 스크립트), `git status`, map01 해시, `maker_get_current_map` edit, build 로그 93건 Info 확인, UIBuilder 읽기 비교(`git show de6e6aa:ui/CombatScreen.ui`를 임시 파일로 저장해 로드) → Play.
2. 정상 경로: 서버 프로브로 몬스터 AttackInterval 9999·HP 100 → 실제 키·마우스로 ←·→·↑·↓ 각각 → `[VRF` 로그 집계. 이펙트 표시는 클라이언트 `_UtilLogic:SetClientTimeScale(0.03)` + 서버 `SetGuarding(false→true)` + 약 3초 뒤 스크린샷 → 배율 1로 복원.
3. 오류 경로: 서버 프로브로 `_CombatRuleCatalog.playerActionFx`·`fxReady`를 사례별로 바꾸고 `PlayerGuardComponent:SetGuarding(false→true→true→false)`, `ValidatePlayerFxRows`·`ReadRows`는 가짜 행으로 직접 호출. 복원은 `_T.fxAttempted = nil` + `EnsurePlayerActionFx()`.
4. 판정 회귀: 서버 타이머 루프(3.4초 간격 24회)로 `StateComponent:ChangeState("ATTACK")` 강제, 1~8회는 `fxReady=false` + GUARD 상태, 9~16회 정상 + GUARD, 17~24회 정상 + IDLE. PARRY는 `patterns["mushmom"]`을 parry.any 한 행으로 바꾸고 공격 +0.38초에 `ChangeState("GUARD")`. JUST는 `rules["default"].JustWindowSec = 30` + 실제 ← 탭 뒤 공격. 팝업은 `_UIPopup:Open`.
5. 정리: 시험 값 복원(카탈로그 재초기화, 배율 1), Stop, 편집 모드 확인, 58경로·59경로 Bundle과 map01 해시 재계산.

#### reviewer가 알아야 할 근거의 한계
- 오류 시험은 CSV를 건드리지 않고 Play 메모리의 캐시·검증 함수 호출로 했다. 필수 열 누락의 경고 줄은 런타임에서 직접 내지 못했다(NOT_RUN 4).
- PlayEffect 호출 자체는 서버 로그로 셀 수 없어, 이펙트 "1회"는 `[VRF] guard fx effect=…` 줄(같은 분기에서 PlayEffect 호출 직전에 찍힘)과 화면 확인(방패 표시 1개)로 판단했다.
- PARRY 정상 창은 서버 타이머가 `ChangeState("GUARD")`를 부르는 논리 경로이고 입력 경로가 아니다. 실제 입력의 JUST/PARRY는 확대 창 또는 미실시다.
- 팝업 정지 시험은 `_UIPopup:Open`으로 열었고 실제 메뉴 버튼(엔진 UI)은 마우스 시뮬레이터가 누르지 못했다.
- 키보드 입력의 지연(1초 이상 불규칙) 때문에 정상 길이의 타이밍 입력 시험은 하지 못했다. 스크린샷은 입력 좌표 확인 1장과 이펙트·패링 화면 확인 목적을 합해 10장 남짓 찍었다(§24.7-4는 좌표용만 허용, 이펙트 표시 확인 용도는 coder와 같은 이유).
- UI 비교는 `build()` 정규화 값 기준이며, 새 `.ui`를 Maker가 다시 저장한 흔적은 map01 해시·git status에 나타나지 않았다.
- 사용 종료: 마지막 maker_stop 성공 뒤 map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 시험 전·후 58경로 Bundle `1d70bc71…75dd`·map01 해시 `3e60c21d…2094` 동일, 제품 파일 무수정, commit·push 하지 않음.

### 2026-11-16 독립 QA 14회차 — 회차 D2(대상 e710907)
- 상태: **실행 완료.** 실행 기준 전부 PASS, FAIL·NEEDS_DECISION·새 결함 없음. 관찰 3건(아래 O-1~O-3)과 NOT_RUN은 PASS로 세지 않았다. 독립 reviewer 재검토 대기.
- 담당: Claude Code msw-tester(coder·앞 QA와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push·run.md·Plan 수정 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았다. 바꾼 파일은 이 QA 절뿐이다.
- 대상 버전: 로컬 커밋 **e710907**(원격 HEAD 7cbf14e, push 전). D2 = 1b41f29(MM-13·MM-15, 패턴 CSV) + e710907(MM-14 2차, OrangeMushroomAttack.mlua). 7cbf14e 제품(8428a05) 대비 제품 경로 변경은 `MonsterAttackPatternData.csv`·`OrangeMushroomAttack.mlua` 2개뿐이다(`git diff 8428a05 e710907 --name-only`, 모델·맵·UI 변경 0). 1b41f29 대비 OrangeMushroomAttack 변경: 속성 2개, BeginWindup 인자 1개와 곡선 선택 고정, 새 메서드 EqualizeLeapBounds, OnUpdate x 곡선 분기, `[VRF]`. `JumpToLocalX`는 `self._T.easeActive = false` 1줄만 추가됐고 `PerformReturnMotion` 변경 0이다(diff를 직접 읽음).
- **Bundle 57경로 SHA-256 `1e468c15dc603e46efe778637a3377e15779554c8bcb55e54f379d14d2f21bc4`: 시작 전 계산 일치(57/57), 시험을 마친 Stop 뒤에도 같다.** 계산 방식은 coder 절과 같다(경로 바이트순, `경로 TAB 파일 sha256 LF`, 확장자 9종, Global·RootDesk·map·ui, 경로 정렬은 UTF-8 바이트). 시작 때 `git status`는 `M skills-lock.json` 하나뿐(범위 밖, 건드리지 않음)이었으므로 제품 파일은 커밋 e710907과 같다. 끝 때 `git status --short`는 비어 있었다(skills-lock.json 변경이 사라진 것은 내 작업이 아니다). 커밋 트리를 따로 해시 계산하지는 않았다.
- 환경: Maker map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit로 시작(worldId 970621b29ba945369d3dc8e90c301186 확인). build 로그(편집 모드·Play 중) 93건 전부 Info(LIA 노이즈), 오류 0 — 앞 회차와 같은 건수. Play 2회(첫 Play는 프로브 환경 확인, 본시험은 둘째 Play 09:25~09:43). `maker_clear_logs` **호출 0회.** 시작 때 normal 로그가 이미 2648건·약 1.65M자(coder 세션 로그)였고 끝 때 4770건·약 3.16M자였으며 기록은 끊기지 않았다(포화 없음). 이 도구는 큰 로그를 파일로 저장해 `[VRF]`·`[T16]`·`[X*]` 줄을 스크립트로 걸러 읽었다. 마지막 `maker_stop` 성공 뒤 `maker_get_current_map` = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, Stop 뒤 LEA-3051 없음.
- 방법: **(A) 서버 프로브**(`maker_execute_script` server_main): 23+12+14개 사례를 한 사례씩 이어서 실행. 시험 값은 모두 Play 안 메모리에서만 바꿨다(`_CombatRuleCatalog.patterns["mushmom"]`을 한 행 복제본으로 교체, `EqualizeLeapFrames`·`EaseLeapMove`·`LeapJumpHeight`, 몬스터 `AttackInterval` 9999, 플레이어 HP, `ApplySlow`, 긴 시험 행). 사례마다 서버 샘플(약 35ms 간격: 서버 시계·액션 시계·x·y·구간·JumpActive·프레임 범위·PlayRate)을 모아 사례가 끝난 뒤 로그로 냈다. **(C) 클라이언트 프로브**(context client): 몬스터 `SpriteAnimPlayerChangeFrameEvent`와 클라이언트 WorldPosition·프레임 범위를 약 35ms 간격(timer 16ms 요청, 실제 약 2프레임)으로 기록. 두 쪽 모두 `ServerElapsedSeconds` 시계. **(B) 실제 키 입력**(`maker_keyboard_input`): UpArrow 탭·DownArrow 유지.
- 프로브 한계(중요): `maker_keyboard_input`은 호출에서 실제 키 입력까지 지연이 1~13초 불규칙해(windup 첫 탭 4초, 접근 탭 8초 이상 늦음) 정상 길이(1.57초) 안에서 구간을 맞출 수 없다. 그래서 B 항목은 **긴 시험 행**(TelegraphLeadSec 24~80, MotionPlayRate 0.04~0.05)과 `OrangeMushroomAttack.JumpDuration` 2~8(복귀 길이)을 Play 안에서만 써서 구간을 길게 늘렸다. 이 값들은 Stop과 사례 끝 복원으로 정리했다(복원 값 확인: patterns 원본, ParryWindowSec 0.2, JumpDuration 0.5).

**기준별 결과 (Plan 22.17.7 + 22.17.10.6)**

| 기준 | 방식 | 이번 독립 실행 결과 | 판정 |
| --- | --- | --- | --- |
| 22.17.7-1 빌드·로드 | 편집 모드 build 로그, Play 부팅 `[VRF]` | build 93건 Info·오류 0. 로드: `pattern row parry.left/right/guard clip=attack1/attack1/skill1 rate=0.7 jumpFrame=1 lead=1.57143`, `parry.any/special.random rate=1 jumpFrame=0 lead=0.5 sound=35ee15e5`, 비율 20/20/25/15/20%, `MonsterSoundData id=mushmom` 1행, MonsterStatData default·mushmom, 스폰 성공·경고 0 | PASS |
| 22.17.7-2 MM-13 시각(슬로우 없음) | A + C, 2칸 좌·우·3칸 | 아래 조합표. W(`frame set 1`) 1.143~1.159(기대 1.142857 ±0.05), 서버 f4 쓰기 = 판정 = 먼지 호출 1.572~1.589(기대 1.571429 ±0.05, f4 쓰기↔판정 차 −0.001~0), 클라이언트 f1 시작 W+0.005~+0.047(최대 +0.047, 한도 0.05 안 경계), 렌더러·이펙트 PlayRate 0.7. 3칸 이펙트: 1단계 `effect windup` x 3.000(머쉬맘 위치)·y 0.581·프레임 0-6·playRate 0.7·호출 시각 공격 시작 +0.000~0.001, 2단계 `effect dust` x 0.000(Pos2)·프레임 8-end·playRate 0.7·호출 시각 판정과 같음(10회). 착지 x: 2칸 좌 0.750·우 −0.750(영역 중앙), 3칸 0.000 전 사례 일치. 접근 전체 슬로우 시험(사례 18·22·23): 시각 2배, PlayRate 0.35 | PASS |
| 22.17.7-3 MM-13 스폰 | A, `MonsterManager:DoSpawn()` | 현재 CSV로 스폰 성공·경고 0. 시험 행(Play 안 메모리)에서 parry.left TelegraphLeadSec 1.1 + MotionPlayRate 0.7(W 1.143 ≥ 1.1): `[VRF] spawn refused reason=windup not shorter than telegraph row=parry.left windup=1.143` + Warning **정확히 1회**(`[CombatRuleCatalog] windup not shorter than telegraph: mushmom parry.left`), 현재 몬스터 유지(`sameMonster=true`). 원본 복원 뒤 `DoSpawn` 성공, 새 몬스터로 교체(이전 몬스터 파괴) | PASS |
| 22.17.7-5 D-Q6 유지 = T8 | A + C | 아래 T8 | PASS |
| 22.17.7-6 MM-15 공격음 | A `[VRF]` + 카탈로그 함수 | parry.any·special.random 강제 실행 7회(사례 15·16·17·107~110)마다 `[VRF] sfx kind=attack ruid=35ee15e5` **정확히 1줄**, `telegraph` → `sfx` → `clip set key=jump`가 같은 `OnEnter` 호출 안의 인접 줄(같은 틱). 2칸 `f135fc39`·3칸 `5da7bb48` 공격음은 모든 2·3칸 실행에서 1줄씩 회귀 없음. 후보 2개: Play 안에서 `_CombatRuleCatalog:ParseOptionalRuid`에 넣음 — 기본값 `35ee15e5…`, 후보 `64c83d14…`·`09df8556…` 모두 원문 반환, 8자 줄임·비16진수는 nil, 빈 값은 빈 문자열. **소리 자체는 미청취** | PASS(청취는 NOT_RUN) |
| 22.17.7-7 회귀: 1칸 | A | 사례 15·16·17·107~110: 접근 jump → stand 0.502~0.516초, 복귀 jump → stand 0.500~0.517초, y 최대 +0.798~+0.800, 진행률 직선 편차 ≤0.004(시간 지연 맞춤 0.016~0.018), 착지 x 0.000(any 2회·special.random 3회) / +1.500(special.random 3회) — 무작위 칸이라 사례마다 다름, 복귀 x 3.0 | PASS |
| 22.17.7-7 회귀: windup 피격 | **B 실입력** | 긴 시험 행(lead 24 / rate 0.05): windup 중 UpArrow → `PlayerHitRule pass hit=1..10`, 몬스터 HP 100 → 90, 피격음 `sfx kind=damaged` 1줄. lead 80 시험(사례 X2)에서도 windup 끝 무렵 탭 → pass 10타 | PASS |
| 22.17.7-7 회귀: approach 차단 | **B 실입력** | lead 80 / rate 0.04 시험 행: approach 도중(`seg=approach x=2.88`) UpArrow → `PlayerHitRule fail rule=targetHittableSegment hit=1`, `hit=2`, HP 변화 없음 | PASS |
| 22.17.7-7 회귀: return 차단 | **B 실입력** | `JumpDuration` 8(Play 메모리)로 복귀를 8초로 늘린 시험: 복귀 시작(`clip set key=jump`) 뒤 UpArrow → `fail rule=targetHittableSegment hit=1..10` 10타 전부, HP 90 그대로 | PASS |
| 22.17.7-7 회귀: die F12 | **B 실입력** + A | Hp 2 + windup 중 UpArrow 1회: `sfx kind=damaged`·`sfx kind=die` 각 1줄, `MonsterDie start frames=6 total=1.100 freezeAfter=0.800`, +0.8초 `MonsterDie freeze frame=5`, 이후 3초 동안 `SpriteRUID ec90f0b6…`·프레임 5-5·PlayRate 1·`DEAD` 유지 | PASS |
| 22.17.7-7 회귀: 판정 결과 | **B 실입력** | **HIT**: 입력 없이 맞음 `defense kind=HIT rate=1`, HP 100 → 88(사례 X1, 자연 공격도 같음). **GUARD**: DownArrow `down` 유지 → `PlayerGuard start` → `PlayerHealth guard eval cellOk=true areaOk=true attr=PARRY` → `defense kind=GUARD rate=0.4`, HP 100 → 96, HUD `feedback=GUARD`, 먼지 이펙트 호출. **PARRY**: 정상 창 0.20초는 도구 지연 때문에 사람 손으로 맞출 수 없어 `_CombatRuleCatalog.rules["default"].ParryWindowSec`를 30으로 늘린 시험 값(Play 메모리, 사례 끝 복원 0.2)에서 DownArrow를 판정 24초 전에 눌러 유지 → `defense kind=PARRY rate=0`, HP 100 그대로, HUD `feedback=PARRY`, 복귀(2초) 뒤 `STUN`·`clip set key=hit`·`groggy applied`. JUST는 이번에 시험하지 않았다(요청 범위 밖) | PASS(PARRY는 창 확대 시험 값) |
| 22.17.7-7 회귀: 판정 전 취소 때 먼지 없음 | A(**논리 경로**: 프로브가 `ChangeState("IDLE")`) | 3칸 시험 행(lead 3.0 / rate 0.3): windup 1.007초에 취소 → `effect windup`만 있고 `effect dust` 0, approach 2.881초(x 1.091)에 취소 → `effect windup`만 있고 `effect dust` 0. 취소 뒤 상태 IDLE, 구간 none | PASS(입력 아님) |
| 22.17.7-7 회귀: 사운드 4종 | A `[VRF]` | `attack`(2칸 f135fc39·3칸 5da7bb48·1칸 35ee15e5), `hitplayer 7c8e5f1e`(HIT·GUARD 때 1줄씩), `damaged c611ae50`, `die d48ec1cc` 각 1줄 | PASS |
| 22.17.7-7 회귀: 소스 | `git diff` | 1b41f29 대비 JumpToLocalX 1줄, PerformReturnMotion 0 | PASS |

**조합표 (슬로우 없음, 서버 액션 시계 초, 클라이언트는 공격 시작 기준; 2칸 좌·우·3칸, 사례 번호는 본시험 순서)**

| 조합 (균등화, 곡선) | 사례 수(번호) | W(f1) | 서버 f2 / f3 | f4 쓰기 = 판정 | `leap bounds` f1 / f2 / f3 / f4 | 클라이언트 f1 / f2 / f3 시작 | 클라이언트 표시 f1 / f2 | 이동 비·정지 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| (켬, 켬) | 15(1~6, 111, 112, 201·203·205·207·209·211·213) | 1.144~1.159 | 1.287~1.301 / 1.430~1.447 | 1.573~1.588 | 1.142857 / 1.285714 / 1.428571 / 1.571429 | 1.148~1.190 / 1.294~1.314 / 1.435~1.466(높이 0.5 사례 13은 f3 1.476) | 0.119~0.157 / 0.121~0.170 | 이동 비 0.54~1.06(k 1.5), 정지 0~0.019 |
| (켬, 끔) | 2(7, 8) | 1.149~1.156 | 1.291~1.294 / 1.430~1.435 | 1.574~1.588 | 위와 같음 | 1.170~1.174 / 1.310~1.312 / 1.451 | 0.136~0.142 / 0.139~0.141 | 0.68~0.74(k 1), 0~0.017 |
| (끔, 켬) | 2(9, 10) | 1.143~1.146 | 1.436~1.442 / 1.506~1.511 | 1.575~1.579 | 1.142857 / 1.428571 / 1.500000 / 1.571429 | 1.162~1.165 / 1.457 / 1.524~1.525 | 0.292~0.295 / 0.067~0.068 | 1.03~1.05(k 1.5), 0.017~0.018 |
| (끔, 끔) | 15(11, 12, 101~106, 202·204·206·208·210·212·214) | 1.144~1.158 | 1.430~1.445 / 1.501~1.517 | 1.572~1.589(판정 최대 1.590) | (끔, 켬)과 같음 | 1.155~1.180 / 1.435~1.465 / 1.520~1.539 | 0.261~0.303 / 0.063~0.089 | 이동 비 0.68~0.74(k 1)**, 정지 0.017~0.019** |

(** 사례 102 한 번만 예외 — 아래 O-1.)

**T1~T11 (22.17.10.6, 대상 조합 포함)**

| # | 판정 | 근거 |
| --- | --- | --- |
| T1 시각 불변 | PASS (4조합) | 위 조합표. W·f4·판정·먼지 ±0.05 안. 착지 x 2칸 좌 0.750·우 −0.750·3칸 0.000(복귀 구간 시작 `jsx`로 읽은 값, 소수 4자리 일치). LeapJumpHeight 0 사례의 approach y 변화 0.0000, 높이 0.5 사례(13)의 착지 직후 첫 복귀 샘플 y 0.581 = Home.y |
| T2 프레임 경계 | PASS (4조합) | `leap bounds`가 표 값과 소수 6자리까지 일치(켬 1.285714·1.428571, 끔 1.428571·1.500000). 서버 `frame set` f2·f3은 기대 ±0.016 안. 클라이언트 f1·f2·f3 시작은 기대 +0.005~+0.047(최대 f1·f3 +0.047), 표시 시간은 켬 f1~f3 모두 0.119 이상(기준 0.071), 끔은 f2 0.063~0.089·f3 0.050 이상(B2 기준 0.035) |
| T3 프레임 순서 | PASS (4조합) | 순서 0→1→2→3→(stand 0), 건너뜀 0, 되돌림 0, 0.011초 넘는 같은 프레임 재도착 0. 프레임마다 같은 ms에 2건 도착은 비교 대상 전 사례에서 그대로 관찰됨(22.17.10.5 중복 묶음, 기록만 — O-3) |
| T4 위치 역행 | PASS (4조합) | 서버 역행 0(전 사례), 클라이언트 접근 구간 역행 0 |
| T5 곡선 모양 | PASS(주의 O-2) | OnUpdate와 같은 틱에 묶기는 불가: 서버 `ElapsedSeconds`는 프레임 고정이 아니라 연속 시계이고, `OrangeMushroomAttack.OnUpdate`를 프로브에서 감싸려는 시도(`m.OnUpdate = function…`)는 `An error occurred while assigning a value to variable <OnUpdate>`로 거부됐다. 대신 샘플마다 "x 진행률에서 거꾸로 푼 시각과 샘플 액션 시각의 차(implied lag)"를 구했다. 곡선 켬(smoothstep)·끔(직선) 모두 사례 안에서 lag이 0.0150~0.0190 사이 ±0.002로 일정하고(서버 틱 이내) 최적 지연 맞춤 후 진행률 편차는 켬 0.0019~0.0068, 끔 0.0025~0.0046. 편차 > 0.01 사례 3건(12: 0.0115, 102: 0.0104, 208: 0.0211)은 모두 샘플러 타이머 간격이 어긋난 한 샘플이 만든 값이다(O-2). LeapJumpHeight 0 y 변화 ±0.01 이내(전부 0.0000~0.0064) |
| T6 클라이언트 연속성 | PASS(주의 O-1) | 정지 최장 0~0.019초(기준 0.05, 곡선 켬 제외 0.1), 이동 비 켬 ≤1.06(k 1.5)·끔 ≤0.74(k 1), B4 착지 튐: 접근 종료 뒤 방향 전환 1회뿐, B5 windup 클라이언트 x 3.0000 고정·프레임 범위 0-0(f0만). 단 사례 102 한 건은 정지 0.09초·이동 비 2.18로 기준을 넘었다(재현 시험 14회에서 반복 안 됨) |
| T7 높이 관계 | PASS | LeapJumpHeight 0.5: 사례 13 (켬, 켬) 2칸 우: 서버 y 편차 0.004(지연 0.017), 서버 y 최대 +0.497, 클라이언트 꼭대기 +0.500(점프 시작 +0.247초, 기대 J/2 0.214에 클라 지연 +0.033). 사례 14 (켬, 끔) 2칸 좌: 편차 0.0087, 서버 +0.500, 클라 +0.500(+0.249초, +0.035). 착지 y Home.y, x는 T5와 같은 곡선 |
| T8 D-Q6 유지 | PASS | (켬, 켬) 5경우 + (끔, 끔) 1경우, 서버 실시간 기대 대비(슬로우 시작·끝을 `slow applied` 로그로 읽어 액션 시계를 거꾸로 푼 값): S1 2칸(0.4초 시작, 6초) f1 +0.001·f4 +0.007·판정 +0.007, 클라 f1 +0.020·착지 +0.043. S2 3칸(공격 전 시작한 1.0초가 windup 안에서 종료) f1 +0.015·f4 +0.007·판정 +0.008, 클라 +0.014·+0.007. S3a 2칸(approach 도중 1.2초에 0.3초) f1 +0.015·f4 +0.016, 클라 +0.019·+0.032. **S3 f2 안**(2칸 우, 슬로우 시작 1.334초·끝 1.434초 모두 균등화된 f2 구간 1.2857~1.4286 안) f1 +0.015·f4 +0.014, 클라 f2가 PlayRate 변경 시점 1.352·1.457초에 다시 도착(허용), 되돌림 0. S3b 3칸(0.95초 시작 6초) f1 +0.005·f4 0.000·판정 +0.018(서버 f4 쓰기↔판정 −0.018), 클라 +0.026·+0.022. **(끔, 끔) S1**(2칸 좌, 0.4초 6초) f1 +0.006·f4 +0.006, 클라 +0.031·+0.023. 클라이언트 프레임 되돌림 6경우 전부 0. 서버 렌더러 PlayRate = 0.7 × ActionRate(윈도우·approach 표본 불일치 0/75, 0/57, 0/45, 0/41, 0/59, 0/75), 착지 뒤 stand는 1 × ActionRate. 이펙트 PlayRate: 슬로우 중 시작한 눈빛 0.35·판정 때 슬로우 중이면 먼지 0.35 |
| T9 1칸·복귀 불변 | PASS | 위 22.17.7-7 1칸 행. (끔, 끔) parry.any(사례 17)도 같다. `easeUsed` 진행률 직선(편차 ≤0.004), JumpToLocalX·PerformReturnMotion diff는 위 대상 버전 절 |
| T10 기본값·로드 | PASS | 부팅 직후 프로브 읽기: `EqualizeLeapFrames`=true, `EaseLeapMove`=true, `LeapJumpHeight`=0.0, `[VRF] leap start … equalize=true ease=true`, 모델 파일 변경 0, build 오류 0 |
| T11 (끔, 끔) = 지금 | PASS | W 1.144~1.158(기준선 1.144~1.152에 틱 오차), f4 1.572~1.589(1.574~1.588), 클라 표시 f1 0.276~0.303·f2 0.063~0.089(기준선 0.273~0.297·0.068~0.088), 정지 ≤0.019(0.035), 이동 비 ≤0.74(기준선 절대량 2칸 0.184·3칸 0.245와 같은 값 0.7 × 거리 × 0.05 ÷ J), 착지 x 같음 |

**관찰 (판정에 쓰지 않음, reviewer·사용자 참고)**
- **O-1 클라이언트 접근 끊김 1건(사례 102, (끔, 끔) 우):** 클라이언트 x가 접근 중간에 0.09초 멈췄다가 한 번에 이동(이동 비 2.18). 같은 순간 서버 샘플러에도 간격 이상(0.042 → 0.028초)이 있었고 서버 위치는 역행·정지 없음. 같은 (끔, 끔) 나머지 14건(사례 11·12·101·103~106·202·204·206·208·210·212·214)에서는 정지 ≤0.019·이동 비 ≤0.74로 반복되지 않았고, 재현을 노려 추가한 사례 201~214(우측 2칸 (켬, 켬)·(끔, 끔) 교대 12회 + 3칸 2회)도 같았다. 원인 미확인(Maker 프레임 정지, 서버→클라이언트 위치 동기화 지연이 한 번에 몰린 경우 등이 후보). 사용자가 "뚝 끊김"을 다시 보면 이 같은 간헐적 현상일 수 있다. Maker 로컬 Play라 실제 접속 지연은 대변하지 못한다.
- **O-2 T5 편차 > 0.01 3건:** 모두 곡선 끔·(끔, 끔) 계열 또는 한 샘플이 늦게 찍힌 경우로, 샘플러 타이머 간격 이상(0.042초, 12·102) 또는 lag 0(208)이다. 이 표본을 빼면 편차 ≤0.0068이다. 제품 식 오류의 근거는 아니다.
- **O-3 프레임 이벤트 이중 도착:** 접근 구동 프레임(f1·f2·f3)과 착지 f0이 프레임마다 같은 ms에 2건 도착(전 사례, 22.17.10.5 기록 항목). 눈에 보이는 되돌림·깜박임 없음.
- 시험 오류(제품 오류 아님): 본시험 직전 첫 Play에서 반복 루프 20만 회짜리 프로브를 보냈으나 스크립트 실행이 느려(약 3천 회/초) 결과가 나오지 않았고 오류 로그도 없어 Stop → 재Play했다. PARRY 시험 첫 두 시도는 GUARD가 나왔다: ① `GetRules({})`가 복사본을 돌려줘 내 ParryWindowSec 변경이 판정에 닿지 않았고(`rules["default"]`를 직접 바꿔 해결), ② 이전 시험의 DownArrow 유지가 풀리지 않은 채 새 `down`을 보내 `PlayerGuard start`가 다시 안 찍혔다(`up` 뒤 새 `down`으로 해결). 세 번째 시도 PARRY. 몬스터를 교체(DoSpawn)한 뒤 내 클라이언트 프로브가 파괴된 개체의 `_T`를 읽어 `[LEA-2007] AttemptToIndex` Error 1건(09:32:19)을 냈다. 제품 Warning은 의도한 스폰 거부 1건뿐이고 제품 Error는 0이다.

#### NOT_RUN (PASS로 세지 않음)
1. 화면 체감("뚝 끊기는 느낌"이 줄었는지)·모션의 부드러움·이펙트 눈빛/먼지의 육안(방향·위치)·효과음 청취(1칸 점프음 3후보, 2·3칸 공격음): 사용자 V11.
2. 실접속(서버–클라이언트 네트워크 지연)의 위치 동기화·모바일·실기기·다중 접속.
3. PARRY의 정상 창(0.20초)을 사람 손으로 맞추는 시험, JUST 판정 결과, 접근 전에 정확히 맞춘 사람 손 타이밍.
4. 커밋 트리(`git ls-tree`/`show`)를 직접 해시 계산한 Bundle 대조(작업 트리 해시와 `git status` 깨끗함으로 대신함).
5. 곡선·균등화 속성을 Maker Inspector에서 바꾸는 사용자 절차와 모델 값 저장.
6. OnUpdate와 같은 틱에 서버 샘플을 정확히 묶는 시험(도구 한계, T5 참고).

#### 사용자 V11 직접 확인 항목
- 2칸 좌·우·3칸 접근에서 기본 (켬, 켬)이 "점프 중 뚝 끊기는 느낌"을 줄였는지, (끔, 끔)·(켬, 끔)·(끔, 켬)과 LeapJumpHeight 0 → 0.3 → 0.5 비교 후 고를 값(Plan 22.17.10.8).
- 위 O-1 같은 간헐적 멈춤이 보이는지.
- 1칸 점프음 후보 3개(35ee15e5…·64c83d14…·09df8556…) 청취 후 선택, 2·3칸 공격음과 겹쳐 들리는지.
- 반응 시간(약 1.57초)·제자리 반격 구간(약 1.14초) 난이도(22.17.8-1·4), 눈빛/먼지 이펙트 위치(22.8 V11).

#### 재현 방법
1. 시작: 57경로 Bundle 계산, `git status`·`git diff 8428a05 e710907 --name-only`·`git diff 1b41f29 e710907 -- OrangeMushroomAttack.mlua` 확인, map01 edit 확인, build 로그 확인, Play.
2. 조합 측정: 서버 프로브로 `_CombatRuleCatalog.patterns["mushmom"] = { 행 복제본 }`, `OrangeMushroomAttack`의 세 속성을 사례별로 바꾸고 몬스터 `MonsterStateControl.AttackInterval = 9999`, `StateComponent:ChangeState("ATTACK")`로 강제 실행. 슬로우는 사례 안에서 `ctl:ApplySlow(지속, 0.5)`를 액션 시각 기준으로 호출. 클라이언트 프로브는 몬스터 `SpriteAnimPlayerChangeFrameEvent`와 WorldPosition을 기록.
3. 실입력: 위 긴 시험 행으로 `maker_keyboard_input` UpArrow 탭(windup·approach·return 각각), DownArrow `down`(GUARD·PARRY)·`up`. PARRY는 `_CombatRuleCatalog.rules["default"].ParryWindowSec`를 Play 안에서 30으로 올려 시험하고 복원.
4. 스폰: `MonsterManager:DoSpawn()`을 시험 행 목록(parry.left lead 1.1·rate 0.7)과 원본 목록으로 각각 호출.
5. 정리: 프로브 중단 플래그, 원본 목록·ParryWindowSec·JumpDuration 복원, Stop, 편집 모드 확인.

#### reviewer가 알아야 할 근거의 한계
- 서버·클라이언트 샘플 간격이 약 35ms(2프레임)라 정지·이동 비 지표는 coder 기준선과 같은 해상도이며, 프레임 사이 순간의 끊김은 볼 수 없다.
- T5는 같은 틱에 묶지 못해 implied lag의 일정함으로 모양을 판정했다. 곡선 식 자체는 소스(`t*t*(3-2*t)`)와 샘플 일치로 확인했고 편차 > 0.01은 O-2의 샘플 이상이다.
- B 실입력 항목은 긴 시험 행과 JumpDuration 8(Play 메모리)로 구간을 늘렸다. 정상 길이의 입력 타이밍이 아니다.
- PARRY는 창 확대 시험 값이다. 판정 규칙(셀·영역·창 포함)과 결과 종류·HUD·그로기 경로가 동작함을 보였지만 0.20초 창 자체는 이 시험으로 증명하지 않았다.
- 취소 시 먼지 없음은 프로브가 상태를 바꾼 논리 경로다(플레이어 사망·맵 이탈 취소 경로는 시험하지 않음).
- 앞 QA13이 PASS였던 55경로 영역(DataSet 외 매니저·카탈로그·플레이어·상태)은 이 버전에서도 바이트가 같다(제품 변경 2경로 외 변경 없음). 이번 실행에서 다시 행사된 경로는 접근·windup·approach·return·이펙트 호출·사운드·die·슬로우·판정 결과·스폰 검증이다.
- 사용 종료: 마지막 maker_stop 성공(play_to_edit) 뒤 map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 시험 전·후 57/57 동일 Bundle(`1e468c15…1bc4`), 제품 파일 무수정, commit·push 하지 않음.

### 2026-11-10 독립 QA 13회차 — 회차 D REV-D-O1 수정(대상 8428a05)
- 제목 날짜 정정(planner, 2026-11-16): 원래 제목은 "2026-11-09"였다. 아래 환경 기록의 Play 시각(2026-11-10 20:18·20:22)과 대상 커밋 8428a05(2026-11-10 20:16)에 맞춰 2026-11-10으로 고쳤다. 본문은 그대로다.
- 상태: **실행 완료.** 실행 기준 PASS, FAIL·NEEDS_DECISION·새 결함 없음. 독립 reviewer 재검토 대기. NOT_RUN은 아래 절.
- 담당: Claude Code msw-tester(coder·앞 QA12와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push·run.md 수정 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았다.
- 대상 버전: coder 로컬 커밋 **8428a05**, 57경로 Bundle SHA-256 **`8d5b6d1c029d1eefad8e6ac2a878ec55facf069aab23d77c96a6fa3465f04eed`**. QA12와 같은 manifest 방식으로 **커밋 트리(git ls-tree·show)와 작업 트리 양쪽에서 시작 때 계산해 일치**(57/57), 시험 뒤(Play 2회·Stop 뒤)에도 같다. `git diff a5efe69 8428a05`의 제품 경로는 **`Monster/@StateControl/Monster_Attack.mlua`·`Monster/OrangeMushroom/OrangeMushroomAttack.mlua` 2개뿐**(나머지는 run.md·WorkRecord 문서)이고, diff를 직접 읽어 coder 기재(BeginWindup이 `leadSec`를 그대로 돌려줌, 불가능 조합·JumpDuration 경고 3종 추가, 일시 상태는 경고 제외)와 같음을 확인했다. 나머지 55경로는 QA12 대상 a5efe69와 같은 바이트다.
- 환경: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit로 시작. Play 2회(본시험 20:18, 기본값 확인 20:22)와 마지막 Stop 뒤 map01 / edit 확인.
- D-Q7 로그 정리(이번 회차 한정): 시작 때 기존 normal 로그 **247건, 2026-11-10 20:14:06~20:15:54**(앞 coder 세션 시험 로그, `[VRF D]` 프로브와 coder가 낸 경고 2건 `[CombatRuleCatalog] attack cancelled …`)의 건수·범위만 기록하고 `maker_clear_logs` **1회**(clearedCount 247). 그 뒤 지우지 않았다. 끝났을 때 버퍼는 785건·약 386k자로 가득 차지 않았다.
- 방법 구분: (A) 서버 프로브(maker_execute_script server_main, 클라이언트 프레임 이벤트는 context client). (B) **실제 키 입력**(maker_keyboard_input UpArrow 탭). 시험값은 모두 Play 안 메모리에서만 바꿨다: 패턴 목록을 한 행 복제본으로 교체하고 그 행의 TelegraphLeadSec·MotionPlayRate 변경, 몬스터 AttackInterval 9999, OrangeMushroomAttack.JumpDuration 0·-1, 기준 위치 플래그 false, 슬로우, 플레이어 SkillAttackCount 2, 몬스터 Hp 2. CSV·모델·코드 파일은 변경 0. Stop 뒤 새 Play의 `[T12] FRESH2 just=0.2 parry=0.2 interval=3 jumpDur=0.5 count=10 patterns=5 hp=100 warnedKeys=false`로 기본값 복구와 부팅 때 경고 없음을 확인했다.

| 기준 | 방식 | 이번 독립 실행 결과 | 판정 |
| --- | --- | --- | --- |
| 빌드·로드 | 편집 모드 build 로그, Play 부팅 | build 로그 93건 전부 Info(LIA), 오류·경고 0(coder와 같은 건수). 부팅 로드 [VRF] `patterns=5`, 비율 20/20/25/15/20%, 부팅 중 `[CombatRuleCatalog]` 경고 0 | PASS |
| 1 REV-D-O1 재현 조합과 다른 조합 | A + 클라이언트 프레임 이벤트 | 아래 표 12행. **12행 모두 공격이 취소되지 않고** `defense`(판정)에 도달해 stand·복귀까지 정상 종료. 경고 로그 0건. W(`leap start` 시계 − `clip driven` 시계)는 기대 0.8 ÷ MotionPlayRate와 최대 0.019초 차이, 판정(`defense` 시계)은 TelegraphLeadSec와 최대 0.015초 차이(둘 다 ±0.05 안, 샘플 틱 0.017초). 클라이언트 f0→f1 간격은 서버 W와 최대 0.021초 차이, 프레임 번호는 모두 단조 증가(고속 행에서 f3 생략은 있어도 되돌림 없음) | PASS |
| 2 진짜 불가능 조합 | A | 취소 + 경고 정확히 1회(같은 조합을 반복해도 추가 줄 없음, 아래 표 2). 경고 총 6건 = 서로 다른 원인 6가지 | PASS |
| 2 일시 상태 | A | 기준 위치 미확보(HomeCaptured false) 상태에서 시작한 2칸 공격은 경고 없이 취소되고 기준 위치는 곧바로 다시 잡힘(`homeCaptured=true`). 정지 상태에서 ATTACK 전환 시도는 상태 IDLE 유지(FSM 정지), `attack cancelled` 경고 없음 | PASS (아래 한계 참고) |
| 3 회귀 — 현재 CSV 2·3칸·1칸 | A + 클라이언트 | RG(parry.guard): W 0.810·f4 1.106·먼지 호출 1.106(`effect dust`, x 0.000 Pos2)·판정 1.106, 클라이언트 0→1→2→3. RL(parry.left): W 0.816·판정 1.116. RA(parry.any 1칸): 시작과 동시에 approach(0.017~0.510초)·y +0.8·판정 후 return. windup x 3.000(변화 0)·JumpActive F, approach y 변화 0 | PASS |
| 3 회귀 — D-Q6 슬로우 | A + 클라이언트 | G-S1(windup 0.4초에 시작·2.0초): W 1.203(기대 1.2), 판정 1.815(기대 1.8), 클라이언트 f0→f1 1.198, 프레임 0→1→2→3. L-S3(approach 0.95초에 시작): W 0.815, 판정 1.253, 클라이언트 f0→f1 0.811, 0→1→2→3. G-S2(windup 도중 종료): W 1.104, 판정 1.418, f0→f1 1.092, 0→1→2→3. 세 경우 f0 재시작 없음, 슬로우 종료 뒤 PlayRate 1 복귀 | PASS |
| 3 회귀 — 제자리 피격·approach 차단 | **B 실입력** | 늦춘 시험 행(TelegraphLeadSec 12·MotionPlayRate 0.1, W 8.008·판정 12.018): windup 중 UpArrow → `pass hit=1,2`, 6초 시점 `seg=windup` Hp 100→98, damaged 음 1줄. approach 중(약 11초) UpArrow → `fail rule=targetHittableSegment hit=1,2`, 10.5초 시점 `seg=approach hp=98` 그대로 | PASS |
| 3 회귀 — die F12·사운드 | **B 실입력** + A | Hp 2 + UpArrow 1회(2타): damaged 음 1줄, die 음 1줄, `MonsterDie start` 1회, +0.804초 `freeze frame=5`, +2.5초·+6초 ruid ec90f0b6·범위 5-5·DEAD·PlayRate 1. 공격음: 2칸 f135fc39, 3칸 5da7bb48(모든 실행에서 [VRF] 확인) | PASS |
| 3 회귀 — 이펙트 2분할 호출 | A [VRF] | RG·G-S1·G-S2·O 시리즈의 parry.guard: `effect windup` x 3.000(머쉬맘 위치)·프레임 0-6, `effect dust` x 0.000(Pos2)·프레임 8-end·호출 시각 = 판정 시계. PlayRate = 행 MotionPlayRate × ActionRate(O2·O12 시험 행 2.5·4.0 그대로, G-S1 먼지 0.5) | PASS |

**표 1 — 조합별 결과(시계 단위 초, 슬로우 없음, 시작 = `clip driven` 시계 0)**

| 행 | 패턴 | lead | MotionPlayRate | W 측정(기대) | f4 서버 쓰기 | 판정 측정(기대 = lead) | 비고 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| O1 | parry.left | 0.9 | 2.5 | 0.322(0.320) | 0.443 | 0.911(0.900) | **REV-D-O1 재현 조합**, W < lead/2 |
| O2 | parry.guard | 0.9 | 2.5 | 0.325(0.320) | 0.447 | 0.909(0.900) | 3칸, 먼지 호출 0.909 |
| O3 | parry.right | 0.7 | 3.0 | 0.272(0.267) | 0.376 | 0.707(0.700) | 정렬식 이탈, W < lead/2 |
| O4 | parry.left | 2.0 | 1.5 | 0.552(0.533) | 0.742 | 2.014(2.000) | 정렬식 이탈, W < lead/2 |
| O5 | parry.guard | 0.55 | 2.0 | 0.412(0.400) | 0.564 | 0.565(0.550) | 정렬식 1.1 ÷ lead |
| O6 | parry.left | 0.95 | 1.1579 | 0.700(0.691) | 0.960 | 0.961(0.950) | 정렬식 |
| O7 | parry.right | 0.45 | 4.0 | 0.205(0.200) | 0.292 | 0.464(0.450) | W < lead/2 |
| O8 | parry.guard | 3.3 | 5.0 | 0.173(0.160) | 0.225 | 3.312(3.300) | W ≪ lead/2, 먼지 3.312 |
| O9 | parry.any(1칸) | 0.6 | (jump 1프레임) | approach 0.017~0.499 | - | 판정 후 return(0.638~) | 접근이 lead보다 짧은 1칸, 대기 뒤 판정 |
| O10 | special.random(1칸) | 0.5 | 2.0 | approach 0.018~0.498(PlayRate 2) | - | 판정 0.5, 취소 없음 | JumpDuration 0.5 = lead 경계 |
| O11 | parry.left | 0.7 | 1.5714 | 0.516(0.509) | 0.707 | 0.706(0.700) | 정렬식 |
| O12 | parry.guard | 0.4 | 4.0 | 0.204(0.200) | 0.290 | 0.410(0.400) | W ≈ lead/2 경계, 먼지 0.410 |
- 정렬식(1.1 ÷ lead)을 따르는 O5·O6·O11은 f4 서버 쓰기와 판정이 같은 틱(차이 0.001 이내)이다. 정렬식에서 벗어난 O1~O4·O7·O8·O12는 취소 없이 W·판정은 맞고 클립 f4 자세만 판정과 어긋난다(Plan 22.16.3 안내대로, 예: O1 f4 0.443 vs 판정 0.911).

**표 2 — 불가능 조합(모두 이번 독립 실행, 로그의 `[CombatRuleCatalog]` 경고)**

| 행 | 조합 | 결과 | 경고 |
| --- | --- | --- | --- |
| X1 | parry.left lead 0.7·rate 0.5(W 1.6 ≥ 0.7) | 취소(IDLE, 이동 없음) | `attack cancelled: windup 1.600 is not shorter than telegraph 0.700 (clip attack1, JumpStartFrame 1)` **1회** |
| X2 | X1 반복 | 취소 | 추가 경고 **0** |
| X3 | parry.guard lead 0.8·rate 1.0(W 0.800 = lead 경계) | 취소 | `windup 0.800 is not shorter than telegraph 0.800 (clip skill1 …)` **1회** |
| X4 | parry.any lead 0.4(JumpDuration 0.5 > 0.4) | 취소 | `approach 0.500 exceeds telegraph 0.400 (parry.any)` **1회** |
| X5 | X4 반복 | 취소 | 추가 0 |
| X6 | special.random lead 0.3 | 취소 | `approach 0.500 exceeds telegraph 0.300 (special.random)` **1회** |
| X7 | parry.any, JumpDuration 0 | 취소 | `invalid JumpDuration 0.0` **1회** |
| X8 | parry.left(2칸), JumpDuration 0 | 취소 | 같은 문구라 추가 0 |
| X9 | parry.any, JumpDuration -1 | 취소 | `invalid JumpDuration -1.0` **1회** |
| X10 | HomeCaptured false로 parry.left | 취소, 기준 위치 재확보 | **0**(일시 상태) |
| X11 | 정지 상태에서 ATTACK 전환 시도 | 상태 IDLE 유지, 정지는 다음 틱에 소유자 확인으로 해제(`abort notify=false`, 기존 동작) | `attack cancelled` 경고 **0** |
| X12 | X 시험 뒤 CSV 값 parry.left | 정상 실행(판정 1.107, hit 88) | 0 |
- 경고 총 6건(Warning 로그 전체), Error 0. 복원 확인: JumpDuration 0.5, 기준 위치 true.

#### 관찰·시험 오류 분리 (제품 오류 아님)
- **수정 전 버전(a5efe69)에서 REV-D-O1 재현은 이번에 하지 않았다.** 이번 시험은 8428a05에서 같은 조합이 취소되지 않음을 보인 것이다(NOT_RUN: 수정 전 실패 재현). 수정 전 동작은 reviewer 소스 분석과 coder 기재를 따른다.
- 샘플러는 ATTACK을 한 번도 못 보면 4초 대신 지정한 maxSec 뒤 `TIMEOUT-never-ATTACK`으로 종료하게 했다. 취소 시험 X1~X10의 이 표시는 의도한 결과다.
- 클라이언트 프레임 이벤트는 프레임당 두 번씩 같은 시각에 온다(내 훅은 한 번 연결, QA12와 같은 현상, 판정 영향 없음). 서버 샘플러 시각 해상도는 약 ±0.02초이고 W·판정은 제품 [VRF] 전투 시계 값의 차이다.
- 시험 개체·타이머: Warning 6건은 모두 위 표 2의 의도한 경고. Play 종료 때 LEA-3051 없음(내 클라이언트 반복 타이머는 종료 전 ClearTimer, 서버 반복 타이머는 샘플러가 스스로 정리).
- maker_logs 직접 읽기에서 build 로그를 한 번 인라인으로 읽어 컨텍스트를 많이 썼을 뿐 시험 결과와 무관하다.

#### NOT_RUN (PASS로 세지 않음)
1. 수정 전(a5efe69)에서 TelegraphLeadSec 0.9 + MotionPlayRate 2.5의 조용한 취소 재현.
2. `IsMotionReady`의 `pause.IsPaused` 분기 자체(PrepareAttack이 정지 중 먼저 nil을 돌려 접근할 수 없는 경로라 X11은 FSM 정지 확인만 했다).
3. QA12에서 PASS이고 이번 버전에서 바이트 동일한 55경로 영역(DataSet·Catalog·MonsterManager·MonsterAttackMotion·MonsterAttackComponent·MonsterHealth·MonsterStateControl·PlayerCombat 등)의 전수 재시험: GUARD·PARRY·JUST 판정, SelectPattern 분포(21,000+20,000×2), Weight·검증 실패 프로브, 재스폰 개체 다프레임, 팝업 정지, 스크린샷 이펙트 위치 — **QA12 근거, 이번 버전 동일 바이트**(`git diff` 제품 경로 2개 외 변경 없음). 이번 버전의 2파일이 닿는 경로(접근·windup·approach·return·이펙트 호출·사운드·die·슬로우)는 위 표에서 다시 실행했다.
4. 사람 손 타이밍, 모바일·실기기·다중 접속, 사용자 V11(효과음 청취·모션 체감·이펙트 육안·속도 조절 항목).

#### 사용자 V11 직접 확인 항목
- QA12 절 "사용자 V11 직접 확인 항목"과 같다. 이번 수정은 사용자가 CSV에서 TelegraphLeadSec·MotionPlayRate를 정렬식 밖(예: lead 0.9 + rate 2.5)으로 바꿔도 공격이 조용히 사라지지 않고, 진짜 불가능한 값에서는 Maker 로그에 원인 경고가 한 번 남는다는 점을 V11 속도 조절 때 안내할 수 있다. 정렬식(MotionPlayRate = 1.1 ÷ lead)을 벗어나면 클립 f4 자세만 판정과 어긋난다.

#### 재현 방법
1. 시작: 57경로 Bundle을 커밋 트리·작업 트리에서 계산, `git diff a5efe69 8428a05` 제품 경로 확인, map01 edit 확인, 기존 로그 건수·범위 기록 후 clear 1회.
2. Play → 서버 프로브로 `_CombatRuleCatalog.patterns["mushmom"]`을 시험 값 복제본 한 행으로 교체, 몬스터 AttackInterval 9999, `StateComponent:ChangeState("ATTACK")`로 강제 실행. 20ms 타이머 샘플러가 구간·x·y·JumpActive·PlayRate를 기록하고 클라이언트 context에서 `SpriteAnimPlayerChangeFrameEvent`를 기록. 불가능 조합은 같은 방식에 행 값·`OrangeMushroomAttack.JumpDuration`·`HomeCaptured`를 바꿔 실행하고 Warning 로그를 센다.
3. 실입력: 늦춘 행에서 구간 안에 maker_keyboard_input UpArrow 탭.

#### reviewer가 알아야 할 근거의 한계
- 정렬식 이탈·불가능 조합은 모두 시험 행 값(Play 메모리)으로 만든 것이다. 제품 CSV로는 스폰 확인(MonsterManager, 바이트 동일)이 대부분 걸러 부팅 단계에서 거부하므로 이번 경로는 Monster_Attack·OrangeMushroomAttack의 마지막 방어선 시험이다.
- 정지 상태 시험(X11)은 FSM 정지로 ATTACK 전환 자체가 일어나지 않은 경우라 `IsMotionReady`의 정지 분기를 직접 밟지는 않았다.
- 사용 종료: 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 시험 전·후 57/57 동일 Bundle(`8d5b6d1c…4eed`), 제품 파일 무수정, commit·push 하지 않음.

### 2026-11-09 독립 QA 12회차 — 회차 D(CombatCore-MM-07~11)
- 상태: **실행 완료.** 실행 기준 PASS, FAIL·NEEDS_DECISION·새 결함 없음. 독립 reviewer 대기. NOT_RUN과 사용자 직접 확인(V11)은 아래 절.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push·run.md 수정 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았고 모든 기준을 이번에 다시 실행했다.
- 대상 버전: coder 로컬 커밋 **a5efe69**, 57경로 Bundle SHA-256 **`8dccccf58c6138d16e5b84277fa275c6a982c8d397e487d85e1f55e33e6ab738`**. coder의 manifest 방식(경로 바이트순 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래)을 내가 새 스크립트로 구현해 **커밋 트리(git ls-tree·show)와 작업 트리(파일 읽기) 양쪽에서 시작 때 계산**해 일치했고(57/57), Play 3회와 마지막 Stop 뒤에도 같다. 작업 트리 `git status`는 시험 전·후 모두 run.md(메인)만 변경. 셸 명령에 `.model` 문자열이 들어가지 않게 계산 스크립트를 파일로 두어 가드에 막히지 않았다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186(앞 회차와 같음). 맵 TileMapMode는 앞 기록(0 MapleTile)을 따랐고 이번 회차는 맵·Body 무변경이라 다시 읽지 않았다. Play 3회(2026-11-09 17:47 본시험, 18:03 재Play 기본값 확인, 18:04 통계 보충)와 매번 Stop 뒤 map01 / edit 확인.
- D-Q7 로그 정리(이번 회차 한정): 시작 때 기존 normal 로그 **123건, 2026-11-09 17:38:12~17:41:18**(앞 coder 세션의 프로브 [VRF D] 진행 로그와 마지막 LEA-3051 1건뿐)의 건수·시간 범위만 기록하고 `maker_clear_logs` **1회**(clearedCount 123). 그 뒤 지우지 않았다. 시험 로그는 `[T12]`(서버)·`[T12c]`(클라이언트)와 제품 `[VRF]` 표지로 저장된 JSON 파일에서 걸러 읽었다. 시험이 끝났을 때 버퍼는 약 1,020건·약 518k자였고 가득 차지 않아 기록이 끊기지 않았다(앞 coder가 본 764건 한계는 하드 한계가 아니다).
- 방법 구분: (A) 서버 프로브 = maker_execute_script(server_main, 클라이언트는 context client). (B) **실제 키 입력 = maker_keyboard_input**(UpArrow 100ms 탭, DownArrow·LeftArrow 홀드). (C) 스크린샷. 시험값은 Play 안에서만 조절했다: 몬스터 AttackInterval 9999, 패턴 목록을 한 행 복제본으로 교체(행 복제본의 TelegraphLeadSec·MotionPlayRate), 슬로우(ApplySlow), OrangeMushroomAttack.JumpDuration 8, 플레이어 SkillAttackCount 2, 판정 창(JustWindowSec·ParryWindowSec) 30, 몬스터 Hp 2·100, 플레이어 Hp 100. 모두 시험 안에서 원래 값으로 되돌렸고(로그 `windows restored just=0.2 parry=0.2`, `attackCount=10`, `JumpDuration restored 0.5`) Stop 뒤 새 Play의 `[T12] FRESH just=0.2 parry=0.2 guardRate=0.4 interval=3 jumpDur=0.5 count=10 patterns=5 hp=100`로 기본값을 확인했다. CSV·모델·코드 파일 변경 0.

| 기준 | 방식 | 이번 독립 실행 결과 | 판정 |
| --- | --- | --- | --- |
| 22.8-1 빌드·로드 | refresh 없이 편집 모드 build 로그, Play 로드 [VRF] | build 로그 93건 전부 Info(LIA 노이즈), 오류·경고 0. 로드 [VRF]: `catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`, `pattern weights mushmom total=20 parry.left=4(20.0%) parry.right=4(20.0%) parry.any=5(25.0%) special.random=3(15.0%) parry.guard=4(20.0%)`, 행별 `rate=1 jumpFrame=1 lead=1.1`(left·right·guard)·`jumpFrame=0 lead=0.5`(any·special), `MonsterSoundData id=mushmom damaged=c611ae50 hitplayer=7c8e5f1e die=d48ec1cc`. 재Play에서도 같음 | PASS |
| 22.8-2 패턴별 결정적(5행) | A | 각 행 강제 실행: parry.left·right = attack1, parry.guard = skill1, parry.any·special = jump. 착지 x(telegraph `landing`): left 0.750·right -0.750(영역 중앙 = 회차 C 식 `(min+max)/2`와 같음), guard **0.000(Pos2 앵커 x)**, any 0.000, special -1.500. 공격음 `sfx kind=attack`: left·right f135fc39, guard 5da7bb48, any·special 없음. 이펙트 호출: guard만(windup·dust 두 줄), left·right·any·special 없음 | PASS |
| 22.8-3 판정(parry.guard) | **B 실입력** + A(창 시험값) | 무입력 → HIT rate 1(플레이어 100→88, hitplayer 음 1줄). DownArrow 홀드를 공격 시작 약 1초 전에 시작(정상 창 0.2) → **GUARD rate 0.4**(100→96, hitplayer 1줄, `guard eval x=0.000 cellOk areaOk attr=PARRY`). DownArrow 홀드 + ParryWindowSec 30 시험 → **PARRY rate 0**(Pos2 x=0.000, cellOk·areaOk, counter granted, groggy applied, hit 클립 PlayRate 1, **hitplayer 0줄**, 플레이어 Hp 100). LeftArrow 홀드(Pos2 시작) + JustWindowSec 30 시험, parry.left → **JUST rate 0**(`evade eval x=0.000 cellOk areaOk dir=LEFT`, slow applied 2.0×0.5, hitplayer 0줄). LeftArrow 150ms 탭(0.25초 안에 Pos2로 복귀) → HIT rate 1(hitplayer 1줄). 범위 밖 회피로 안 맞는 special.random(A5)은 defense kind=HIT·플레이어 Hp 변화 0·hitplayer 0줄 | PASS (Pos1·Pos3에 선 채 판정 시점이 오는 경우는 NOT_RUN) |
| 22.8-4 SelectPattern 분포 | A(timer 안 루프로 방법 변경) | 제품 `MonsterAttackComponent:SelectPattern`을 직접 호출. **표본 A 21,000회**(3,000 + 18,000): left 4134(19.69%, -0.31%p)·right 4096(19.50%, -0.50)·any 5334(25.40%, +0.40)·special 3145(14.98%, -0.02)·guard 4291(20.43%, +0.43). **표본 B 20,000회**: 3945(19.73%, -0.28)·3918(19.59%, -0.41)·5072(25.36%, +0.36)·2989(14.95%, -0.05)·4076(20.38%, +0.38). **표본 C 20,000회**: 3971(19.86%, -0.15)·3981(19.91%, -0.09)·5045(25.23%, +0.23)·2960(14.80%, -0.20)·4043(20.22%, +0.22). 세 표본 모두 기대(20/20/25/15/20%) ±1.0%p 안(최대 |-0.50|%p), 합계 일치. 경계 프로브(난수 0, 0.1999999 / 0.2, 0.3999999 / 0.4, 0.6499999 / 0.65, 0.7999999 / 0.8, 0.9999999): left / right / any / special / guard 순서 그대로 | PASS |
| 22.8-5 Weight 변경 | A(행 목록 시험 입력, CSV 미수정) | 실제 표에서 읽은 행에 시험값: Weight 전부 1 → 거부 없이 `pattern weights mushmom total=5` 각 20.0%. Weight 0·-2·abc → 카탈로그 거부 + 경고 1회(`invalid weight`, `invalid pattern number`) | PASS |
| 22.8-6 실패 동작(프로브) | A | 거부 + 경고 각 1회: MotionClip 빈 값·`die`·대문자, AttackSound 형식·대문자 오류, EffectClip 짧은 값, MotionPlayRate 0·-1·abc·1e999, JumpStartFrame -1·1.5·abc, 열 누락(ReadRows nil). JumpStartFrame 빈 값·0은 허용. 경고는 키별 한 줄(같은 키 반복 시 추가 줄 없음): `invalid weight`·`invalid pattern number`·`invalid motion clip`·`invalid attack sound ruid`·`invalid effect clip ruid`·`invalid motion play rate`·`invalid jump start frame`. 스폰 거부(모두 `[VRF] MonsterManager spawn refused` + 경고 1회): 모델에 없는 MotionClip(attack3), JumpStartFrame 5(프레임 수 이상), parry.guard TelegraphLeadSec 0.7(W 0.800 ≥ 0.7), 사운드 행 없음. 네 경우 모두 현재 몬스터 유지(keep=true)·`머쉬맘` 자식 1개(새 엔티티 파괴), 시험 뒤 사운드 행·패턴 목록 복구 확인. 파일을 바꿔야만 확인되는 항목은 미실시(V11 6번) | PASS |
| 22.8-7 사운드 [VRF] | A + **B 실입력** | UpArrow 탭 1회(2타)마다 `sfx kind=damaged` **1줄**(R3 windup, 사망 시험 각 1줄), 사망 확정 때 `kind=die` **1줄**, hitplayer는 HIT·GUARD에서만 각 1줄, PARRY·JUST·범위 밖 회피에서는 0줄. 소리 자체는 청취 불가(사용자 V11) | PASS |
| 22.8-8 / 22.15 재스폰 다프레임 | A + 클라이언트 프레임 이벤트 | **첫 스폰 개체**(부팅 머쉬맘): attack1(A1·A3)·skill1(A2) 접근에서 클라이언트 프레임이 0→1→2→3 단조 증가, 서버가 f4를 판정 시각에 씀. **`MonsterManager:DoSpawn()` 재스폰 개체**(사망 뒤 교체): 직후·1초 뒤 서버 범위 **0-0**(coder 기준선 재현, 0-0 그대로 stand) → attack1(RS-L)·skill1(RS-G) 강제 실행에서 클라이언트 0→1→2→3, 서버 f1~f4 기록, 판정 뒤 stand 범위 0-2147483647. 첫 프레임에 멈춘 개체 없음 | PASS |
| 22.8-9 재생 배율 | A + 클라이언트 | 슬로우 없음: 접근 렌더러 PlayRate 1, 이펙트 PlayRate 1, 판정 뒤 stand PlayRate 1, 1칸 PlayRate 1. 슬로우 rate 0.5: 렌더러·이펙트 PlayRate 0.5(접근 전체 슬로우 G-S0·L-S0), 종료 뒤 stand·복귀 1. die PlayRate 1이고 마지막 프레임(5-5) 정지(F12). 로드 [VRF]에 행별 rate 기록. 실패 동작은 22.8-6. 이펙트 PlayRate는 호출 순간 값이고 재생 중 슬로우 변화는 따라가지 않음(기존 부채) | PASS |
| 22.16.7-10 제자리·도약 분리 | A(서버 20ms 샘플) + 클라이언트 프레임 이벤트 | 슬로우 없음 6회(A1 left, A3 right, A2 guard, RS-L, RS-G, GD): windup x **3.000..3.000**(변화 0), 구간 `windup`·JumpActive **F**·범위 0-0. W(`leap start` 시계 − `clip driven` 시계) 0.803~0.815초. 그 뒤 구간 `approach`·JumpActive **T**. 판정(`defense` 시계) 1.103~1.119초(기대 1.1, ±0.05 안), f4 서버 쓰기와 같은 틱. 착지 x: left 0.750, right -0.750, guard 0.000(Pos2). 클라이언트 f0→f1 간격 0.803~0.830초(서버 W와 차이 최대 0.015), f1→f2 0.201~0.206, f2→f3 0.050~0.055. f4는 같은 틱에 stand로 바뀌어 클라이언트에 그려지지 않음(착지 때 stand 계약). 접근 전체 슬로우(G-S0·L-S0 rate 0.5): W 1.598·1.597, 판정 2.202·2.200, 클라이언트 f0→f1 1.591·1.578(차이 0.007·0.019) | PASS |
| 22.16.7-11 이펙트 분할(parry.guard) | A [VRF] + 스크린샷 | 1단계: 호출 시각 = 공격 시작(`clip driven`과 같은 전투 시계 ±0.001), 위치 x 3.000(머쉬맘 현재)·y 0.581, 프레임 0-6. 2단계: 호출 시각 = 판정(`defense` 시계와 같은 값), x 0.000(Pos2)·y 0.581, 프레임 8-end. 두 호출 PlayRate = 1 × ActionRate(슬로우 0.5면 1단계 1·2단계 0.5, G-S0). 판정 전 취소 때 2단계 없음은 이번에 별도로 실행하지 않았다(소스: 2단계는 OnAttackComplete에서만 호출, coder 시험은 coder 근거) | PASS(취소 경로 NOT_RUN) |
| 22.16.7-12 제자리 피격 | **B 실입력** | 접근 속도를 늦춘 시험 행(TelegraphLeadSec 11, MotionPlayRate 0.1 → W 8초)에서 windup 중(공격 시작 약 1~2초) UpArrow 1회: `PlayerHitRule pass hit=1,2` 규칙 통과, 6초 시점 `seg=windup` 몬스터 Hp 100→**98**, damaged 음 1줄. **approach 중**(시험 R1, 접근 8~11초 구간의 약 10.5초) UpArrow 1회: `fail rule=targetHittableSegment hit=1,2`, 몬스터 Hp 변화 0. **return 중**(R2, 1칸 parry.any, JumpDuration 8·TelegraphLeadSec 8 시험값 → 접근 0~8초·복귀 8~16초, 12초 시점) UpArrow 1회: `fail rule=targetHittableSegment hit=1,2`, 15초 시점 `seg=return hp=100` | PASS |
| 22.16.7-13 높이 | A(서버 20ms 샘플) | 2·3칸 windup·approach y **0.581..0.581**(변화 0). 1칸 parry.any·special.random approach y 0.581..1.38(+0.8)·return 0.581..1.38(+0.8), 시작과 동시에 점프(approach 0.016~0.50초), 판정 0.513·0.50초 | PASS |
| 22.16.7-14 1칸 회귀 | A | parry.any·special.random: 시작과 동시에 JumpDuration 0.5 점프, 착지 x 0.000·-1.500(회차 C와 같음), PlayRate 1, 착지 뒤 stand, 복귀 jump | PASS |
| 22.16.7-15 검증 실패 | A | 22.8-6 표에 포함(JumpStartFrame 음수·소수·문자 거부 + 경고 1회, 프레임 수 이상·W ≥ TelegraphLeadSec 시험 행 스폰 거부 + 경고 1회) | PASS |
| 22.16.7-16 접근 클립 이어 재생(D-Q6) | A + 클라이언트 프레임 이벤트 | 슬로우를 접근 도중 시작·종료(서버 `ApplySlow`, 시각은 공격 시작 기준): **parry.guard** G-S1(windup 0.4초에 시작·2.0초, 판정 뒤 종료), G-S2(0.01초에 시작·0.6초, windup 도중 종료), G-S3(0.9초에 시작·0.2초, approach 안에서 시작·종료), **parry.left** L-S1·L-S2·L-S3(0.95초에 시작·2.0초, approach 도중 시작·판정 뒤 종료). 8회 모두 클라이언트 프레임 순서 0→1→2→3(**f0 재시작·되돌림 없음**). f1: 서버 W 대비 클라이언트 f0→f1 차이 G-S1 0.016, G-S2 0.006, G-S3 0.009, L-S1 0.001, L-S2 0.003, L-S3 0.002초(모두 ±0.05 안). f4: 서버 쓰기 시계 = 판정 시계 ±0.018초 이내(G-S0 2.184 vs 2.202, 나머지 0~0.001). 슬로우 종료 뒤 렌더러 PlayRate "클립 배율 × ActionRate"(접근 중 0.5, 판정 뒤 stand·복귀 1). 예상 실제 시각: G-S1 W 1.205·판정 1.803(기대 0.4 + 0.4/0.5 = 1.2, 0.4 + 0.7/0.5 = 1.8), G-S2 W 1.108·판정 1.418, L-S1 1.204·1.793, L-S2 1.102·1.412 | PASS |
| 회귀 — die 1회·F12 | **B 실입력** | 몬스터 Hp 2 + UpArrow 1회(2타) → 사망 확정, `MonsterDie start frames=6 total=1.100 freezeAfter=0.800` **1회**, +0.805초 `MonsterDie freeze frame=5` 1회, +2.5초·+6초에도 ruid ec90f0b6 범위 5-5·DEAD·PlayRate 1 유지 | PASS |
| 회귀 — Pos2 JUST·PARRY(F13) | **B 실입력** | 22.8-3 행(Pos2에서 PARRY·JUST 성공 조건 `cellOk=true areaOk=true`) | PASS |
| 회귀 — 팝업 정지 | 클라이언트 `_UIPopup:Open`/`OnClickOk` 호출(논리 경로, 실제 버튼 클릭 아님) + A | parry.left 접근 도중 팝업: `CombatPause server paused=true`(전투 시계 887.899), `client paused=true`. 정지 중 +1.5초·+2.4초 시점 상태 ATTACK·전투 시계 887.899·범위 2-2 그대로(진행 정지). 약 20초 뒤 닫기: `server paused=false`(887.899), f3 +0.019·f4 +0.071 전투 시계, 판정 1.103, `popup closed session=1`, `client paused=false`. 정지 시간이 공격 진행에서 빠짐 | PASS (토스트는 NOT_RUN) |
| 회귀 — DataSet 로드 값·실패 동작 | A | 22.8-1·5·6 및 재Play 기본값 확인(위) | PASS |
| 회귀 — 머쉬맘 스폰·피격 규칙 | A + B | 부팅 스폰·재스폰 모두 `MonsterStat applied key=mushmom MaxHp=100 AttackDamage=12 AttackInterval=3.0`, 규칙 목록 6개 한 번 생성, 실입력 타격 통과·차단(22.16.7-12), 스폰 거부 때 현재 상대 유지 | PASS |
| 회귀 — 1칸 착지 x | A | 22.16.7-14 | PASS |
| 이펙트 화면 위치·방향 | 스크린샷(원본 800x450, 일부 확대) | windup 중(skill1 클립 f0, 시험 행 MotionPlayRate 0.1로 이펙트 8초 연장): **머쉬맘 눈 위치에 노란 눈빛 이펙트가 겹쳐 보임**(확대 확인). 접근 중 스크린샷에서 머쉬맘이 Pos2(가운데 칸) 위 공중. 먼지: 판정 뒤 Pos2 근처에 옅은 입자 흔적이 있으나 이펙트가 얇고 옅어 육안으로 단정하지 못함. 방향(FlipX·SyncFlip): 눈빛이 좌우 대칭에 가까워 판별 불가 | 위치 PASS(눈빛)·먼지·방향 NOT_RUN |

#### 관찰·시험 오류 분리 (제품 오류 아님)
- maker_execute_script 본문 루프는 약 100회/초로 느리다(3,000회 28초). 같은 루프를 `_TimerService:SetTimerOnce` 콜백 안에서 돌리면 한 번에 끝나(20,000회 즉시) 분포 시험이 가능했다. 방법만 바꾼 것이며 제품 코드는 그대로 호출했다. 본문에서 시작한 `bound`+`stat2` 스크립트는 다음 스크립트에 멈춰 stat2 결과 줄이 없고, 표본 B·C(재Play)로 대체했다.
- 첫 approach 차단 시험(R1)은 tap이 windup이 아니라 approach에 떨어졌다(스크린샷·읽기 지연). 그대로 approach 차단 근거로 쓰고 windup 통과는 별도 R3으로 다시 실행했다.
- 팝업이 열리면 클라이언트 TimeScale이 0이라 클라이언트 타이머가 돌지 않아 내 2.6초 닫기 타이머는 발동하지 않았다. 닫기는 직접 `OnClickOk()` 호출로 했고 정지 시간이 약 20초가 되었다(시험 방식 때문, 제품 오류 아님).
- 클라이언트 프레임 이벤트가 프레임당 두 번씩 같은 시각에 온다(내 훅은 한 번만 연결됨). 순서·간격 판정에는 영향이 없고 제품 로그가 아니다.
- 서버 샘플러는 20ms 간격이라 구간 시각 해상도는 약 ±0.02초다. 판정·W 값은 제품 [VRF]의 같은 전투 시계 두 값의 차이로 계산했다.
- 시험 개체·타이머: 시험 로그의 Error 0건, Warning 11건은 모두 시험 프로브가 일부러 낸 `[CombatRuleCatalog]` 경고(검증 7키 + 스폰 거부 4건). Play 종료 때 LEA-3051 MemoryLeak 없음(내 클라이언트 반복 타이머는 종료 전에 ClearTimer).

#### NOT_RUN (PASS로 세지 않음)
1. 이펙트 방향(FlipX)과 먼지의 정확한 위치·크기 육안 확정, 효과음 실청취, 모션 체감(속도·f4 잘림·재미): 사용자 V11.
2. 판정 전 취소 때 이펙트 2단계 호출 없음(22.16.7-11 취소 경로)을 이번 실행에서 다시 하지 않았다.
3. 사망한 DoSpawn 재스폰 개체의 die 정지(F12는 부팅 개체에서만 확인), Pos1·Pos3에 선 채 판정 시점이 오는 회피 경우, 토스트 표시, 실제 팝업 버튼 클릭.
4. 같은 CSV 파일을 바꿔야만 확인되는 실패 동작, CSV Weight 직접 수정(V11 6번), 사람 손 타이밍, 모바일·실기기·다중 접속, 접근 중 슬로우 때 이펙트가 따라가는지(기존 부채).

#### 사용자 V11 직접 확인 항목 (Plan §22.8 V11 1~9·22.16.9, AI 결과로 대신하지 않음)
- 2칸 attack1·3칸 skill1·1칸 jump 모습, 눈빛 동안 제자리 → 도약 → 착지 순서와 속도(원작 1배, 판정 1.1초 난이도), f4가 잘리는 것이 괜찮은지.
- 3칸 눈빛이 머쉬맘 눈에, 먼지가 착지 지점에 자연스럽게 보이는지와 이펙트 위치·크기·방향.
- 효과음 4종 시점·음량, 비율 체감, CSV Weight 직접 조정(V11 6번), 속도 조절 항목(AttackInterval·TelegraphLeadSec·MotionPlayRate·JumpStartFrame·JumpDuration·JumpHeight·LeapJumpHeight·WindupHittable) 설정(22.16.9 안내 표).

#### 재현 방법
1. 시작: 57경로 Bundle을 커밋 트리·작업 트리에서 계산, map01 edit 확인, 기존 로그 건수·범위 기록 후 clear 1회.
2. Play → 서버 프로브로 `_CombatRuleCatalog.patterns["mushmom"]`을 한 행(또는 시험 값 복제본)으로 바꾸고 몬스터 AttackInterval 9999, `StateComponent:ChangeState("ATTACK")`으로 강제 실행. 20ms 타이머 샘플러가 구간(Segment)·x·y·JumpActive·PlayRate·프레임 범위를 기록하고, 클라이언트 context에서 `SpriteAnimPlayerChangeFrameEvent`를 몬스터에 연결해 프레임 번호·시각을 기록.
3. 슬로우: 공격 시작 뒤 지정 시각에 `MonsterStateControl:ApplySlow(duration, rate)`. 실입력: 늦춘 시험 행(TelegraphLeadSec 11·MotionPlayRate 0.1, 또는 JumpDuration 8)에서 구간 안에 maker_keyboard_input UpArrow 탭. 판정: DownArrow·LeftArrow 홀드 후 강제 공격(창 시험값은 같은 Play 안에서 복구).
4. 통계: 같은 서버 context에서 `SelectPattern(rows, math.random())`을 `SetTimerOnce` 콜백 안에서 20,000회 반복.

#### reviewer가 알아야 할 근거의 한계
- 판정(GUARD·PARRY·JUST·HIT)은 실제 키 입력이지만 PARRY·JUST는 창 시험값(30초)으로 타이밍 난이도를 없앤 것이다. 정상 창 0.2초 사람 손 타이밍은 NOT_RUN. GUARD는 정상 창에서 홀드를 일찍 시작한 경우다.
- windup·approach·return 타격 차단·통과는 실제 UpArrow 입력이지만 구간을 길게 늘린 시험 행(MotionPlayRate 0.1, JumpDuration 8)에서 확인했다(기본값 시각에서는 사람 손 타이밍이 어려움). 구간 선언·규칙 코드는 기본값과 같은 경로다.
- 클라이언트 프레임 시각은 클라이언트 ElapsedSeconds의 간격(f0→f1 등)이고 서버 전투 시계와의 절대 오차가 아니다. f4는 클라이언트에 그려지지 않으므로 서버 쓰기 시각 기준이다.
- 이펙트 눈빛 위치만 육안으로 확인했고 먼지·방향은 확정하지 못했다.
- 사용 종료: 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 시험 전·후 57/57 동일 Bundle(`8dccccf5…b738`), 제품 파일 무수정, commit·push 하지 않음.

### 2026-11-06 독립 QA 11회차 — 회차 C2(CombatCore-MM-12, 주황버섯 모델 영어 이름)
- 상태: **실행 완료.** 실행 기준 PASS, FAIL·NEEDS_DECISION·새 결함 없음. 독립 reviewer 대기. NOT_RUN과 사용자 직접 확인(V11)은 아래 절.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push 없음, **maker_clear_logs 호출 없음**(Maker 로그는 저장된 JSON 파일을 `[T11]`·`[VRF]` 표지와 시각으로 걸러 읽음). coder 개발절의 PASS는 이번 실행으로 세지 않았다.
- 대상 버전: HEAD **163fc37**(coder `[code]` 커밋, 기준 105e585). 55경로 manifest(경로 바이트순 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래) **Bundle SHA-256 `8ef9c6f1c60d73b7b74f5febd09932abfe6ba5866bfc577cb226c82d5ed2e080`**. 나는 이 값을 **커밋 트리(git ls-tree·show)와 작업 트리(파일 읽기) 양쪽에서 새로 계산**해 coder 보고와 일치함을 확인했다(계산 스크립트는 scratchpad, 앞 회차와 같은 규칙으로 105e585 커밋 트리에서 `222e7a041b619cc26bb3bd51492a352cd95a41c42259fc8f6f06e9c5e03b476d`도 재현해 방법이 같음을 확인). **시험 전·후 작업 트리 값 모두 동일**(Play·refresh가 제품 파일을 바꾸지 않음). 작업 트리 `git status`는 시험 전·후 모두 run.md(메인)만 변경.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186(앞 회차와 같음). TileMapMode는 앞 기록(0 MapleTile)을 따랐고 다시 읽지 않았다(이번 회차는 맵·Body 무변경). Play 1회(2026-11-06 15:00:15 부팅~15:02 종료), 마지막 Stop 뒤 map01 / edit 확인.
- 방법 구분: (A) 서버 프로브 = maker_execute_script(server_main). (B) 실제 키 입력 = maker_keyboard_input(UpArrow 100ms 탭). 시험값(Play 내부, Stop으로 폐기): 몬스터 AttackInterval 9999 → 0.2 → 9999, 몬스터 Hp 5. 시험 개체 이름 접두사 `T11Probe_`.

| Plan §23.3 | 방식 | 이번 독립 실행 결과 | 판정 |
| --- | --- | --- | --- |
| 1 Glob | Glob 도구 | `RootDesk/**/*.model` = `Models/MapObjects/AttackAreaMark.model`·`Models/Monsters/Mushmom.model`·`Models/Monsters/OrangeMushroom.model` 3개. `**/주황버섯*` 일치는 `.handoff-backups/2026-11-02-claude-setup-before/…/주황버섯.model` 1건뿐(2026-11-02 설정 이전 백업 폴더, 제품 경로·Maker 대상 아님). 제품 경로에 `주황버섯.model` 없음, Mushmom 그대로 | PASS |
| 2 ModelBuilder.read 비교 | 내가 `git show 105e585:…/주황버섯.model`을 임시 파일로 꺼내 ModelBuilder.read로 두 판 snapshot 재귀 비교 (b93e2ac 판도 같은 결과) | 두 판 모두 컴포넌트 14·Values 45·자식 0. model_id `orangemushroom`(EntryKey `model://orangemushroom`, 안쪽 Id `orangemushroom`). **snapshot 의미 차이 1곳: name `주황버섯` → `OrangeMushroom`.** 원문 바이트 비교: 옛 파일에서 `주황버섯`(1회 등장)을 `OrangeMushroom`으로 바꾸면 새 파일과 **완전히 같다**(+2바이트: 한글 4자 12바이트 → 영문 14바이트). 형식·숫자 표기 차이도 없음. 파일 값 대조(ModelBuilder): ActionSheet 5키 stand 96e955c1…·move 6ad988b3…·jump 94bbe2a7…·hit aec9504d…·die 65a2bfb0…, Scale (1,1,1), SpriteRUID 96e955c1…, HitComponent BoxSize (0.63,0.58)·ColliderOffset (0.045,0.29) | PASS |
| 3 refresh 뒤 build 로그 | maker_refresh_workspace + maker_logs(build) | refresh ok. build 로그 83건 전부 Info(LIA 1114/1115 동적 참조), 오류 0·경고 0, 앞 회차와 같은 건수. 항목 시각이 모두 12:57:08(= .mlua 변경이 없어 재컴파일 없음, 모델 이름 변경은 build 로그 대상 아님). Play 부팅에서 모델이 정상 스폰되어 옛 이름 항목 잔존 징후(경고·경로 이동·내용 되돌림) 없음. 이 항목은 Play 뒤 build 로그를 다시 읽지 않았다 | PASS |
| 4 Play 회귀(머쉬맘 부팅·수치) | A + 부팅 [VRF] | `catalog ready rules=1 patterns=4 monsterStats=2`, `MonsterStatData id=mushmom MaxHp=100 AttackDamage=12 AttackInterval=3.0 source=DataSet`, `MonsterStat applied key=mushmom MaxHp=100.0 Hp=100.0 AttackDamage=12.0 AttackInterval=3.0 …`, `MonsterManager spawned parent=map01 x=3.0`. MonsterData 행 1개(`머쉬맘 / model://mushmom`). 서버 프로브: 맵 자식 `머쉬맘` 1개, Scale (1,1,1), MaxHp/Hp 100, AttackDamage 12, AttackInterval 3.0, modelKey mushmom, 상태 IDLE. 플레이어 `PlayerBaseStatData … MaxHp=100 MoveSpeed=12 ReturnSpeed=12`, `PlayerStat applied MaxHp=100 Hp=100`, `MovementInput boot speed=12.0 return=12.0` | PASS |
| 4 피격 규칙 — 통과 | **실제 UpArrow 100ms 탭 1회**(몬스터 IDLE) | `PlayerHitRule list built rules=6 builds=1`, hit 1~10 모두 `pass`(checks 1→19, 타격당 2회), 몬스터 Hp 100→**90** | PASS |
| 4 피격 규칙 — targetHittableSegment 실패 | A(논리: 몬스터 AttackInterval 0.2로 낮춰 ATTACK 진입 시 타이머가 0.05초 뒤 서버 `player.StateComponent:ChangeState("ATTACK")`, 진입 직후 AttackInterval 9999 복귀) | 몬스터 ATTACK(예고 parry.right) 진입 +0.05초 시전: hit 1~10 모두 `fail rule=targetHittableSegment`, 몬스터 Hp 90 그대로 | PASS (실제 키 입력이 아니라 논리 경로) |
| 4 사망 F12 — die 한 번 재생·끝 모습 정지 | 몬스터 Hp 5(시험값) + **실제 UpArrow 100ms 탭 1회**, 서버 30ms 폴링으로 SpriteRUID·프레임 범위·상태 변화 기록 | hit 1~5 pass(Hp 5→4→…→0), 상태 HIT→(Hp 0)DEAD, `MonsterDie start frames=6 total=1.100 freezeAfter=0.800` **1회**, `DeadEvent` 연결 카운트 **1**, `MonsterHealth lethal state=DEAD` 1회. SpriteRUID는 stand 860153…→**die ec90f0b6…(프레임 0~끝)** 로 한 번 바뀐 뒤 +0.8초 `MonsterDie freeze frame=5` **1회**, 범위 5-5로 고정. 이후 시각 15:02:00·15:02:03(고정 +약 4.5~8초)에도 `ec90f0b6… 5-5 DEAD` 유지. hit 6~10은 로그에 없음(사망 뒤 타격 제외) | PASS |
| 5 직접 스폰 | A(`_SpawnService:SpawnByModelId("orangemushroom", "T11Probe_orangemushroom", 스폰 위치-2, 맵)`) | 성공. 이름 그대로, Scale (1,1,1), SpriteRUID 96e955c1…(stand), ActionSheet 5키 stand 96e955c1bf27415e84f96deea200a8f1·move 6ad988b3ef6d4ceab3a504d300755a5b·jump 94bbe2a7eb9c4f9caa10dd9de44ee860·hit aec9504d5dc24aceb5646b79d30abad4·die 65a2bfb039614f2e9e4ccc354340153d(**파일 값과 키·RUID 전부 일치**), stun·attack 키 없음, HitComponent BoxSize (0.63,0.58)·ColliderOffset (0.045,0.29). `isManagerMonster=false`. 같은 방식으로 `mushmom`도 1회 스폰해 구성 확인(Scale 1, 5키, BoxSize (1.2,1.1)·Offset (0,0.55)). 둘 다 Destroy. **잔존 확인: 1.5초 뒤 맵 자식 목록에 `T11Probe*` 0개**(자식 14개 = 원래 목록과 같음). 대조: `SpawnByModelId("castleenemy")`·`("주황버섯")` 둘 다 nil, `[LEA-3028] MissingModel` 각 1건(의도한 프로브 오류) | PASS |
| 5 MonsterManager 경로 미출현 | A + 부팅 [VRF] | MonsterData 행 1개(`머쉬맘`), 부팅 스폰이 머쉬맘 1개, 직접 스폰한 주황버섯은 `mm.CurrentMonster`와 다름. 오로지 코드·데이터 근거로 DoSpawn이 주황버섯을 고를 행이 없음(행 수 1) | PASS |
| 6 Grep | Grep 도구 | `주황버섯` 일치: 제품 파일(.mlua·.model·.map·.ui·.csv·.userdataset·.config·.stateset·.collisiongroupset·.codeblock·.directory)에서 `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua:52` 한국어 주석 **1건뿐**(범위 밖, 그대로). 그 밖에 `.claude/skills/msw-ui-system/…/style-1-black/HUDGroup.ui:1048`과 `.agents/…` 같은 파일은 스킬 템플릿 문구(제품 파일 아님) | PASS |
| 7 git 변경 범위 | `git diff -M 105e585 163fc37` | 제품 변경은 **모델 1개 경로 변경 `주황버섯.model → OrangeMushroom.model`(R097, 한 줄)뿐**. 그 밖에 `.maplestory-skill-maker-ledger.md` 1줄(23행 모델 경로만), Plan 1줄, WorkRecord 추가 47줄. 다른 재저장 파일 없음(.directory 포함). 원장 행의 괄호 `(castleenemy)`·"현재 MonsterData는 castleenemy 1행" 표현은 낡았지만 coder가 보고한 대로 바꾸지 않았다(범위 밖 관찰) | PASS |
| 지문 | Bundle 계산 | 위 대상 버전 절. 시험 전 = 시험 후 = 8ef9c6f1…e080 (55/55) | PASS |

#### 시험 오류·불확실성 분리 (제품 오류 아님)
- 첫 직접 스폰 프로브가 `#e.Components` 길이 조회로 `[LEA-2002]`을 냈다(coder 인계에 이미 적힌 같은 실수를 내가 반복). 그 때문에 첫 시험 개체 `T11Probe_orangemushroom`이 Destroy 전에 멈춰 남았고, 수정한 두 번째 프로브가 시작에서 그 개체를 지운 뒤(`destroying stale probe`) 다시 스폰·확인·Destroy했다. 최종 잔존 0. 이 오류 1건은 로그에 보존했다.
- 시험 시작 전에 몬스터 자연 공격이 플레이어에게 12씩 9번 들어가 플레이어가 한 번 사망→5초 뒤 부활했다(`duel player=none` 15:00:58 → 복귀 15:01:04, 이후 Hp 100). 시험 준비 지연 때문이며 이번 회차 범위의 제품 동작(앞 회차와 같은 사망·부활)이다.
- 추가로 요청 범위 밖이지만 `mushmom` 모델도 1회 스폰해 비교용으로 확인했다(Destroy됨).
- Play 로그 Error 3건: 위 LEA-2002(내 프로브) 1 + 의도한 LEA-3028 2. 제품 경로의 Error·Warning 0.

#### NOT_RUN (PASS로 세지 않음)
1. 회차 C 전수 회귀(접근 점프 중 내 시전 외 구간 — 복귀 중 무대응/패링/저스트, 착지 뒤, 걸친 공격, 그로기 중 시전, 반격 창, 규칙 실패 이름별 프로브, 크기 무관), 그로기 중 사망, 패링·저스트·가드 실제 입력(F13), V07 팝업 정지, V10 UI 출처 합산, DataSet 검증/실패 동작. 이번 변경은 모델 Name 한 줄이라 지시대로 전수 회귀는 하지 않았다.
2. Stop 뒤 **새 Play에서 시험값(AttackInterval·Hp)이 남지 않는지** 다시 확인하지 않았다(제품 파일 지문은 같고 시험값은 런타임 값이므로 Stop 폐기 근거만 있음).
3. 대소문자 다른 `"OrangeMushroom"` 키 스폰(coder가 확인한 항목, 이번에 다시 하지 않음).
4. 사람 손 타이밍, 실기기·모바일·터치, 다중 접속, 화면 육안(스크린샷 안 찍음).

#### 사용자 V11 직접 확인 항목 (Plan §23.4, AI 결과로 대신하지 않음)
- Maker 작업 공간 창에 주황버섯 모델이 `OrangeMushroom` **하나로만** 보이는지(옛 이름 항목이 없는지). AI는 작업 공간 창을 볼 수 없다. (AI 쪽 근거: 디스크·ModelBuilder·런타임 등록은 하나뿐이고 `castleenemy`·`주황버섯` 키 스폰은 nil.)
- 플레이 화면은 회차 C와 같아야 한다(머쉬맘). 주황버섯은 나오지 않는다.

#### 재현 방법
1. Glob `RootDesk/**/*.model`, `git diff -M 105e585 163fc37`, `git show 105e585:RootDesk/MyDesk/Models/Monsters/주황버섯.model`을 임시 파일로 꺼내 ModelBuilder.read로 두 판 snapshot 비교.
2. 작업 트리·커밋 트리 55경로 Bundle 계산(대조 값 8ef9c6f1…e080).
3. 편집 모드 refresh → build 로그 → Play. 서버(server_main)에서 맵 자식을 순회해 MonsterManager를 찾고 `SpawnByModelId("orangemushroom", …, 맵)` 구성 확인 후 Destroy, `castleenemy`·`주황버섯` 스폰 nil 확인. 실제 UpArrow 100ms 탭(몬스터 IDLE)으로 규칙 pass 10건과 Hp 100→90, 몬스터 ATTACK 진입 +0.05초 시전으로 targetHittableSegment 실패 10건, 몬스터 Hp 5 + UpArrow 탭으로 die 시작 1회·정지 프레임 5-5.

#### reviewer가 알아야 할 근거의 한계
- 피격 규칙의 segment 실패 사례는 서버 `ChangeState("ATTACK")` 논리 경로이고, pass 사례와 사망 사례만 실제 UpArrow 입력이다. 규칙·사망의 회차 C 전수는 하지 않았다.
- 모델 파일 의미 비교는 ModelBuilder snapshot 재귀 비교와 원문 문자열 치환 일치(바이트 단위)로 했다. 파일의 형식 차이는 없었다.
- 원장(`.maplestory-skill-maker-ledger.md`)의 낡은 `castleenemy` 표현은 정리되지 않았다(coder가 보고). 규칙에 정리 범위가 없어 결함으로 세지 않고 메인 판단에 남긴다.
- 사용 종료: 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 시험 뒤 55/55 동일 Bundle(`8ef9c6f1…e080`), 제품 파일 무수정, commit·push 하지 않음.

### 2026-11-04 독립 QA 9회차 — 회차 B(V11-F14·V11-F07)
- 상태: **실행 완료.** 실행 기준 PASS, FAIL·새 결함 없음. 결함 후보 없음(추가 항목 (a)는 재현되지 않음). 독립 reviewer 대기. NOT_RUN과 사용자 직접 확인은 아래 절.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품 코드·모델·맵·UI·.codeblock 수정 없음. CSV는 Plan 지시대로 2종만 시험 변경 후 백업에서 복원했고 byte 일치를 확인했다(아래). commit·push 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 호출하지 않았다**(Maker 로그는 저장된 JSON 파일을 `[T9…]` 표지와 시각으로 걸러 읽었다).
- 실행 경위: 첫 실행(Play 1, 2026-11-04 19:10~19:18)이 사용량 제한으로 중단됐고 사용자 재시도 지시로 2026-11-05에 남은 기준부터 이어 실행했다(Play 2~5). Play 1에서 이미 읽고 판정한 항목은 다시 하지 않고 아래에 "Play 1"로 표시했다. Play 1의 원본 로그는 Play 2 시작 때 Maker가 비워 파일로 남지 않았다(판정에 쓴 값은 당시 읽은 로그 줄에서 옮겼다). Play 2~5의 로그는 시각·표지로 재확인 가능하다.
- 대상 버전: coder 로컬 커밋 **1b4f4ee**(기준 9eed765). 59경로 manifest Bundle SHA-256 **9325c33ade8a2c32c058cb7e4050a82f8b44d9f22dcfe68c82874cd3e23bcd19**(= 기존 54경로 `a8c96297411224849adc9613f278d76f6f2eb94ab5cb8e1f785548a185fbcc5d` + 새 5경로), 같은 계산법(coder 절의 V11-F06 표 54경로 + 새 5경로를 `LC_ALL=C sort`, 경로 + TAB + sha256 + LF 연결의 SHA-256). **Play 1 시작·재개 시작·시험 끝 세 번 모두 같은 값**이고 경로별 해시 목록도 일치했다. 작업 트리는 시작 때 run.md(메인)만 변경이었고, 재개 때 `RootDesk/MyDesk/Player/@Assist/Stat.directory`가 추가로 변경돼 있었다(아래 범위 밖 재저장). .directory는 manifest 대상 밖이라 Bundle 값은 변하지 않았다.
- 범위 밖 재저장(기록만, 되돌리지 않음): `RootDesk/MyDesk/Player/@Assist/Stat.directory` — `StudioVersion` ""가 "0.1.0.0"으로 바뀐 한 줄(Maker 재저장). 내가 직접 수정하지 않았고 시험 시작 시점에도 이미 이 상태가 아니었다가(1b4f4ee 커밋 상태 M 없음) 재개 시점에 변경돼 있었으므로 중단된 Play/Stop 중 Maker가 저장한 것으로 본다. CSV·.userdataset·.mlua·모델·맵·UI·기존 CSV 5종은 커밋과 같다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따랐고 다시 읽지 않았다. build 로그 89건 모두 Info(LIA 1114/1115 동적 참조, 오류 0·경고 0, coder와 같은 건수). Play 5회(중단된 1회 포함), 마지막 Stop 뒤 map01 / edit.
- 방법 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트에서 한 번에 스크립트 하나만 돈다). (B) 실제 키 입력 = maker_keyboard_input. 도구 왕복이 수 초라 0.20초 판정 창에 손으로 맞출 수 없어 F13 회귀는 **판정 창을 Play 내부에서 30초로 넓힌 "시험값" 근거**이고 모두 원복을 로그로 확인했다. 패턴 단일 행 교체·몬스터 AttackInterval 9999·플레이어 Hp 20 설정은 Play 내부 시험값이며 Stop으로 폐기됐다. 검증 함수 프로브(`ValidateStatRows`·`_PlayerBaseStatCatalog:Validate`)는 시험 행을 함수에 넣는 "프로브 근거"다. 팝업은 `_UIPopup:Open`과 취소 핸들러 호출(마우스 클릭 아님). 근거 한계는 맨 아래.

#### 값 동일성 (Plan §20 회귀 기준)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 로드 [VRF]와 값 출처 | A | Play 1·2·5 부팅 모두 서버 `MonsterStatData id=default/castleenemy MaxHp=100 AttackDamage=12 AttackInterval=3.0 source=DataSet`, `PlayerBaseStatData side=server`·`side=client default MaxHp=1000 MoveSpeed=6 ReturnSpeed=6 source=DataSet`, `MonsterStat applied key=castleenemy MaxHp=100.0 Hp=100.0 AttackDamage=12.0 AttackInterval=3.0 … blankFromDefault=false/false/false`, `PlayerStat applied MaxHp=1000 Hp=1000 source=DataSet`, `MovementInput boot speed=6.0 return=6.0 source=DataSet`. 서버/클라이언트가 각자 같은 표를 읽음(ExecSpace 분리 확인) | PASS |
| 플레이어 HP 1000, 시작 Hp 1000, 클라이언트 값 | A | 서버 `PlayerComponent.MaxHp` 1000·시작 Hp 1000, 클라이언트 MaxHp 1000(Play 1 프로브). HP 바 육안·스크린샷은 찍지 않음 | PASS(값) / NOT_RUN(화면) |
| 몬스터 수치 서버·클라이언트 | A | 서버 몬스터 MaxHp 100·Hp 100·AttackDamage 12·AttackInterval 3.0·modelKey castleenemy, 클라이언트 MaxHp/Hp 100(Play 1). `DoSpawn` 재호출로 새 상대도 같은 값 적용 | PASS |
| 자연 공격 간격 | A | Play 1 서버 감시: IDLE→ATTACK **시작~시작 4.003~4.030초**(9회). 코드상 `attackTimer`는 IDLE에서만 누적(MonsterStateControl.OnUpdate 106~111행)이라 시작~시작 = IDLE 대기 3.0 + ATTACK 약 1.0이다. 직접 쟀을 때 ATTACK→IDLE 뒤 다음 ATTACK 시작까지 **IDLE 구간 2.92~3.03초**(Play 2 T9b 0.1초 표본: 144.50→147.49·148.53→151.56·156.56→159.59·164.53→167.53·168.55→171.55, 전투 시계). 팝업 정지 중 타이머 2.48 고정 → 재개 2.49→2.97 (아래 V07). 값 AttackInterval 3.0은 전과 같음 | PASS(값 3.0, 대기 구간 기준). 판정 메모: coder/Plan의 "시작 간격 3.0"은 시작~시작이 아니라 IDLE 대기 구간 기준이다(소스 변경 없음) |
| 피해: 무대응 12, 일반 가드 4, HP 감소 = HitEvent 합계 | A+B | Play 1 감시 35초: 무대응 자연 공격 9회 모두 12씩(Hp 736→628), HP 감소 108 = HitEvent 합계 108. 가드: 시험 단일 행 GUARD·NORMAL(예고 3.0초) + **실제 DownArrow 홀드** → `defense kind=GUARD rate=0.4`, 516→512 = 4 = floor(12×0.40), hitEventDelta 4 | PASS |
| 처치까지 피해 합계 100, DEAD·DeadEvent 1회 | A+B | Play 1: 새 상대(DoSpawn, Hp 100) → 실제 UpArrow 250ms 1회 + 클라이언트 `RequestChangeState("ATTACK")` 논리 호출 9회(총 10회 시전 × 타수 10 × 피해 1). Hp 100→0, **HitEvent 합계 100·이벤트 100건**, 마지막 `Hp 2.0→0.0`, `MonsterHealth lethal state=DEAD`, DeadEvent 1·DEAD 상태 변화 1, `MonsterDie freeze frame=2` | PASS (실제 키 1회 + 논리 경로 9회) |
| Stop → 다음 Play 재로드, 시험값 비잔존 | A | Play 1은 중단됐고 Play 2 부팅이 위 [VRF] 값을 DataSet에서 다시 로드. Play 2 시험 시작 값 `origJust=0.2 origParry=0.2 origPatterns=4`(앞 Play의 창 30초·단일 패턴이 남지 않음). Play 5(CSV 원복 뒤)도 같은 값으로 로드, Play 3·4의 시험 CSV 값(MoveSpeed 9·MaxHp 150·무효값)이 남지 않음 | PASS |

#### DataSet 동작
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| **CSV 실제 변경 반영**(Plan 값, 1회) | 파일 수정 + Refresh + Play 3 | 변경 전 바이트 해시 `PlayerBaseStatData.csv 3202ac06…d094`(53바이트)·`MonsterStatData.csv f9709bd8…1dc3`(85바이트)를 백업. `default,1000,6,6`→`default,1000,9,6`, `castleenemy,100,12,3.0`→`castleenemy,150,12,3.0`(BOM·CRLF 보존). Refresh → Play 3: 서버·클라이언트 `PlayerBaseStatData … MoveSpeed=9 ReturnSpeed=6`, `MovementInput boot speed=9.0 return=6.0`, 실제 LeftArrow OUTBOUND `elapsed=0.154`(약 1.5/9), RETURNING 0.241(복귀 6 그대로), `MonsterStat applied MaxHp=150.0 Hp=150.0`, 서버·클라이언트 몬스터 MaxHp/Hp 150 → **DataSet이 모델 Values(주황버섯 MaxHp 100)를 덮어씀**. 같은 Play 부팅 직후 첫 DownArrow도 `PlayerGuard start`가 남음(아래 (a)) | PASS |
| **원복·byte 일치** | Stop + 백업 복원 + Refresh + Play 5 | 복원 뒤 sha256: PlayerBaseStatData.csv `3202ac06b9ebf31c13d73a2eb343ab788f5393e8b7f8255a36ad3efa815ed094`, MonsterStatData.csv `f9709bd83183f0c85f36d0d1037a6e7c85f4cb55111ad8d4bfe5536869471dc3`, .userdataset 2종 `f6d8da25…5d7f`·`b5a226f2…2f0` — 변경 전과 **모두 일치**. Play 5: `MoveSpeed=6`·`MaxHp=100`·`boot speed=6.0`·OUTBOUND 0.239·RETURNING 0.247, 경고·오류 0. git status는 run.md와 Stat.directory(범위 밖 재저장)뿐 | PASS |
| **파일 단위 무효 데이터 거부**(추가 시험, Plan 표의 프로브를 실제 파일로 확장) | 파일 수정 + Refresh + Play 4 | `PlayerBaseStatData default,1000,0,6`(MoveSpeed 0)·`MonsterStatData castleenemy,150,12,0`(AttackInterval 0)로 바꿔 Play: `[CombatRuleCatalog] MonsterStatData invalid AttackInterval` 경고 1회 → `MonsterManager spawn refused key=castleenemy reason=stats`(**몬스터 스폰 없음**, 서버 currentMonster=nil·catalogReady=false); `PlayerBaseStatData invalid MoveSpeed` 경고 **서버·클라이언트 각 1회**, 서버 `PlayerStat rejected reason=table`·`IsBaseStatsReady()=false`·duel player=nil, 8초 뒤에도 대결 없음·Hp 1000 변화 없음; 클라이언트 `MovementInput boot … source=rejected`, **실제 LeftArrow 두 번 모두 `MovementInput rejected reason=stats`로 이동하지 않음**. 모델 maxHp·.mlua 속성 6으로 대신 진행하지 않음(PlayerComponent.MaxHp 1000은 엔진·모델 값이 그대로 남은 것이고 대결·이동에 쓰이지 않음). 원복은 위 행 | PASS |
| 빈 칸 → default 값(몬스터, 프로브) | A(`ValidateStatRows`) | 빈 문자열·공백만·빈 문자열 행 → 세 열 모두 default 값(`fromDefault=truetruetrue`), MaxHp만/AttackDamage만/AttackInterval만 빈 칸이면 해당 열만 default 값 | PASS |
| default 행 문제(몬스터 서버 + 플레이어 클라이언트, 프로브) | A | default 없음, default의 각 열 빈 칸(MaxHp·AttackDamage·AttackInterval / MaxHp·MoveSpeed·ReturnSpeed 각각), default의 무효 값 → 표 전체 거부 + 원인별 경고 1회 | PASS |
| 무효 값(프로브) | A | 몬스터 MaxHp 0·−5·1.5·abc·1e999·−1e999, AttackDamage −1·−0.1·abc·1e999, AttackInterval 0·−1·abc·1e999 모두 거부(AttackDamage 0·0.5와 MaxHp "100.0"은 수락). 플레이어 MoveSpeed·ReturnSpeed 0·−1·abc·1e999(−1e999), MaxHp 0·−5·1.5·abc·1e999 모두 거부. default 아닌 행의 무효 값도 default로 대체하지 않고 표 거부. 같은 원인은 경고 1회(예: MoveSpeed 5종 입력에 경고 1줄) | PASS |
| 키(프로브) | A | 중복 id·공백 포함 중복 id·빈 id·공백만 id 거부(경고 원인별 1회). 스폰 modelKey 행 없음(`nosuchmodel9`)·예약 `default` → `GetMonsterStats` nil + 경고 1회(같은 키 두 번째 호출은 경고 없음), `DoSpawn`은 `spawn refused`로 스폰하지 않고 **현재 상대 유지**, default로 스폰하지 않음 | PASS |
| 필수 열 누락·추가 열(프로브) | A | `ReadRows(MonsterData, {"id","MaxHp"})`→nil(거부), 없는 표 `NoSuchTable9`→nil. `#memo`·추가 열은 무시(수락) | PASS |
| 플레이어 표 실패 시 이동·대결 거부 | A+B | 위 파일 단위 무효 데이터 행(실제 CSV)이 근거. 코드 경로: 서버 PlayerHealthComponent.OnBeginPlay와 클라이언트 PlayerMoveComponent.CanStart가 같은 `ValidateStatRows` 기준 | PASS |

#### 이동·입력 회귀 (V09·V10, 1단계)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 이동·복귀 속도 6 | B | 실제 Left/RightArrow 홀드 OUTBOUND(1.5 거리) `elapsed` 0.228~0.245, RETURNING 0.240~0.262, 복귀 완료 `state=IDLE`. 서버 `PlayerEvade start x=0.000`과 클라이언트 `OUTBOUND x=0.0` 차이 0.000 | PASS |
| 방향키·UI 출처 합산, 반환 잠금 | B+A | 실제 LeftArrow `down` + `RequestChangeState("LEFT","ui.left")` 수락(true) → 실제 키 `up` 뒤에도 `MOVE|held=LEFT|src=ui.left|phase=HOLD|x=−1.50` 유지 → `ReleaseHeldState("LEFT","ui.left")` 뒤에만 RETURNING. 복귀 중 `RequestChangeState("RIGHT")` **false**(잠금), 복귀 완료 뒤 수락. UI 출처는 논리 호출(마우스 클릭 아님) | PASS(키 출처 실제, UI 출처 논리) |
| 기본 공격 타수·범위(AttackSkillData 무변경) | B+A | 시전 1회마다 `manual cast count=10`, 타격 10건 × 피해 1 = 10, 총 10회 시전 = 100(위). 기본 공격 `UpArrow` 100ms 탭 1회도 시전됨(아래 관찰) | PASS |
| 최초 Play 직후 입력과 DownArrow 시작 | B | 아래 (a) | 아래 |

#### 회귀 (회차 A·F06·F08·V07)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| F12 die 1회 재생 후 정지 — IDLE 피격 사망 대표 | A+B | 위 처치: `MonsterDie start frames=3 total=0.660 freezeAfter=0.360` → `MonsterDie freeze frame=2`, 서버 SpriteRUID die 시작 후 `2/2` 고정 | PASS |
| F12 — 그로기 중 사망 | A | Play 2: `ApplyGroggy(3)` 0.5초 뒤 `STUN|aec950`(hit) → `ApplyDamage(999)` → `DEAD|aec950`→`65a2bf(die) 0/MAX`(+0.21)→`2/2`(+0.57), DeadEvent 1, 이후 변화 없음 | PASS |
| F13 Pos2 시작 PARRY | A+B | 시험값 창 30초, `parry.any`(ANY·PARRY·NEAREST, 예고 8초) + **실제 DownArrow 홀드** → `guard eval x=0.000 cellOk=true areaOk=true attr=PARRY`, `defense kind=PARRY rate=0`, Hp 416→416, `groggy applied` | PASS(시험값) |
| F13 Pos2 시작 JUST | A+B | 시험값 창 30초, `parry.any` + **실제 LeftArrow 탭** → `evade eval x=0.000 cellOk=true areaOk=true dir=LEFT`, `counter granted until=33.536 factor=2.2`, `slow applied duration=2.0 rate=0.5`, `defense kind=JUST rate=0`, Hp 928→928 | PASS(시험값) |
| F13 끝 칸 1칸 공격 무보상 | A+B | 시험값 창 30초, `RIGHT`·PARRY·앵커 1~1(첫 시도 `LEFT` 응답 행은 "telegraph escape area invalid"로 제품이 거부 — 시험 데이터 오류, 아래) + **실제 LeftArrow 홀드 8초(플레이어 x=−1.5)** → `evade eval x=0.000 cellOk=true areaOk=false dir=LEFT`, `defense kind=HIT rate=1`, Hp 748→736(−12) = JUST·반격·슬로우 없음 | PASS(시험값) |
| 서버 기록 시작 x 대 클라이언트 segment.startX | B | 실제 키 6건 이상에서 서버 `PlayerEvade start x=0.000` / 클라이언트 `OUTBOUND x=0.0` 차이 0.000 | PASS |
| F06·F10 패턴 4행·Weight 2·2·2·1, 2칸 중간 착지·판정 시각 | A | 카탈로그 `parry.left:2,parry.right:2,parry.any:2,special.random:1`. `parry.left` 형(앵커 2~3, 예고 2.0) 시험: 몬스터 시작 x=3.0 → 점프 +0.54초에 **x=0.750 중간 착지**, 판정 `defense` 전투 시계 300.954 = 공격 시작 298.961 + 1.993(≈2.0), 이후 복귀 점프로 x=3.0 | PASS |
| F08·F02 패링 → 복귀 뒤 그로기 1.5초, 그로기 중 hit 표시 | A | PARRY 사례: `groggy applied deadline=490.504`, 몬스터 `STUN|aec950`(hit 클립) 489.021 → `IDLE` 490.529 = **1.508초**, 그로기 중 hit 표시 | PASS |
| V07 팝업 정지·재개(공격 간격 타이머 포함) | A | 실제 `_UIPopup:Open`: `CombatPause server paused=true clock=449.112`, 몬스터 `attackTimer` **2.48 고정 ≥9초**(전투 시계 449.11 고정), 취소 핸들러 호출 뒤 `paused=false` → 타이머 2.49→2.97, 3.0에서 예고 시작. 예고 중 팝업 정지·재개는 이번에 실행하지 않음 | PASS(간격 타이머) / NOT_RUN(예고 중 팝업) |
| V08 Stop 뒤 다음 Play 기본 상태 | A | 위 "Stop → 다음 Play" 행. 시험 중 만든 Play 내부 값(창 30초·단일 패턴·AttackInterval 9999)이 다음 Play에 없음 | PASS |

#### 추가 항목 (a)·(b) 와 기타 관찰
- **(a) 예고 없을 때 ↓ 홀드의 `[VRF] PlayerGuard start`**: **재현되지 않음.** 몬스터 AttackInterval을 9999로 올려 예고가 없는 IDLE에서 실제 DownArrow를 5번 눌렀다: 1500ms·100ms·300ms·1000ms(Play 1, 모두 `PlayerGuard start x=0.000`이 남음)와 Play 3 부팅 직후 첫 입력 800ms(전투 시계 0.406, 첫 예고보다 먼저 → `PlayerGuard start x=0.000 t=0.406`). 기록한 값(Play 1 1500ms): 클라이언트 `GUARD|held=GUARD|src=key.DownArrow`, 서버 `GUARD|g=true|gT=175.281|gX=0.0`, 키를 놓으면 클라이언트 `IDLE`·서버 `g=false`(gT는 이전 시각 유지 = 설계, 사망·팝업·정지 때 `ClearStart`로 삭제). 이미 GUARD 상태에서 재홀드한 사례 아님(매번 IDLE에서 시작). 소스 근거: PlayerStateControl.RequestChangeState(IDLE에서 `ChangeState("GUARD")`, 예고 조건 없음) → Player_Guard.OnEnter(서버) → PlayerGuardComponent.SetGuarding(true) 로그. 코드에 예고 유무로 막는 분기가 없다. 본 관찰의 가능한 원인: Play 2에서 `maker_play` 직후 곧바로 보낸 입력이 기록되지 않았다(같은 순간 `maker_get_context_keys`가 "Not in play mode"로 아직 Play가 준비되지 않았음을 보였고, Play 3에서 컨텍스트 확인 뒤 보낸 첫 입력은 기록됨). 이전 QA8의 같은 관찰도 입력 시점이 Play 준비 전/중이었을 가능성이 있으나 확인하지 못했다. **분류: 결함 후보 아님, 재현 불가. 설계 의도 질문 없음.**
- **(b) 실제 HP 0 플레이어 사망**: Play 2에서 실제 `DownArrow` 홀드(`PlayerGuard start x=0.000 t=123.712`)와 `LeftArrow` 탭(`PlayerEvade start x=0.000 t=124.541`)으로 시작 위치 기록을 만든 뒤(`gX=0.0 gT=123.71 evX=0.0 evT=124.54`) 서버에서 Hp를 20으로 낮추고 자연 공격만으로 사망시켰다. Hp 20→8→**−4**(두 번째 공격 12), 약 1초 뒤 `DEAD|dead=true`, 이때 `gX=nil gT=-1.00 evX=nil evT=-1.00`(**시작 위치·시각 기록 삭제**), `CombatCore duel player=none`. 5.0초(RespawnDuration) 뒤 `Hp=1000|MaxHp=1000|IDLE|dead=false`(**부활 Hp = MaxHp 1000**), 대결 재개, 이후 자연 공격 12씩(1000→988…). 클라이언트도 `Hp=1000|MaxHp=1000|IDLE`. → **PASS.** 관찰: 사망 직전 Hp가 −4로 내려간다(네이티브 PlayerComponent, 이전부터 알려진 범위 밖 관찰: 사망 직후 HP 문자 음수 표시 가능성).
- **↑ 100ms 탭 관찰(coder)**: 이번 변경과 무관해 보인다. 재현: 100ms 탭 **한 번**은 시전됨(Play 1, `manual cast id=15`, 클라이언트 `ATTACK`이 0.83초(= FrameCount 14 × 0.06) 유지 뒤 `IDLE`). 같은 블록으로 곧바로 보낸 두 번째 100ms 탭은 시전되지 않았다 — ATTACK 중에는 `PlayerStateControl.RequestChangeState`가 `state.CurrentStateName ~= "IDLE"`이면 거부하는 기존 규칙("먼저 수락한 한 동작만, 입력 예약 없음")이고 PlayerStateControl·Player_Attack·PlayerCombatComponent는 9eed765 대비 변경 파일에 없다(`git diff --stat HEAD~1 HEAD`: 변경 4개 .mlua는 CombatRuleCatalog·MonsterManager·PlayerHealthComponent·PlayerMoveComponent). 3탭 연속(100/100/250ms)에서 시전 2회가 난 것도 같은 잠금으로 설명된다. 판정: 설계 규칙의 정상 동작, 결함 아님.
- 시험 오류(제품 오류 아님): (1) 첫 server 프로브에서 `MonsterManager`를 맵 엔티티에서 찾아 `mm` nil(LEA-2007 서버·클라이언트 각 1건). (2) `DoSpawn` 직후 `mm.CurrentPlayer`가 nil(스폰이 대결을 초기화)이라 가드 시험 첫 스크립트가 중간에 멈췄고 패턴을 복원하지 못해 Hp 변화가 기록되지 않아 같은 시험을 `_UserService.UserEntities`로 플레이어를 잡아 다시 실행했다(본문은 재실행 값). (3) F13 끝 칸 첫 시도는 `LEFT` 응답 + 앵커 1~1 행이 제품의 "telegraph escape area invalid" 검증에서 거부돼 공격이 시작되지 않았고 `[Monster_Attack] Battle position missing` 경고가 6건 났다(시험 행 오류, 시험 행 복원 확인). (4) 클라이언트 모니터 스크립트가 두 번째 클라이언트 스크립트 실행으로 중단됐다(한 컨텍스트에 스크립트 하나). (5) `maker_logs(kind=build)`를 한 번 그대로 호출해 큰 출력이 문맥에 들어왔다(시험 결과 영향 없음).
- 로그 요약: 정상 구간의 Warning·Error 0. 경고는 모두 내 무효 데이터 프로브·무효 CSV 시험·잘못된 시험 행이 의도적으로(또는 시험 오류로) 낸 것이며 제품 경로의 예상 밖 Error·Warning 없음(위 시험 오류 (1)의 LEA-2007 2건은 내 프로브 코드).

#### ExecSpace·구현 대조 (소스 읽기, 런타임 PASS와 구분)
- 몬스터 값(MaxHp·AttackDamage·AttackInterval)은 서버 `MonsterManager.DoSpawn`(ServerOnly)이 쓰고 서버 로그에만 `MonsterStat applied`가 남으며 클라이언트는 `@Sync` 값을 읽는다. 플레이어 HP는 서버 `PlayerHealthComponent.OnBeginPlay`(ServerOnly), 이동·복귀 속도는 클라이언트 `PlayerMoveComponent.ApplyBaseStats`(ClientOnly)가 쓴다. 두 쪽이 같은 표를 각자 읽는 것이 로그의 `side=server`·`side=client`로 확인됨. `.mlua` 속성 기본값 중 이동 속도(MoveSpeed 9로 변경 시 반영)와 몬스터 모델 값(주황버섯 MaxHp 100, MaxHp 150으로 변경 시 150 반영)은 CSV 변경 반영으로 DataSet이 이김을 확인했다. **정정(2026-11-05):** 이 문장의 앞 판본은 DefaultPlayer 모델 maxHp 1000까지 같은 시험으로 확인했다고 읽힐 수 있었으나, 몬스터 MaxHp 150 시험은 플레이어 MaxHp의 근거가 아니다. 플레이어 MaxHp는 모델 maxHp·엔진 기본값·DataSet이 모두 1000이라 그 시험만으로는 DataSet이 이기는지 알 수 없었고, 아래 "보충 시험 1"(default MaxHp 800)이 그 근거다.
- 변경 4개 .mlua + 새 5경로 외 제품 파일 변경 없음(`git diff --stat HEAD~1 HEAD` 확인: 모델·맵·UI·기존 CSV 5종·기존 .userdataset 변경 없음).

#### NOT_RUN (PASS로 세지 않음)
1. HP 바 육안·스크린샷(값만 확인). 2. 사람 손 기본 0.20초 타이밍(F13은 판정 창을 30초로 넓힌 시험값, 회차 A V11에서 사용자 수락 이력 있음). 3. 모바일·실기기·터치, 다중 접속. 4. V07 예고 도중 팝업 정지·재개 전수(간격 타이머 정지·재개만 실행), 사망 경로별 팝업 조합. 5. F06 `parry.right` 대칭 착지, F10 4패턴 각각의 실제 출현 빈도 통계. 6. 실제 다른 맵 전환에서의 위치 기록 삭제. 7. 플레이어 표 실패 시 서버만/클라이언트만 실패하는 비대칭 상황. 8. DataSet을 Maker UI에서 직접 수정하는 경로.

#### 사용자 직접 확인 항목 (Plan §20 사용자 V11)
- 이동·복귀 체감이 회차 A와 같은지(값 6 그대로, 시험 로그의 elapsed 0.24초는 수치 근거일 뿐 체감 평가가 아님).
- 원하면 `PlayerBaseStatData.csv`의 MoveSpeed를 직접 바꾸고 Maker Refresh → Play로 속도가 바뀌는지, 표·열 이름이 고치기에 알아보기 쉬운지.
- 몬스터 HP·공격력·공격 간격도 `MonsterStatData.csv` castleenemy 행으로 고칠 수 있는지.
- 공격 간격 3.0은 "IDLE 대기 3.0초 + 공격 약 1.0초 = 시작~시작 약 4.0초"로 동작한다(전과 동일). 사용자가 말한 "공격 간격"이 어느 쪽인지 체감 확인.

#### reviewer가 알아야 할 근거의 한계
- 중단된 Play 1의 원본 로그는 남아 있지 않고 값만 이 기록에 옮겨 적었다. Play 2~5는 로그 파일로 재확인 가능하다.
- F13·V07은 시험값(판정 창 30초 등)과 프로브 근거가 섞여 있다. 사용자 손 타이밍·실기기·다중 접속은 없다. 팝업 닫기는 취소 핸들러 호출이다. 클라이언트가 실제로 그리는 화면은 보지 않았다(스크린샷 없음).
- 범위 밖 재저장: Stat.directory(StudioVersion 한 줄). 되돌리거나 커밋에 넣을지는 메인 결정.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 시작·끝 59/59·54/54 동일 Bundle(9325c33a…cd19 / a8c96297…c5d), 제품 파일 무수정, CSV 2종 byte 원복. Maker 사용 종료. commit·push 하지 않음.

#### QA9 보충 시험 1 — 플레이어 MaxHp를 DataSet이 실제로 정하는가 (2026-11-05, 같은 버전 1b4f4ee, reviewer WAITING 사유 대응)
- 사유: 리뷰가 지적한 대로 플레이어 MaxHp는 DefaultPlayer 모델 maxHp·엔진 PlayerComponent.MaxHp 기본값·DataSet이 모두 1000이라 앞 QA9에서는 DataSet 값이 이기는지 근거가 없었다(위 정정 문장).
- 대상·지문: 1b4f4ee, 59경로 Bundle 9325c33ade8a2c32c058cb7e4050a82f8b44d9f22dcfe68c82874cd3e23bcd19가 **시험 전·시험 변경 중이 아닌 시점(CSV 원복 뒤)·끝** 모두 같다(CSV 시험 값이 들어가 있는 동안은 계산하지 않음, 원복 뒤 계산). 제품 파일 수정 없음, commit·push 없음, maker_clear_logs 호출 없음, Stat.directory 그대로(범위 밖 재저장 상태 유지). Play 2회(시험 Play 1, 원복 확인 Play 1).
- 시험 변경: `PlayerBaseStatData.csv`의 `default` 행만 `default,1000,6,6` → **`default,800,6,6`**(BOM·CRLF 보존, MonsterStatData는 건드리지 않음). Refresh → Play.
- 결과(서버·클라이언트 각자 읽음, 모델 maxHp는 그대로 1000):
  | 기준 | 실제 결과 | 판정 |
  | --- | --- | --- |
  | 로드·적용 | 서버 `PlayerBaseStatData side=server default MaxHp=800 … source=DataSet`, `PlayerStat applied MaxHp=800 Hp=800 source=DataSet`, 클라이언트 `side=client default MaxHp=800 …` | PASS |
  | 서버·클라이언트 MaxHp와 시작 Hp | 서버 `PlayerComponent.MaxHp=800`(시작 Hp 800, 첫 자연 공격 뒤 776·764), 클라이언트 `MaxHp=800 Hp=776`. 모델 maxHp 1000·엔진 기본 1000이 아니라 **DataSet 값 800**이 쓰임 → DataSet이 실제로 이김 | PASS |
  | HP 바 | 스크린샷 2장(`maker_screenshot`, 558×314): 사망 직전 Hp 8일 때 좌측 HP 바가 "…/ 800" 형식으로 표시되고 최댓값 칸이 800으로 읽힘, 부활 뒤(Hp 약 776) 바가 다시 거의 가득 찬 상태에서 "…/ 800". 우측 상대 바는 100/100. 해상도가 낮아 자릿수 자체는 확정하지 못함(최댓값 800과 채움 비율은 읽힘). 값 판정은 위 로그가 근거 | PASS(값) / 화면 자릿수는 제한적 |
  | 실제 HP 0 사망 | 서버에서 Hp를 20으로 낮춘 뒤 자연 공격만으로 사망: `Hp=20→8→-4`, 클라이언트 `DEAD|dead=true`, `CombatCore duel player=none`(Play 내부 시험값 Hp 20, 사망은 실제 피해 경로) | PASS |
  | 부활 뒤 Hp·MaxHp | 5초 뒤 서버·클라이언트 모두 **`Hp=800|MaxHp=800|IDLE`**(14:13:20), 대결 재개, 이후 자연 공격 12씩(788…). **1000으로 돌아간 값은 사망·부활 과정 어디에도 없음** | PASS |
- **1000으로 돌아가는 경로**: 하나도 관찰하지 못함(시작·사망·부활·부활 뒤 피해 모두 MaxHp 800 유지). 결함 후보 없음. 소스 읽기상으로도 MaxHp를 쓰는 곳은 PlayerHealthComponent.OnBeginPlay(서버) 한 곳이다. 다만 이 시험은 사망→같은 Play 안 자동 부활까지이고, 다른 맵으로 옮겼다 돌아오는 경우(OnBeginPlay 재실행 여부)나 접속 재입장은 하지 않았다(NOT_RUN).
- 원복: Stop → 백업 복사로 CSV 복원 → sha256 `PlayerBaseStatData.csv 3202ac06b9ebf31c13d73a2eb343ab788f5393e8b7f8255a36ad3efa815ed094`(변경 전·리뷰 기재와 **일치**), MonsterStatData.csv `f9709bd8…1dc3`, PlayerBaseStatData.userdataset `f6d8da25…5d7f` 불변. Refresh → Play: 서버 `PlayerStat applied MaxHp=1000 Hp=1000`, 클라이언트 `MaxHp=1000`(Hp 988은 자연 공격 뒤 값) → **1000으로 복귀 확인**. 경고·오류 0. 끝 git status는 run.md·WorkRecord(이 기록)·Stat.directory(범위 밖 재저장)뿐.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료.

### 2026-11-04 독립 QA 8회차 — 회차 A(V11-F12·V11-F13) — 중단(사용자 일시정지)
- 상태: **중단(사용자 일시정지) 뒤 같은 날 재개·남은 NOT_RUN 실행 완료(아래 "QA8 재개" 소절이 최신)**. 사용자 요청("작업 일시 정지")으로 진행 중이던 위치 기록 삭제 단계(D1)만 마무리하고 새 시험은 시작하지 않았다. 아래에 실제 실행한 기준만 결과를 적고 나머지는 NOT_RUN이다. FAIL·결함 없음. 독립 reviewer 대기가 아니라 **재개 뒤 남은 NOT_RUN 실행이 먼저**다.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 `[TQ8S]`·`[TQ9S]`·`[TQ10S]`·`[TQ11S]`·`[TQ12S]`·`[TQ13R]`·`[TQ13D]`(서버)·`[TQ8C]`(클라이언트) 표지와 시각으로 파일에 저장해 걸러 읽음). 시험이 만든 반복 타이머는 없다(`wait` 루프만 사용, 클라이언트 모니터는 마지막에 빈 스크립트로 중단). LEA-3051 없음.
- 대상 버전: coder 커밋 7f2d0b4 / 작업 트리 54경로 Bundle SHA-256 **b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f**(= 커밋 + 미커밋 Maker 재저장 3경로 AssistModel·AttackSkillData userdataset·주황버섯 모델, 건드리지 않음). 경로는 coder 절(V11-F06 표) 54경로를 이름으로 모아 ASCII 정렬, 각 줄 `경로\t해시\n`의 SHA-256. **시험 시작과 끝 모두 같은 값**(54개 경로별 해시 목록 diff 일치). 같은 방법으로 7f2d0b4 **커밋 트리** 값은 `7f32ae45d37aa6613db2c8de1c56ede5e0915fb5d0e0c34abb12a63340ce21e3`이다(Maker 재저장 3경로가 커밋과 달라 작업 트리 값과 다름이 정상). 시작·끝 git status는 Maker 재저장 3경로(M)와 메인·planner 문서뿐.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 다시 읽지 않았다. Refresh 하지 않음(파일 무변경). build 로그 81건 모두 Info(오류 0·경고 0, coder와 같은 건수). **Play 1회 연속**(약 18분, 14:13~14:32), Stop 1회. Warning 로그 2건은 모두 내 프로브가 만들었다: `[CombatRuleCatalog] pattern model missing: x`(첫 정보 프로브의 지역 변수 오류), `[Monster_Attack] Battle position missing`(S9에서 죽은 몬스터에 일부러 ChangeState("ATTACK")를 호출한 프로브). 제품 경로의 Error·Warning 없음. 최종 Stop 뒤 map01 / edit.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트에서 한 번에 스크립트 하나만 돈다). 서버·클라이언트가 같은 `_UtilLogic.ServerElapsedSeconds` 시계를 써 같은 시간축이다. 클라이언트 모니터는 몬스터 엔티티의 `SpriteAnimPlayerChangeFrameEvent` 프레임 번호와 렌더러 `SpriteRUID`/`StartFrameIndex`/`EndFrameIndex`/상태를 기록했고, 서버 프로브는 같은 값을 0.02초 폴링했다. 사망은 서버 `MonsterHealthComponent:ApplyDamage(999)`(제품 사망 확정 경로 그 자체)로 일으켰다. (B) 실제 키 입력 = maker_keyboard_input DownArrow 홀드·LeftArrow/RightArrow 탭(2.5~4.5초)·UpArrow 탭. 도구 왕복이 수 초라 판정 창을 손으로 맞출 수 없어 **시작 위치·시각을 강제한 사례는 "프로브 근거", 실제 키 사례는 판정 창을 넓힌 "시험값"**으로 구분했다. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(320,165)~(420,225)의 평균 절대 RGB 차이/최대값(Pillow). (D) 팝업 = 실제 `_UIPopup:Open`과 취소 핸들러 `OnClickCancel` 호출(마우스 클릭이 아님).
- 시험 한정 값(모두 Play 내부, Stop으로 폐기): 몬스터 `AttackInterval` 9999, 패턴 목록 단일 행 교체(`TelegraphLeadSec` 1.0~8.0, 속성·유형·대상 칸 지정), `math.random` 일시 교체(RANDOM 칸 고정, 호출 후 즉시 복원), 플레이어 HP 보충, 강제 시작 위치·시각(`SetEvading`/`ChangeState("GUARD")` 뒤 `_T.evadeStartX`/`guardStartX`·시각 덮어쓰기), 판정 창 **ParryWindowSec 40(R1 실제 ↓ 홀드 시험)·JustWindowSec 3.0·CounterWindowSec 8.0(K1b~K3 실제 ←/→ 시험, 이유: 실제 키로 0.20초 창에 맞출 수 없고 접근 점프 0.5초 때문에 선행 시간이 0.5초 이상)**, K4부터 JustWindowSec 0.2·ParryWindowSec 0.2·CounterWindowSec 2.0으로 복원(로그로 확인), F12 참조 화면용 렌더러 강제(프레임 고정·PlayRate 0), 서버 MOVE 순번 재정렬(아래 시험 오류). 모두 Stop으로 폐기. **Stop 뒤 다음 Play 기본값 재확인은 하지 못했다(NOT_RUN).**

#### V11-F12 — die 1회 재생 후 마지막 프레임 정지
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 8개 사망 경로(S1 IDLE, S2 ATTACK 시작 직후, S3 점프 중, S4 착지 대기(예고 4초 중 1.6초), S5 복귀 점프 중(판정 뒤 0.2초), S6 HIT, S7 슬로우 중(PlayRate 0.5), S8 그로기(STUN) 25초 중)의 서버 렌더러 | A | 모두 사망 +0.05~0.09초에 `65a2bf…\|0/2147483647\|DEAD`(die 첫 프레임부터), +0.40~0.49초에 `65a2bf…\|2/2\|DEAD`로 정지. 서버 로그 `MonsterDie start frames=3 total=0.660 freezeAfter=0.360`→`MonsterDie freeze frame=2`(전투 시계 차 0.36~0.37초). 관찰창 7.5초 동안 서버 렌더러 변화 0건, END 시점 `s/e=2/2`·상태 DEAD·hp 0. S7은 사망 직전 PlayRate 0.5가 사망 후 첫 폴링에서 1.0(복원)이었다 | PASS |
| 같은 8경로의 소유 클라이언트 프레임 시계열 | A | 사망 시점 기준 die 프레임 0@+0.06~0.08 → 1@+0.21~0.27 → 2@+0.38~0.44초가 한 번(지연 0.18·0.18초와 일치), 정지 시 프레임 2 이벤트가 한 번 더 나온 뒤 **1초 이후 프레임 이벤트·렌더러 변화 0건**(경로별 7.5초 창 전부). 클라이언트 렌더러 값은 마지막에 `65a2bf…\|2/2\|DEAD`. 슬로우(S7)도 기본 속도 간격(0.18/0.19초)으로 한 번 | PASS |
| 정지 뒤 서로 다른 세 시점 이상 스크린샷 | C | 살아 있는 stand 화면과 정지 뒤 4장(사망 후 약 5초 두 장(0.07초 간격)·약 19초·약 33초)의 몬스터 영역: 정지 4장끼리 평균 0.000·최대 0(완전 동일), 살아 있는 stand와는 29.8/255. 읽은 장면은 눌린 die 마지막 모습(HP 0/100) | PASS |
| 재생 중과 다른 화면(참고) | C(렌더러 강제 참조) | 재생 중 장면은 0.36초라 캡처하지 못했고(팝업이 가림), 살아 있는 몬스터에 die RUID·PlayRate 0으로 **프레임 0**을 붙잡은 화면은 정지 화면과 23.2/255 다름. 프레임 1을 붙잡은 화면(StartFrameIndex=EndFrameIndex=1)은 정지 화면(프레임 2)과 0.000/0으로 **같다**(die 클립의 프레임 1·2는 같은 모습). 따라서 화면 픽셀로 구별되는 것은 첫 프레임 0.18초뿐이고, 재생·정지 증명은 프레임 이벤트·렌더러 값이 근거다 | PASS(근거 한계 있음, 관찰 3번) |
| 실제 UIPopup — die 재생 도중 열고 닫기 | A+D | 사망 +0.087초에 팝업 요청, 서버 전투 시계 424.468(die 시작 424.415)에서 정지, 약 12초 뒤 닫자 서버 정지 해제(시계 424.468 그대로) → 클라이언트 프레임 1@+0.16초·2@+0.17초 뒤 이어서 재생(**프레임 0 이벤트 없음, 처음부터 다시 시작하지 않음**), 서버 정지 전투 시계 424.788(= die 시작 0.373초)에 프레임 2 고정 | PASS |
| 실제 UIPopup — 정지 뒤 열고 닫기 | A+C+D | 사망 +0.36초 정지 뒤 +6.07초에 팝업(서버 정지 485.467), 19초 뒤 닫음: 렌더러 `2/2` 유지, 프레임 이벤트·렌더러 변화 0건, 닫은 뒤 스크린샷 두 장은 앞서 찍은 정지 화면과 0.000/0 | PASS |
| 추가 관찰(우연히 만든 조합): 팝업으로 정지된 상태에서 사망 | A | 내 모니터 오류로 팝업이 먼저 열린 상태에서 몬스터가 생성·사망(`MonsterHealth lethal state=DEAD enabled=false`). die 시작 시계 346.296에서 정지 중 시계가 흐르지 않았고, 닫은 뒤 프레임 1·2가 한 번 재생되고 시계 346.671에 고정 | PASS(참고) |
| 늦은 경로 — 사망 +0.155초와 +2.1~3.0초(S9, 프로브가 직접 호출) | A | +0.155초에 `SetVisualClip("die")`·`("stand")`·`("jump")`·`("stun")` 연속 호출, +2.1초에 `SetStunned(false)`·`ClearCombatEffects`·`CancelPendingAttack`·`ApplyGroggy(2)`·`ApplySlow(5,0.5)`·`CancelMotion`, +3.0초에 `JumpActive` 강제 뒤 `CompleteMotion`·`SetVisualClip("stand")`·`ApplyDamage(5)`: 서버·클라이언트 렌더러 `65a2bf…\|2/2` 그대로, 클라이언트 프레임 이벤트는 정상 한 번(0·1·2)뿐이고 추가 이벤트 0건. S2~S8은 제품 경로 자체(그로기 종료 `SetStunned(false)`→die 재호출(S8), 슬로우 복원(S7), 공격 취소·점프 완료·복귀 완료(S2~S5), HIT 복귀(S6))를 그대로 거쳤고 정지를 풀지 않았다 | PASS |
| DEAD·DeadEvent 1회·HP=HitEvent=숫자(F12 항목) | - | DeadEvent 횟수와 HitEvent 합계는 이번에 읽지 않았다. DEAD 상태·HP 0·IsDead true만 확인 | NOT_RUN(DEAD만 확인) |
| 사망 후 새 상대 stand 시작·Stop 뒤 다음 Play stand·정지 설정 잔존 없음 | - | 살아 있는 새 몬스터(DoSpawn)의 시작 렌더러는 `96e955…\|0/0\|IDLE`이고 클라이언트에서 stand가 프레임 0↔1로 정상 반복 재생(첫 맵 배치 몬스터는 `0/2147483647`). 이전 사망의 정지 값이 새 몬스터에 남은 사례 없음(8번 교체). **Stop 뒤 다음 Play는 확인하지 못했다** | PASS(DoSpawn 교체)·NOT_RUN(Stop 뒤 다음 Play) |
| 회귀: 살아 있는 동안 stand·jump 재생, 그로기 hit(F08), 2칸 중간 착지(F06), 복귀 뒤 그로기(F02) | A | stand 0↔1 반복, ATTACK 점프 클립(`94bbe2`)·stand 복귀를 클라이언트 모니터에서 확인. F13 PARRY 사례 10건(프로브 7·실제 ↓ 3) 모두 `sawStun=true`로 복귀 뒤 그로기 진입(F02). hit 클립 표시와 2칸 중간 착지 위치(x=±0.75)는 직접 측정하지 않았다 | PASS(stand·jump·F02 진입 대표)·NOT_RUN(F08 hit 표시·F06 착지 위치 측정) |

#### V11-F13 — JUST·PARRY 성공은 Pos2 시작 + 영역 Pos2 포함
기본 실행 x는 Pos1 -1.5·Pos2 0·Pos3 1.5, 패딩 0.5, 칸 경계 ±0.75. 사례마다 `[VRF] PlayerHealth evade/guard eval x=… cellOk=… areaOk=…`와 `[VRF] CombatCore defense` 로그를 같이 확인했다.
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 회피 20사례(프로브 근거: 시작 위치·시각·방향을 서버가 강제, 플레이어는 x=0에 서 있음, 창 0.20 안에서 판정 직전 입력) | A | E01 parry.left LEFT·E02 parry.right RIGHT·E03/E04 parry.any 최근접(Pos2) 좌/우·E05/E05b special.random 칸 2 좌/우 → **JUST**·피해 0·반격 권한 true·슬로우 true. E06 special.random 칸 1(영역 -2.0~-1.0)에서 멀어지는 방향·E07 칸 3·E17 패링 속성 1칸 칸 1·E19 입력 없음 칸 1 → **JUST 아님**, 영역 밖이라 네이티브 피격 없음 → 피드백 EVADE·피해 0·반격/슬로우 없음(QA5 K3b·QA7 E1 계열 기대가 JUST에서 바뀜). E08 시작 x +0.75·E09 -0.75 → JUST(경계 포함). E10 +0.76·E11 -0.76·E12 +0.80(parry.left)·E13 -0.80(parry.right) → JUST 아님, 영역 안이라 **HIT**·피해 12. E14 틀린 방향·E15 창보다 0.6초 일찍 시작·E16 시작 위치 기록 없음·E18 입력 없음 → HIT 12. 20건 모두 기대와 일치 | PASS(프로브 근거) |
| 가드 20사례(프로브 근거: 서버 `ChangeState("GUARD")`로 시작 기록 뒤 위치·시각 덮어쓰기) | A | G01 parry.left·G02 parry.right·G03 parry.any·G05 패링 속성 1칸 칸 2 → **PARRY**·피해 0·반격 권한·복귀 뒤 그로기 예약. G04/G04b 패링 속성 1칸 칸 1/3(영역이 Pos2 불포함) → PARRY 아님(결과 종류 GUARD), 영역 밖이라 피드백 EVADE·피해 0·그로기 없음. G06 x=+0.80·G07 -0.80·G09 +0.76·G09b -0.76 → **GUARD** 12×0.40=4.8→4. G08 +0.75·G08b -0.75 → PARRY(경계 포함). G10 special.random 칸 2 → **UNGUARDABLE**·원래 피해 12, G10b 칸 1(영역 밖) → 피드백 EVADE 0. 시험 데이터(가드형 3칸, Pos2 포함): G11 NORMAL → GUARD 4, G12 PARRY 속성 → PARRY, G13 같은 행 x=+0.80 → GUARD 4. G14 가드 시작 0.5초 전(창 밖)·G15 시작 위치 기록 없음 → GUARD 4. G16 일반 속성 ANY → GUARD 4. 20건 모두 일치. PARRY 7건 모두 복귀 뒤 `sawStun=true` | PASS(프로브 근거, 가드형 3칸은 시험 데이터 근거) |
| 실제 DownArrow 홀드(시험값 ParryWindowSec 40, 서버 GUARD 상태·시작 x=0.000 기록) 6사례 | B+A | R1a parry.left·R1b parry.right·R1c parry.any → **PARRY**·피해 0·반격·그로기. R1d 패링 속성 1칸 칸 1 → 결과 GUARD, 피드백 EVADE 0·그로기 없음. R1e special.random 칸 2 → **UNGUARDABLE** 12. R1f 가드형 일반 3칸 → GUARD 4. 6건 일치 | PASS(시험값) |
| 실제 LeftArrow/RightArrow(시험값 JustWindowSec 3.0) JUST | B+A | K1b LeftArrow + parry.left·K2 RightArrow + parry.right → **JUST**·피해 0·반격 권한·슬로우(K1b `manual cast … factor=2.2`: 곧바로 **실제 UpArrow**로 반격 1회 소비 확인, count=10) . 판정 순간 플레이어는 이미 x=∓1.5(영역 밖, nativeHit nil)였고 시작 기록 x=0.000으로 성공 | PASS(시험값) |
| 실제 키: 끝 칸 홀드 겹침(H1) 및 창 밖 시작·홀드 해제 | B+A | K3 LeftArrow 홀드 + special.random 칸 1(영역 -2.0~-1.0, 판정 때 플레이어 -1.5): `areaOk=false` → **HIT**·피해 12. K4(기본 창 0.20, 선행 2.5초) LeftArrow + special.random 칸 3: 창보다 일찍 시작, 판정 때 영역 밖 → JUST 아님·**EVADE 0**. K5 LeftArrow 홀드 후 실제 키 해제(2.5초), 선행 5.0초, 칸 1: 판정 때 x=0.000(복귀) → EVADE 0 | PASS(K3은 시험값 창 3.0, K4는 기본 창 0.20, K5는 기본 창 0.20 상태로 실행) |
| 서버 기록 시작 x 대 클라이언트 segment.startX | B+A | 실제 LeftArrow/RightArrow 6건(K1 첫 실행·K1b·K2·K3·K4·K5)의 클라이언트 `MovementInput phase=OUTBOUND x=0.0`과 서버 `PlayerEvade start x=0.000` **차이 0.000**. DownArrow 1회 홀드(R1 6사례가 같은 홀드) 서버 `PlayerGuard start x=0.000`(클라이언트 이동 구간 없음). 서버가 MOVE를 감지한 뒤 0.1초 시점에 서버가 읽은 플레이어 x는 -0.59~-0.91로 이미 움직였지만 서버가 시작 기록을 남긴 순간은 0.000이었다. 정상 입력이 위치 때문에 거부된 사례 0건 | PASS(시료 6건, 단일 접속) |
| 위치 기록 삭제 — 팝업 닫기 | A+D | 예고(선행 8.0초) 중 회피 시작 x=0.12·시각, 가드 시작 x=0.34·시각을 심은 뒤 실제 UIPopup 열기: 정지 중 예고 남은 시간 6.127→(닫음)5.973(정지 중 보존), 정지 중 x 값 0.120/0.340 유지. 닫은 직후 `evX=nil evT=-1.0 gdX=nil gdT=-1.0`. 이어진 판정은 JUST·PARRY가 아닌 **HIT 12**(이전 시작 기록이 쓰이지 않음) | PASS |
| 위치 기록 삭제 — 플레이어 사망, Stop 뒤 | - | 실행하지 않음 | NOT_RUN |
| 회귀: 일반 가드 ×0.40, 특수 가드 UNGUARDABLE, 무가드 범위 안 HIT, 영역 밖 EVADE 0, 반격 소비·슬로우 | A+B | 위 가드·회피 사례 그대로(GUARD 4=12×0.40 내림, UNGUARDABLE 12, HIT 12, EVADE 0, 반격 ×2.2 소비 1회, 슬로우 true). 피해 숫자는 `hpDelta`가 기대값(12·4·0)과 일치한 것으로만 확인(HitEvent 합계는 읽지 않음) | PASS(대표) |
| 회귀: 예고 중 팝업(정지·재개), 패링 뒤 그로기 대표 | A+D | 위 팝업 사례에서 예고 정지·재개 확인. 그로기는 복귀 뒤 진입 10건 확인 | PASS(대표) |
| 회귀: HP=HitEvent=숫자 직접 비교, parry.any Pos1·Pos3 홀드 끝 칸, Stop 뒤 다음 Play 기본값 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 결함: **없음**. FAIL·NEEDS_DECISION 없음. 새 결함 ID 없음.
- 시험 오류(제품 오류 아님): (1) **K1 첫 실행은 MISMATCH였으나 시험 오염**이다. 내 강제 시험이 `SetEvading(true)`를 약 40번 호출해 서버 `PlayerEvadeComponent._T.moveEpoch`가 19까지 올랐고 소유 클라이언트의 실제 MOVE 순번은 1이어서 `ConfirmDirection`이 방향 순번 불일치로 거부됐다(`dir=` 빈 값, 두 값을 읽어 확인: 서버 19/클라이언트 1). 서버 순번을 클라이언트에 맞춰 1로 되돌린 뒤 같은 사례를 K1b로 다시 실행해 JUST가 나왔다. K1 첫 결과는 과거 시험 오류로 남긴다(제품 코드 변경 경로 아님, 이번 버전이 바꾼 영역도 아님). 이후 사례(K1b~K5)의 `[VRF] PlayerHealth evade eval … dir=LEFT/RIGHT`로 방향 확정 확인. (2) 첫 팝업 시험에서 클라이언트 모니터가 이전 사망 몬스터를 보고 먼저 팝업을 열어 의도한 "사망 +0.03초 팝업"이 아니라 "정지 상태에서 사망" 조합이 됐고, 감시 대상을 새 몬스터로 바꿔 다시 실행했다(위 두 행). (3) 첫 정보 프로브의 지역 변수 범위 오류로 `pattern model missing: x` 경고가 한 건 났다. (4) 프로브의 "재생 중 화면" 참조는 StartFrameIndex=EndFrameIndex=0이 "전체 클립"과 같은 기본값이라 프레임 0을 고정하지 못했고(루프 재생), PlayRate 0 방식으로 다시 찍었다.
- 관찰(바꾸지 않음, 판정은 reviewer): (1) 맵 배치 몬스터의 시작 렌더러는 `0/2147483647`, DoSpawn 몬스터는 `0/0`이다(coder 관찰과 같은 기존 현상, stand는 0↔1 정상 재생, 사망 때 PlayDieOnce가 `0/2147483647`로 정리). (2) die 클립의 프레임 1과 2가 화면상 같아서 화면 픽셀로는 "재생 중"을 거의 구별할 수 없다(프레임 0 0.18초만 다름). (3) 죽은 몬스터에 프로브가 `StateComponent:ChangeState("IDLE"/"HIT"/"ATTACK")`을 직접 호출하면 엔진이 전환을 허용해 상태가 IDLE로 바뀌었다(제품 코드는 모든 경로에서 IsDead를 확인해 이 호출을 하지 않음, 이번 변경 밖). 그때도 렌더러는 die 2/2 그대로였고 프레임 이벤트가 새로 생기지 않았다. (4) 시료 크기: 실제 키 위치 차이 6건(단일 접속)·강제 사례 40건.
- 한계: 판정 창을 넓힌 시험값(위)으로 방향·유형·결과 종류를 확인했고 0.20초 손 타이밍은 K4(기본 창, 창 밖 시작) 한 사례뿐이다. 재생 중(0.36초) die 화면의 캡처와 사람 육안 평가 없음. 팝업 닫기는 취소 핸들러 호출. 클라이언트가 실제로 그리는 클립을 읽는 API가 없어 렌더러 값·프레임 이벤트·스크린샷이 근거다. 단일 접속·Maker 환경. 서버 지연이 큰 환경에서의 위치 기록 오차는 미확인.

#### NOT_RUN(재개 뒤 실행할 것)
1. F12: 사망 경로별 팝업(재생 중·정지 뒤)은 IDLE 경로 한 건만 실행(나머지 경로 조합 NOT_RUN), 실제 UpArrow로 그로기 중 처치, DeadEvent 1회·HP=HitEvent 합계 직접 비교, **Stop 뒤 다음 Play에서 stand 시작과 정지 설정 잔존 없음**, F08 hit 표시·F06 2칸 중간 착지 위치 측정.
2. F13: **플레이어 사망 뒤 위치 기록 삭제**, **Stop 뒤 위치 기록·시험값 기본 복원**, parry.any Pos1·Pos3 홀드 끝 칸 실제 키, HP=HitEvent 합계 직접 비교, 사람 손 0.20초 타이밍.
3. 사용자 V11: die 한 번 재생·끝 모습 정지의 육안(그로기 중 처치·팝업 뒤·모바일), Pos2에서 가운데 칸 공격에만 저스트·패링이 나는 체감과 끝 칸 1칸 공격(특수 무작위) 무보상 난이도. 그 밖의 기존 V11 미확인 항목(모바일·터치·음향·반격 체감·CF-F07).
- 사용 종료: maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 시작·끝 54/54 동일 Bundle b321d71c…040f, 제품 파일 무수정. Maker 사용 종료. commit·push 하지 않음.

#### 2026-11-04 QA8 재개 (사용자 일시정지 해제 뒤, 같은 버전·남은 NOT_RUN 실행)
- 상태: **재개 실행 완료.** 위 NOT_RUN 1~2번 중 사람 손 0.20초 타이밍과 HP 0 실제 플레이어 사망을 뺀 항목을 실행했다. FAIL·결함 없음, 새 결함 ID 없음. 다음은 reviewer 판정과 사용자 V11 확인이다.
- 담당: Claude Code msw-tester(coder와 별도 실행, 앞 QA8 실행과도 별도 세션). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. **maker_clear_logs 호출 없음**(큰 로그는 파일로 저장된 것을 `[TQ8…]`·`[TQ9…]`·`[VRF` 표지와 시각으로 걸러 읽음). 이전 QA8·coder 절의 PASS는 이번 재개로 다시 세지 않는다.
- 대상 버전: coder 커밋 7f2d0b4 / 작업 트리 54경로 Bundle SHA-256 **b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f**(= 커밋 + Maker 재저장 미커밋 3경로, 건드리지 않음). 커밋 트리(7f2d0b4) 값 `7f32ae45d37aa6613db2c8de1c56ede5e0915fb5d0e0c34abb12a63340ce21e3`. 같은 계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF)으로 **재개 시작과 끝 모두 같은 값**(54개 경로별 해시 diff 일치). 일시정지 커밋 bac801b는 문서만 바꿨다. 끝 git status는 Maker 재저장 3경로(M)와 run.md뿐.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따랐다. Refresh 하지 않음(파일 무변경). **Play 2회**(Play 1: 17:57~18:10 약 13분, Stop 1회, Play 2: 18:10~18:11), 마지막 Stop 뒤 map01 / edit. 두 Play의 모든 Maker 로그가 Info(전체 486건 중 Warning·Error·LEA·LWA 0건). 시험이 만든 반복 타이머 없음(`wait` 루프와 한 번짜리 타이머만 사용).
- 방법 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트 한 번에 스크립트 하나). 서버 헬퍼는 `_CombatRuleCatalog._T.TQ`에 두었고 Stop으로 폐기됐다(Play 2에서 nil). (B) 실제 키 입력 = maker_keyboard_input(UpArrow 탭, LeftArrow/RightArrow 긴 탭·탭, DownArrow 홀드). (C) 팝업 = 실제 `_UIPopup:Open`과 취소 핸들러 `OnClickCancel`(마우스 클릭이 아님). 시험 한정 값은 모두 Play 내부: 몬스터 AttackInterval 9999, 몬스터 최대 HP 40·100, 그로기 25~40초, 패턴 단일 행 교체(예고 1~40초), JustWindowSec 30(B3 한 사례), 플레이어 서버 상태 DEAD 직접 전환. 패턴 목록·창 값은 로그로 원복 확인(`patterns=4`, `JustWindow restored=0.20`).

##### V11-F12 재개 결과
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| Stop 뒤 다음 Play — 몬스터 stand 시작, 정지 잔재 없음 | A | Play 1 마지막 상태는 죽어 2/2로 정지한 몬스터였고 Stop 뒤 Play 2에서 서버 `96e955…\|0/2147483647\|IDLE`·PlayRate 1.0, 소유 클라이언트 프레임 0↔1이 0.18초 간격으로 3초에 16회(stand 정상 재생). 클라이언트 렌더러가 한 시점 jump 클립(94bbe2)으로 읽힌 것은 Play 시작 3초 뒤 첫 자연 공격의 점프이고 die 잔재(65a2bf/2·2)가 아님 | PASS |
| 그로기 중 실제 UpArrow 키로 처치 | A+B | 몬스터 최대 HP 40, 그로기 40초(STUN, hit 클립 aec950 유지). 실제 ↑ 5번 중 수동 시전 4회가 걸려 시전당 약 10타. HP 40→0, STUN 내내 `aec950` 유지(F08 hit 표시), 사망 순간 `65a2bf`(die) 0/MAX 시작 → 전투 시계 0.361초 뒤 `2/2` 고정, 25초 뒤에도 `2/2·DEAD` | PASS |
| DeadEvent 1회, HP 감소량 = HitEvent 합계 | A+B | 위 처치에서 `DeadEvent` 연결 카운터 1, 모든 폴링 행에서 `hp = 40 − hitEvents 합계`(예: hp19↔21, hp0↔40), 최종 HitEvent 합계 40 = 감소량 40, 사망 뒤 추가 피해 없음. 그 밖의 사망 시험(P1~P4, 아래)도 DeadEvent 각 1 | PASS |
| 사망 경로 × 팝업 — 점프 중 사망(P1) | A+C | 몬스터 ATTACK 시작 +0.2초 점프 중(`94bbe2\|ATTACK`) 서버 `ApplyDamage(999)` → die 시작 전투 시계 257.436. 소유 클라이언트가 첫 die 프레임 이벤트(프레임 0, 사망 +0.00초)에서 실제 `_UIPopup:Open` → 전투 시계 257.45에서 정지. 약 9초 뒤 취소 핸들러로 닫자 프레임 1(+8.85)·2(+9.02, 프레임 2 이벤트가 한 번 더 +9.04)로 **이어서 한 번** 재생(프레임 0 재시작 없음), 서버 고정 전투 시계 257.802(= 시작 +0.366), 15초 뒤에도 `2/2·DEAD`. 서버는 팝업 중 `0/MAX` 유지, 정지 중 기한이 흐르지 않음 | PASS |
| 사망 경로 × 팝업 — 착지 대기 중 사망(P2, 예고 4초 중 2초) | A+C | 사망 직전 `96e955\|ATTACK`(stand 클립). 같은 방식으로 프레임 0에서 팝업, 약 4.7초 뒤 닫음: 프레임 1(+4.69)·2(+4.86), 서버 고정 전투 시계 291.098(= 시작 290.723 + 0.375), 약 19초 뒤 `2/2·DEAD` | PASS |
| 사망 경로 × 팝업 — 그로기 중 사망(P3) | A+C | 사망 직전 `aec950\|STUN`. 프레임 0에서 팝업, 약 3.2초 뒤 닫음: 프레임 1(+3.21)·2(+3.39), 서버 고정 전투 시계 330.317(= 시작 329.949 + 0.368), 약 20초 뒤 `2/2·DEAD` | PASS |
| 팝업이 먼저 열린 상태에서 사망(HIT 상태, 서버 전투 시계 정지 약 90초) | A+C | 정지 중 사망·die 시작(시계 187.066) → 0/MAX 그대로 약 90초(기한이 흐르지 않음) → 닫자 프레임 1(+0.40)·2(+0.56) 한 번, 고정 시계 187.429(= +0.363), 이후 `2/2` 유지 | PASS(참고, HIT 경로 한 건) |
| 회귀: 그로기 hit 표시(F08) | A | 위 그로기 구간(B1·P3 사망 직전) 서버 `aec950\|STUN` | PASS |
| 회귀: 2칸 공격 중간 착지(F06) | A | 몬스터 시작 x=3.0, 예고 2.0초: parry.left(영역 −0.5~2.0) 착지 x=0.76(→0.75), parry.right(영역 −2.0~0.5) 착지 x=−0.75, 예고 판정 +2.03초 뒤 복귀 점프(x가 3.0 쪽으로 증가) | PASS |

##### V11-F13 재개 결과
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 위치 기록 삭제 — 플레이어 사망 | A+B | 예고 40초 중 **실제 LeftArrow 탭**(`PlayerEvade start x=0.000`)과 **실제 DownArrow 홀드**(`PlayerGuard start x=0.000`, 상태 GUARD)로 `evadeX=0.0 evadeT=42.877 guardX=0.0`을 만든 뒤 서버 `ChangeState("DEAD")`: 직후 `evadeX=nil evadeT=-1.0 guardX=nil`(상태 DEAD). 한계: HP 0에 의한 실제 사망(플레이어 HP 904 그대로)이 아니라 서버 상태 전환 | PASS(상태 전환 근거) |
| 위치 기록 삭제 — Stop 뒤 다음 Play, 기본값 복원 | A+B | Stop 직전 실제 LeftArrow 탭으로 `evadeX=0.0 evadeT=574.792`(guardX nil) → Stop → Play 2 시작: `evadeX=nil evadeT=−1.0 guardX=nil`, 시험 헬퍼 nil, 규칙 Parry 0.2·Just 0.2·Counter 2.0·GuardRate 0.4, 패턴 4행, AttackInterval 3.0. (참고: 예고가 없을 때의 DownArrow 홀드는 `PlayerGuard start`를 남기지 않았고 예고 중에는 남겼다. 이유는 소스를 더 읽지 않았다) | PASS |
| parry.any를 Pos1에서 실제 LeftArrow 홀드로 받기(A1) | A+B | 홀드 시작 직후 예고가 시작돼 가장 가까운 칸이 Pos1로 정해짐(`parry.any min=−2.0 max=−1.0 cells=100 target=1 dirs=R`). 판정 때 플레이어 x=−1.50(영역 안), 시작 기록 x=0.000이지만 시작이 판정 8.5초 전이라 창(0.20) 밖, `eval x=0.000 cellOk=true areaOk=false` → 피해 −12, 피드백 HIT, 저스트·반격 없음 | PASS(보상 없음, 끝 칸 겹침 = HIT) |
| parry.any를 Pos3에서 실제 RightArrow 홀드로 받기 | A+B | (A2) 예고는 Pos2(`min=−0.5 max=0.5`, 대상 칸 2)로 시작, 홀드 3초 뒤 Pos3(x=1.5)로 이동. 판정 때 영역 밖 → 피해 0, 피드백 **EVADE**(`eval x=0.000 cellOk=true areaOk=true dir=RIGHT`), 시작이 창 밖이라 저스트·반격 없음. (B2a 대칭) RightArrow를 먼저 홀드해 Pos3에 있는 상태에서 예고 → 대상 칸 3(`min=1.0 max=2.0 cells=001 dirs=L`), 피해 −12, `areaOk=false`, 보상 없음 | PASS(보상 없음) |
| 실제 키로 Pos1에서 새 회피 시작(추가 시험) | A+B | 대기: JustWindowSec 30(시험값)·parry.right 예고 12초, LeftArrow 홀드로 x=−1.5에 도착한 뒤 RightArrow를 3초 눌렀으나 새 회피 구간이 시작되지 않았다(`PlayerEvade start` 추가 없음, MovementInput OUTBOUND 추가 없음). 판정 때 x=−1.5 → 피해 −12 HIT. 값은 0.20으로 원복 확인 | PASS(정보: 실제 키로는 Pos2 밖 시작 회피를 만들 수 없음 — Pos2 밖 시작 거부 사례는 앞 QA8 강제 프로브 E10~E13이 근거) |
| 사람 손 기본 0.20초 타이밍 성공 사례 | B | 도구 왕복(수 초)과 탭 지연이 판정 창 0.20초보다 길어 자동 입력으로 재현하지 못했다. 앞 QA8의 기본 창 근거는 강제 프로브 20사례와 실제 키 K4(창 밖 시작)뿐 | NOT_RUN(사용자 V11 확인으로 넘김) |

##### 시험 오류와 관찰 (제품 오류 아님)
- 시험 오류: (1) 첫 팝업 시험 두 번은 클라이언트 모니터가 직전에 죽은 몬스터를 보고 먼저 팝업을 열었고(또는 한 번짜리 취소 타이머), 팝업이 열리면 클라이언트 시간 배율이 0이 돼 `wait`·`_TimerService` 취소가 돌지 않아 서버 시나리오가 전투 시계 정지 상태로 진행됐다. 그 실행의 P1~P3는 폐기하고(마지막 HIT 경로 한 건만 위 참고 행으로 사용) 취소를 별도 스크립트로 수동 호출하는 방식으로 다시 실행했다. (2) 로그 필터 정규식이 넓어 중복 출력이 있었다. 둘 다 제품 경로 변경 아님.
- 관찰(바꾸지 않음, 판정은 reviewer): (1) 프레임 2 이벤트가 정지 시점에 한 번 더(+0.01~0.02초) 나온다(앞 QA8·coder 관찰과 같음). (2) 정지 전 die 프레임 1·2가 화면에서 같아 화면 픽셀로는 재생을 구별하기 어렵다(앞 QA8 관찰). 이번에는 스크린샷을 새로 찍지 않았고 프레임 이벤트·렌더러 값으로 판정했다. (3) 플레이어 HP는 시험 도중 900대로 유지(이전 시험 값, 이번 변경 영향 없음).
- 한계: 단일 접속·Maker 환경, 팝업 닫기는 취소 핸들러 호출, 사망 정지의 실제 화면 육안과 사람 손 0.20초 타이밍은 사용자 몫. 위치 기록 삭제의 플레이어 사망은 서버 상태 전환 근거, 실제 맵 전환·HP 0 사망 미실시.

##### 남은 NOT_RUN (재개 이후)
1. 사람 손 0.20초 타이밍(사용자 V11). 2. HP 0 실제 플레이어 사망과 실제 다른 맵 전환에서의 위치 기록 삭제. 3. 파일 CSV 변경 반영, 실기기·터치·모바일, V12 외부 환경. 4. 사용자 V11: die 한 번 재생·끝 모습 정지 육안(그로기 중 처치·팝업 뒤·모바일), Pos2에서 가운데 칸 공격만 저스트·패링 나는 체감과 끝 칸 1칸 공격 무보상 난이도.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 시작·끝 54/54 동일 Bundle b321d71c…040f, 제품 파일 무수정. Maker 사용 종료. commit·push 하지 않음.

### 2026-11-03 독립 QA 7회차 — REV-F02·V11-F10·V11-F11·H1
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA와 coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·`[QA7S]`(서버)·`[QA7C]`(클라이언트)·`[QA7V]`(검증 프로브)·`[QA7W]`(선택 경계)·`[QA7M]`/`[QA7U]`/`[QA7H]`/`[QA7R]`/`[QA7G]` 표지로 파일에 저장해 걸러 읽음). 시험 스크립트는 `_TimerService` 타이머를 만들지 않고 `wait` 루프만 써 `LEA-3051`이 나지 않았다.
- 대상: coder 커밋 5c4eda3(기준 a921c76) / 작업 트리 54경로 Bundle SHA-256 fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80(= 커밋 + 미커밋 Maker 재저장 3경로, 건드리지 않음). 계산법은 coder 절 manifest의 54경로(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결). 경로 행은 표를 **이름으로 모아** 계산했고(coder 절이 늘어 줄 번호가 밀림) 시험 시작과 끝에 같은 값이며 두 계산의 54개 경로별 해시 목록도 `diff` 일치다. 시작과 끝 git status는 Maker 재저장 3경로(M)와 메인·planner 문서뿐이다.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. Refresh는 하지 않았다(파일 무변경, Maker 재저장 방지). build 로그 81건 모두 Info, 오류 0·경고 0(시험 전·후 같음). Play 4회(최초 Play 1회, Stop 뒤 재Play 3회), Stop 4회. 최종 Stop 뒤 map01 / edit. Maker 로그 시각 19:45~20:03. Error·Warning 레벨 로그는 시험 시간대에 [QA7V] 검증 프로브가 일부러 만든 CombatRuleCatalog 경고 13건뿐이다(14건 중 baseline 제외 13항목 각 1건). 19:36~19:40의 경고·LEA-3051 1건은 coder의 이전 Play 로그다.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트에서 한 번에 스크립트 하나만 돈다 — 새 스크립트가 이전 것을 멈춰 병렬 모니터는 서버/클라이언트로 나눴다). 서버는 `_UtilLogic.ServerElapsedSeconds`로, 클라이언트도 같은 시계로 기록해 시간축이 같다. 시험 헬퍼는 서버 `_CombatRuleCatalog._T.QA`와 클라이언트 `_CombatInputController._T.QA`에 두었고 Stop으로 폐기됐다(재Play에서 nil 확인). (B) 실제 키 입력 = maker_keyboard_input(DownArrow 가드·LeftArrow/RightArrow 이동·UpArrow 공격). 도구 왕복이 수 초라 판정 창 안에 손을 맞출 수 없어, **키 입력으로 시작·유지하는 시험은 서버 프로브가 플레이어 상태(GUARD/MOVE)를 감지한 직후 예고를 시작하는 방식**으로 했고 창 값은 시험 값으로 넓혔다. 타이밍이 중요한 해제(H1 홀드 떼기)는 실제 키 `down` 홀드 뒤 클라이언트가 입력 수락 지점 `PlayerStateControl:ReleaseHeldState`(키 해제 핸들러가 부르는 같은 함수)를 `TelegraphRemaining` 기준으로 호출했다 — 논리 경로 검사다. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(330,165)~(400,222)의 평균 절대 RGB 차이와 사람이 읽은 장면.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 마지막 재Play에서 기본값 확인: JustWindowSec 0.2·ParryWindowSec 0.2·CounterWindowSec 2.0·GuardDamageRate 0.4·AttackInterval 3.0·패턴 4행·Weight 2·2·2·1): `_CombatRuleCatalog.rules["default"]`의 Just·Parry 창 3.0(B·B2·C2·D·E·H1·PL·PR 실제 키 시험을 위해, LG는 Parry 0.1), CounterWindowSec 8(반격 소비 시험 한정), 단일 행 패턴 목록과 `TelegraphLeadSec`(0.6~6.0, 시험 행), `math.random` 일시 교체(한 번 호출 동안 고정 단위로 무작위 칸 고정, 즉시 복원), 몬스터 AttackInterval 9999·HP 5·`ApplyGroggy(25)`·`ApplySlow(8, 0.5)`·`ApplyDamage(999)`, 플레이어 HP 보충. CSV·제품 파일은 바꾸지 않았다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| REV-F02 IDLE 사망(실제 UpArrow) | A+B | HP 5, 서버 IDLE→실제 ↑ 공격(`manual cast`)→DEAD. 사망 +0.00·+0.2·+1.2·+2.5초 서버 SpriteRUID=ActionSheet die, 상태 DEAD, IsDead true, HP 0, paused false. (참고: 이 실행에서 클라이언트 프로브가 이전 몬스터의 사망을 보고 먼저 UIPopup을 열어 첫 ↑ 입력은 팝업 입력 차단으로 무시됐고, 팝업을 닫은 뒤 입력으로 처치했다. 순서 실수이며 입력 차단은 기대 동작) | PASS |
| REV-F02 ATTACK 시작 직후·점프 중·착지 대기·복귀 점프·HIT·슬로우+점프(S2·S3·S3b·S4·S5·S6, 서버 `ApplyDamage(999)`) | A | 모두 사망 시점(+0.00)부터 +0.2·+1.2·+2.5초까지 서버 clip=die, DEAD. 점프 중 사망은 몸이 y만 0.58로 낙하하고 x 고정. S6은 사망 때 PlayRate 0.5→1.0 복원, die 유지. 클라이언트 SpriteRUID·상태는 같은 몬스터에 대해 `DEAD\|die`로 한 번 바뀐 뒤 stand·jump·hit로 바뀐 줄이 없다(변경만 기록) | PASS |
| REV-F02 그로기 중 사망(실제 UpArrow, S7) | A+B | `ApplyGroggy(25)`로 STUN\|hit 유지 중 실제 ↑ → 클라이언트 STUN→HIT\|hit(타격 이벤트 1회)→DEAD\|die. 서버 +0.00부터 +8.0초까지 die, isStunned false | PASS |
| REV-F02 실제 UIPopup 열고 닫기 중·후 사망 표시 | A+C | S7 사망 +3.4초에 `_UIPopup:Open`(실제 코드, 서버 paused=true 승인) → 열린 동안 사망 +4.0·+6.0 서버 clip die·paused true → `OnClickCancel`(취소 버튼 핸들러) → `popup closed`, +8.0초 paused false·die 유지. 열린 스크린샷은 팝업이 몬스터를 가려 근거가 안 되고, 닫은 뒤 스크린샷은 눌린 die 프레임으로 읽힘(몬스터 영역 차이: die 기준 22.6, stand 기준 44.3. S1 처치 뒤 팝업 닫은 장면과 같은 값) | PASS(팝업 클릭은 마우스가 아니라 취소 핸들러 호출) |
| REV-F02 Stop 뒤 재Play stand 시작 | A+C | 사망(서버 DEAD\|die 확인) 뒤 Stop → Play: 서버 t=1.36초 IDLE\|stand·IsDead false·HP 100, 클라이언트 t=2.92초 IDLE\|stand, 재Play 스크린샷은 stand 계열(stand 기준 20.8·die 기준 44.5). 시험 값(규칙·창·AttackInterval·패턴 4행)도 기본으로 돌아옴 | PASS |
| V11-F10 로드(4행·AreaTarget) | A+파일 읽기 | CSV는 4행(`AreaTarget` 열 추가), normal.*·special.left·special.right·special.any 없음. 매 Play `[VRF] CombatCore catalog ready rules=1 patterns=4`. 런타임 행 id·ResponseType·속성·앵커·Weight 2·2·2·1·AreaTarget FIXED·FIXED·NEAREST·RANDOM | PASS |
| V11-F10 검증 거부(V09) | A | 실제 DataSet 행을 복사해 한 항목씩 변경한 ValidateRows 호출을 같은 입력 두 번씩: baseline ok/ok, AreaTarget 빈 값·BOGUS·nil, ANY+FIXED, LEFT+NEAREST, RIGHT+RANDOM, RANDOM 앵커 1/1, NEAREST 앵커 0/2, FIXED 앵커 0/0, FIXED 앵커 3/2, SPECIAL+GUARD, Weight 0, Weight abc, 선행 시간 < 창이 모두 REJECT/REJECT, 항목마다 경고 1건(두 번째 호출은 늘지 않음). 필수 열 누락(`ReadRows`에 없는 열 요구)은 nil(전체 거부). 거부 뒤 카탈로그 Ready true·4행 유지. CSV 파일 자체를 바꾼 열 누락 시험은 하지 않음 | PASS(CSV 파일 변경 NOT_RUN) |
| V11-F10 패턴 선택·무작위 칸 경계 | A | 합 7: 단위 0·1.999/7→parry.left, 2/7·3.999/7→parry.right, 4/7·5.999/7→parry.any, 6/7·0.9999999999→special.random(누적 [0,2)·[2,4)·[4,6)·[6,7), CSV 행 순서). 700표본 199/192/198/111. SelectRandomCell: 0·0.3·0.3333→1, 1/3·0.34·0.6666→2, 2/3·0.67·0.9999999999→3, 600표본 197/201/202 | PASS |
| V11-F10 RANDOM 칸·플레이어 위치 무관·예고 뒤 불변 | A | 플레이어 Pos2(x=0.0)일 때 난수 고정 0.1/0.5/0.9: 칸 1→영역 -2.0~-1.0·cells 100·유효방향 R, 칸 2→-0.5~0.5·010·LR, 칸 3→1.0~2.0·001·L, TelegraphAttribute SPECIAL. 예고 뒤 플레이어가 중앙→Pos3으로 움직이는 동안에도(E1) 판정 영역은 예고 때 값 -2.0~-1.0·cells 100 그대로. 예고 중 UIPopup(PU2: 칸 3, 영역 1.0~2.0)도 영역·cells 불변, 클라이언트 칸 표시 `3:[SPECIAL]`(1·2번 칸은 꺼짐), 팝업 중 남은 예고 시간 4.441→4.352(정지), 닫은 뒤 2.028로 재개 | PASS |
| V11-F10 special.random 판정(실제 키 입력 포함) | A+B | 무대응 범위 안(A·A2·플레이어 Pos2): HIT, 피해 12=HitEvent 12, HUD "피격". 범위 밖(C·C3: 칸 1·3, 플레이어 중앙): nativeHit nil, HP 0, HUD "회피". 실제 DownArrow 가드(창 3.0 시험값, 가드 시작이 판정 1.03초 전) 범위 안(B): UNGUARDABLE·rate 1, HP -12=HitEvent 12, 패링·슬로우·반격 권한·그로기 없음 → **↓ 패링 불성공**. 같은 시험값에서 PARRY 속성(B2, parry.any)은 실제 ↓로 PARRY·피해 0·반격 권한·그로기 → 시험값이 실제로 패링을 허용하는 상태였음(대조) | PASS(창 3.0은 시험값) |
| V11-F10 RANDOM 저스트·슬로우·반격 권한 | A+B | 실제 LeftArrow(칸 2, 범위 안 출발 E2): JUST·rate 0, 슬로우 2.0초 ×0.5(`slow applied duration=2.0 rate=0.5`), 반격 권한 ×2.2, HUD "저스트 회피 성공"+"반격 준비"+"상대 슬로우". 실제 RightArrow(칸 1, 범위 밖 중앙에서 출발 E1·E1b·E1c·E1d·E1e): JUST·rate 0, nativeHit nil, 같은 결과. 반격 소비(E1e): 반격 권한 부여 뒤 입력 수락 지점의 ATTACK 요청(논리 경로, 지연 때문에 실제 ↑ 3번은 창 안에 못 맞춤)이 `manual cast ... factor=2.2` | PASS(반격 소비는 논리 경로) |
| V11-F10 고정 칸 쪽 방향·중앙 복귀는 저스트 아님 | A+B | 칸 1에서 LeftArrow(고정 칸 쪽): evDir=LEFT, 결과 HIT(영역 안에 머무름)·JUST 아님(H1a·H1b). 칸 3에서 RightArrow도 HIT. 중앙 복귀는 홀드 뒤 떼기(H1e)에서 EVADE 0, JUST 아님 | PASS |
| V11-F10 parry.any 회귀(Pos1·Pos2·Pos3) | A+B | 실제 LeftArrow 홀드 Pos1에서 parry.any: 대상 칸 1·영역 -2.0~-1.0·유효방향 R(H1d). Pos2(B2): 칸 2·010·LR, 실제 ↓로 PARRY. 실제 RightArrow 홀드 Pos3(H1f-R): 칸 3·001·L, HIT 12=HitEvent 12 | PASS |
| V11-F10 parry.left·parry.right 회귀 | A+B+C | parry.left(실제 ↓ 가드로 PARRY): 클라이언트 관측 ATTACK\|jump(x 2.92)→착지 ATTACK\|stand x=0.75(영역 -0.5~2.0의 중앙)→판정(PARRY·피해 0)→복귀 ATTACK\|jump→**x=3.00 처음 위치에서** STUN\|hit 1.5초→IDLE\|stand. parry.right: 착지 x=-0.75(영역 -2.0~0.5의 중앙), 같은 흐름. F02 복귀 뒤 그로기·F08 그로기 hit·2칸 중간 착지 유지(parry.left 첫 실행 PL은 서버 모니터가 멈춰 판정 로그만 있고, PL2·PR을 클라이언트 모니터로 판정에 사용) | PASS |
| V11-F10 일반(NORMAL)·가드형(GUARD) 유형(시험 데이터 근거) | A+B | NORMAL 시험 행(parry.any 복사, 속성만 NORMAL, D): 실제 ↓ 가드 → GUARD·rate 0.4, 피해 4=HitEvent 4(12×0.4=4.8→4), HUD "가드 · 피해 경감". GUARD 유형 시험 행(속성 NORMAL, 앵커 1~3, FIXED): cells 111·영역 -2.0~2.0·유효방향 없음, 실제 ↓ 가드 → GUARD·0.4, HP -4. 실제 데이터에는 없음 | PASS(시험 데이터 근거) |
| V11-F11 가드 중 범위 안 "가드 불가" | A+B | 위 B: 실제 ↓ 가드 중 special.random 범위 안: `[VRF] defense kind=UNGUARDABLE rate=1`, nativeHit true, HP -12=HitEvent 12, 클라이언트 defenseText "가드 불가" 색 (1.00, 0.43, 0.36), 456.078→457.076초 약 1.0초 뒤 비워짐. 슬로우·반격·그로기 없음 | PASS |
| V11-F11 가드 중 범위 밖 "회피"·무가드 "피격"·일반 가드 문구 | A+B | 가드 중 범위 밖(C2, 칸 1): UNGUARDABLE이나 nativeHit nil → RecordDefense가 EVADE로 대체, HP 0, HUD "회피"(0.65, 0.83, 1.00). 무가드 범위 안(A2): HUD "피격"(1.00, 0.43, 0.36). 일반 가드(D): "가드 · 피해 경감"(0.65, 0.83, 1.00)·40%. 패링 속성 늦은 가드(LG, 창 0.1·가드 시작이 판정 2.05초 전): GUARD·0.4·HP -4. 패링 성공(B2·PL·PR): "패링 성공"(0.88, 0.65, 1.00)·피해 0. 예고 문구(telegraphText)는 모든 실행에서 빈 문자열 | PASS |
| HP = HitEvent = 숫자(V02 대표) | A | A·A2 12=12, B 12=12, D 4=4, LG 4=4, GUARD 유형 4, H1a·H1d·H1f 12=12, 범위 밖·저스트·패링은 0=0 | PASS(대표) |
| H1 끝 칸 홀드 중 special.random이 그 칸일 때(홀드 유지) | A+B | 실제 LeftArrow 홀드 Pos1(x=-1.50, 콜라이더 -1.75~-1.25), 칸 1(영역 -2.0~-1.0) 두 번(H1a·H1b-4 등): 판정 순간 콜라이더가 영역과 겹침(overlap true), nativeHit true, HIT, HP -12=HitEvent 12. RightArrow·Pos3 대칭(H1c-R: 콜라이더 1.25~1.75, 영역 1.0~2.0): HIT 12. parry.any 끝 칸(Pos1 H1d-1·H1d-2, Pos3 H1f-R): HIT 12 | PASS(규칙상 정상, 겹침) |
| H1 홀드를 떼어 중앙 복귀하는 서로 다른 시점 | A+B(홀드 시작)+논리 경로(해제) | 실제 키 홀드 Pos1 후 클라이언트가 `TelegraphRemaining`≤θ에서 해제. θ 0.289초(H1b-1): 복귀 중, 판정 뒤 읽은 위치 x=-0.79(콜라이더 -1.04~-0.54, 영역 -2.0~-1.0과 겹침, 여유 0.04) → nativeHit true, HIT 12. θ 0.170·0.087·0.020초(H1b-2·3·4): 해제 효과가 판정 뒤(x=-1.50 홀드 중) → HIT 12. θ 0.535(H1e-1)·0.448(H1e-2)·0.372(H1e-3)초: 판정 때 x=0.00(콜라이더 -0.25~0.25, 겹침 false), nativeHit nil, EVADE·HP 0·HUD "회피". Pos3(RightArrow) θ 0.443(H1e-4): x=0.00, EVADE 0. **겹치는데 피해 없음 또는 안 겹치는데 피해는 한 건도 없었다** → 결함 후보 없음 | PASS(실제 키 해제 타이밍은 NOT_RUN) |
| 기존 기능 대표 회귀(V06·V10·V01) | A+B | 실제 UpArrow 공격 반복(`manual cast count=10`, 처치·그로기 중 타격·팝업 입력 차단), 실제 DownArrow 가드·LeftArrow/RightArrow 이동·복귀, 패링→반격 권한(0.88,0.65,1 문구)→그로기 흐름, 팝업 열기·닫기 승인(`CombatPause paused=true/false`·`popup closed`). 예고 문구 없음·칸 속성색(특수 칸 `[SPECIAL]`) | PASS(대표) |
| 사람 육안(die 모습·가드 불가 문구 느낌·난이도·구별)·0.20초 손 타이밍·Weight 체감 | - | 실행하지 않음. 스크린샷은 내가 읽은 장면과 픽셀 차이만 | NOT_RUN(V11 사용자) |
| CSV 파일을 바꿔 열 누락·값 변경을 Refresh로 반영하는 시험(V09) | - | 하지 않음(제품 파일 무수정 원칙). CSV 새 열 적용은 Refresh 뒤 런타임이 4행·AreaTarget을 읽는 것으로만 확인 | NOT_RUN |
| 실제 마우스·터치로 UIPopup 버튼 클릭, 실기기·모바일, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 제품 결함 후보 없음. 새 결함 ID 없음. FAIL·NEEDS_DECISION 없음.
- 시험 오류(제품 오류 아님): (1) S1 첫 실행에서 클라이언트 프로브가 서버가 새 몬스터를 만들기 전(약 3초 도구 지연) 이전 몬스터의 사망을 보고 팝업을 열어, 새 몬스터 처치 입력이 막혔다. 같은 시나리오를 팝업을 닫은 뒤 다시 처치해 판정했다. (2) 서버 모니터 스크립트가 다음 서버 스크립트 디스패치에 멈춰 PL 첫 실행은 위치 시계열이 없었다. 클라이언트 모니터로 PL2·PR을 다시 실행해 판정했다. (3) 반격 소비 실제 ↑ 3번은 도구 지연으로 반격 창 2.0초(첫 시도)·8초(두 번째)를 넘겨 소비되지 않았다. 입력 수락 지점 호출(E1e)로 소비를 확인했다. (4) 첫 번째 재Play 관찰(t=7.1초)은 몬스터가 자연 공격(AttackInterval 3.0) 중이라 stand 시작 근거가 되지 않아, 세 번째 재Play(t=1.36초)를 판정에 썼다. (5) 한 번 Stop 직전 시험 스크립트가 끝나기 전에 Stop해 `second pre-Stop` 줄이 없다(판정에 쓰지 않음).
- 관찰: (1) H1b-1의 겹침 여유는 0.04 단위로 작다. 판정 뒤 읽은 위치라 정확한 판정 순간 값이 아니며, 엔진 nativeHit true와 계산 겹침이 일치한다. (2) 팝업이 열려 있는 동안 클라이언트 `wait`는 시간 배율 0 때문에 재개되지 않는다(시험 스크립트 한정). (3) 사망 몬스터 영역에서 클라이언트 `DEAD|die`의 첫 프레임은 시험 스크립트가 사망 후 약 0.03초 뒤에 기록했다. (4) UNGUARDABLE은 범위 밖 가드에서 `[VRF] defense` 로그에는 UNGUARDABLE로 남고 HUD·RecordDefense는 EVADE로 대체된다(Plan 기대와 같음). (5) die 프레임과 die 기준 영상의 픽셀 차이가 22.6으로 stand와의 차이(44.3)보다 작지만 0은 아니다. die 클립이 정지가 아니라 시간에 따라 변하는 동안 찍어서로 보이며, 사람이 읽은 장면은 눌린 몬스터(얼굴 없음)다. 육안 평가는 사용자 몫이다.
- 한계: 실제 키 입력으로 0.20초 창을 맞출 수 없어 창을 넓힌 시험 값으로 방향·유형·결과 종류를 검증했다(창 경계 0.20 자체는 이번 변경 경로 밖이며 재시험 안 함). 실제 키 해제 시점 시험은 입력 도구 지연 때문에 논리 경로(`ReleaseHeldState`)로 했다. 클라이언트 렌더러 실제 클립 이름 API가 없어 표시는 SpriteRUID와 스크린샷으로만 확인했다. 육안·실기기·터치 미실시.

#### 판정 요약
- REV-F02(7개 사망 경로 서버·클라이언트 die 유지, 실제 UIPopup 열고 닫기, Stop 뒤 재Play stand), V11-F10(로드·검증·선택·RANDOM 칸·판정·RANDOM 저스트·↓ 패링 불성공·반격·슬로우·parry.any/left/right 회귀·시험 데이터 유형), V11-F11("가드 불가"·"회피"·"피격"·일반 가드·패링 늦은 가드), H1(홀드 유지·해제·Pos3·parry.any 끝 칸), HP=HitEvent=숫자 대표 모두 **PASS**. FAIL·NEEDS_DECISION 없음.
- NOT_RUN: 사람 육안 평가, 0.20초 손 타이밍과 실제 키 해제 타이밍, CSV 파일을 바꾼 반영 시험, 실제 마우스·터치 클릭·실기기, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 전·후 54/54 동일 Bundle fdca556d…ee80, 제품 파일 무수정. Maker 사용 종료.
- 다음은 독립 reviewer: H1이 겹침 규칙대로임, 시험 값(창 3.0·반격 8초)이 Play 안에서만 쓰였음, 사용자 V11 확인(die 모습, 가드 불가 문구, 난이도·구별, 범위 밖에서 시작한 저스트 인정 체감)을 정리한다.

### 2026-11-03 독립 QA 6회차 — V11-F08·F09
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA 1~5회차와 coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·`[QA6S]`(서버)·`[QA6C]`(클라이언트)·`[QA6M]`(칸·문구)·`[QA6P]` 표지로 구분해 파일로 걸러 읽음).
- 대상: coder 커밋 a921c76 / 작업 트리 54경로 Bundle SHA-256 377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363(= 커밋 + 미커밋 Maker 재저장 3경로, 건드리지 않음). coder 절 "2026-11-03 최종 제품 버전 묶음"의 경로 집합(V11-F06 표 54경로)·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)을 node 스크립트로 **시험 시작과 끝 모두 재계산해 같은 값**이었고 두 계산의 54개 경로별 해시 목록이 완전히 같았다. 시험 끝 git status도 시작과 같은 3경로(M)뿐이다. 참고: WorkRecord에 이 절이 추가돼 coder 절 표의 줄 번호가 밀렸으므로 다음 계산은 표 행(`| 경로 | 해시 |`)을 이름으로 모아야 한다.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. build 로그 81건 모두 Info(오류·경고 0, coder와 같은 건수). Play 3회(최초 통합 Play 1회, Stop 뒤 재Play 2회), Stop 3회. Maker 로그 시각 14:49~15:03. Error·Warning 레벨 로그는 시험 시간대(14:49~) 0건이다(14:38대 LEA-2007은 coder의 이전 프로브). 최종 Stop 뒤 map01 / edit, worldId 일치.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client). 서버 상태·SpriteRUID·isStunned·GroggyRemaining·PlayRate·HP를 0.02초 폴링으로, 클라이언트 StateComponent·SpriteRUID·PlayRate·AnimationClipEvent·StateChangeEvent를 같은 방식으로 기록했다. 두 쪽 모두 `_UtilLogic.ServerElapsedSeconds`(같은 서버 시계)를 써 같은 시간축이다(로그 시각이 두 쪽에서 0.02초 안으로 일치). 시작 트리거(패턴 단일 행 교체, 몬스터 `ChangeState("ATTACK")`, 플레이어 `ChangeState("GUARD")`로 패링 창 안 가드, 그로기 연장 `ApplyGroggy`, `ApplySlow`, `ApplyDamage`)는 프로브가 맡았고 판정·피해·그로기 진입·복귀·표시 클립은 제품 경로다(논리 경로 검사). (B) 실제 입력 = maker_keyboard_input UpArrow 탭·LeftArrow 홀드. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(335,160)~(425,228)의 평균 절대 RGB 차이. 기준 영상: stand(애니메이션이 있어 stand끼리도 0~41.5 차이), hit(IDLE 몬스터에 서버가 hit 클립을 직접 쓴 정지 프레임), die(IDLE 몬스터에 die 클립 쓰기). 분류 기준은 hit 기준과의 차이 작음(≤ 약 17, 공격 이펙트가 겹치지 않을 때 0~7)이면 hit, stand 기준과 0~41.5이면 stand, 둘 다 80 이상이면 jump 등 다른 프레임이다. 스크린샷 파일 시각(ms)을 로그 시각(초)과 맞추려고 서버 로그의 초 경계가 바뀌는 지점으로 시계 오프셋을 보정해(구간 폭 0.02~0.46초) 각 스크린샷의 서버 시각을 구했다. 정렬 불확실성 약 ±0.15초.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 재Play에서 기본값 확인): AttackInterval 9999, 패턴 목록 단일 행 교체(예고 선행 0.5~60초), 그로기 연장 25초(`ApplyGroggy`), 슬로우 8초 ×0.5, 몬스터 HP 5, 시험용 ApplyDamage 999, TelegraphAttribute 직접 변경("SPECIAL"·"PARRY"·"XYZ"). CSV·제품 파일은 바꾸지 않았다. 참고: `_CombatRuleCatalog:GetRules({}).GroggyDurationSec` 쓰기는 반영되지 않아(복사본) 연장은 `ApplyGroggy`로 했다. 자연 1.5초 구간은 그로기 값을 바꾸지 않은 실행(NA3·NB·NC)이다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| V11-F08 조건 (a) 피격 없음, 자연 1.5초(NA3, parry.any) | A+C | 서버·클라이언트 시계열: ATTACK\|jump(접근) → ATTACK\|stand(착지 대기) → ATTACK\|jump(복귀, 0.5초) → 317.35 STUN\|hit/stun(서버·클라이언트 SpriteRUID 모두 hit) 1.50초 → 318.86 IDLE\|stand. 스크린샷 20장(≈0.18초 간격) 서버 시각 정렬: 복귀 구간 프레임은 vsStand 80~117·vsHit 92~121(jump, stand도 hit도 아님), **STUN 구간 317.38~318.68 프레임 모두 vsHit 0.0~6.7·vsStand 73~78(hit 유지)**, STUN 종료 318.86 이후 vsStand 0.0 또는 41.5(stand 프레임 계열) | PASS |
| V11-F08 조건 (b) 그로기 중 실제 ↑ 공격 | B+A+C | (b1) 연장 그로기 25초 중 UpArrow 3회: 서버 상태 STUN 유지·SpriteRUID hit/stun 유지, 클라이언트 STUN→HIT(ACE clip=hit 1회) 뒤에도 SpriteRUID hit/stun 유지, 서버 GroggyRemaining 감소(조기 해제 없음), 몬스터 HP 100→70(수동 공격 10타×3회, 1/타). 스크린샷 vsHit 3.1~8.8·vsStand 75~77(그로기 3.4초·16초·22초·24초 시점). 그로기 만료 직후 스크린샷 vsStand 0.0. (b2) 자연 1.5초 중 UpArrow(반격 ×2.2): 서버 STUN 유지 grog 0.85→0.47, HP 70→50(2/타 ×10), 클라이언트 STUN→HIT 후 SpriteRUID hit/stun 유지. 공격 이펙트·숫자가 겹친 프레임은 vsStand 74~144, **그로기 안에서 stand 프레임(vsStand ≤ 41)은 종료 시점 전까지 없음**, 종료 336.33 뒤 stand | PASS(이펙트 겹침으로 hit 정지 프레임과의 정확한 일치는 일부 프레임만) |
| V11-F08 조건 (c) 슬로우 겹침(NC, ApplySlow 8초 ×0.5, 자연 1.5초) | A+C | STUN 진입 직후 서버 PlayRate 0.5·클라이언트 rate=0.5, SpriteRUID hit/stun 유지 353.74~355.25, 그로기 1.50초 동안 서버 시간 진행 정상. 스크린샷 353.92~355.21 모두 vsHit 0.0~3.9·vsStand 73~76(hit 유지), 종료 355.39 이후 vsStand 0.0/41.5 | PASS |
| V11-F08 종료 뒤 stand | A+C | 위 (a)(b)(c) 모두 STUN→IDLE 시 서버 SpriteRUID stand·클라이언트 ACE clip=stand, 이후 스크린샷 stand 계열. 연장 그로기 종료 뒤 스크린샷 vsStand 0.0(145239) | PASS |
| V11-F08 복귀 중 jump 유지(그로기 시작에만 hit) | A+C | 복귀 jump 구간(서버 ATTACK\|jump, 약 0.5초) 스크린샷은 hit 아님(vsHit 92~121). 그로기 시작 시점 서버·클라이언트 SpriteRUID가 jump→hit로 바뀜(NA3 317.35, ND 396.6, E1 446.19 등). 2칸 패턴(parry.left·parry.right)도 같음 | PASS |
| V11-F08 그로기 중 사망 die | A+B+C | 그로기 중 HP 5 → 실제 UpArrow(반격) → 서버 STUN→DEAD, SpriteRUID die, isStunned false, 클라이언트 ACE clip=die·SCE HIT→DEAD, 스크린샷은 die 클립 재생(고통 얼굴 없음)과 die 마지막 포즈 정지(vsDie 0.0·7.0, vsStand 88~92). 10초 이상 뒤 스크린샷 두 장이 같은 die 마지막 프레임(vsStand 67.7) | PASS |
| V11-F08 정리 경로 — 상대 교체·소유자 이탈(ClearOpponentExecution) | A+C | 그로기 중 `mgr:ClearOpponentExecution()`: 직전 STUN·hit·stunned true·grog 23.5 → 직후 IDLE·stand·stunned false·grog 0, 클라이언트 SCE STUN→IDLE·ACE stand. `mgr:DoSpawn()`(그로기 중 새 상대 생성): 이전 몬스터 무효(isvalid false), 새 몬스터 IDLE·stand RUID·stunned false, 이후 스크린샷 stand 계열(생성 직후 0.3초 프레임 2장은 vsStand 80~106의 생성 연출 프레임). DoSpawn·ClearOpponentExecution 호출은 프로브가 시작한 논리 경로 검사 | PASS(논리 경로) |
| V11-F08 정리 경로 — 맵 이탈(MonsterStunComponent:OnMapLeave 서버 분기) | A+C | 그로기 중 `stun:OnMapLeave(map)` 직접 호출: 직전 STUN·hit/stun·stunned true → 직후 SpriteRUID stand·stunned false·grog 0(상태는 STUN으로 남음: 직접 호출 때문이며 실제 이탈은 몬스터가 맵과 함께 정리됨), 스크린샷 vsStand 0.03(stand). 실제 다른 맵 이동은 하지 않았다(맵이 1개) | PASS(논리 경로)·실제 맵 이동 NOT_RUN |
| V11-F08 정리 경로 — Stop | A+C | (1) 연장 그로기 18초 남은 시점 maker_stop → 재Play: 서버 IDLE·stand·stunned false·grog 0·cells ''·AttackInterval 3.0·패턴 9행·그로기 규칙 1.5·몬스터 HP 100, 스크린샷 vsStand 0.03. (2) 아래 V08 2칸 복귀 중 Stop 재Play도 같음 | PASS |
| V11-F09 9패턴 예고 문구 없음·서버 영역 칸 속성색 | A(클라이언트 칸 컴포넌트 `_T.attribute`·UI 텍스트 폴링)+C | 9패턴을 제품 경로로 1회씩 실행(플레이어 무대응): normal.left 011→`-NN`, special.left 011→`-SS`, parry.left 011→`-PP`, normal.right 110→`NN-`, special.right `SS-`, parry.right `PP-`, normal.any 010→`-N-`, special.any `-S-`, parry.any `-P-`. 모든 실행에서 telegraphText.Text는 빈 문자열(예고 시작~판정~종료 내내 길이 0). 결과 문구(def=피격 등)는 이전처럼 표시, 판정 뒤 칸은 1~2프레임 안에 꺼짐. 칸 변화는 서버 TelegraphCells 뒤 1프레임 이내 | PASS |
| V11-F09 칸 색값(픽셀 근거) | C(스크린샷, 알파 0.45 역산) | 예고 60초 단일 행(normal.left 011, 가드형이 아님·값은 속성 직접 지정)에서 칸 영역 중앙값 역산 색: NORMAL (1.00,0.84,0.40), SPECIAL (1.00,0.43,0.36), PARRY (0.88,0.65,1.00)(기대 노랑 1,0.85,0.4 / 적색 1,0.43,0.36 / 보라 0.88,0.65,1). 같은 칸에서 속성을 서버가 NORMAL→SPECIAL→PARRY→"XYZ"→NORMAL로 바꾸는 동안 칸이 켜진 채 `-NN`→`-SS`→`-PP`→`---`→`-NN`으로 새 색을 반영했고 "XYZ"는 칸 픽셀이 배경과 같아져(변화 0/176) 숨김, 0.25초 뒤 `[VRF] AttackAreaMark unknown attribute` 로그가 칸 2·3에 1회씩, NORMAL 복귀 시 다시 노랑 | PASS(속성 값 직접 변경은 시험값, 칸 색 자체는 제품 경로) |
| V11-F09 속성 미상 숨김·결과·상태 문구 유지 | A | 속성 "XYZ" 숨김(위). 결과 문구 `def`(피격·회피)와 counter·effect 텍스트 경로는 그대로 표시(9패턴 실행의 피격 문구, 실제 LeftArrow 홀드 회피의 회피 문구 길이 6바이트). 반격 준비·상대 그로기·슬로우 문구는 이번에 새로 확인하지 않음(변경 없는 경로) | PASS(대표) |
| V11-F09 팝업 중 칸 유지·재개 | A | 예고 60초(NORMAL 011) 중 실제 `_UIPopup:Open`: server paused true, 칸 `-NN`·cells 011 유지(복원 전까지 칸 변화 없음), 7초 뒤 Close: paused false, 이어서 정리 호출 뒤 칸 꺼짐. 팝업이 화면을 덮어 칸 색은 로그 근거만 | PASS |
| V11-F09 사망·Stop 경계 | A | 예고 중 몬스터 사망(ApplyDamage 999): cells '' 즉시, 칸 `---`(1프레임 이내). 재Play 뒤 칸 `---`·텍스트 빈 값·팝업 닫힘. 플레이어 사망 중 칸 정리는 이번에 새로 실행하지 않음(변경 경로 밖, 이전 QA5 V08 근거) | PASS(몬스터 사망·Stop) / 플레이어 사망 NOT_RUN |
| Plan §16 필수: 2칸 패턴 패링 → 복귀 중 팝업 정지·재개(V07) | A+C | parry.left(착지 x=+0.75): 복귀 점프 0.2초 뒤 팝업 Open(x=1.74): 서버 paused true, ATTACK\|jump 그대로 x 1.98에 **7.6초 이상 정지**(0.5초 간격 로그 전부 x=1.98, 전투 시계 646.322 고정), Close 후 paused false로 x 2.21→3.00 이어서 이동 → STUN\|hit/stun(grog 1.48 시작, 정지 시간이 그로기에 섞이지 않음) 1.5초 → IDLE\|stand. 스크린샷(재개 뒤 15장): STUN 구간 vsHit 0.0~3.6(hit 유지), 종료 뒤 stand 계열 | PASS |
| Plan §16 필수: 2칸 패턴 복귀 중 Stop → 재Play 기본값(V08) | A+C | parry.right(착지 x=-0.75) 복귀 점프 중 팝업 정지(x=1.19, paused true) 상태에서 maker_stop(CombatPause abort·popup closed 로그) → 재Play: IDLE·stand·stunned false·grog 0·ParryEffect (0,0,0)·cells ''·paused false·AttackInterval 3.0·패턴 9행·그로기 규칙 1.5·몬스터 HP 100, 클라이언트 IDLE·stand·칸 `---`·텍스트 빈 값·popupOpen false, 스크린샷 stand 계열(재Play 직후 플레이어 HP 964는 AttackInterval 3.0 자연 공격 3회 12씩 — 프로브가 늦은 것) | PASS |
| HP = HitEvent = 숫자(V02 대표) | A(제품 경로) | normal.any 무대응 HIT hpDelta 12 = HitEvent 12, normal.any 가드 GUARD 4 = 4(12×0.4=4.8→4), special.any 무대응 12=12, parry.any 가드(창 안) PARRY 0=0 + 그로기·반격, 그로기 중 수동 공격 HP 감소 = 수동 공격 숫자(10타 합계 20=2×10, 반격 ×2.2·1 타당 2) | PASS(대표) |
| V03(저스트·패링 판정 대표)·V04 반격 | A | 패링(창 안 가드 PARRY 0, `counter granted factor=2.2`, 그로기 1.5초) 반복 10여 회 정상, 반격 ×2.2 수동 공격 로그(`manual cast ... factor=2.2`). 저스트 회피 시각 경계(0.20)는 이번 변경 경로 밖이라 재시험하지 않았다 | PASS(대표) |
| V10 대표(실제 입력) | B+A | 실제 LeftArrow 홀드(예고 5초 중 2초): 칸 `-N-` 예고, 판정 시 EVADE HUD 문구(6바이트 "회피"), hpDelta 0·HitEvent 0, 예고 문구 길이 0. UpArrow 탭 5회(수동 공격 로그 `manual cast count=10`) 모두 동작 | PASS(대표) |
| V01·V06 기존 기능 대표 회귀 | A | 9패턴 칸·유형 대응(위), 패링→복귀→그로기→IDLE 흐름(위), 사망(위) | PASS(대표) |
| 육안(스크린샷 대신 사람의 눈) 그로기 hit 모션 가독성·별·접촉 파티클·칸 색 가독성·색약 접근성 | - | 사람 평가는 하지 않았다. 스크린샷 픽셀 근거만 | NOT_RUN(V11 사용자) |
| 0.20초 창 손 타이밍·CSV 변경 반영(V09)·UI 좌·우 버튼 실기기·플레이어 사망 중 칸·실제 다른 맵 이동 | - | 실행하지 않음 | NOT_RUN |
| V11(사용자)·V12 외부·CF-F07 연출 평가 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 범위 밖 관찰(coder 인계 사항 재현, 판정은 reviewer): **일반 사망의 표시.** (1) IDLE 상태 몬스터에 `ApplyDamage(999)`: 서버 DEAD·SpriteRUID **stand**(3초 뒤도 stand), 스크린샷 stand 계열(vsStand 41.5). (2) 공격(ATTACK) 중 사망도 같음(DEAD\|stand, HP 0/100 표시 화면에서 웃는 stand 얼굴). 이벤트(ACE clip=die)는 1번 나오지만 서버 SpriteRUID는 stand로 남는다. 반대로 **그로기 중 사망은 die가 고정**돼 표시가 다르다. 이번 변경(그로기 중 사망만 die 고정)의 결과로 두 경우가 달라 보이는 것이며, 일반 사망 die 유지는 결함 후보·사용자 판단(새 ID는 붙이지 않음).
- 관찰: (1) 그로기 hit 프레임은 시간이 지나면서 vsHit가 0.0에서 6.7까지 서서히 변한다(hit 클립 마지막 부분의 미세한 움직임으로 보이며 stand와는 항상 70 이상 떨어져 있다). (2) 그로기 만료 순간에 실제 공격 타격이 겹치면 서버가 STUN→IDLE→HIT로 지나가 0.5초 HIT(stand 표시)가 보인 뒤 IDLE로 돌아간다(연장 그로기 b1 마지막, 221.37~221.88). 기존 HIT 규칙대로이며 새 변경과 무관. (3) 새로 생성된 몬스터(DoSpawn)는 0.3초 동안 생성 연출 프레임(vsStand 80~106)이 보인다. (4) 클라이언트 화면 표시 클립을 직접 읽는 API가 없어 스크린샷 픽셀이 근거이며, 스크린샷은 약 5~16장/초이고 공격 이펙트·숫자 겹침 프레임은 hit 정지 프레임과 정확히 일치하지 않는다.
- 시험 오류(제품 오류 아님): (1) 초기 시험의 sleep 간격 도구 지연(1~3초)으로 첫 연장 그로기 실행의 일부 스크린샷이 그로기 밖(stand)이었다. 그 실행은 판정에 쓰지 않고 `ApplyGroggy` 연장·자연 구간 장수 확대로 다시 실행한 결과만 썼다. (2) `GetRules` 복사본 쓰기는 반영되지 않았다(위). (3) 실행 G에서 프로브의 패턴 복원 타이머가 정지 중 서버에서 먼저 돌아 `RUN G NO-STUN restore` 로그가 찍혔으나 이미 판정이 끝난 뒤라 영향 없음. (4) 몬스터 사망 뒤 `mgr:DoSpawn()`으로 새 상대를 만들었다(시험용 호출). (5) LEA-3051 MemoryLeak은 시험 타이머를 모두 정리해 이번 시간대에는 관측되지 않았다.
- 한계: 육안 평가 불가, 클라이언트 렌더러 실제 클립 이름 API 없음(픽셀 대체), 그로기 1.5초 구간은 스크린샷 약 8장(0.18초 간격)으로만 덮음, 정렬 불확실성 ±0.15초, 실기기·터치·실제 맵 이동·0.20초 손 타이밍 미실시.

#### 판정 요약
- 기준: V11-F08(세 조건 그로기 전체 hit, 종료 뒤 stand, 복귀 중 jump, 그로기 중 사망 die, 상대 교체·Stop·맵 이탈 정리 뒤 잔존 없음), V11-F09(9패턴 문구 없음·서버 영역 칸 속성색·같은 칸 속성 연속 변경·속성 미상 숨김·결과 문구 유지·팝업/몬스터 사망/Stop 경계), Plan §16 필수 2칸 패턴 F02 복귀 조합(V07·V08), HP=HitEvent=숫자 대표, V10·V01·V06 대표 회귀 모두 **PASS**. FAIL·NEEDS_DECISION 없음. NOT_RUN: 사람 육안 평가, 0.20초 손 타이밍, V09 CSV 변경 반영, 실기기·터치, 플레이어 사망 중 칸, 실제 맵 이동, V12, CF-F07 연출. 이번 회차의 새 결함 ID 없음.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. 시험 전·후 54/54 동일 Bundle 377a5ccc…0363, 제품 파일 무수정, git status 시작·끝 동일(M 3경로: Maker 재저장 userdataset 2·주황버섯 모델). Maker 사용 종료.
- 다음은 독립 reviewer: 범위 밖 관찰(일반 사망 stand 표시)의 결함 여부와 사용자 V11 확인 항목(그로기 hit 모션 육안, 속성색 칸 가독성)을 정리한다.

### 2026-11-03 독립 QA 5회차 — V11-F01~F06
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA 1~4회차의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·[VRF-QA5] 표지로 구분해 읽음, QA4 계약 위반 재발 없음).
- 대상: coder 커밋 b89de46 / 54경로 Bundle SHA-256 b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf. coder 절 "최종 제품 버전 묶음"의 경로 목록·계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF 연결의 SHA-256)을 node 스크립트로 시험 전·후 재계산해 둘 다 54/54 개별 해시 일치·Bundle 동일, 시험 후 git status 변경 없음.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186 시작·중간 반복 확인. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. build 로그 80건 모두 Info(오류·경고 0, coder와 같은 건수). Play 5회(시험 중 Stop 4회 포함), Maker 로그 시각 10:22~10:37. 최종 Stop 뒤 map01 / edit.
- 실행 방식 구분: (B) 실제 입력 = maker_keyboard_input의 Left/Right/Down/UpArrow 실제 키 이벤트, maker_mouse_input의 UI 뒤 버튼 홀드·공격 버튼 클릭. (A) 서버 프로브 = maker_execute_script(server_main)로 `_CombatRuleCatalog.patterns["castleenemy"]`를 시험 행 1개로 교체하고 몬스터를 `ChangeState("ATTACK")`로 시작시킨 뒤 회피 방향·시작 시각 필드(`EvadeDirection`·`evadeStartTime`)나 서버 GUARD 상태를 정해진 시점에 부여. 방어 판정(EvaluateDefense)·영역·피해(CalcDamage→ResolveIncomingDamage)·네이티브 AttackFast/HitEvent·HP는 제품 경로이며 프로브는 시작 트리거와 관찰만 맡았다(논리 경로 검사). (C) 순수 함수 호출 = SelectPattern·FindNearestCell·ValidateRows(시험 행). 시험 한정 값(모두 Play 내부, Stop으로 폐기): AttackInterval 9999, 패턴 목록 1행 교체, 예고 선행 1~8초, 일부 실제 키 시험의 JustWindowSec·ParryWindowSec 8.0(손 타이밍으로 0.20초 창을 맞출 수 없어 창만 확대), 가드형 시험 행(Play 내부 메모리 행). CSV는 시험용으로도 바꾸지 않았다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| V01·V09 로드 | 로그 | `catalog ready rules=1 patterns=9`(매 Play), 9행 id·유형·속성·앵커 0-0/2-3/1-2·Weight 문자열 "1", 가드형 0행 | PASS |
| V01 주황버섯 9행 판정 대응(LEFT·RIGHT·ANY × 일반·특수·패링) | A | 모든 행이 예고 문구·칸·영역·판정과 일치(아래 행들). 일반 가드 12×0.4=4.8→4(=HitEvent 4), 특수 가드 12, 패링 창 안 가드 PARRY 0, 창 밖 가드 4 | PASS |
| V01 ANY Pos2(x=0) 조준 | A | tgt=2 cells=010 영역 -0.5~0.5 dirs=LR 착지 x=0.0. 무대응 HIT 12=HitEvent 12. 일반·특수·패링 모두 LEFT·RIGHT 저스트 JUST·피해 0·슬로우 1.72(≈2.0 시작)·반격 true | PASS |
| V01·V03 ANY Pos1 조준(실제 LeftArrow 홀드, x=-1.5) | B+A | tgt=1 cells=100 영역 -2.0~-1.0 dirs=R 착지 x=-1.5. 무대응 HIT 12, RIGHT 저스트 JUST(특수 포함), 조준 칸 쪽 LEFT는 HIT 12(저스트 아님), 창 밖 RIGHT HIT 12 | PASS |
| V01·V03 ANY Pos3 조준(실제 RightArrow 홀드, x=+1.5) | B+A | tgt=3 cells=001 영역 1.0~2.0 dirs=L 착지 x=+1.5. LEFT 저스트 JUST 0(특수), 조준 칸 쪽 RIGHT HIT 12, 창 밖 LEFT HIT 12, 무대응 HIT 12 | PASS |
| V03 최근접·동률 경계 | C | anchors -1.5/0/1.5: -9→1, -1.5→1, -1.0→1, -0.76→1, -0.75→2(동률 중앙), -0.74→2, 0→2, 0.74→2, 0.75→2(동률 중앙), 0.76→3, 1.0→3, 1.5→3, 9→3. 같은 입력은 같은 칸 | PASS(PrepareAttack에 플레이어를 -0.75 등에 세운 통합 시험은 안 함, 함수 단위) |
| V03 저스트 시각 경계(ANY, 서버 부여) | A | 판정시각-시작시각 0.013 JUST, 0.115·0.158 JUST, 0.198 JUST, 0.222 HIT, 0.241 HIT, 판정 뒤 시작(-0.032·-0.122) HIT, 빈 방향 HIT. 정확히 0.200 등호값은 타이머 간격(0.02) 때문에 재현하지 못함 | PASS(근사 경계, 등호 경계 NOT_RUN) |
| V03 예고 뒤 이동해도 조준 불변 | B | 실제 RightArrow(K2: Pos2 조준, 판정 때 x=+1.5)·키 이동 중 telegraph 칸·영역·방향 집합이 판정까지 tgt=2 cells=010 영역 -0.5~0.5 불변 | PASS |
| V03 조준 칸 쪽·중앙 복귀는 저스트 아님, 탈출 | B | K1b: Pos1 LeftArrow 홀드 뒤 예고 중 키 해제 → 판정 x=0.0(영역 -2~-1 밖) → 피해 0·HitEvent 없음·kind HIT/native nil(HUD EVADE)·JUST 아님. K3: Pos3 홀드→Right 해제→(복귀 중 Left 눌림은 무시됨, 입력 예약 없음)→ x=0.0 EVADE·JUST 아님. 자연 공격 id=45(Pos2 조준, 예고 중 실제 RightArrow로 영역 이탈): HUD EVADE, 피해 0 | PASS |
| V03 끝 칸 조준에서 중앙 복귀 뒤 중앙 쪽 방향 회피 저스트 | B(시험 한정 창 8.0) | K3b: Pos3 조준(dirs=L) → Right 해제 → 중앙 복귀 후 실제 LeftArrow → JUST, 판정 x=-1.5, evDir=LEFT 실제 입력으로 기록, 피해 0, HUD JUST | PASS(창은 시험 값) |
| V03·V10 Pos2 조준에서 실제 RightArrow | B(창 8.0) | K2: JUST, evDir=RIGHT 실제 기록, 판정 x=1.5, 슬로우·반격 true, HUD JUST | PASS(창은 시험 값) |
| 가드형 시험 데이터(V01 "시험 데이터 근거") | A(Play 내부 메모리 행 2개, 제품 CSV 아님) | 영역 -2~2 cells=111 dirs 빈 집합 착지 x=0.0. 일반+GUARD: 무대응 HIT 12, 가드 GUARD 4, 회피 방향 부여해도 HIT 12. 패링+GUARD: 창 안 가드 PARRY 0·반격 true, 창 밖 가드 GUARD 4 | PASS(시험 데이터 근거) |
| V01·V09 잘못된 ANY 영역·유형 조합 거부 | C(ValidateRows 시험 행) | ANY 1/1·ANY 0/2는 `ANY area must be 0/0`, LEFT 0/0·RIGHT 1/4는 `invalid anchor`, 역전 3/2 `invalid pattern area`, SPECIAL+GUARD `SPECIAL cannot request GUARD`, 잘못된 유형 `invalid response`, 선행 0.1 `invalid pattern area or lead`, AreaHeight 0, 중복 id `invalid or duplicate pattern`, 빈 목록 `patterns missing` — 모두 REJECT, 경고 정확히 1회씩. 허용 케이스(GUARD 일반 1/3, Weight 0.5, 전체 2.5)는 ACCEPT. 거부 뒤 live 카탈로그 ready=true rows=9 | PASS |
| V09 Weight 거부 | C | 누락(nil)·빈 값·abc·nan·inf·1e999는 `invalid pattern number`, 0·-1은 `invalid weight`. 모두 REJECT·경고 1회(카탈로그 전체 거부). 열 자체 누락(`NoSuchColumn`)은 ReadRows nil | PASS |
| V09 Weight 가중치 선택 | C | 9행 균등 중간값 (i-0.5)/9 → 1~9행 순서대로. 경계 u=0·1/9-1e-9→normal.left, 1/9+1e-9→special.left, 2/9+1e-9→parry.left, 8/9-1e-9→special.any, 8/9+1e-9·1-1e-12·1.0·1.5→마지막 parry.any. 가중치 1,2,3 행: u=0·0.1666→a, 0.17·0.49→b, 0.5·0.9999·1.0→c(마지막 행). math.random 900회: 9행 각 82~118회(전부 선택), 가중 600회 a87/b204/c309(≈1:2:3) | PASS |
| V09 CSV 파일 변경→Refresh→Play 반영 | - | 지시상 CSV·제품 파일을 바꾸지 않아 실행하지 않았다(ValidateRows 시험 행으로 대체) | NOT_RUN |
| V01 2칸 중앙 착지·판정 일치 | A | normal.left 착지 x=+0.750, normal.right -0.750(두 칸 중간), ANY 고정 칸 x(0.0/-1.5/+1.5), 가드형 시험 0.0. 판정 시각 hitDt≈0.47(예고 후 점프 0.5초 고정), 영역 min/max·피해 12=HitEvent 12 이전과 동일 | PASS(서버 위치 근거) |
| V01·F01 빨간 칸(클라이언트 마크) | A+로그 | 클라이언트 TelegraphCells·marks: ANY Pos2 010→marks 010, ANY Pos1 100→100, ANY Pos3 001→001, normal.left 011→011, parry.right 110→110, 가드형 시험 111. 판정 뒤·종료 뒤 000(≈0.03초 지연). ANY에서 고정 1칸만 켜짐 | PASS |
| V01 예고 문구 | 로그 | ANY: "일반 · 방향 무관 회피 [좌·우] / 가드", "특수 · 방향 무관 회피 [좌·우] · 가드 불가", "패링 · 방향 무관 회피 [좌·우] / 정확히 가드"(Pos1·Pos2·Pos3 동일). LEFT "일반 · 뒤 회피 [왼쪽] / 가드", RIGHT "패링 · 앞 회피 [오른쪽] / 정확히 가드" | PASS |
| 육안(스크린샷 800×450) | B | 예고 중 상단 문구와 빨간 칸이 플레이어 위치에 보임(2회 캡처). 몬스터 착지 모양·색·가독성·1칸 공격 난이도·2칸 중간 착지 모션 모양은 판단하지 않음 | 일부 NOT_RUN(V11 사용자) |
| 실제 입력 창 0.20초 안 손 타이밍의 저스트·패링 성공 | - | 재현하지 않음(실제 키 성공은 시험 한정 창 8.0, 창 0.2 안 성공은 서버 프로브 A) | NOT_RUN |
| V02 회귀 | A+B | 모든 케이스에서 HP 감소=HitEvent 합계: 무가드 12/12, 가드 4/4, 저스트·패링·범위 밖 0/0 | PASS |
| V04 회귀 | B | ANY JUST 직후 실제 UpArrow: `manual cast id=32 count=10 factor=2.2`, 반격 즉시 소비(counter false). 성공 전 UpArrow는 factor=1 | PASS(대표) |
| V05 회귀 | A | ANY 저스트 슬로우 시작 값 ≈2.0(1.71~1.73 측정), 예고·복귀 진행 정상 | PASS(대표, 전 구간 재시험 아님) |
| V06·F02·F04 회귀 | B | ANY 패링(K4b, 실제 DownArrow, 시험 한정 창 8.0): PARRY 0, 판정 후 몬스터 ATTACK(복귀 중) → x=3.0에서 STUN → 그로기 약 1.5초 → IDLE, 반격 true 유지 후 만료. `parry effect serial=5 x=0.0`(F03 접촉 파티클 로그 1회). F04 hit 클립 RUID는 이번에 재계측하지 않음 | PASS(대표) / F04 클립 NOT_RUN |
| V07 회귀 | A | ANY 예고(선행 8초) 중 실제 `_UIPopup:Open`: 전투 시계 501.670 고정 5초, rem 7.176·cells 010 불변. Close 뒤 같은 실행이 이어져 판정 시계 508.852(=501.670+7.176+0.006), HIT 12=HitEvent 12 | PASS |
| V08 회귀 | A+B | 몬스터 사망(예고 2.35초 남음): 즉시 DEAD, cells·resp 비움, snapshot nil, 판정(res) 변화 없음, 클라이언트 마크 000, 이후 3초 유지. 플레이어 사망(HitComponent:OnHit 5000): 몬스터 IDLE로 복귀, cells 비움, 판정 없음, plState DEAD 유지. 예고 도중 실제 Stop → 다음 Play: interval 3.0·dmg 12·rows 9·cells ''·seq 새로 시작·규칙 .2/.2/.4/2.0×2.2/2.0×0.5/1.5·evDir ''·반격 false·몬스터 HP 100·마크 000 | PASS |
| V10 회귀 | B | 실제 Left/Right/Down/UpArrow 키, UI 뒤 버튼 마우스 홀드(예고 선행 5초 동안 홀드 → 판정 x=-1.5, EVADE, 피해 0), UI 공격 버튼 클릭 2회(`manual cast factor=1` 2건) | PASS(대표) |
| F05 회귀 | B+A | 실제 LeftArrow 홀드 Pos1: 뒤 회피형 3패턴 EVADE 피해 0/HitEvent 0, 앞 회피형 3패턴 HIT 12/12, ANY(tgt=1) HIT 12/12. 실제 RightArrow 홀드 Pos3(대칭): 앞 회피형 2패턴 EVADE 0/0, 뒤 회피형 2패턴 HIT 12/12, ANY(tgt=3) HIT 12/12 | PASS |
| F01·F02·F03 나머지, F04 클립·별 크기·접촉 파티클 육안 | - | QA4 범위 중 이번에 새로 재실행하지 않은 항목(복귀 중 팝업·피격·슬로우 조합, 그로기 중 피격 클립 재생, 별·파티클 가시성)은 F06 변경 경로(영역 전달·착지·선택)와 겹치지 않아 재실행하지 않았다 | NOT_RUN(V11 사용자) |
| V11(사용자 직접)·V12 외부 환경·CF-F07 연출 | - | 실행하지 않음. V12 단일 참조 없음/폐기 경로는 위 사망·Stop 시험이 일부 겹치나 V12 전체로 세지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 시험 오류(제품 오류 아님): (1) 첫 harness는 몬스터가 자연 공격 중(ATTACK)일 때 `ChangeState("ATTACK")`가 무시돼 아무 케이스도 기록되지 않았다. Stop→재Play 후 "IDLE이 된 뒤 시작"하도록 고쳐 다시 실행했고 그 이후 결과만 사용했다. (2) K4 첫 시도는 직전 시험의 RightArrow를 해제하지 않아 플레이어가 MOVE 중이라 DownArrow가 수락되지 않았다(kind HIT, 무효). 키를 해제하고 K4b로 다시 실행한 결과만 썼다. (3) K1b는 직전 harness가 `EvadeDirection`을 초기화해 실제 LeftArrow 홀드의 방향 기록은 남지 않았다(탈출 결과·조준은 확인, 방향 불일치 판정은 Pos1 서버 부여 시험이 근거). (4) 한 harness 시작 직후 키 이동과 겹쳐 id=45 공격이 harness 케이스 로그 없이 지나갔다(위 EVADE 근거로만 사용).
- 시험 스크립트 한계: maker_execute_script는 한 번에 약 900회 반복 이상은 완료되지 않았다(900회 선택 시험을 나눠 실행). LEA-3051 MemoryLeak 3건(10:25:09, 10:34:48 두 건)은 모두 `MakerScript`의 시험 타이머이며 제품 오류가 아니다. 제품 runtime 오류는 관측되지 않았고 Warning은 V09 시험 행의 의도한 경고(1회씩)뿐이다.
- 관찰: (1) ANY 끝 칸(Pos1·Pos3) 조준에서도 예고 문구는 "[좌·우]" 일반형이라 실제 유효 방향(한쪽)과 다르게 읽힐 수 있다. Plan §15가 허용한 표현이며 칸 표시가 조준 칸을 알린다. 체감은 V11에서 판단. (2) 끝 칸에 홀드 중인 플레이어는 새 회피를 시작할 수 없고(홀드 해제 → 중앙 복귀), 복귀 중 들어온 반대 방향 입력은 무시된다(입력 예약 없음). Plan 설계대로이며 난이도는 사용자 V11. (3) `TelegraphAttribute`는 공격 종료 뒤에도 마지막 값이 남는다(Response가 비어 HUD에는 안 보임, 이전 버전부터의 동작). (4) 접촉 파티클 serial·판정 로그 근거만 있고 화면 가시성은 미확인.

#### 판정 요약
- 기준: F06(ANY 3칸 조준·최근접·동률, 유효 방향 저스트, 조준 칸 쪽·복귀 비저스트, 탈출, 2칸 중앙 착지·판정 일치, Weight 선택·거부, 가드형 시험 데이터, F01 1칸 표시, 예고 문구) **PASS**. 회귀 F01·F02·F05·V02·V04~V08·V10 대표 **PASS**. 실제 입력의 창 안 성공은 시험 한정 창 확대(K2·K3b·K4b)이며 창 0.20 안 손 타이밍, CSV 파일 변경→Refresh→Play, F04 클립 재계측, 육안·V11·V12는 NOT_RUN. FAIL·NEEDS_DECISION 없음.
- 사용 종료: 모든 키·마우스 up. 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, Maker 사용 종료. 시험 전·후 54/54 동일 Bundle b985aa4b…74dbf, git status 변경 없음.
- 다음은 독립 reviewer(F01~F06 일괄): 위 실행 방식 구분과 한계를 같은 Bundle에서 대조한다. 사용자 V11에서 1칸 공격 구별·난이도, 2칸 중간 착지 모션, F01~F04 체감, 별·접촉 파티클 가시성, 좌·우 UI 버튼 전체 면적을 확인한다.

### 2026-11-02 독립 QA 4회차 — V11-F01~F05
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA/QA2/QA3의 PASS는 이번 실행으로 세지 않았다.
- 대상: coder 커밋 1447ff8 / 54경로 Bundle SHA-256 d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb. 시험 전·후 54/54 byte 일치(Bundle 재계산 동일, git status 제품 변경 없음). 계산은 coder 절의 manifest·방법을 그대로 썼다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. 기준 build 로그 80건 모두 Info(오류·경고 0). Play context server_main/client. Maker 로그 시각 23:09~23:22. TileMapMode는 기존 기록(0)을 따르며 이번에 MapBuilder를 다시 읽지 않았다.
- 실행 방식 구분: (B) 실제 입력 = maker_keyboard_input(LeftArrow/RightArrow/DownArrow/UpArrow 실제 키 이벤트), maker_mouse_input(UI 버튼 누름·홀드). (A) 서버 프로브 = maker_execute_script로 패턴 목록을 단일 행으로 교체해 `StateComponent:ChangeState("ATTACK")`로 공격 시작, 플레이어 GUARD는 서버 `ChangeState("GUARD")`(패링 창 안 시점 맞춤), 저스트 회피는 `PlayerEvadeComponent:SetEvading`+`EvadeDirection`, 피격·사망은 `HitComponent:OnHit`(네이티브 HitEvent 경로), 팝업은 클라이언트 `_UIPopup:Open/Close`, 슬로우는 `MonsterStateControl:ApplySlow`. 판정(EvaluateDefense)·피해·그로기 진입·복귀·클립 전환·칸 표시는 모두 제품 경로이며 프로브는 시작 트리거와 관찰만 맡았다. 클라이언트에서는 AnimationClipEvent(clip 이름과 ActionSheet RUID), 칸 컴포넌트(AttackAreaMarkComponent._T.shown), TelegraphCells 동기값, 로컬 플레이어 상태를 폴링해 기록했다.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 다음 Play 기준값 확인): AttackInterval 9999, 패링 창 0.9(DownArrow 실제 홀드 패링), 반격 창 6초·그로기 4초/9초, 슬로우 0.02배·60초(칸·팝업 화면 확인용), 몬스터 HP·시험용 즉사 피해 999. 중간 복원 후 사용했다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| F05 뒤 회피형 (normal/special/parry.left) Pos1(x=-1.50) 실제 LeftArrow 홀드, 서버 상태 MOVE | B+A | 3패턴 모두 판정 순간 plx=-1.50 / pst=MOVE, 네이티브 피격 없음, HUD feedback=EVADE, HP 감소 0 / HitEvent 합계 0 | PASS |
| F05 앞 회피형 (normal/special/parry.right) 같은 조건 | B+A | 3패턴 모두 네이티브 피격 있음, kind HIT, HP 감소 12 / HitEvent 12 | PASS(기대 HIT) |
| F05 가드형 (normal.guard, parry.guard) 같은 조건 | B+A | 두 패턴 HIT, HP 감소 12 / 12(가드 없음) | PASS(기대 HIT) |
| F05 예고 시작 뒤 방향 전환 | B(실제 RightArrow·LeftArrow, 서버가 MOVE 수락 순간 정확히 시작) | normal.right+RightArrow → 판정 시 x=+1.50, EVADE, HP 0 / 0. normal.left+LeftArrow → x=-1.50, EVADE, HP 0 / 0. 플레이어 Scale.x는 모든 이동에서 1.0 그대로라 시작 시 Scale 기준 검증과 판정 콜라이더가 어긋날 여지가 관측되지 않았다 | PASS |
| F05 UI 버튼 경로 | B(실제 mouse 홀드) | 뒤 버튼 누름(ButtonState Pressed)→클라이언트 MOVE→normal.left 판정 시 x=-1.50, EVADE, HP 0 / 0. 앞 버튼 누름은 x=1.50 MOVE·복귀 확인. 가드 버튼 누름은 GUARD 진입·해제 확인 | PASS(아래 좌표 관찰 별도) |
| F05 입력→서버 수락 지연(키·UI 공통) | B | 클라이언트 MOVE 진입 시각 대비 서버 MOVE 관측 시각 차 0.065~0.079초(키 3회, UI 1회, 서로 다른 시계라 지시용 값, 샘플 타이머 0.01초 포함). 수백 ms 단위 지연은 관측되지 않음 | PASS(지시 수준) |
| F02 패링 → 복귀 → 그로기 1.5초 → IDLE | B(실제 DownArrow 홀드 + 패링 창 0.9) | 시작 x=3.00 → 판정 PARRY 피해 0, 판정 순간 x≈0.0~0.1 → 복귀 중 상태 ATTACK(isStunned false, 별 표시 없음, jump=true) → 복귀 완료 시점에 x=3.00 STUN, GroggyRemaining 1.50, stun 진입 로그 FinishAttack 호출 → 1.5초 뒤 IDLE. 그로기 길이는 전투 시계 1.50/1.51초. 접촉 시 추가 타격 없음 | PASS |
| F02 반격 창 | B+A | 성공 시점(clock 344.493)부터 until 346.493 = 2.0초. 복귀 시간만큼 그로기 구간이 줄고 창 종료 시 CounterReady false | PASS |
| F02 다음 공격 Home 시작 | A | 그로기 종료 IDLE 위치 x=3.00(Home)이고, 이후 시작한 모든 공격이 x=3.00에서 시작(x=2.90 점프 시작) | PASS |
| F02 복귀 중 슬로우 | A | 복귀 중 슬로우(2초 ×0.5) 적용 → STUN 진입이 판정 후 +0.90초(0.1초 정상 + 나머지 0.4 가 두 배)로 늘어남. 그로기 deadline은 진입+1.5로 슬로우와 무관(맵 전투 시간), IDLE까지 1.51초 | PASS |
| F02 복귀 중 팝업 | A(실제 _UIPopup) | 복귀 중 x=1.23에서 정지, 약 11초 동안 clock·x 불변(server paused=true). Close 뒤 복귀를 이어 가 x=3.00 STUN(deadline=재개 후 복귀 완료+1.5), 반격 창은 전투 시간만 흘렀다 | PASS |
| F02 복귀 중 피격 | A(OnHit 5) | 서버 상태 ATTACK 유지(HIT 아님), HP 100→95, 복귀 계속 후 STUN 진입. 클라이언트에는 HIT 클립 이벤트가 한 번 나온다(아래 관찰) | PASS(서버 규칙) / 관찰 있음 |
| F02 복귀 중 사망 | A(OnHit 999) | 즉시 DEAD, STUN·그로기 진입 없음(isStunned false, stunDeadline -1), 별·칸 없음, 이후 2.5초 resolutionCount 변화 없음 | PASS |
| F02 복귀 중 Stop | B(실제 maker_stop) | 팝업으로 정지된 복귀 중(x=1.25) Stop → 다음 Play에서 몬스터 IDLE, stunned false, GroggyRemaining 0, ParryEffect (0,0,0), pause false, counter false, 칸 000, 규칙 기본값 | PASS |
| F04 STUN 동안 hit 클립 | A(제품 STUN 진입 경로) | STUN 진입 순간 클라이언트 AnimationClipEvent clip=stun ruid=aec950…(주황버섯 ActionSheet hit와 같은 RUID)를 패링 시험 매 회(9회) 관측. 복귀 중에는 stun 클립이 나오지 않았다(clip=jump는 서버 SetVisualClip 경로, 이벤트 없음) | PASS |
| F04 종료 후 stand | A | 그로기 만료 IDLE에서 clip=stand ruid=96e955…를 매 회 관측 | PASS |
| F04 그로기 중 피격 | B(실제 UpArrow)+A | 실제 UpArrow 공격 10타(반격 factor 2.2) 중 서버 상태 STUN 유지·GroggyRemaining 계속 감소·deadline 만료 시 IDLE, HP 100→80. 클라이언트는 로컬 상태 HIT가 되며 clip=hit ruid=aec950…(stun RUID와 동일)가 한 번 발생. RUID가 같아 화면 클립 변화는 없으나 같은 클립이 다시 재생(처음부터)되는지는 로그로 구분 못 함 | PASS(RUID 근거) / 재생 재시작 NOT_RUN |
| F04 사망 시 die 우선 | A | 예고 중·복귀 중·그로기 중 사망 모두 clip=hit 직후 같은 프레임에 clip=die ruid=65a2bf…, 최종 DEAD, isStunned false(별 제거) | PASS |
| F01 8패턴 칸 = 서버 영역 | A+자연 공격 | TelegraphCells(서버)·클라이언트 칸 표시 일치: left 3패턴 011, right 3패턴 110, guard 2패턴 111(서버 영역 left -0.5~2.0, right -2.0~0.5, guard -2.0~2.0). 처음 자연 공격 13회(칸·영역 로그)에서도 동일. 칸은 동기값 수신 1프레임(≈0.03초) 뒤 켜짐 | PASS |
| F01 예고~판정 사이 유지, 판정 뒤 꺼짐 | A+B | 각 공격에서 TelegraphCells 설정과 같은 프레임대에 칸 on, 판정 직후 sync 비워지면 칸 off(0.03초 이내) | PASS |
| F01 슬로우 | A | 슬로우 0.02배로 예고가 25초로 늘어나도 칸 011이 계속 켜짐, 슬로우 0.5배에서 예고 0.5→1.0초 | PASS |
| F01 팝업 | A(실제 _UIPopup) | 예고 중 팝업: TelegraphRemaining 1.51→1.458(정지 반영 직전 값), 3초 동안 변화 없음·칸 011 유지·몬스터 위치 불변. Close 뒤 같은 실행이 이어져 칸 유지(rem 0.21) | PASS |
| F01 사망 | A | 예고 0.23초 시점 사망: 서버 TelegraphCells·Response 비움, snapshot nil, 판정(Resolve) 없음, 클라이언트 칸 011→000(0.03초), 상태 DEAD | PASS |
| F01 Stop | B | 복귀 정지 중 Stop 뒤 새 Play에서 칸 표시 000(클라이언트 _T.shown 3칸 false) | PASS(예고 중 Stop 단독 시험은 없음, 복귀·정지 중 Stop과 Stop→재Play 기준값으로 확인) |
| F01 스크린샷 칸 위치·색 | B | 예고 중(slow 시험값) 558×314 캡처에서 normal.left(011) 때 BattlePos2·3 위치에 반투명 빨강/주황 사각이 보이고 BattlePos1에는 없음. 몬스터 높이대와 맞음. 마크 3개 컴포넌트 값 pos x=-1.5/0/1.5, y=0.98, scale 25(1.0×1.0), MapLayer0 order 1 확인 | PASS(저해상도, 색·가독성 평가는 V11) |
| F03 패링 성공에만 접촉 파티클 1회 | A+B | PARRY 판정마다 `parry effect serial=N x=0.0 y=0.981` 한 번씩(패링 9회: serial 1,3,5,7,9,11,13,14,18, 별 serial과 짝 번호) 관측. GUARD(HP 4), 저스트 JUST, 일반 HIT(8패턴 포함)에서는 parry effect 로그와 그로기가 없었다 | PASS |
| F03 별 크기·높이 표시 | B | 그로기 9초 시험 중 캡처에서 몬스터 위쪽에 작은 청색 점/스파크가 희미하게만 보임(높이는 머리 위로 넉넉). 크기·가시성은 이 해상도에서 판정 불가 | NOT_RUN(육안 판정은 V11 사용자) |
| F03 접촉 파티클 육안 | - | 순간 효과라 도구 왕복 시간 안에 캡처하지 못함. 로그(재생 serial)만 근거 | NOT_RUN(육안은 V11) |
| F03 팝업·사망·Stop 뒤 잔존 | A+B | 그로기 중 사망 시 isStunned false(별 제거 경로), 복귀 중 팝업 뒤 Stop → 재Play 기준 ParryEffect (0,0,0)·별 없음. 시각 잔존은 로그·상태값 근거, 화면 확인 없음 | PASS(상태·로그 근거) |
| 회귀 V01 | A+B | 8패턴 예고↔영역 일치(F01 행), HUD feedback 문구 EVADE/HIT/GUARD/PARRY/JUST가 판정과 일치 | PASS(대표) |
| 회귀 V02 | A+B | HP 감소=HitEvent 합계: 무가드 12/12(앞 회피·가드형 12회), 가드 4/4, 패링·저스트·뒤 회피 0/0. 가드 12×0.4=4.8→4 | PASS |
| 회귀 V03 | A+B | 패링 창 0.2 안(판정 0.086~0.10초 전 가드 시작) PARRY, 창 밖(1.0초 전 홀드) GUARD, 저스트 RIGHT 0.09초 전 SetEvading JUST(슬로우 1회), 다른 방향·전부 범위 밖 EVADE 0피해 | PASS(대표 경계, 전체 경계 열 재실행 아님) |
| 회귀 V04 | B | 패링 뒤 실제 UpArrow: manual cast count=10 factor=2.2, 즉시 CounterReady false(소비), HP 100→80. 창이 끝난 뒤 UpArrow는 factor=1 | PASS(대표) |
| 회귀 V05 | A | 슬로우 시 예고 0.5→1.0초, 복귀 +0.9초, 그로기는 맵 전투 시간 1.5초. 슬로우 만료 후 IDLE 정상 | PASS(대표) |
| 회귀 V06 | B+A | 그로기 중 피격에서 서버 STUN 유지·조기 해제 없음·deadline 만료로 IDLE | PASS(대표) |
| 회귀 V07 | A | 예고 중·복귀 중 팝업 정지·재개 | PASS(대표) |
| 회귀 V08 | A+B | 예고·복귀·그로기 중 사망, 복귀 중 Stop→재Play 기준 확인. 플레이어 사망·다른 맵 전환은 실행하지 않음 | PASS(대표) |
| 회귀 V09 | - | 이번 Play마다 `catalog ready rules=1 patterns=8` 로드, CSV 변경 시험 없음 | PASS(로드만) / CSV 변경 NOT_RUN |
| 회귀 V10 | B | 실제 Left/Right/Down/Up 키, 실제 mouse로 뒤·앞·가드·공격 버튼 | PASS(대표) |
| V11(사용자 직접) / V12 외부 / CF-F07 연출 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- UI 버튼 좌표 관찰: 뒤·앞 버튼은 시뮬레이터에서 UI 좌표상 중심(790/1130, y 110~180 및 x=760~790 구간 반복 시도)에서 ButtonStateChange(Pressed)가 오지 않았고 x=805·1115, y=170에서만 Pressed가 왔다. 가드(960,180)·공격(960,340)은 중심에서 정상이다. 앞서 QA1도 첫 버튼 가장자리 무반응을 좌표 조건으로 기록했다. 제품 결함인지 시뮬레이터 좌표 재매핑 때문인지 이번 근거로 구분하지 못했다. 사용자 실기기(V11)에서 좌·우 버튼 전체 면적이 눌리는지 확인이 필요하다. 이것으로 F05 UI 경로 PASS를 취소하지 않았다(누름이 입력되면 판정까지 정상).
- 클라이언트 HIT 신호: 복귀 중·그로기 중 피격에서 서버 상태는 ATTACK/STUN을 유지하지만 클라이언트 로컬 상태가 HIT가 되고 clip=hit가 발생한다. 그로기 중에는 hit와 stun RUID가 같아 화면이 같고 복귀 중에는 jump 클립이 hit 클립으로 바뀔 수 있다(이 변경 이전부터 있는 구조, 이번 변경으로 새로 생긴 것으로 판단하지 않음). 화면 확인은 하지 않았으며 reviewer·사용자 판단 대상이다.
- 시험 오류(제품 오류 아님): (1) 첫 G 회차는 이전 snapshot 잔존으로 트리거 시각이 어긋나 무효, 같은 조건을 snapshot 시퀀스 확인으로 고쳐 G2로 다시 실행한 결과만 사용했다. (2) V4 첫 회차는 서버 GUARD 상태 중 UpArrow가 입력돼 거부되어(factor 로그 없음) 무효, 그로기 구간에 맞춰 V4b로 재실행했다. (3) 첫 저스트 프로브는 EvadeDirection을 SetEvading 앞에 줘서 방향이 초기화돼 HIT, 순서를 고쳐 JU2에서 JUST를 확인했다. (4) J2(예고 중 사망) 첫 결과는 로그를 읽기 전에 clear_logs를 호출해 잃었고, 새 몬스터로 같은 조건을 A 회차로 다시 실행한 결과만 사용했다. (5) 시험 시작 시 clear_logs를 호출해 이전 Play의 normal 로그 36건이 지워졌고(사용자 로그 보존 대상 확인 없이 호출함) 이후 회차 사이에도 호출했다. build 로그는 지우지 않았다.
- 제품 runtime 오류·경고 로그는 관측되지 않았다.
- 사망 직후 반격 권한(CounterReady)은 사망 직후 로그에 true였다가 2.0초 창이 끝난 뒤 false였다. 사망 시점에 즉시 소멸하는지는 이번에 구분하지 못했다(사망은 PlayerCombatComponent.ClearCounter 호출 경로가 RefreshDuelPlayer에 있어 소스상 소멸 예정, 로그로는 미확인).

#### 사용 종료
- 모든 키·마우스 up. 서버·클라이언트 프로브 타이머는 완료 시 해제, 나머지는 Stop으로 폐기. 시험값(AttackInterval, 패턴 목록, 규칙 창, 슬로우, HP)은 Play 내부뿐이며 Stop→재Play에서 기준값(interval 3.0, dmg 12, patterns 8, 규칙 .2/.4/2.0/2.2/1.5/2.0×0.5, HP 100, pause false)을 확인했다. 최종 maker_stop 성공, maker_get_current_map map01 / edit, Maker 사용 종료. 시험 후 54/54 동일 Bundle d2b57802…0fbb.
- 다음은 독립 reviewer: 위 PASS/NOT_RUN과 실행 방식 구분(A 서버 프로브 vs B 실제 입력)·한계를 같은 Bundle에서 대조한다. 사용자 V11에서 F01~F04 체감, 별·접촉 파티클 가시성, 좌·우 UI 버튼 전체 면적, 복귀 중 피격 화면을 확인한다.

### 2026-11-02 독립 QA 3회차 — REV-F01
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA/QA2의 PASS를 이번 실행으로 세지 않았다.
- 대상: coder 커밋 6614b20 / 52파일 Bundle SHA-256 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4. 시험 전·후 manifest 52/52 byte 일치(Bundle 재계산 동일, git status 제품 변경 없음). 이전 e8a20728…a49 대비 변경은 MonsterAttackComponent.mlua:134, PlayerHealthComponent.mlua:38이며 두 파일을 소스로도 읽어 확인했다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록 0(MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. 재개 전 build 로그는 coder 갱신본(Info 79, 오류·경고 0)을 그대로 사용했고 이 회차에서 refresh하지 않았다. Play context server_main/client. Maker 로그 시각 19:11~19:20, 오류/경고 로그 0(normal 전체 Info만).
- 실행 방식 구분: (A) 서버 프로브 = 지정 패턴 1행 임시 교체(`_CombatRuleCatalog.patterns`), 몬스터 AttackInterval 일시 상향, 몬스터 `StateComponent:ChangeState("ATTACK")`로 공격 시작, 플레이어 가드는 서버 `ChangeState("GUARD")`, 저스트는 `PlayerEvadeComponent:SetEvading`+`EvadeDirection` 부여. 판정(EvaluateDefense)·피해(CalcDamage→ResolveIncomingDamage)·native AttackFast/HitEvent·HP는 제품 경로이며 HitEvent는 플레이어 엔티티 핸들러로 TotalDamage와 Damages 합계를 읽었다. (B) 실제 입력 = maker_keyboard_input의 DownArrow/RightArrow/LeftArrow/W 실제 키 이벤트가 클라이언트 PlayerInputComponent→PlayerStateControl→서버 상태 진입까지 이어진 경로. 서버 스크립트는 "방어 입력이 서버에서 수락된 순간"에 몬스터 ATTACK을 시작시키는 시험 트리거만 맡았고 방어 상태·시작시각은 실제 입력이 만들었다. 모든 시험값(AttackDamage, 패턴, 간격, WeaponAttack, 몬스터/플레이어 HP, 패링·저스트 창)은 Play 내부에서만 바꿨고 Stop→다음 Play 기준값(dmg12/interval3/rows8/가드.4/패링·저스트 .2/Weapon1) 확인으로 폐기를 확인했다.

| ID·조건 | 방식 | 실제 결과 (HP delta / HitEvent.TotalDamage / Damages 합계) | 판정 |
| --- | --- | --- | --- |
| REV-F01 무가드 일반 (12.7) | A | 12 / 12 / 12, kind HIT | PASS |
| REV-F01 특수 무가드 (12.7) | A | 12 / 12 / 12 | PASS |
| REV-F01 특수+가드 홀드 (12.7) | A(서버 가드) + B(DownArrow 실제 홀드, special.left) | A 12/12/12, B 12/12/12 (kind HIT) | PASS |
| REV-F01 일반 가드 (12.7) | A(normal.guard·normal.left) + B(DownArrow, normal.guard) | 모두 5/5/5, kind GUARD rate .4 (구 코드 기대 4와 구별) | PASS |
| REV-F01 패링 공격 실패 가드 (12.7) | A 가드 시작 hit-1.13s·hit-0.254s(창 밖) + B DownArrow, 가드 시작 hit-.52s·기본 창 .2 | 모두 5/5/5, kind GUARD | PASS |
| REV-F01 유효 패링 성공 (12.7) | A 가드 시작 hit-.103s + B DownArrow, 시험 한정 ParryWindowSec .9(손 타이밍으로 .2 창 불가) | A·B 모두 0/0/0, kind PARRY, native 이벤트 1건 0피해 | PASS (B의 창 폭은 시험 값) |
| REV-F01 유효 저스트 회피 (12.7) | A SetEvading RIGHT(텔레그래프 잔여 .12s 이하에서 부여, 시작시각 직접 미계측, native 이벤트 1건) + B RightArrow 실제, 시험 한정 JustWindowSec .9 | A 0/0/0 kind JUST. B kind JUST, 플레이어가 x=1.5로 이동해 범위 밖이므로 native HitEvent 없음, HP delta 0 | PASS (B는 범위 밖 회피, 창 폭 시험 값) |
| 저스트 방향 불일치 (12.7, 보조) | A SetEvading LEFT + B LeftArrow 실제(RIGHT 예고) | A 12/12/12 HIT. B 플레이어 x=-1.5, native HitEvent 1건 12/12/12 | PASS (보조, 방향 일치 필수 경계 불변) |
| 다른 소수 보조 | A | 7.5 가드 3/3/3(구 선내림 2), 12.99 가드 5/5/5·무가드 12/12/12, 13.99 특수+가드 13/13/13, 0.9 무가드·가드 0/0/0(native 이벤트 1건 0피해) | PASS |
| 기본12 회귀 | A | 무가드 12, 가드 4(12*.4=4.8 내림), 특수+가드 12, 패링 0, 저스트 0 (각 HP=TotalDamage=Damages) | PASS |
| QA-F01 회귀 몬스터 처치 상한 (HP5, Weapon10) | B 실제 W (몬스터·플레이어 HitEvent 핸들러, Weapon10은 Play 내부) | 몬스터 HP 5→0 감소 5, HitEvent 1건 TotalDamage 5, Damages 5, IsCritical 0, DEAD 전이 1회 | PASS(수치) |
| QA-F01 후속 치명·후속 제외 (HP25, Weapon10) | B 실제 W | HP 감소 25, HitEvent 3건 합계 25(10,10,5), Damages 25, DEAD 1회. 10타 예약 중 사망 후 추가 이벤트 없음 | PASS(수치) |
| 플레이어 사망 경계 (HP5, D12.7, 무가드) | A 몬스터 ATTACK | 5→-7, delta 12, 이벤트 1건 12/12, IsDead true, DEAD 전이 1회 (플레이어 쪽 HP 하한 없음은 기존 범위 밖 관찰과 동일) | PASS (경계만, 별도 표시) |

#### 판정 요약
- 기준 1 (소수 12.7 HP delta=TotalDamage=Damages 합계: 무가드·특수/가드홀드=12, 일반·패링실패 가드=5, 유효 저스트/패링=0): PASS. 대표 경우(DownArrow 가드, RightArrow/LeftArrow 회피)는 실제 키 입력 경로로 독립 확인했다. 패링 성공과 저스트 성공의 실제 입력은 .2초 창을 손 타이밍으로 맞출 수 없어 시험 한정으로 창만 .9로 넓혔다(창 경계 자체는 이번 변경과 무관, 기존 QA 근거 범위). 창 .2 안에서 맞춘 성공은 서버 프로브(A)로 확인했다.
- 기준 2 (기본12 가드4/특수12/성공0): PASS (서버 프로브).
- 기준 3 (QA-F01 처치 상한·사망 1회·후속 제외): PASS(수치, 실제 W).
- 기준 4 (플레이어 사망 경계): PASS(경계만). 그 외 슬로우/그로기/팝업/DataSet 로드·V01~V12의 나머지 회귀는 이번 변경(두 파일 각 1줄)과 무관해 재실행하지 않았다. 새 전수 실행으로 세지 않는다.
- NOT_RUN / 미완료: V11(사용자 직접 PC/모바일 가독성·체감·음향·피격/die), CF-F07 연출, V12 외부(실제 두 사용자·비전투 몬스터·다른 맵), 실제 mouse/touch 입력, 창 .2 안의 손 입력 패링/저스트 성공, 가드 시작이 타격 이후인 경우의 별도 관찰(그 경우는 가드 상태가 아니라 HIT로 처리됨).

#### 시험 오류·불확실성 분리
- A 회차에서 서버 `SetEvading`을 직접 호출하면 서버 MOVE epoch가 올라가 클라이언트 epoch와 어긋난다. 그 직후 같은 Play에서 시도한 첫 RightArrow 저스트(kind HIT, EvadeDirection 빈 값)는 이 시험 상태 오염이 원인이라 제품 결과로 세지 않고, Stop→새 Play에서 A 호출 없이 다시 실행한 결과(kind JUST, evadeDir RIGHT)만 사용했다. 제품 오류로 보지 않는다.
- QA-F01 두 번째 시험 첫 스크립트가 몬스터 사망 뒤 재생성(DoSpawn) 전에 시작해 죽은 개체에 Hp를 세팅했다. 해당 시도의 결과는 사용하지 않고 `MonsterManager:DoSpawn()` 후 새 개체에서 다시 실행한 결과만 사용했다. 몬스터 사망 뒤 자동 재생성이 없는 것은 기존 동작(DoSpawn은 OnBeginPlay에서만 호출)이다.
- 서버 프로브 중 몬스터 자연 공격은 AttackInterval 상향으로 막았고, 각 회차의 hit 시각·snapshot kind로 판정 로그를 분리했다.

#### 사용 종료
- 모든 키 up. HitEvent/StateChangeEvent 핸들러 명시 Disconnect, 임시 패턴/창/AttackInterval/WeaponAttack는 Stop으로 폐기. Stop→다음 Play(19:20) baseline: dmg12.0/interval3.0/rows8/가드.4/패링·저스트.2/Weapon1/몬스터 HP100 확인, 이후 maker_stop. maker_get_current_map map01 / edit 확인(전이 중 play 응답 1회 뒤 재확인), Maker 사용 종료. 시험 후 52/52 동일 Bundle 1ac324e6…9de4.
- 다음은 독립 reviewer: 위 REV-F01 수치 PASS와 실행 방식 구분(서버 프로브 vs 실제 키)·한계를 같은 Bundle에서 대조한다.

### 2026-10-29 독립 QA 2회차 — QA-F01 수치 재시험 PASS·리뷰 대기
- 담당: /root/combat_core_tester_v2. coder_v4 종료·사용 양도 후 별도 실행. 제품·모델·맵·UI·DataSet·CSV·원장 수정 없음. 과거 결과를 새 실행으로 세지 않았다.
- 대상: 52파일 Bundle SHA-256 e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49. 시험 전후 52/52 byte 일치. 변경된 PlayerCombatComponent.mlua 외 51파일은 2026-10-25 QA와 동일이며 이전 조건의 적용 한계를 유지한다. 전체 manifest는 뒤의 2026-10-29 개발절.
- 연결: 실제 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root·TileMapMode=0 일치. Play context server_main/client. build 오류0/경고0(Info79).
- 실제 시험 시각: 21:22~21:31 Maker 로그. keyboard_input W/방향키와 명시한 Play 내부 fixture·RPC/상태 진입 프로브 사용. HP/공격력/보너스 부여/시전 간격·길이/적 대기/패턴 선택/복귀 속도는 시험 세션 값뿐이다. 파일/CSV 변경·사용자 로그 clear 없음.

| ID·조건 | 이번 독립 실행 결과 | 판정·한계 |
| --- | --- | --- |
| QA-F01 / V02 원재현 HP5·Weapon10 | 실제 W 첫 native HitEvent5/Damages 합5/HP감소5. 1타·DeadEvent1회·DEAD, 이후 타격 제외 | PASS(수치). 과거 FAIL은 아래 1회차에 보존 |
| V02 후속 치명 HP25·Weapon10 | 실제 W native10,10,5의3타. HP/event/display 모두25·사망1회 | PASS(수치) |
| V02 비치명·보너스·DEFENSE·0피해 | 실제 W: 일반10타100, 보너스10타220, 실제 DEFENSE 첫6+후속16×9=150, DEFENSE 치명5의1타, Weapon0의0피해10타. 각 HP감소=TotalDamage합=Damages합 | PASS(수치). 보너스 부여는 GrantCounter fixture, DEFENSE는 실제 FSM 진입. 숫자 화면 가시성은 V11 |
| V02/V08 사망 뒤 추가 타격 | DEAD 상태에서 native AttackFast·같은 예약 재호출: extra event0/death0/HP변화0, DEAD 유지 | PASS(실행 조건), 일반 사망 프레임워크·연출 평가 아님 |
| V03/V10 지연 방향·거부 입력 | ATTACK 중 client ConfirmDirection(다음 epoch)→server ATTACK/pendingnil/start-1. 실제 GUARD 중 W 거부 후 같은 지연RPC도 GUARD/pendingnil/start-1/evadingfalse. 이후 actual Right가 정상 수락·endpoint 도달 | PASS(대표 조건). 모든 네트워크 도착 순열·실제 맵 이탈은 NOT_RUN |
| V04 진행 중 재성공·시전 실패 | actual W 시전 첫 native hit에서 GrantCounter fixture. 기존 cast multiplier1 유지·10타100, 다음 권한true. Weapon=-1 실제 W는 ATTACK 진입/activefalse/피해0/권한true(remaining .611) | PASS(대표 조건). 시전 데이터 실패 모든 조합은 새 전수 실행 아님 |
| V05 접근·실타격·복귀·만료 | 강제 GUARD/NORMAL 패턴 선택·FSM ATTACK에서 ApplySlow(2,.5). 접근 map .278/action .139=0.5, JumpActive/rate.5. 실타격1회 map1.019/action .5095, 예약due .5085. 복귀 JumpActive/action progress .1295/원래duration.5/targetHome/rate.5. map2.022 후 IDLE/slow0/native rate1. 다음 예고 sequence+1·같은 action clock .5비율, 효과만료 ActionRate1/native1/savednil | PASS(대표 경로). 다음 예고 계측은 명령·로그 사이 선수행분을 포함해 .396map/.198action 및 정렬 fixture .877map/.447action 관측; 이를 정확한 대기 종료시각 정량 PASS로 사용하지 않음. 전수 모션·음향·실기기 평가는 아님 |
| V07/V10 endpoint 실제 팝업 | actual Right 홀드→x1.5/HOLD/sequence17. 실제 _UIPopup.Open→ownertrue/pausedtrue, .5초 뒤 clockDelta0/xDelta0. 키해제·Close 뒤 actual W는 RETURNING/MOVE/held빈값/blockedtrue·sequence17 유지. 완료 후 x0/IDLE/NONE. server pausedfalse/evadeStart-1/evadingfalse/pendingnil | PASS(대표 조건). 복귀 중 관찰창 확보용 ReturnSpeed=.5 fixture 사용 후6복원, 최종 재진입6 확인. 모든 응답 순열·실제 모바일 입력 아님 |
| V08 death 뒤 늦은 metadata | native HitComponent.OnHit 치명 fixture 후 server/client DEAD, HP-25. 그 뒤 client ConfirmDirection은 server DEAD/pendingnil/start-1/evadingfalse | PASS(실행 조건). 수동 HP 차감 아님. 실제 맵 이탈·모든 외부 상태 순열은 NOT_RUN |
| V01/V06/V09/V12 등 무변경 경로 | 2026-10-25 QA·51파일 동일성을 대조. 이번 실제 재진입 rules .4/patterns8·기본상태 확인. 이전 예고·가드/패링·그로기·원자검증·상대 수명 결과는 당시 범위 근거로만 유지 | 새 전수 실행으로 세지 않음. CSV 재편집, 실제 두 사용자·다른 맵·비전투 몬스터 환경은 NOT_RUN 유지 |
| V11 / CF-F07 연출 | 실제 PC/모바일 가독성·타이밍 체감·터치/혼합 조작·화면 잘림·음향·피격/die 평가는 수행하지 않음 | NOT_RUN. CF-F07는 이번 수치 PASS만 추가, 전체 종결 금지 |

#### QA2 시험 오류·계측 한계
- 첫 새 몬스터가 HomeCaptured 되기 전 Home.y=0으로 배치해 낙하했다. lethal5의 event0, 최초 normal100의4타40은 잘못된 배치 조건이라 유효 제품 결과로 세지 않는다. MapBuilder의 발판 maxY=.580000043 및 기존 접지 높이 .581로 배치·Home fixture를 맞춰 동일 조건을 다시 시험한 retry 결과만 위 PASS로 사용했다. 제품 오류·수정 후 재검증 실패 횟수로 합산하지 않는다.
- maker_execute_script는 dispatch 완료일 뿐이다. 중간 시전실패 첫 준비의 대기/입력 순서는 별도 양성으로 사용하지 않고, grant 직후 actual W→ATTACK/activefalse/권한true를 재관찰한 결과만 기록했다.
- 다음 행동 대기의 내부 시계비율·실행 연결은 확인했지만 도구 dispatch 사이의 정확한 시작점 불확실성을 정밀 deadline 통과로 확대하지 않는다. 접근/복귀의 실타격 시각과 적분 배율을 실제 수집한 양성은 별개다.
- 이번 통합 회차 normal runtime 오류/경고0. 위 배치 실패는 로그/계측상 무피해 조건이며 예외 로그를 지우지 않았다.

#### QA2 사용 종료·다음 담당
- fixture HitEvent/DeadEvent·중간 성공/적 공격 관찰 핸들러 명시 Disconnect, runtime fixture=nil. 모든 키 up. 패턴 목록·복귀 속도는 세션 내 복원했고 Stop에서 시험 상태 폐기. 실제 다른 맵 이동·제품/CSV 수정 없음.
- actual Stop→다음Play(21:30:59~21:31:00) baseline: readytrue/Weapon1/10타/.045/range3×1/Counterfalse/fixture nil/evadeStart-1/pendingnil/적간격3/slow0/ActionRate1/jump.5/.8/patterns8/guard.4. client MoveSpeed6/ReturnSpeed6/popupfalse.
- 최종 actual maker_stop 성공 후 maker_get_current_map map01/edit 확인·Maker 사용 종료. 시험 후 52/52 동일 Bundle e8a20728…a49. tester가 제품을 고치거나 QA-F01의 과거 실패를 삭제하지 않았다.
- 다음은 독립 reviewer가 같은 새 버전·승인 요구·개발/QA·잔여 미실시를 대조한다. QA-F01 수치 수정은 PASS지만 V11·CF-F07 연출·실제 외부 환경은 미완료이며 단계 완료/Features 이관/Plan·WR 삭제를 하지 않는다.

### 2026-10-25 독립 QA 1회차 — 결함 1건·필수 미확인 유지
- 담당: /root/combat_core_tester, coder와 별도 실행. 제품·DataSet·CSV 수정 없음. 유일한 Maker 사용 담당으로 인수했으며 과거 coder 결과를 이번 실행으로 세지 않았다.
- 대상: 52파일 Bundle SHA-256 8be49440a9ebbda62fc38df333fb09673db66d2e60a8f873aa38012d7b505e21. 시험 전후 byte 지문 52/52 일치·묶음 동일. manifest/계산법은 뒤의 coder 2026-10-25 절.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186; MapBuilder TileMapMode=0/root 일치. 실제 context server_main/client. 기준 build 오류0·경고0(동적 참조 Info만 있음).
- 실행: Maker 로그 11:07~11:19. native keyboard_input, mouse_input 및 명시한 Play 내부 상태 fixture/논리 RPC 프로브. 임시 HP·무기 공격·행동 간격·타격 간격/시전 시간·패턴 목록은 Play 내부만 조절했다. CSV는 수정하지 않았다. 사용자 로그 clear 없음.

| 검증 ID | 이번 독립 결과·양성 근거 | 남은 범위·한계 |
| --- | --- | --- |
| V01 | PASS: 유효 8행을 각각 Prepare→native Resolve하고 재호출에도 resolutionCount +1. 중앙 HP/HitEvent/Damages 각각12. 별도 실제 클라이언트 HUD 8/8 방향·속성 문구와 3색 구별, 같은 snapshot response/attribute 일치. special+guard 데이터 거부 | 체감·가독성/기기 화면은 V11 |
| V02 / CF-F07 | FAIL: 일반/짧은 가드4·특수12·패링0·실패패링 가드4에서 HP=HitEvent.TotalDamage=Damages 합계. native W 보너스 22×10=220, 실제 DEFENSE 첫6+후속16×9=150도 세 값 일치. 다만 몬스터 HP5를 기본10 첫타로 처치하면 HP감소5·이벤트10·표시10으로 문자 기준 불일치(QA-F01) | CF-F07 종결 보류. 화면 숫자 가시성·die 체감은 V11 |
| V03 | PASS(실행 조건): 창 직전 -.200001/정확히-.20/안/공격시점/직후 .000001 = false/true/true/true/false. 해제된 최근 회피도 범위 밖 JUST 0피해·권한1회, wrong/future는 피해0·보상0. 실제 Left+A 추가출처 시작시각 불변, 다음 실제 RIGHT epoch=bound/미소비예약없음. 동일 client RPC에서 방향 선도착→Close의 pending 폐기와 이후 실제 MOVE 정상 | NOT_RUN: 모든 네트워크 도착 순열, 거부 ATTACK/실제 맵 이탈 뒤 metadata 도착. 직접 훅/시험 RPC는 실제 키 입력과 구분 |
| V04 | PASS(실행 조건): 실제 W와 실제 UI 공격 클릭. 10타 전부 동일 factor2.2, HP/event/display220. 거부 시전(Play 내부 WeaponAttack=-1)은 권한 보존, 실제 whiff는 HP변화0·소비1, 재성공 배율2.2 유지. 고정 맵시계 fixture에서 만료1us전 유지/정확만료 해제 | NOT_RUN: 이번 독립 회차의 진행 중 재성공 비소급·시전 데이터 실패 모든 조합. coder의 해당 근거는 개발 절에 별도 유지 |
| V05 | PASS(실행 조건): 적 action/map 진행 비율 .128/.256=.5, 재적용 rate=.5·남은2초로 비중첩. 실제 팝업에서 action/남은slow 동결, 사망 시 rate/slow 정리, 정상 재진입 rate1 | NOT_RUN: 접근·복귀·대기 전체 구간의 모션/실타격 시각 전수 대조, 오디오·실제 기기 관찰. 기존 coder 만료복원 근거와 구분 |
| V06 | PASS(실행 조건): 실제 그로기 STUN, .25초 뒤 재적용 deadline +.292초. native HitComponent.OnHit3 중 STUN/deadline 유지·HP3 차감. slow와 공존, 실제 팝업 중 잔여 동결, 몬스터 치명 후 DEAD/slow0/stunfalse | NOT_RUN: 모든 상태 조합·옛 completion 직접 재호출 전수. 별 표시 가시성은 V11 |
| V07 | PASS(실행 조건): _UIPopup.Open→RequestPopupPause의 실제 owner/IsPaused 확인. slow1.395·groggy.931·counter1.467·양쪽 진행시계 동결. 다중타격 시험용 HitInterval=.1/시전2초에서 8타 뒤 실제 팝업으로 정지, HP와 fired 불변, 닫은 후 잔여2타만 실행되어 총220·소비1 | NOT_RUN: 이번 독립 회차의 회피 endpoint 팝업·모든 응답 순서. 시험용 시전/간격은 Stop에서 폐기·기본값 재확인 |
| V08 | PASS(실행 조건): 몬스터 native 치명 DEAD/slow0/stunfalse, 실제 DoSpawn oldValidfalse·새상대 연결. 플레이어 actual DownArrow GUARD 중 특수12로 HP5→-7, native 이벤트·표시12. .2초 뒤 server/client DEAD, 가드false·시작시각-1/회피시각-1·보너스false·slow0·상대nil. 이후 실제 W+RightArrow도 sequence불변·DEAD 유지. 실제 Stop→다음Play 기본 설정·권한/효과0 | 사망 직후 순간 state=IDLE 관측을 이번 지연 DEAD 관측으로 보완. die 화면 평가 아님. 옛 Resolve 추가피해0은 자동 Respawn 뒤 관찰이므로 DEAD 상태 검증으로 확대하지 않음. 실제 맵전환은 기존 후속 |
| V09 | PASS(런타임 스키마): 빈값/NaN/nan/inf/음수창·1초과가드·0/1초과slow·0배율·빈id·중복·specialguard·nil table·실제 다른 DataSet의 누락열·무효 modifier 거부. 유효 cache rules default=.4/patterns8 유지. 정상 재진입 rules .4 | NOT_RUN: tester 역할상 실제 CSV 재편집/파일 삭제 시험. coder의 .30→NaN→원본복원 실제 CSV 근거와 현재 byte 지문을 확인했으며 새 독립 실행으로 세지 않음 |
| V10 | PASS(실행 조건): 실제 LeftArrow+A/RightArrow/DownArrow/W. 실제 mouse_input 공격 중심(960,340) 클릭으로 ActionSequence6→7/ATTACK. 실제 뒤 버튼(790,180) 홀드+A→UI해제 후 MOVE/heldLEFT/keyAtrue/ui없음, 마지막 A해제 뒤 중앙복귀. 앞선 방향 Close fixture 후 실제 RIGHT도 정상 | 첫 버튼 가장자리 클릭의 무반응은 좌표 조건으로 구분. 실제 모바일 다중터치·모든 동시 입력/차단 순열은 NOT_RUN/V11 |
| V11 | NOT_RUN | 사용자 직접 PC/mobile 가독성·체감·터치·화면/음향·피격/die 평가 필요 |
| V12 | PASS(실행 조건): 기존 단일 manager 참조, monster 실제 교체 old invalid/new opponent, player 사망 후 opponent nil·공격/효과 거부 | NOT_RUN: 실제 두 사용자·비전투 몬스터·다른맵 환경. 독립 Run 격리 완료로 표시하지 않음 |

#### CombatCore-QA-F01 — 치명 overkill에서 HP 감소와 숫자 불일치
- 요구: R02 / V02 / CombatFoundation-F07. 기대: Plan의 치명 포함 HP 감소=HitEvent 합계=피해 숫자 문자 기준.
- 재현: 같은 버전 map01 Play. 현재 상대 Hp=5, 플레이어 WeaponAttack=10, 기본 스킬·보너스없음·사거리 안. 기존 W 입력으로 정상 시전한다.
- 실제(11:17:32~33): 첫 native HitEvent.TotalDamage=10, Damages 합계10. MonsterHealth.Hp 5→0, 감소량5. 이후 타격은 DEAD 필터로 제외되고 effects는 정상 정리된다. [VRF][QA] lethal.monster.equality FAIL hpDelta=5.0 event=10 display=10.
- 코드 경계: PlayerCombatComponent.mlua:233은 합성 피해를 내림해 반환하며 남은 HP 상한을 두지 않는다. MonsterHealthComponent.mlua:25에서 이벤트 후 HP를 0으로 clamp한다. 기본 비치명·DEFENSE의 단일 차감은 통과했다.
- 영향/처리: 기존 clamp/overkill 표시 관행에서 발생하지만 승인된 문자 기준에는 FAIL이다. tester가 요구를 완화하거나 제품을 수정하지 않았다. reviewer가 native 단계·승인된 최종 피해 규칙과 수정 범위의 충돌 여부를 검토한 뒤 coder 재작업/기획 판단을 정한다. CF-F07은 미완료 유지한다.
- 재검증: 동일 5HP/10피해를 포함해 비치명·가드·저스트·패링·DEFENSE·두 번째 타격 시 남은 HP보다 큰 경우·사망 1회/숫자/연출을 변경 버전에서 다시 확인.

#### 시험 오류·불확실성 분리
- 첫 setup에서 Entity._T에 fixture를 저장해 LEA-2007이 났다. 제품 오류가 아니다. 즉시 Stop/재진입해 해당 핸들러를 폐기하고 Component._T fixture로 재실행했다.
- 실시간이 흐르는 두 API 사이의 0.01초 미래 회피/만료1us전은 호출 도중 경계가 지나 초기 예상과 달랐다. 제품 수치 대신 고정 맵시계 fixture로 바로 전/정확/후를 재검사하여 통과. 이 fixture를 실제 팝업으로 표시하지 않는다.
- 첫 groggy 시험은 server wait 중 client popup을 먼저 dispatch해 pause.IsPaused=true로 적용이 정당하게 거부됐다. 실제 unpaused→효과 확정→popup 순서로 다시 실행한 양성 결과만 사용했다.
- 정상 회차의 제품 runtime 오류는 관찰되지 않았다. 의도한 무효 데이터 경고와 위 setup 프로브 오류는 로그에 보존했다.

#### 사용 종료·다음 담당
- native Event 핸들러는 명시 Disconnect, 첫 잘못된 setup은 Stop으로 폐기. 모든 키/마우스는 up/tap으로 종료. 임시 프로브/수치는 Play 내부뿐이며 제품/CSV 쓰기 없음.
- 마지막 정상 재진입 [VRF][QA] restart true: SkillDataReadytrue/기본10타/WeaponAttack1/HitInterval.045/AttackInterval3/권한false·회피시각-1·slow/groggy0·rate1·guard기본.4. pHP940은 정상 AI가 이미 12피해를 반복한 관찰값이며 초기HP 변경으로 보지 않는다.
- 최종 maker_stop 성공 후 maker_get_current_map map01/edit 확인, Maker 사용 종료. 시험 후 지문 52/52 동일. 독립 reviewer에게 QA-F01과 위 NOT_RUN을 포함해 인계한다. 제품 수정/기준 완화/3단계 진행·CF-F07 종결은 수행하지 않았다.

## 리뷰 기록

### 2026-11-19 독립 리뷰 — 회차 E(CombatCore-UX-01·UX-02) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 미사용, 제품·Plan·run.md 무수정, commit·push 없음. 바꾼 파일은 이 리뷰 절뿐이다.
- 판정: **WAITING** — AI 측 필수 근거(Plan §24.7 1~7)는 같은 버전으로 충족했고 고칠 결함·범위 밖 변경은 없다. 남은 것은 사용자 V11(§24.8) 직접 확인이다. 이 판정은 사용자 수락·출시 승인이 아니다.
- 검토 버전: 로컬 커밋 **3e29a35**(기준 de6e6aa, push 전). 334a934는 run.md·QA 절만 담은 [ops] 커밋이라 제품 판정 대상이 아니다.
- 관련 ID: CombatCore-UX-01(버튼 테마), CombatCore-UX-02(가드 alert·이펙트·효과음, E-Q1 PlayerActionFxData). 새 결함 ID 없음.

#### reviewer가 직접 한 일 (읽기·계산만)
- `git diff de6e6aa 3e29a35` 전체를 읽고 §24.4 대상 파일과 맞췄다. 제품 변경은 CombatRuleCatalog·PlayerGuardComponent·PlayerStateControl·새 DataSet 1쌍·ui/CombatScreen 6경로뿐이고, 문서는 Plan·WorkRecord·AssetList·run.md다. .codeblock·.directory·모델·맵·GameDesign 변경 없음. §24.4 "바꾸지 않는 파일"(CombatInputController·MonsterAttackComponent·MonsterStunComponent·Player_Guard·PlayerCombatComponent·MonsterSoundData 등) 무변경.
- **커밋 트리 Bundle 계산**(node 스크립트, `git show`로 체크아웃 없이 같은 방식): 3e29a35의 map01.map 제외 58경로 = `1d70bc71a65ddd70d8f29c377065b4058e7e60d71f0690ffcab48618e23975dd`, 5ce65d6 57경로 = `28f833db…012a`. coder·tester의 작업 트리 값과 같다 → 두 담당 근거가 3e29a35와 같은 제품 묶음이다(QA15 NOT_RUN 6 해소).
- **UIBuilder 비교**(scratchpad에 `git show`로 저장한 de6e6aa·3e29a35 판 + 현재 작업 트리 판을 `UIBuilder.load().build()`로 읽어 id 기준 깊은 비교, 셸로 .ui를 읽지 않음):
  - de6e6aa → 3e29a35: 최상위 필드 차이 0(EntryKey·CoreVersion 26.10.0.0 등 같음), 엔티티 19 → 23, 삭제 0, 추가 4(`{버튼}/Icon` c208d754·4a770505·8f4dd28a·2f1c31a3), 기존 엔티티 변경 7개(버튼 4개 ImageRUID → e314c09b…·Type 0→1, Highlight 3개 displayOrder 0→1)뿐이다. QA15 기록과 정확히 같다.
  - 3e29a35 → 현재 작업 트리(2026-11-16~19 일시정지 중 Maker 재저장): 최상위 차이 0(파일 안 CoreVersion도 26.10.0.0 그대로), 엔티티 23개·UUID·이름·컴포넌트 구성·RUID·색·크기·앵커·anchoredPosition·displayOrder 모두 같다. 차이는 (1) Icon 4개를 부모 바로 뒤로 옮긴 엔티티 배열 순서(그리는 순서는 displayOrder라 의미 없음), (2) Icon 4개 UITransform의 엔진 관리값 `Position` (0,0,0) → (0,70,0)(같은 버튼의 Highlight가 이미 가진 값과 같음), (3) Icon 4개에 기본값 `Rotation (0,0,0)`·`ZRotation 0` 추가(기존 엔티티는 이미 가진 필드)뿐이다. **의미 있는 변경 없음 — 빌더가 비워 둔 엔진 관리 필드를 Maker가 채운 형식 재저장이다.**
- 소스 읽기: CombatRuleCatalog 전체, PlayerGuardComponent 전체, PlayerStateControl 전체, 새 DataSet 2파일 바이트 형식, `Environment/NativeScripts` EffectService.PlayEffect 정의(고정 위치·instigator 의미 확인).

#### 1. 요청·Plan §24.4 ↔ 실제 변경 (빠짐·초과 없음)
| §24.4 항목 | 3e29a35 실제 | 결과 |
| --- | --- | --- |
| CombatScreen.ui: 버튼 4개 ImageRUID·Type 1·Color 흰색만, Icon 4개 추가, Icon 0·Highlight 1 | 위 UIBuilder 비교와 같음. Color는 원래 (1,1,1,1)이라 값 차이 없음. ButtonComponent·크기·위치·PreserveSprite 무변경 | 일치 |
| PlayerStateControl 16행 sit → alert | 한 단어만 변경 | 일치 |
| PlayerGuardComponent 시작 분기에 연출 1회 | 기존 시작 시각·위치 기록 뒤, `isHeld and not self.isGuarding` 분기 안 | 일치 |
| CombatRuleCatalog 로드·검증·조회 | +53줄 추가뿐, EnsureInitialized·Ready·패턴·능력치·MonsterSoundData 코드 무변경 | 일치 |
| 새 DataSet 1쌍(D-Q1 수동 작성) | 아래 3-5 | 일치 |
- 규칙·수치·입력 계약·판정 코드 변경 없음. 사용자 선택 6개(§24.6)와 E-Q1 답 밖의 기능 추가 없음.

#### 2. 같은 버전 근거와 §24.7 1~7
- coder(2026-11-16)와 tester QA15는 모두 map01 제외 58경로 `1d70bc71…75dd` 작업 트리에서 실행했고, 위 계산으로 이 값이 3e29a35 커밋 트리와 같다. map01.map(사용자 변경)은 두 실행 전후 해시 `3e60c21d…2094` 불변이며 커밋에 없다. `maker_clear_logs` 미사용 기록 일치.
- §24.7 근거 판단(tester 독립 실행 기준, coder PASS는 다시 세지 않음):
  1. UI 정적 — tester UIBuilder 검사 + reviewer 재비교 일치. 화면 존재는 스크린샷(어울림은 V11). 충족.
  2. 데이터 로드 — 부팅 [VRF] guard 행 1회, 회차 D 로드 값 동일. 충족.
  3. 오류 동작 — 빈 칸·형식 오류·중복·빈 id·표 무효·행 없음(경고 1회, 두 번째 없음)·Ready·스폰 유지 모두 런타임 근거. 필수 열 누락의 **경고 줄 자체**만 NOT_RUN이다. 그 결과 경로(ReadRows nil → fxReady false → `guard fx off`, 전투 정상)는 런타임으로 확인됐고, 남은 것은 같은 분기의 `WarnOnce` 한 줄이라 소스 읽기로 판단한다(아래 3-3). 충족으로 본다.
  4. 입력 회귀 — 실제 키·마우스, 터치(마우스)+키 동시 출처 합산 PASS, ←·→·↑에서 sfx 0·↓에서 kind=guard 1. 모바일·실기기는 V11. 충족.
  5. 가드 모션 — 서버 시트 GUARD=alert, 클라이언트 Alert·복귀 stand. 충족.
  6. 이펙트·소리 — 가드 시작당 정확히 1회, 홀드 중 추가 없음, 클라이언트 표시 확인(@Sync 대체 불필요). 충족.
  7. 다른 회귀 — 가드 0.4·hitplayer 소리·PARRY(정상 창, 서버 타이머 논리 경로)·JUST(확대 창)·팝업 정지 중 연출 0·회차 D 대표 회귀·build 오류 0. JUST 정상 0.2초 창의 사람 손 입력은 NOT_RUN이지만, 회차 E는 회피·판정 코드를 바꾸지 않았고(diff 확인) 사람 손 0.20초 타이밍은 회차 A 사용자 V11에서 이미 확인됐다. 충족으로 본다.

#### 3. 새 코드 정확성 (소스 읽기, 런타임 근거와 구분)
1. **ExecSpace**: `EnsurePlayerActionFx`·`GetPlayerActionFx`는 ServerOnly이고, 호출자는 ServerOnly인 `CombatRuleCatalog.OnBeginPlay`와 `PlayerGuardComponent.SetGuarding`뿐이다. `ValidatePlayerFxRows`는 지정 없음(순수 함수). 표는 serveronly true라 클라이언트가 읽지 않는다. `PlayEffect`(서버, 맵 고정 위치·instigator)와 `PlayMonsterSound`(서버 → 결투 플레이어 UserId)는 기존 선례(PlayerCombatComponent 166행·회차 D)와 같은 경로다. 문제 없음.
2. **1회 시도 플래그**: `_T.fxAttempted`는 `_T.attempted`와 별개이고 읽기 전에 세운다. OnBeginPlay에서 EnsureInitialized가 실패해 false를 돌려도 EnsurePlayerActionFx는 이어서 실행되고, 반대로 연출 표 실패는 `Ready`·rules/patterns/monsterStats/monsterSounds를 건드리지 않는다. OnEndPlay에서 캐시·`fxReady`·플래그·`warned`를 함께 지운다. §24.10 계약과 같다.
3. **경고 1회 규칙**: 모든 경고가 `WarnOnce`(세션 키 중복 제거)를 거친다. 열 누락·표 없음은 `ReadRows`가 nil → `WarnOnce("PlayerActionFxData missing or required columns missing")` 후 return이며, 이 줄은 회차 D의 `MonsterSoundData missing …`과 같은 형태다. 로드는 세션당 1회이고 검증은 첫 오류에서 멈추므로 실제 세션에서 표 경고는 최대 1건이다. 표 무효 때 조회는 추가 경고 없이 nil, 행 없음은 키 `player action fx row missing: guard`로 1회. 계약과 같다.
4. **실패하면 연출만 끔**: 조회가 nil이면 PlayEffect·PlayMonsterSound를 모두 건너뛰고 `self.isGuarding = isHeld`까지 그대로 진행한다. 가드 시작 시각·위치 기록은 연출 코드보다 앞이라 판정 입력이 바뀌지 않는다. 빈 EffectClip은 PlayEffect만, 빈 EffectSound는 PlayMonsterSound 안에서 무호출. 계약과 같다.
5. **DataSet 형식(D-Q1)**: `PlayerActionFxData.userdataset`은 같은 폴더 MonsterSoundData.userdataset(회차 D)과 EntryKey·`id`·`name`만 다르고 바이트 형식(CRLF·끝 줄바꿈 없음·필드 순서)이 같다. EntryKey와 `ContentProto.Json.id`가 같은 새 UUID `ecb9c840-…`이고 저장소 안에서 중복 없음. serveronly true·UseService 1·CoreVersion 26.10.0.0(작성 당시 Environment/config 값). 회차 B 파일(PlayerBaseStatData)과의 차이는 UseService·serveronly 값뿐이며 이는 §24.10 지정값이다. CSV는 UTF-8 BOM·CRLF·끝 줄바꿈으로 기존 CSV들과 같다. 일치.
6. **PlayerStateControl**: `alert`는 MapleAvatarBodyActionState 값이고, 서버 OnBeginPlay의 기존 SetActionSheet 경로를 그대로 쓴다(PlayRate 1은 이전 sit와 같음). 문제 없음.
- 비차단 메모(수정 요구 아님): SetGuarding에서 연출 호출이 `self.isGuarding = isHeld`보다 앞에 있어, 만약 PlayEffect·PlaySound가 예외를 내면 가드 상태 기록이 빠질 수 있다. 검증된 RUID와 유효한 엔티티만 넘기고 기존 공격 이펙트 선례도 같은 호출이라 현실 위험은 낮다. 이후 회차에서 이 함수를 고칠 일이 있으면 연출을 상태 기록 뒤로 옮기는 것을 고려할 수 있다.

#### 4. CombatScreen.ui 재직렬화 의견
- (a) de6e6aa → 3e29a35 근거: tester의 UIBuilder 깊은 비교(build 정규화 값)에 reviewer의 독립 재비교(최상위 필드 포함)가 정확히 일치하고, coder·tester Play에서 UI가 표시되고 build 오류 0이며 CombatInputController 바인딩 12개가 새 파일 엔티티로 풀렸다. 의미 변경 확인 근거로 충분하다. 빌더가 흡수하는 필드는 구분하지 못한다는 한계는 남지만, Maker 26.11이 이 파일을 다시 저장하고도 의미 차이가 없었다는 점(아래 b)이 Maker 인식 쪽 근거를 보탠다.
- 위험: `.gitattributes * -text`라 바이트가 보존되고, 빌더 출력은 Maker가 읽고 다시 썼으므로 인식 위험은 없다고 본다. 남는 위험은 검토성뿐이다(줄 diff가 수천 줄이라 사람이 git diff로 의미를 볼 수 없음). 그래서 이 파일의 이후 변경 검토는 계속 UIBuilder 비교로 하고, Maker 저장마다 형식 변경이 생길 수 있음을 전제로 한다.
- (b) 3e29a35 ↔ 작업 트리: 위 "직접 한 일"대로 형식 재저장(배열 순서·엔진 관리 Position·기본 Rotation 필드)이며 의미 변경 없음. 회차 E 커밋에 섞지 않는 것이 맞고, 처리(그대로 둠·별도 [ops] 커밋·되돌림)는 메인이 사용자에게 알리고 정한다. 되돌려도 다음 Maker 저장 때 같은 형식으로 다시 바뀔 가능성이 크다.

#### 5. CoreVersion 26.11 영향 (의견, 환경 판단은 메인·사용자)
- 판정 대상 3e29a35의 근거는 2026-11-16 Maker(당시 Environment/config 26.10.0.0)에서 나왔다. 이 판정은 그 버전 기준이며 26.11 런타임은 AI가 확인하지 않았다.
- 정적 영향은 작다고 본다: 26.11 동기화로 바뀐 `.d.mlua` 23개·새 파일들 가운데 이 회차가 쓰는 API(EffectService.PlayEffect, SoundService, DataService, AvatarStateAnimationComponent.SetActionSheet, StateComponent, PlayerControllerComponent)는 바뀌지 않았고, 바뀐 멤버(MapComponent.InstanceMap 정의 위치·ScrollBar 속성·UserEnter/LeaveEvent 생성자·Tweener·ApplicationService 등)를 RootDesk 스크립트가 쓰지 않는다(Grep 0건). Maker 26.11이 CombatScreen을 다시 저장했지만 의미 차이는 없다.
- 사용자 V11은 지금 Maker(26.11)에서 하게 되므로 V11 자체가 26.11 실행 확인을 겸한다. 다만 V11 전에 AI가 짧게 확인하고 싶다면 tester 1회 연기 시험을 권한다: Refresh → build 로그 오류 0 → Play 부팅 [VRF](`catalog ready`·`PlayerActionFxData id=guard`) → ↓ 가드 시작 1회(`guard fx`·`sfx kind=guard` 각 1줄, alert) → Stop. 결과가 다르면 26.11 회귀로 따로 다룬다. 필수 여부는 메인이 사용자에게 묻는다.
- 참고: 이후 손으로 만드는 DataSet 래퍼는 `CoreVersion`을 그때의 Environment/config 값(현재 26.11.0.0)으로 쓴다(platform.md §16). 이미 있는 PlayerActionFxData의 26.10.0.0은 작성 당시 값이라 고칠 필요 없다.

#### 6. tester NOT_RUN·관찰 반영
| 항목 | 판정 반영 | 넘길 곳 |
| --- | --- | --- |
| NOT_RUN 열 누락 경고 줄 직접 실행 | 비차단. 결과 경로는 런타임, 경고 한 줄은 소스 판단(3-3) | 없음(PASS로 세지 않음, 기록만) |
| NOT_RUN JUST 정상 창 사람 손 입력 | 비차단. 판정 코드 무변경, 회차 A V11에서 사람 손 0.20초 확인됨 | 원하면 사용자 V11에서 함께 |
| NOT_RUN 모바일·실기기 터치 | 비차단(기존 V11 미확인 항목) | 사용자 V11(§24.8 "모바일 터치") |
| NOT_RUN 커밋 트리 Bundle | reviewer 계산으로 해소 | 없음 |
| NOT_RUN .ui 줄 diff | 셸 가드 대상이라 UIBuilder 비교로 대체(위 4) | 없음 |
| O-1 무기 없으면 공격·가드 같은 모습 | 결함 아님(§24.5 기록된 위험, 규칙 변경 없음) | 사용자 V11 |
| O-2 형식 오류 경고 문구 하나 | 결함 아님. 실제 세션은 첫 오류에서 검증이 멈춰 경고 1건이며 회차 D MonsterSoundData와 같은 방식. 칸·값을 경고에 넣는 것은 새 요구 | 문서 정리(§24.7-3 "원인당 1회" = 문구 키 단위라고 적기) |
| O-3 이펙트 첫 프레임 흰 세로선·오른쪽 위 방패 | 결함 아님(클립 자체 모습, 화면 판단) | 사용자 V11(이펙트 모습·위치·좌우 반전) |
| O-5 팝업 중 입력 차단 원인 미구분 | 결과는 §24.7-7 충족. 소스상 클라이언트 `PlayerStateControl.CanAcceptInput`가 `_UIPopup.isOpen`·InputBlocked에서 새 입력을 먼저 막는다(서버 정지 규칙 이전 단계) | 문서 정리(근거 한 줄) |
| O-6 §24.7-2 "패턴 4행" | 낡은 표현(실제 5행) | 문서 정리 |
| 스크린샷 사용(coder 3장·tester 10장 남짓) | §24.7-4는 좌표용만 허용했지만 §24.7-6이 클라이언트 표시 1회 확인을 요구해 Plan 안에서 충돌. 제품 판정에는 영향 없음 | 문서 정리(다음 Plan에서 이펙트 표시 확인용 스크린샷 허용 범위를 명시) |

#### 사용자 V11 (§24.8 그대로 + 관찰 연결, AI 결과로 대신하지 않음)
1. 버튼 4개 원형 배경·아이콘이 메이플 분위기와 맞는지, 눌림 표시(어둡게), 노란 Highlight와 어울림, ↓ 아이콘이 ←·→·↑(칼)와 어울리는지.
2. 흰 아이콘이 원형 배경 위에서 잘 보이는지(아니면 테마 문자색 계열로 바꿀지 그때 결정).
3. 가드 모습 alert가 대기 stand와 구분되는지, 무기 없는 계정에서 공격과 같은 모습인 점이 괜찮은지(O-1).
4. 가드 이펙트 크기·위치·방향(좌우 반전 필요 여부), 첫 프레임 흰 선(O-3), 소리 크기, 가드 직후 맞을 때 가드음·피격음 연속.
5. 팝업 정지 중 모습, 모바일 터치(해 보셨다면).
6. (선택) PlayerActionFxData.csv guard 행 칸을 비워 그 연출만 끄기(CSV 수정 → Refresh → Play).
- CoreVersion 26.11에서 V11을 하게 되므로, 이상이 보이면 26.11 차이일 수 있음을 함께 알려 달라고 안내한다.

#### 회차 종료 planner 정리 목록 (사용자 V11 뒤)
- Plan §24.7-2 "패턴 4행" → 5행(O-6). §24.7-3 "원인당 1회"는 경고 문구 키 단위임을 한 줄로(O-2). O-5 근거(클라이언트 입력 게이트) 한 줄.
- §24.7-4·6 스크린샷 허용 범위 충돌을 다음 Plan 작성 원칙에 반영할지 판단.
- §24.9 UX-01·UX-02 상태, AssetList "사용 예정(회차 E)" → "사용 중" 이동과 교체된 기존 버튼 이미지 4개 기록(§24 AssetList 문구), GameDesign·로드맵·WorkRecord 재개 지점은 V11 결과대로.
- 작업 트리의 일시정지 중 변경(Environment/config 26.11, 스킬·NativeScripts·AGENTS.md·skills-lock 동기화, CombatScreen 형식 재저장)은 회차 E 문서가 아니라 메인의 [ops] 판단 대상이다.

#### 검사하지 않은 범위
- Maker 실행(26.10·26.11 모두), 화면 육안, 소리 청취, 모바일·실기기, 다중 접속. `.ui` 원본 JSON 줄 단위 내용(UIBuilder 정규화 값으로만 비교).

#### 다음 행동
- 메인: 회차 E [review] 커밋·push(3e29a35·334a934 포함, map/map01.map과 일시정지 중 작업 트리 변경은 제외) → 사용자에게 작업 트리 변경(CoreVersion 26.11·CombatScreen 형식 재저장 등) 알림과 26.11 연기 시험 여부 질문 → 사용자 V11(§24.8).
- tester: 사용자가 원할 때만 위 5의 26.11 연기 시험 1회.
- coder: 할 일 없음.
- planner: 사용자 V11 수락 뒤 위 정리 목록. V11에서 새 요구·결함이 나오면 해당 ID만 다시 돈다.

### 2026-11-16 독립 리뷰 — 회차 D2 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행).
  - 하지 않은 것: Maker MCP 제어·Play·refresh·로그 비우기, 제품·Plan·run.md 수정, QA 판정 수정, commit·push.
  - 런타임 사실은 coder 두 절("2026-11-10 회차 D2 — MM-13~15", "2026-11-10 회차 D2 MM-14 2차")과 QA14를 대조한 것이다. reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: 회차 D2 = **1b41f29**(MM-13·MM-15, 패턴 CSV) + **e710907**(MM-14 2차, OrangeMushroomAttack.mlua). 기준은 원격 HEAD 7cbf14e(제품 8428a05, 57경로 Bundle `8d5b6d1c…4eed`). QA14 대상 = coder 마지막 커밋 = 이 리뷰 대상이다. 함께 push될 87413bd([ops] skills-lock.json)는 회차 범위 밖이며 비밀값·경로만 봤다.
- 요구 ID: CombatCore-MM-13·MM-14·MM-15(Plan §22.17).
- 판정: **WAITING**. 고칠 제품·문서 결함은 없다(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 남은 필수 일은 사용자 V11이다(0.7배 체감, 조절 항목 비교·선택, 1칸 점프음 청취·선택, 난이도). 이 판정은 사용자 수락이 아니다.

#### reviewer가 직접 한 일
- git 대조:
  - `git log origin/main..HEAD`: push 전 1b41f29·e710907·87413bd 3개.
  - `git diff --name-status 8428a05 e710907 -- RootDesk Global map ui`: 제품 변경은 패턴 CSV·OrangeMushroomAttack.mlua 2경로뿐(모델·맵·UI·.codeblock 0).
  - `e710907..HEAD`, 작업 트리 대 HEAD의 같은 경로 diff: 0. 추적 안 된 파일 0(`git status --untracked-files=all`은 run.md·이 WorkRecord만).
  - CSV diff 전문(7cbf14e→1b41f29), mlua diff 전문(1b41f29→e710907)을 읽었다.
- 바이트 지문(커밋 트리에서 직접 계산): `git cat-file blob`의 SHA-256이 coder manifest 값과 모두 같다.
  - e710907 CSV `f71c57a5…142e`(= 1b41f29 CSV), e710907 mlua `28a53a2b…d99a`.
  - 바뀌기 전 값: 8428a05 CSV `f1ebd85e…58e4`, 1b41f29 mlua `dcc35351…147d`.
- **57경로 Bundle 문자열 자체는 커밋 트리에서 다시 계산하지 않았다.** 전체 문자열에는 `.model` 파일 바이트가 들어가는데, 셸로 `.model`을 읽는 명령은 프로젝트 가드가 막는다. 가드를 피해 가는 방식은 쓰지 않았다(2026-11-08 C2 리뷰와 같은 처리). 대신 아래로 대신했다.
  - 8428a05 커밋 트리 Bundle `8d5b6d1c…4eed`는 앞 리뷰가 커밋 트리에서 재계산했다.
  - 8428a05→e710907 차이는 위 2경로뿐이고, 두 경로의 새 해시가 coder manifest의 줄과 같다.
  - 작업 트리 = e710907(제품 경로)이다. 그래서 tester가 작업 트리로 계산한 `1e468c15…21bc4`(시험 전·후 57/57)가 커밋 트리 e710907에도 그대로 적용된다.
- 소스 읽기: OrangeMushroomAttack 전문, MonsterAttackMotion 전문(StartDrivenClip·TickClip·GetClipTimeline·GetWindupSeconds·ApplyClipRate), CombatRuleCatalog의 ParseOptionalRuid 사용처.
- 비밀값·경로 검사: push 전 3커밋 diff와 메시지, 작업 트리 문서 diff에 토큰·키·개인 이메일·로컬 사용자 경로가 없다. 작성자는 기존 GitHub noreply다. 87413bd는 `version` 1→2와 스킬 14개의 `computedHash`만 바뀌었다. 값은 공개 저장소 출처 이름·저장소 상대 경로·내용 해시라 비밀값이 아니다.

#### 판단
1. **사용자 요청 세 가지 반영과 범위:** 승인 범위대로다. 범위를 넘은 변경은 없다.
   - 0.7배(D-Q8, MM-13): CSV 2·3칸 세 행만 `TelegraphLeadSec 1.571429`·`MotionPlayRate 0.7`이다. 다른 열·행·순서·BOM·줄 끝은 그대로다(diff 5줄 교체). 22.17.2 표와 같다.
   - "점프 중 뚝 끊김"(D-Q11)을 조절 항목으로 비교(D-Q12, MM-14 2차): 속성 2개(기본 true/true)와 그 동작만 들어갔다. 22.17.10.4 밖 파일 변경 0, MonsterAttackMotion·Monster_Attack·MonsterStateControl·모델 변경 0이다.
   - 1칸 점프음(D-Q10, MM-15): 1칸 두 행 AttackSound만 `35ee15e5…`로 바뀌었다. 재생 시점 코드는 바뀌지 않았다(22.17.4대로 공격 시작 = 점프 시작). 후보 2개는 CSV에 넣지 않았다(V11용).
   - 바꾸지 않을 것(22.17 머리말)이 지켜졌다: 판정 창·피해·Weight, 1칸 0.5초, JumpDuration·JumpHeight, LeapJumpHeight 0, JumpStartFrame, 착지 x, 22.15, 22.16.4, D-Q6.
2. **MM-14 1차 STOP → 2차 계약 흐름:** 계약대로다.
   - 1차(1b41f29): 기준선에서 B2~B5가 통과했고, B1은 순서·건너뜀·되돌림이 통과했다. 22.17.3-3에 따라 코드를 고치지 않고 멈춰 메인에 돌려줬다. 분리 시험 코드는 제품에 남지 않았다(1b41f29 .mlua 변경 0).
   - 그 뒤 순서: 메인이 사용자에게 순간을 다시 물음(D-Q11) → 사용자가 방향을 정함(D-Q12) → planner가 22.17.10 계약을 정함 → coder가 구현함. 22.17.3의 "사용자에게 다시 묻는다" 절차와 맞다.
   - 남는 점: MM-14는 "원인 확정 후 수정"이 아니라 "사용자가 고르는 조절 항목"으로 끝났다. 측정상 원인은 여전히 확정되지 않았다. 해소 판단은 V11 체감뿐이다(Plan 22.17.10.6도 같은 뜻).
3. **코드 ↔ 22.17.10 정의:** 일치한다.
   - 경계 인덱스: `bounds[1]=0`, `bounds[i+1]` = f_i 시작(StartDrivenClip). 그래서 W = `bounds[j+1]`, L = `bounds[count]`(f4 시작)다. 루프 `bounds[j+1+i] = W + i·(L−W)/n`(i = 1…n−1)은 j=1·c=5에서 `bounds[3]`·`bounds[4]`(f2·f3 시작)만 바꾼다. 정의(n = c−1−j)와 같다.
   - W·L 불변, 캐시 불변: bounds는 공격마다 새로 만드는 표다(`local bounds = { 0 }`). 캐시 `_T.timelines`의 delays는 건드리지 않는다. `GetWindupSeconds`·스폰 검증·`_T.leapStart`는 같은 캐시를 써서 변하지 않는다.
   - 슬로우와의 관계: PlayRate 변경(ApplyClipRate)은 bounds를 다시 만들지 않는다. 그래서 균등화가 공격 끝까지 유지되고, 경계가 액션 시계라 D-Q6 동작도 그대로다.
   - 적용 제외: j ≤ 0이거나 n ≤ 1이거나 구동이 없으면 "skip"이다. 1칸은 BeginWindup을 타지 않는다.
   - smoothstep 적용 대상: `_T.easeActive`가 켜졌을 때 x 진행률만 `t·t·(3−2t)`다. y는 시간 t의 포물선 그대로다. `t ≥ 1`이면 먼저 CompleteMotion으로 빠지고, 착지 위치는 CompleteMotion이 맞춘다.
   - 1칸·복귀 불변: JumpToLocalX에 `self._T.easeActive = false` 1줄만 더해졌고 PerformReturnMotion 변경은 0이다. 복귀는 JumpToLocalX를 거치므로 직선이다.
   - 공격 시작 때 고정: EaseLeapMove는 BeginWindup에서 StartDrivenClip 성공 직후 `_T.easeActive`로, EqualizeLeapFrames는 같은 자리의 EqualizeLeapBounds에서 읽는다. 공격 도중 속성을 바꾸면 다음 공격부터 적용된다.
   - 실패 경로: StartDrivenClip이 실패하면 CancelMotion 뒤 -1이다. 그때 이전 easeActive 값이 남지만 이동이 시작되지 않으므로 영향이 없다. 다음 이동은 BeginWindup이나 JumpToLocalX가 다시 정한다.
   - ExecSpace는 새 메서드도 ServerOnly이고, [VRF]는 `IsMakerPlay` 안에만 있다.
   - 사소한 점(결함 아님): EqualizeLeapBounds는 속성이 끔이면 n ≤ 1이어도 "false"를 돌려준다. [VRF] `leap bounds`는 f1~f4만 적는다(이 클립 5프레임 기준). 둘 다 로그 표시만의 차이다.
4. **QA14 근거의 한계가 판정을 막는가:** 막지 않는다. 각 한계를 다음과 같이 본다.
   - 시험 값으로 늘린 실입력 시험(lead 24~80, JumpDuration 8): 피격 가능 여부는 `Segment` 값으로 정해지고, 그 경로(Monster_Attack·PlayerHitRule·IsSegmentHittable)는 D2에서 바뀌지 않았다. 정상 길이의 구간 전환(windup → approach → return)은 A 프로브가 시각으로 따로 보였다. 정상 길이의 사람 손 타이밍은 V11 몫이다.
   - PARRY 창 확대(30초): 판정 코드는 D2에서 바뀌지 않았다. 0.20초 창의 사람 손 성공은 회차 A V11에서 이미 수락됐다. 이번 시험은 결과 종류·HUD·그로기 경로가 이 버전에서 돈다는 확인으로 충분하다. JUST 미시험도 같은 이유로 막지 않는다.
   - 35ms 샘플: 정지 기준(0.05초)과 표시 시간 기준(켬 0.071초 이상, 끔 0.035초 이상)보다 촘촘하다. coder는 약 16ms로 같은 결론을 냈다. 프레임 사이의 순간 끊김은 두 측정 모두 볼 수 없고, 그 부분은 V11 체감 몫이다.
   - O-1(사례 102, (끔,끔) 클라이언트 0.09초 멈춤 1건, 재현 0/28): 서버 위치는 역행·정지가 없었다. 같은 순간 샘플러도 간격이 흔들렸다. 그리고 (끔,끔)은 1b41f29와 같은 이동식이다. 그래서 D2 코드가 만든 회귀로 볼 근거가 없다. 다만 사용자가 말한 "뚝 끊김"이 이런 간헐 현상일 가능성은 남는다(아래 V11 2번).
   - O-2: 샘플 시각 문제로 설명된다. 식 자체는 소스와 맞는다.
   - O-3: 22.17.10.5가 판정 대상에서 뺀 기록 항목이다.
   - 경계값: 22.17.7-2 클라이언트 f1 최대 +0.047(한도 0.05)과 coder T8 S2 클라이언트 착지 +0.047은 클라이언트 이벤트 지연(1~2프레임)이다. 계약 문구(서버 f1↔W, 서버 f4↔판정)는 여유 있게 통과했다.
   - 커밋 트리 해시 미실시(tester): 위 "reviewer가 직접 한 일"의 git 동일성으로 메웠다.
5. **문서·기록:** 결함은 없다. 정리할 낡은 표기는 아래 planner 목록에 넣었다(22.17.9·22.17.10.10 상태 문구, coder 절 제목 날짜).
6. **관찰(판정에 쓰지 않음):**
   - 접근 이동이 서버 `OnUpdate`의 매 틱 `body:SetPosition`이다. msw-combat-system §1-6은 이 방식을 연속 이동에 쓰면 끊겨 보인다고 적는다. 22.17.10.3이 이번 2차에서는 이동 방식을 바꾸지 않기로 정했으므로 계약 위반은 아니다. V11에서 끊김이 남으면 다음 후보다(22.17.3 허용 해결의 "속도 기반 이동"). 이것은 T1·D-Q6 재증명이 필요한 새 결정이다.
   - 87413bd 커밋 시각(09:25:27)이 tester 본시험 Play 시작(09:25)과 겹친다. 제품과 무관한 파일이고 판정에 영향이 없다. 다만 CLAUDE.md의 "Play 중 커밋하지 않음"을 문자 그대로 지키려면 담당 종료 뒤에 커밋하는 편이 맞다.

#### 사용자 V11 재점검 (Plan 22.17.8 + 22.17.10.8, AI 결과로 대신하지 않음)
1. **0.7배 속도:** 2칸 좌·우·3칸에서 눈빛 제자리 약 1.14초 → 도약 약 0.43초 → 착지 = 판정(약 1.57초)이 괜찮은지 본다.
2. **"점프 중 뚝 끊김" 비교:** 머쉬맘 모델 → OrangeMushroomAttack 컴포넌트에서 값을 바꾸고 Play한다. Stop 상태에서 바꾸는 것을 권장한다. 공격 시작 때 읽으므로 도중 변경은 다음 공격부터 적용된다.
   - 비교 순서: ① 기본 (켬,켬) → ② (끔,끔) = 이전 모습 → ③ (켬,끔)·(끔,켬)으로 어느 쪽이 효과인지 가른다 → ④ 마음에 드는 조합에서 LeapJumpHeight 0 → 0.3 → 0.5.
   - 볼 것: 도약 자세가 고르게 바뀌는지, 출발·착지가 딱 멈추지 않는지, 판정 체감이 그대로인지.
   - 여전히 끊기면 어느 순간(눈빛 정지, 도약 시작, 이동 중, 착지)인지, 그리고 가끔 한 번씩만 멈추는지(O-1 같은 간헐)를 알려 준다.
3. **1칸 점프음:** 1칸 두 행 AttackSound에 기본 `35ee15e50b17410093e768c33f7f76d6`(0.29초)과 후보 `64c83d144b5d46ffa6d460ca61a66f1d`(0.86초)·`09df85566b984d72b97c7aa9860c4b18`(1.25초)을 넣어 듣는다. 절차는 CSV → Maker Refresh → Play다.
   - 긴 후보는 착지(0.5초) 뒤에도 이어지고 슬로우에 늦춰지지 않는다.
   - 두 행에 다른 소리를 둘 수 있다. 값은 소문자 32자를 그대로 복사한다. 형식이 틀리면 패턴 표가 거부되고 경고 1회 "invalid attack sound ruid"가 남는다.
4. **난이도:** 2·3칸 반응 시간 약 1.57초와 제자리 반격 구간 약 1.14초가 괜찮은지 본다.
5. **회차 D 나머지 V11은 그대로 남아 있다(22.8 V11 1~9, 22.16.9):** 모션·순서, f4 잘림, 3칸 판정, 효과음 4종, 눈빛·먼지 이펙트 위치·방향, 비율·Weight, 속도 값 설정.
6. 고른 값(CSV AttackSound, 기본값과 다른 모델 속성 값)은 회차 종료 커밋에 들어간다.

#### 속도 조절 표 (22.16.9 갱신본 기준, 절차: CSV 수정 → Maker Refresh → Play / 속성은 머쉬맘 모델의 OrangeMushroomAttack 값)

| 항목 | 위치 | 지금 값 | 바꿀 때 알아둘 동작 |
| --- | --- | --- | --- |
| AttackInterval | MonsterStatData.csv(mushmom) | 3.0 | 공격 종료 뒤 대기. 크게 줄이면 슬로우가 다음 접근과 겹칠 수 있다(D-Q6 이어 재생으로 처리됨) |
| TelegraphLeadSec | MonsterAttackPatternData.csv(행별) | 1.571429/1.571429/0.5/0.5/1.571429 | 2·3칸 = 1.1 ÷ MotionPlayRate. 참값 이상이 되게 여섯째 자리에서 **올려** 적는다(예: 0.6 → 1.833334, 0.8 → 1.375, 0.5 → 2.2). 제자리 W(= 0.8 ÷ MotionPlayRate) 이하로 줄이면 스폰 검증이 거부해 머쉬맘이 나오지 않는다(경고 1회). 1칸은 JumpDuration(0.5)보다 짧으면 그 행이 취소되고 경고 1회 |
| MotionPlayRate | 같은 표(행별) | 0.7/0.7/1/1/0.7 | 2·3칸 클립·이펙트 재생 속도. 정렬식 1.1 ÷ TelegraphLeadSec을 지켜야 클립 착지 자세가 판정과 맞는다. 벗어나도 공격은 사라지지 않고 자세만 어긋난다 |
| AttackSound(1칸 두 행) | 같은 표 | 35ee15e5…/35ee15e5… | 1칸 공격 시작(= 점프 시작) 소리. 후보 64c83d14…·09df8556…. 빈 값은 무음 |
| JumpStartFrame | 같은 표 | 1/1/빈/빈/1 | 클립 프레임 수(5) 이상이면 스폰 거부 + 경고. 음수·소수·문자면 표 전체 거부 + 경고 |
| EqualizeLeapFrames | OrangeMushroomAttack 속성 | true | 켬: 도약 f1·f2·f3 각 약 0.143초(0.7배). 끔: 원작 비율 0.286/0.071/0.071초. W·착지·판정 시각은 같다 |
| EaseLeapMove | OrangeMushroomAttack 속성 | true | 켬: 2·3칸 수평 이동 smoothstep(천천히 출발·멈춤, 가운데 최대 1.5배 속도). 끔: 일정 속도. 착지 x·시각은 같다 |
| LeapJumpHeight | OrangeMushroomAttack 속성 | 0 | 2·3칸 실제 점프 높이(시간 포물선, 곡선과 따로). 클립 자체 도약 약 0.88과 겹친다 |
| JumpDuration·JumpHeight | OrangeMushroomAttack 속성 | 0.5·0.8 | 1칸 접근·복귀 점프. JumpDuration이 0 이하면 모든 공격 취소 + 경고 |
| WindupHittable | OrangeMushroomAttack 속성 | true | 눈빛(제자리) 중 피격 여부 |

- 공통: 값이 맞지 않으면 대신할 값 없이 거부·취소하고, Maker 로그에 `[CombatRuleCatalog]` 경고를 같은 원인당 한 번 남긴다.

#### 회차 D 최종 V11 수락 뒤 planner 정리 목록 (앞 리뷰 목록 + D2 추가)
- 앞 리뷰 목록 그대로:
  - §22.14 상태, §22.2·§22.8 V11 1번 대체 표시, "클라이언트 f4" 문구, §22.16.9 속성 이름
  - GameDesign(메인), AssetList, FileStructure §4, 로드맵 §5, WorkRecord 머리말·재개 지점, 원장 castleenemy(범위 밖)
  - REV-D-O1 수정 완료(8428a05, QA13) 기록, §22.16.9 경고 동작 반영, QA13·coder 소절 날짜 표기
- D2 추가:
  1. §22.17.9·22.17.10.10 상태를 갱신한다. "로컬 미커밋", "tester 대기"를 커밋 1b41f29·e710907, QA14, 이 리뷰, V11 결과로 바꾼다.
  2. MM-14 마감 문구를 한 줄로 남긴다. 측정상 원인은 확정되지 않았다(22.17.3-3 (라)). 사용자 선택 조절 항목(D-Q12)과 V11에서 고른 값으로 마감했다.
  3. V11 선택값을 반영한다. 1칸 AttackSound 최종값(CSV)을 넣고, AssetList "사용 예정 (회차 D)"의 임시 3행을 채택값만 남겨 확정한다. 모델 속성이 기본값과 다르면 사용자 Maker 저장분을 회차 종료 커밋에 넣는다.
  4. §22.16.9·22.17.2의 "여섯째 자리 반올림"을 "참값 이상이 되게 올림"으로 바로잡는다(0.7배 값은 반올림 = 올림이라 지금 값은 맞음).
  5. §22.13 부채·관찰에 등록한다.
     - O-1 간헐 클라이언트 멈춤(원인 미확인)
     - O-3 프레임 이벤트 이중 도착(22.17.10.5)
     - 서버 OnUpdate `SetPosition` 연속 이동(1칸·복귀 포함, msw-combat-system §1-6 비권장. V11에서 끊김이 남으면 후속 후보)
     - 착지 순간 정지 0(coder 1차 관찰 3, 22.16.2 구조)
  6. GameDesign(메인)에 반영한다: 2·3칸 반응 약 1.571초·제자리 반격 약 1.143초(22.17.2), 1칸 점프음, 도약 조절 항목과 고른 값.
  7. coder MM-14 2차 절 제목(2026-11-10, 실제 2026-11-16)과 Plan 22.17.10 날짜 표기를 맞춘다.

#### 다음 행동
- 메인: 회차 커밋 `[CombatCore][review] WAITING`(QA14·이 리뷰 절·run)을 만든다. push 전에 비밀값 검사를 하고 1b41f29·e710907·87413bd와 함께 push한다. 그다음 사용자에게 위 V11과 속도 조절 표를 안내한다. 57경로 Bundle 문자열의 커밋 트리 직접 재계산이 꼭 필요하면 `.model` 가드 안에서 할 수 있는 방법을 사용자에게 물어야 한다. 지금 근거로는 판정에 필요하지 않다.
- 사용자: V11 1~6.
- planner: 회차 D 최종 V11 수락 뒤 위 정리 목록을 처리한다.
- coder·tester: 이번 범위의 추가 작업은 없다. V11에서 끊김이 남거나 새 값이 나오면 그 결정에 따라 다시 돈다.

### 2026-11-10 독립 리뷰 — 회차 D REV-D-O1 수정 WAITING
- 제목 날짜 정정(planner, 2026-11-16): 원래 제목은 "2026-11-09"였다. 리뷰 커밋 7cbf14e(2026-11-10 20:28)에 맞춰 고쳤다. 본문의 "2026-11-09 REV-D-O1 수정" 같은 절 이름 인용은 당시 제목 그대로 두며, 지금 제목은 "2026-11-10 REV-D-O1 수정"이다.
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). 앞 리뷰("회차 D … WAITING", a5efe69)에서 REV-D-O1을 낸 같은 reviewer 역할이다. 이번에는 수정 회차만 다시 판단했다.
  - 하지 않은 것: Maker MCP 제어·Play·refresh·로그 비우기, 제품·Plan·run.md 수정, QA 판정 수정, commit·push.
  - 런타임 사실은 coder 소절("2026-11-09 REV-D-O1 수정")과 QA13 기록을 대조한 것이다. reviewer가 다시 실행한 결과가 아니다.
- reviewer가 직접 한 일:
  - git 대조: `git log origin/main..HEAD`(push 전 8428a05 하나), `git diff 9918e3d 8428a05 -- RootDesk`(전문 읽음), `git diff --stat a5efe69 8428a05 -- RootDesk Global map ui`(제품 2경로뿐), `git status`(작업 트리 차이는 run.md·이 WorkRecord뿐).
  - Bundle 재계산: QA12·QA13과 같은 manifest 방식으로 커밋 트리에서 계산했다. 8428a05 57경로 `8d5b6d1c…4eed`로 기재값과 같다.
  - 소스 읽기: `CombatRuleCatalog.WarnOnce`(키 문자열별 세션 1회), `OrangeMushroomAttack`의 `IsMotionReady`·`JumpToLocalX`·`BeginWindup`·`PerformAttackMotion`·`PerformReturnMotion` 호출 관계.
  - 비밀값 검사: 8428a05 diff·메시지와 작업 트리 문서 차이에 토큰·키·개인 이메일·로컬 사용자 경로가 없다(작성자는 기존 GitHub noreply).
- 검토 버전: coder 로컬 커밋 **8428a05**(기준 9918e3d, 제품 = a5efe69), 57경로 Bundle `8d5b6d1c029d1eefad8e6ac2a878ec55facf069aab23d77c96a6fa3465f04eed`. QA13 대상 = coder 커밋 = 이 리뷰 대상이다.
- 판정: **WAITING**. REV-D-O1은 해소됐고, 고칠 제품·문서 결함은 없다(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 회차 D의 남은 일은 앞 리뷰와 같이 사용자 V11(Plan §22.8 V11 1~9, 22.16.9)이다. 이 판정은 사용자 수락이 아니다.

#### 판단
1. **원인 제거(근본):** 제거됐다.
   - `BeginWindup(…, windupSec, leadSec)`가 안에서 `jumpSec = leadSec − windupSec`를 쓰고 `leadSec`를 그대로 돌려준다. 다시 더하는 식이 없어졌으므로 Monster_Attack의 `TelegraphLeadSec < duration`은 2·3칸에서 항상 거짓이다(같은 값 비교).
   - 착지 시각은 `시작 + W + (lead − W)`이고 판정 예약은 `시작 + lead`다. 둘 다 `OnAttackComplete` → `CompleteMotion` 한 번으로 모이므로, ulp 차이는 동작을 바꾸지 않는다(coder 판단과 같음).
   - "그대로 둔" 비교들도 맞다고 본다.
     - `windup >= leadSec`(PerformAttackMotion)와 `windup >= TelegraphLeadSec`(MonsterManager 스폰): 같은 `GetWindupSeconds`(같은 캐시 타임라인, 같은 계산)를 같은 값과 비교하므로 두 곳의 결론이 갈리지 않는다. 경계 W = lead는 J = 0이라 진짜 불가능한 조합이다.
     - 1칸 `lead < JumpDuration`: 입력 값 두 개를 직접 비교하고 재계산이 없다.
2. **추가 경고 3종:** 규칙·수치는 그대로이고 경고만 더했다. 22.7 범위 안이다(두 파일 모두 22.7 표에 있음).
   - 취소 조건 자체는 바뀌지 않았다: `jumpSec <= 0`, `windup == nil or windup >= leadSec`, `duration` 검사, `IsMotionReady`의 세 조건. 바뀐 것은 경고 줄과 `IsMotionReady` 안의 확인 순서(JumpDuration을 먼저 확인)뿐이다. 둘 다 false를 돌려주므로 결과는 같다.
   - 1회 보장: `WarnOnce`는 키 문자열별로 세션 1회다. 키에 행 id·값이 들어가므로 "같은 원인(같은 행·같은 값)은 1회, 값을 바꾸면 새 1회"다. QA13 X2·X5·X8(반복 시 추가 0)과 맞는다.
   - 일시 상태 제외:
     - Monster_Attack은 `duration` −1(정지·기준 위치 미확보·클립 시작 실패)이면 경고하지 않는다.
     - `IsMotionReady`는 `HomeCaptured`·정지·control 없음이면 경고 없이 false다.
     - JumpDuration 0 이하·NaN·무한은 속성 오류라 일시 상태가 아니다. 이 경우만 경고하고, 복귀 점프에서도 같은 키라 추가 경고가 나지 않는다.
   - 부팅 경고 0: QA13 재Play `warnedKeys=false`.
3. **앞선 판정(a5efe69 WAITING) 근거 유지:** 유지된다.
   - a5efe69→8428a05 제품 차이는 위 2경로뿐이다(git). 나머지 55경로는 바이트가 같으므로 QA12의 판정·분포·Weight·검증 실패·재스폰·팝업·이펙트 위치 근거가 그대로 적용된다.
   - 두 파일이 닿는 경로는 QA13이 이 버전에서 다시 실행했다: 현재 CSV 2·3칸·1칸, D-Q6 슬로우 3경우, windup 피격·approach 차단(실입력), die F12·사운드(실입력), 이펙트 2분할 호출.
   - 앞 리뷰의 22.8·22.16.7 대조표와 "특히 판단한 점" 1~6은 이 버전에도 그대로 유효하다.
4. **NOT_RUN이 판정을 막는지:** 막지 않는다.
   - 수정 전(a5efe69) 조용한 취소 재현: 원인은 부동소수 계산으로 확정된다. 같은 식 `0.8/2.5 + (0.9 − 0.8/2.5) > 0.9`가 참이다(reviewer가 앞 리뷰 때 계산). 수정 뒤에는 같은 조합(O1·coder 재현 행)과 W < lead/2인 조합 7개가 취소되지 않았다. 재현이 없어도 수정의 효과는 입증된다.
   - `IsMotionReady`의 정지 분기: PrepareAttack이 정지 중 먼저 nil을 돌려 실제로는 닿지 않는 경로다. 이 분기의 동작(경고 없이 false)은 이번 수정에서 바뀌지 않았다. 소스 확인으로 충분하다.
5. **문서:** 결함은 없다. 한 가지만 적어 둔다. QA13 본문의 로그 시각은 2026-11-10 20:14~20:22인데 절 제목·coder 소절 제목은 2026-11-09다. 날짜 표기 차이이고 근거에는 영향이 없다. 회차 종료 정리 때 맞추면 된다.

#### 사용자 V11 (앞 리뷰 그대로 + 속도 조절 안내 갱신)
- 확인 항목은 앞 리뷰와 같다. 모션·순서·속도·f4 잘림, 3칸 판정, 효과음 4종, 이펙트 위치·크기·방향(먼지 포함), 비율 체감·CSV Weight 조정, 속도 조절 설정이다.
- 속도 조절 표(갱신, 절차: CSV 수정 → Maker Refresh → Play. 속성은 머쉬맘 모델의 OrangeMushroomAttack 컴포넌트 값):

| 항목 | 위치 | 지금 값 | 바꿀 때 알아둘 동작 |
| --- | --- | --- | --- |
| AttackInterval | MonsterStatData.csv | 3.0 | 크게 줄이면 슬로우가 다음 접근과 겹칠 수 있다(D-Q6 이어 재생으로 처리됨) |
| TelegraphLeadSec | MonsterAttackPatternData.csv(행별) | 1.1/1.1/0.5/0.5/1.1 | 2·3칸: 제자리 W(= 0.8 ÷ MotionPlayRate) 이상으로 줄이면 **스폰 검증이 먼저 거부해 머쉬맘이 나오지 않는다**(Maker 로그 경고 1회 "windup not shorter than telegraph"). 1칸: JumpDuration(0.5)보다 짧으면 그 행 공격이 취소되고 경고 1회 "attack cancelled: approach … exceeds telegraph …" |
| MotionPlayRate | 같은 표(행별) | 1/1/1/1/1 | 정렬식 1.1 ÷ TelegraphLeadSec이면 클립 착지 자세와 판정이 맞는다. 벗어나도 이제 공격은 사라지지 않고(REV-D-O1 해소) 클립 f4 자세만 판정과 어긋난다. TelegraphLeadSec를 줄일 때는 이 값을 같이 올려야 위 스폰 거부를 피한다 |
| JumpStartFrame | 같은 표(행별) | 1/1/빈/빈/1 | 클립 프레임 수(5) 이상이면 스폰 거부 + 경고 1회. 음수·소수·문자면 패턴 표 전체 거부 + 경고 1회 |
| JumpDuration | OrangeMushroomAttack 속성 | 0.5 | 1칸 접근·복귀 점프 시간. 0 이하면 모든 공격이 취소되고 경고 1회 "invalid JumpDuration". 1칸 행 TelegraphLeadSec보다 크면 그 행 취소 + 경고 |
| JumpHeight | OrangeMushroomAttack 속성 | 0.8 | 1칸 접근·복귀 점프 높이 |
| LeapJumpHeight | OrangeMushroomAttack 속성 | 0 | 2·3칸 실제 점프 높이(클립 도약 0.88과 겹침 주의) |
| WindupHittable | OrangeMushroomAttack 속성 | true | 눈빛(제자리) 중 피격 여부 |
| EffectWindupLastFrame·EffectDustFirstFrame | MonsterAttackMotion 속성(참고) | 6·8 | 이펙트 자원 구조. 보통 바꾸지 않는다 |

- 공통: 값이 맞지 않으면 대신할 값 없이 거부·취소하고 Maker 로그에 `[CombatRuleCatalog]` 경고를 같은 원인당 1번만 남긴다. 몬스터가 안 나오거나 어떤 공격이 안 나오면 그 경고를 먼저 본다.

#### 회차 종료 planner 정리 목록 (앞 리뷰 목록 + 이번 추가)
- 앞 리뷰 목록 그대로: §22.14 상태, §22.2·§22.8 V11 1번 대체 표시, "클라이언트 f4" 문구, §22.16.9 속성 이름, GameDesign(메인), AssetList, FileStructure §4, 로드맵 §5, WorkRecord 머리말·재개 지점, 원장 castleenemy(범위 밖).
- 추가 1: REV-D-O1을 "수정 완료(8428a05, QA13)"로 기록한다(§22.14 또는 §22.16 아래 짧은 소절). 앞 리뷰의 "부채로 둘 경우 22.13" 항목은 필요 없어졌다.
- 추가 2: §22.16.9 속도 조절 표에 위 "바꿀 때 알아둘 동작"(스폰 거부·취소 경고)을 반영한다.
- 추가 3: QA13·coder 소절의 날짜 표기(11-09/11-10)를 맞춘다.

#### 다음 행동
- 메인: 이 판정 확인 뒤 회차 커밋 `[CombatCore][review] WAITING`(QA13·이 리뷰 절·run)을 만들고, push 전 비밀값 검사 뒤 8428a05와 함께 push한다. 그다음 사용자 V11을 안내한다(위 표).
- 사용자: V11 1~9와 속도 조절 설정.
- planner: V11 수락 뒤 위 정리 목록을 처리한다.
- coder·tester: 이번 범위의 추가 작업은 없다. 선택 보강(판정을 막지 않음)은 앞 리뷰와 같다(Pos1·Pos3에 선 채 판정, 재스폰 개체 die, 이펙트 취소 경로).

### 2026-11-09 독립 리뷰 — 회차 D(CombatCore-MM-07~11) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행).
  - 하지 않은 것: Maker MCP 제어·Play·refresh·로그 비우기, 제품 파일 수정, Plan 요구·QA 판정 수정, run.md 수정, commit·push.
  - 런타임 사실(빌드 로그, Play, 프레임 이벤트, 실입력, 스크린샷)은 coder 절("2026-11-09 coder 회차 D 재작업")과 QA12 기록을 대조한 것이다. reviewer가 다시 실행한 결과가 아니다.
- reviewer가 직접 한 일:
  - git 대조: `git log origin/main..HEAD`(push 전 e5f7249 [code]·f82c549 [ops]·a5efe69 [code] 3개), `git diff --stat 7a796aa a5efe69`, `git diff e5f7249 a5efe69`(제품 6경로 + DataSet.directory), `git status`(작업 트리 차이는 run.md·이 WorkRecord뿐).
  - Bundle 재계산: QA12에 적힌 manifest 방식(경로 바이트순, 경로 TAB sha256 LF, 확장자 9종, Global·RootDesk·map·ui)을 커밋 트리에서 다시 계산했다. a5efe69 57경로 `8dccccf5…b738`, e5f7249 57경로 `a7bc3d73…539d`, 7a796aa 55경로 `8ef9c6f1…e080`으로 기재값과 모두 같다. 셸 명령에 `.model` 문자열을 넣지 않아 가드를 우회하지 않았다.
  - 모델 의미 비교: `ModelBuilder.read`로 7a796aa·e5f7249·a5efe69의 머쉬맘 모델을 읽어 비교했다(커밋 판을 임시 위치로 꺼내 읽기만 함).
  - 소스 읽기: MonsterAttackMotion·OrangeMushroomAttack·Monster_Attack 전문, CombatRuleCatalog·MonsterManager·MonsterStateControl·MonsterAttackComponent·MonsterHealthComponent 회차 D 차이, 패턴 CSV, MonsterSoundData 래퍼·CSV, Environment/config.
  - Grep: 제품 .mlua에 `mushmom`·`Mushmom`·`orangemushroom` 문자열 없음(modelId 하드코딩 없음).
  - 비밀값 검사: push 전 3커밋 diff·메시지와 작업 트리 문서 차이에서 토큰·키·개인 이메일·로컬 사용자 경로 없음. 커밋 작성자는 기존 GitHub noreply 주소, `PublicKeyToken`은 모델 값의 .NET 형식 이름이다.
- 검토 버전: coder 로컬 커밋 **a5efe69**(e5f7249 위 재작업), 57경로 Bundle `8dccccf58c6138d16e5b84277fa275c6a982c8d397e487d85e1f55e33e6ab738`. QA12 대상 = coder 커밋 = 이 리뷰 대상이다.
- 판정: **WAITING**. 고칠 제품·문서 결함은 없다(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 남은 것은 Plan §22.8 사용자 V11 1~9(22.16.9 속도 조절 안내·설정 포함)다. 이 판정은 사용자 수락·다음 회차 승인이 아니다.

#### 요구·사용자 결정 → 변경 대조 (빠짐·초과 없음)
| 요구·결정 | a5efe69 실제 변경(소스·CSV·모델) | 판단 |
| --- | --- | --- |
| MM-07 패턴별 모션 | ActionSheet `attack1` 90c5456e…·`skill1` b9345875… 추가(ModelBuilder 비교로 의미 차이는 이 2키뿐, `attack` 키 없음). CSV MotionClip attack1/attack1/jump/jump/skill1. 접근 클립은 패턴에서, 복귀는 jump | 충족 |
| MM-08 3칸 착지 Pos2 | MonsterAttackComponent `landingX`: 앵커 1~3이면 Pos2 앵커 x, 1·2칸은 영역 중앙 그대로 | 충족 |
| MM-09 Weight 4/4/5/3/4 + [VRF] 비율 | CSV 값, `FormatWeights`, `SelectPattern` 무변경 | 충족 |
| MM-10 이펙트(22.16.4 분할) | `PlayWindupEffect`(공격 시작, 머쉬맘 현재 위치, 프레임 0~6)·`PlayDustEffect`(OnAttackComplete의 판정 경로, 착지 x, 프레임 8~끝), 옵션 PlayRate = MotionPlayRate × ActionRate. 2칸은 EffectClip 빈 값이라 없음 | 충족 |
| MM-11 효과음 | 공격음(PrepareAttack 뒤)·피격음(공격 회차별 첫 HitEvent)·플레이어 피격음(HIT·GUARD·UNGUARDABLE)·사망음, MonsterSoundData 수동 작성(D-Q1) | 충족 |
| 사용자 요구 "눈빛 중 점프 금지" | 2·3칸: `BeginWindup` 제자리(구간 windup, JumpActive false) → W에 실제 점프(approach) → 착지 = 판정. 1칸·복귀는 `JumpToLocalX` 그대로 | 충족 |
| D-Q3 원작 1배·판정 1.1초(planner 추천과 다름) | CSV parry.left·right·guard TelegraphLeadSec **1.1**·MotionPlayRate **1**, 1칸 0.5·1. W = 0.8 ÷ (클립 PlayRate × 1), J = 1.1 − W | 정확히 반영 |
| D-Q4 제자리 피격 | `WindupHittable` 기본 true, approach·return false 그대로 | 충족 |
| D-Q5 수평 이동만 | `LeapJumpHeight` 기본 0, 1칸·복귀는 `JumpHeight` 0.8·`JumpDuration` 0.5 | 충족 |
| D-Q6 지금 고침(planner 추천과 다름) | 후보 1 서버 프레임 구동(`StartDrivenClip`·`TickClip`·`StopDrive`): RUID를 쓴 뒤 Start=End=0, 액션 시계 경계마다 Start=End=k. 후보 2 미사용 | 정확히 반영. 대체 구현(부채·슬로우 미반영) 없음 |
| D-Q7 로그 비우기 | 제품 코드와 무관(아래 5번) | 허용 범위 안 |
| JumpStartFrame 열·검증(22.16.3) | Catalog 0 이상 정수 검증·빈 값 0, MonsterManager 스폰 때 프레임 수·W < TelegraphLeadSec 확인 | 충족 |

- 초과 없음: 새 파일은 MonsterSoundData 2개와 Maker가 만든 `DataSet.directory`뿐이다. 판정 규칙·피해·창·회차 C 피격 규칙 코드는 바뀌지 않았다. 코더가 정한 구현 선택 두 가지는 Plan 범위 안의 선택으로 본다. 하나는 이펙트 구간 경계를 상수 대신 인스펙터에 보이는 속성 `EffectWindupLastFrame` 6·`EffectDustFirstFrame` 8로 둔 것이다(자원 구조, modelId 분기 아님). 다른 하나는 제자리 피격·접근 높이를 `WindupHittable`·`LeapJumpHeight` 속성으로 둔 것이다(Plan 22.16.3이 속성으로 지정).

#### 특히 판단한 점
1. **변경 범위(22.7 + 22.16.6):** 범위 안이다.
   - 7a796aa→a5efe69 제품 경로: 패턴 CSV, MonsterSoundData(.userdataset·.csv), `DataSet.directory`, 머쉬맘 모델, CombatRuleCatalog, MonsterManager, Monster_Attack, MonsterAttackMotion, MonsterAttackComponent, OrangeMushroomAttack, MonsterHealthComponent, MonsterStateControl이다. 모두 22.7 표에 있다. `.codeblock`·맵·`.ui`·CombatRuleData·MonsterStatData 변경은 없다.
   - e5f7249→a5efe69 재작업은 CSV·Catalog·Manager·Monster_Attack·MonsterAttackMotion·OrangeMushroomAttack 6경로와 `DataSet.directory` 1줄뿐이다(22.16.6 안).
   - MonsterStateControl 조건부 수정(e5f7249)도 범위 안이다. 저장·복원 3곳을 `_T.slowPlayRateOn` 플래그와 `ApplyMotionClipRate()`로 바꾼 것뿐이고, 슬로우 시간·배율·ActionRate·액션 시계·공격 대기 수식은 그대로다(diff 확인). 22.7 조건("모션 배율이 저장값에 섞임")의 이유가 coder 절에 적혀 있고, 메인도 run에서 수락했다. 재작업에서는 고치지 않았다.
   - `DataSet.directory`: Maker가 새 폴더에 만든 메타데이터다. 재작업 커밋의 변경은 `StudioVersion` "" → "0.1.0.0" 한 줄이며, 다른 추적 `.directory` 20개와 같은 값이 됐다. 이번 회차가 만든 폴더의 Refresh 산출물이고 사용자 변경이 아니어서 [code] 커밋에 넣은 것은 적절하다(platform.md §2 ".directory는 Refresh 산출물", 프로젝트는 .directory를 추적함). Bundle 대상 확장자가 아니라 지문에는 들어가지 않는다.
   - 머쉬맘 모델 재기록: 적절하다. ModelBuilder 비교 결과, 구성요소 14개는 같고 값은 45개로 같다. 차이는 ActionSheet 값 1개(`attack1`·`skill1` 추가)뿐이고, 값 형식 메타데이터·자식·이벤트 링크·snapshot은 같다. git 텍스트 차이는 빌더의 들여쓰기·숫자 표기(`6.0`→`6`) 재기록 때문이다. `-w --ignore-cr-at-eol` 기준으로는 ActionSheet와 숫자 표기만 남는다. `.model`은 빌더 전용이라는 규칙을 따랐다. 나중에 Maker가 다시 저장하면 숫자 표기가 다시 바뀔 수 있다(b4adbdd 선례, 의미 무변경).
2. **22.12 고정 수치:** 승인되지 않은 변경은 없다.
   - 사용자 결정으로 바뀐 것은 2·3칸 TelegraphLeadSec 1.1·MotionPlayRate 1·접근 높이 0·W/J 구조와 windup 피격 가능이다.
   - 그대로인 것: CSV의 AreaPaddingX 0.5·AreaHeight 1·AreaOffsetY 0.4·범위 앵커·1칸 TelegraphLeadSec 0.5, 스크립트 기본값 JumpDuration 0.5·JumpHeight 0.8, CombatRuleData·판정 창(QA12 재Play `just=0.2 parry=0.2 guardRate=0.4`), D01~D04·ResolveAttack, 회차 C 피격 규칙(구간 선언에 windup 하나만 추가, D-Q4).
3. **D-Q6 서버 프레임 구동이 기존 원칙을 깨는지(코드 확인):** 깨지 않는다.
   - die 가드: `SetMotionClip`·`StartDrivenClip`·`TickClip`·`ApplyClipRate`가 `_T.dieStarted`면 쓰지 않는다. `StopDrive`는 범위를 되돌리기 전에 확인하고, `PlayDieOnce`는 `_T.drive = nil`로 구동을 끊는다. TickDie의 마지막 프레임 고정을 덮는 경로는 없다(22.15 원칙 3). QA12 F12 PASS(실입력)와도 맞는다.
   - 22.15 원칙 1: 접근 클립이 아닌 모든 지정(`SetMotionClip`)은 전체 범위 → RUID 순서를 유지한다. 접근 클립은 서버가 매 프레임 범위를 명시해 0-0 잔존 문제가 생기지 않는다(22.16.12 관계 문단 그대로).
   - 원칙 2: 클립 쓰기는 모두 ServerOnly다. 원칙 4: 모델에 프레임 값을 추가하지 않았다.
   - 정리 경로: 착지(`CompleteMotion` → `TickClip` → stand 지정이 구동 해제·전체 범위), 취소·맵 이탈·종료(`CancelMotion` → `ResetClipRate` → `StopDrive`), 일시정지(OnUpdate가 정지 중 돌지 않고, 액션 시계도 멈춤).
   - 회차 C 결과: ATTACK 중 피격은 상태를 바꾸지 않는다(MonsterHealthComponent 기존 조건). windup 피격은 HP만 줄고 공격이 계속된다(QA12 22.16.7-12).
   - modelId 하드코딩: 없다(Grep). 이펙트 프레임 경계는 속성 기본값이다.
4. **완료 기준(22.8·22.16.7) — 같은 버전 근거:** 아래 표와 같다. 실행 기준은 모두 같은 버전 coder·tester 근거가 있다. NOT_RUN은 PASS로 세지 않았고, 판정을 막는 NOT_RUN은 없다.
   - 시험값 완화는 근거로 충분하다고 본다. 판정 창 30초는 PARRY·JUST의 사람 손 타이밍만 없앤 것이다. 판정 코드(ResolveAttack·MonsterAttackComponent)는 재작업에서 바뀌지 않았고, 창 값은 Play 안에서 되돌렸다(재Play 기본값 로그). 늘린 구간 행(TelegraphLeadSec 11·MotionPlayRate 0.1, JumpDuration 8)도 기본값과 같은 `IsSegmentHittable`·W 계산 경로이고, 기본값 시각의 구간·JumpActive 전환은 22.16.7-10에서 따로 측정됐다. 정상 창의 사람 손 타이밍은 사용자 V11에 남는다.
   - 해석 하나: 22.16.7-10·22.8-9의 "클라이언트 f4 시작"은 착지 때 stand 계약(22.6) 때문에 클라이언트에 그려지지 않는다. coder·tester 모두 서버 f4 쓰기 시계 = 판정 시계로 판단했고 이를 밝혔다. 클라이언트 f0→f1→f2→f3 간격(0.80/0.20/0.05)도 그 시각과 맞는다. 이 해석으로 충족으로 보며, Plan 문구 정리 대상으로 넘긴다(아래 7번).
5. **D-Q7 로그 비우기:** 허용 범위 안이다(이번 회차 한정, 각 1회, 건수·시간 범위만 기록).
   - coder: 1회(741건, 17:30:43~17:37:11, 모두 자기 시험 로그). 세션 시작 때는 이미 0건이라 비우지 않았고, 검증 도중 자기 로그로 버퍼가 찼을 때 1회 비웠다. "세션 시작 때"라는 문구와 시점은 다르지만, 횟수·대상(사용자 로그 아님)·기록 방식은 허용 목적 안이다.
   - tester: 시작 때 1회(123건, 17:38:12~17:41:18, 앞 coder 세션 로그).
   - 두 담당 모두 내용을 옮겨 적지 않았고 파일·DataStorage를 건드리지 않았다. 2026-11-08의 사용자 세션 로그 94건은 coder 재작업 시작 전에 이미 Maker에서 비어 있었다(coder 기재, AI 호출 기록 없음).
6. **비밀값·경로:** 커밋 대상 문서와 push 전 커밋에 비밀값·개인 이메일·로컬 사용자 경로가 없다(위 검사).

| 기준 | coder(a5efe69) | QA12(a5efe69) | 리뷰 판단 |
| --- | --- | --- | --- |
| 22.8-1 빌드·로드 | PASS | PASS | 충족 |
| 22.8-2 패턴별 결정적 | PASS | PASS | 충족 |
| 22.8-3 parry.guard 판정 | GUARD·PARRY·HIT(창 시험값) | 실입력 GUARD(정상 창)·PARRY·JUST(창 30초)·무입력 HIT·탭 복귀 HIT | 충족. "Pos1·Pos3에 선 채 판정"은 NOT_RUN(판정 코드는 e5f7249 뒤 무변경, coder e5f7249 "이동 → HIT", 사용자 V11 2번) |
| 22.8-4 분포·경계 | 경계 PASS, 2만 회 NOT_RUN | 3표본(21,000·20,000·20,000) 최대 \|−0.50\|%p, 경계 PASS | 충족(tester 근거) |
| 22.8-5·6·15 Weight·실패 동작·JumpStartFrame 검증 | PASS | PASS(경고 키별 1줄, 스폰 거부 4종 현재 상대 유지) | 충족. 파일 변경 필요 항목은 V11 6번 |
| 22.8-7 사운드 [VRF] | PASS | PASS | 충족. 청취는 V11 3번 |
| 22.8-8 / 22.15 재스폰 | PASS | 첫 스폰·DoSpawn 재스폰 각각 0→1→2→3, 서버 0-0 재현 뒤 정상 | 충족. 재스폰 개체 die는 NOT_RUN(부팅 개체 F12 PASS, die는 RUID 지정이 범위를 되돌린다는 coder 측정 (a)와 PlayDieOnce 전체 범위 지정) |
| 22.8-9 재생 배율(1배) | PASS | PASS | 충족 |
| 22.16.7-10 제자리·도약 | PASS | 6회 + 접근 전체 슬로우 2회, W 0.803~0.815, 판정 1.103~1.119 | 충족 |
| 22.16.7-11 이펙트 분할 | PASS(취소 경로 포함) | PASS, 취소 경로 NOT_RUN | 충족. 취소 경로는 같은 버전 coder 근거 + 소스(2단계는 IsCurrent 통과한 OnAttackComplete에서만) |
| 22.16.7-12 제자리 피격 | 선언 값만 | 실입력 windup 통과·approach·return 차단 | 충족 |
| 22.16.7-13 높이 | PASS | PASS | 충족 |
| 22.16.7-14 1칸 회귀 | PASS | PASS | 충족 |
| 22.16.7-16 D-Q6 이어 재생 | S1~S5 PASS | 8회 되돌림 없음, f1 차이 최대 0.016 | 충족 |
| 회귀(F12·F13·팝업 정지·DataSet·스폰) | PASS | PASS(토스트·실제 팝업 버튼 NOT_RUN) | 충족. 토스트·UI 파일은 이번 회차 무변경 |
| 이펙트 위치·방향 | 화면 일부 | 눈빛 머쉬맘 눈 위치 PASS, 먼지·방향 NOT_RUN | 사용자 V11 4·8번 |

#### 관찰 (비차단, 새 결함 ID 아님)
- **REV-D-O1 부동소수 경계(권고):** `BeginWindup`은 `windupSec + (leadSec − windupSec)`를 돌려준다. Monster_Attack은 `TelegraphLeadSec < duration`이면 공격을 경고 없이 IDLE로 취소한다. W가 TelegraphLeadSec의 절반보다 작으면 이 합이 1 ulp 커질 수 있다.
  - 계산 확인: 1.1·1처럼 사용자 결정 값과 정렬식 값(MotionPlayRate = 1.1 ÷ TelegraphLeadSec)에서는 생기지 않는다. 예를 들어 TelegraphLeadSec 0.9 + MotionPlayRate 2.5에서는 생긴다.
  - 스폰 확인(W < TelegraphLeadSec)은 통과하므로, 그 행 공격만 조용히 나오지 않는다.
  - 현재 값에는 영향이 없다. V11에서 MotionPlayRate를 1.6 ÷ TelegraphLeadSec보다 크게 올리지 않으면 피할 수 있다.
  - 고치려면 `BeginWindup`이 leadSec 자체를 돌려주거나 비교에 작은 허용치를 두면 된다. coder→tester 한 바퀴가 필요하므로 지금 고칠지, 부채로 둘지는 메인·사용자가 정한다.

#### 회차 종료 planner 정리 목록 (사용자 V11 뒤)
- Plan §22.14 상태: MM-07~11이 "coder 재작업 대기"에 머물러 있다. a5efe69 구현, QA12, 이 리뷰를 반영한다.
- Plan §22.2 "이펙트 시점·위치" 행과 §22.8 V11 1번 "2.2배 재생 속도" 문구에 대체 표시를 단다(22.16.4·D-Q3 1배).
- Plan §22.16.7-10·22.8-9의 "클라이언트 f4 시작"은 "서버 f4 쓰기 = 판정, 클라이언트 f3까지"로 정리한다(위 4번).
- §22.16.9 표: 속성 이름을 `LeapJumpHeight`·`WindupHittable`로 확정하고, 이펙트 경계 속성 `EffectWindupLastFrame`·`EffectDustFirstFrame`을 참고로 넣는다. REV-D-O1 처리(수정 또는 부채)도 적는다.
- GameDesign: 100행 "회차 D 전인 지금…"을 현재형으로 바꾼다. 2·3칸 텔레그래프 1.1초·제자리 0.8초 피격 가능·눈빛 제자리→도약 순서·난이도 하락을 반영한다(22.16.11, 메인 담당으로 지정됨). 98행 피격 규칙의 공격 중 구간 설명도 같이 본다.
- AssetList: 54행 "사용 예정(회차 D)"을 사용 중으로 바꾼다. 19~26행 상태를 V11 결과로 정리한다.
- FileStructure §4: 회차 D 새 파일로 `DataSet/MonsterSoundData`(.userdataset·.csv)와 새 `DataSet/` 폴더를 적는다. 기존 DataSet은 이동 회차 전까지 `@Assist/DataSet/`에 남는다는 점을 함께 적는다.
- 로드맵 §5 재개 지점, WorkRecord 머리말("최신: 회차 C2")과 "현재 재개 지점"을 갱신한다.
- 범위 밖 남은 사항: 원장 castleenemy 문구(이전 리뷰 그대로).

#### 다음 행동
- 메인:
  - 이 판정 확인 뒤 회차 커밋 `[CombatCore][review] WAITING`을 만든다(QA12·이 리뷰 절·run). push 전 비밀값 검사를 한 뒤 e5f7249·f82c549·a5efe69와 함께 push한다.
  - 그다음 사용자 V11을 안내한다.
- 사용자 V11(Plan §22.8 V11 1~9, 22.16.9):
  - 모션·순서·속도·f4 잘림, 3칸 판정, 효과음 4종, 이펙트 위치·크기·방향(먼지 포함), 비율 체감·CSV Weight 직접 조정을 확인한다.
  - 속도 조절 항목을 설정한다(아래 반환의 안내 목록).
- planner: V11 수락 뒤 위 정리 목록을 처리한다. REV-D-O1을 부채로 둘 경우 22.13에 적는다.
- coder·tester: 이번 범위의 추가 작업은 없다. REV-D-O1을 지금 고치기로 하거나 V11에서 결함이 나오면 같은 승인 범위로 다시 돈다. 선택 보강(tester)은 Pos1·Pos3에 선 채 판정, 재스폰 개체 die, 이펙트 취소 경로다. 모두 판정을 막지 않는다.

### 2026-11-08 독립 리뷰 — 회차 C2(CombatCore-MM-12) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). 2026-11-06 reviewer 호출은 사용자가 판정 전에 중지했고 남긴 결과가 없어, 처음부터 따로 판단했다.
  - 하지 않은 것: Maker MCP 제어·Play·refresh, 제품 파일 수정, Plan 요구·QA 판정 수정, commit·push.
  - 런타임 사실(refresh·build 로그·Play·직접 스폰)은 coder 절("2026-11-06 coder 회차 C2 구현·기본 검증 인계")과 QA11 기록을 대조한 것이다. reviewer가 다시 실행한 결과가 아니다.
- reviewer가 직접 한 일:
  - git 대조: `git diff b93e2ac 105e585 -- Global RootDesk map ui`(제품 차이 없음), `git diff -M --numstat 105e585 163fc37`, `git diff 163fc37 c02aab4`, `git status --porcelain --untracked-files=all`, `git log origin/main..HEAD`.
  - Glob `RootDesk/MyDesk/**/*.model`, Grep(`주황버섯` 제품 경로 전수, 원장 `castleenemy`).
  - Plan §23, run C2 절, FileStructure·AssetList·GameDesign·DevelopmentRoadmap 대조.
- 검토 버전: coder 로컬 커밋 **163fc37**. 55경로 Bundle `8ef9c6f1c60d73b7b74f5febd09932abfe6ba5866bfc577cb226c82d5ed2e080`(coder·QA11 기재).
  - 105e585→163fc37 제품 차이는 모델 1경로뿐이다. `주황버섯.model → OrangeMushroom.model` 이름 변경(R097)이고 바뀐 줄은 1줄(+1/−1)이다. 나머지는 원장 1줄·Plan 1줄·WorkRecord 47줄이다. `.directory`·`.codeblock` 변경은 없다.
  - 163fc37→c02aab4는 run.md와 WorkRecord(QA11 절)뿐이고 제품 변경은 없다. 작업 트리 차이는 run.md(메인)뿐이고 추적하지 않는 파일도 없다.
  - b93e2ac→105e585의 제품 차이는 0이다. 따라서 Plan의 기준 b93e2ac와 coder가 쓴 기준 105e585는 제품상 같다. 사용자의 이름 변경은 [plan] 커밋(89fd986·105e585)에 섞이지 않았다.
  - Bundle 문자열은 다시 계산하지 못했다. 셸 계산 명령이 프로젝트의 `.model` 셸 가드에 막혔고, 가드를 우회하지 않았다. 대신 위 git 동일성으로 확인했다. QA11은 커밋 트리와 작업 트리 양쪽에서 같은 값을 독립 계산했고, 105e585에서 222e7a04…476d도 재현했다.
  - QA11 대상 = coder 커밋 = 이 리뷰 대상이다.
  - 모델 내용의 의미 비교는 reviewer가 ModelBuilder로 다시 하지 않았다. 근거는 다음 세 가지다. git 기준 바뀐 줄 1줄, coder·QA11의 ModelBuilder snapshot 재귀 비교(의미 차이 Name 1곳), QA11의 원문 치환 바이트 일치.
- 판정: **WAITING**. 고칠 제품·문서 결함은 없다(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 남은 것은 Plan §23.4 사용자 V11 직접 확인뿐이다. 이 판정은 사용자 수락·회차 D 시작 승인이 아니다.

#### 요구 → 변경 대조 (CombatCore-MM-12, 충족)
- 파일: 제품 경로의 모델은 `Models/MapObjects/AttackAreaMark.model`·`Models/Monsters/Mushmom.model`·`Models/Monsters/OrangeMushroom.model` 3개다(reviewer Glob). `주황버섯.model`은 없고 Mushmom은 변경이 없다.
- Name `OrangeMushroom`, 키 `orangemushroom`(EntryKey·Id)은 그대로다. 구성요소 14·값 45·ActionSheet 5키·Scale 1·HitComponent가 기준 판과 같다(coder·QA11 ModelBuilder, git 1줄 차이와 일치).
- 바꾸지 않을 것도 지켰다: MonsterData·MonsterStatData·패턴 표, `OrangeMushroomAttack.mlua`, 머쉬맘 모델, 맵·Body·스크립트·규칙·수치. 105e585→163fc37 제품 차이가 위 1경로뿐인 것이 근거다.
- 요구가 빠지거나 늘지 않았다. 사용자 요청 7번 "MonsterData에 주황버섯으로 추가"는 사용자 결정("6단계로 미루기")으로 범위에서 빠졌다. 이것은 Plan §23.1·로드맵 §6에 적혀 있다.

#### Plan §23.3 완료 기준 — 같은 버전 근거
| 기준 | coder(163fc37 작업 트리) | QA11(163fc37) | 리뷰 판단 |
| --- | --- | --- | --- |
| 1 Glob | PASS | PASS(백업 폴더 `.handoff-backups/…` 1건은 제품 경로 밖) | 충족. reviewer Glob도 같음 |
| 2 ModelBuilder 비교 | 의미 차이 Name 1곳 | 105e585·b93e2ac 두 판 모두 Name 1곳, 원문 치환 바이트 일치 | 충족 |
| 3 refresh 뒤 build 로그 | 83건 Info, 오류·경고 0 | 같음 | 충족. Play 뒤 build 로그는 다시 읽지 않았다(QA11 기재) |
| 4 Play 회귀 | 부팅 머쉬맘, 걸친 공격(실제 클라이언트 요청 경로, hit1 fail·2~10 pass) | 부팅 머쉬맘·수치, 실제 UpArrow pass 10건, segment fail 10건(서버 ChangeState 논리 경로), F12 die 1회 정지 | 충족. 이번 변경은 MonsterManager가 스폰하지 않는 모델의 Name 한 줄이다. 그래서 대표 사례로 기준 4의 "회차 C와 같다"를 뒷받침한다고 본다. 전수는 아래 NOT_RUN |
| 5 직접 스폰 | 성공, 구성 일치, 잔존 0, castleenemy·주황버섯 nil | 같음, 잔존 0 | 충족 |
| 6 Grep | 주석 1건 | 같음 | 충족. reviewer Grep(Global·RootDesk·map·ui)도 `OrangeMushroomAttack.mlua:52` 주석 1건뿐 |
| 7 git 범위 | 모델 1개 + 원장 1줄 | 같음 | 충족. reviewer git도 같음 |

#### 특히 판단한 점
1. **§23.2 절차 생략·순서 차이:** 결함이 아니다(정당).
   - renameModel·모델 재기록을 하지 않았다: §23.2 순서 4 단서("Maker가 Name까지 바꿨으면 쓰지 않고 기록만 한다")대로다. 쓰지 않았으므로 빌더 재기록에 따른 형식 차이도 생기지 않았다.
   - 사용자 이름 변경이 시작 지시 전에 있었다: Plan은 "시작 지시 → Stop 확인 → 사용자 이름 변경" 순서다. 실제로는 사용자가 먼저 바꿨다(run "회차 E 사용자 선택" 절). 순서 1~3의 목적(다른 제품 재저장 없음, 옛 경로·새 경로 1쌍)은 다음 근거로 충족됐다. 메인 git 확인, coder 시작 때 map01/edit 확인, reviewer의 b93e2ac→105e585 제품 차이 0. Play 중 변경이었다는 징후는 없다.
   - planner 범위 확인 생략: Plan §23 "다음 흐름"에 planner 단계가 없다. planner 계약도 "이미 승인된 계획을 매 실행마다 다시 설계하지 않는다"이다. §23.6 미결정 3개의 처리:
     - Name 변경 여부: 관찰로 정해졌다(run·coder 기록).
     - 원장 범위: Plan 단서대로 처리했다.
     - 문서 정리: 회차 종료 때 planner 몫이다.
   - 따라서 coder 시작을 막는 미결정은 없었다. 승인 범위·완료 기준을 어기지 않았다.
2. **원장의 낡은 castleenemy 문구:** 이번 회차 결함이 아니라 **범위 밖 기록 사항**이다.
   - 근거 1: `git log`상 원장은 초기 커밋 29433b7 이후 163fc37에서 처음 바뀌었다. `(castleenemy)`·MHP-01~04.castleenemy·"MonsterData는 castleenemy 1행"과 실효 모델 표에 머쉬맘이 없는 점은 회차 C 이전부터 있던 상태다.
   - 근거 2: §23.2 순서 5는 "규칙에 없으면 경로만 고치고 나머지는 메인에 보고"이고, coder는 그대로 했다.
   - 한계: reviewer는 maplestory-skill-maker 원장 규칙 원문을 직접 확인하지 않았다(스킬 파일을 경로로 읽지 않음). 규칙 판단은 coder 인용을 따랐다. 다만 낡은 내용이 C2 전부터 있었으므로 판정은 같다.
   - 권고(비차단): 회차 D에서 이 스킬을 다시 쓸 때 그 단계의 원장 갱신으로 실효 대상(머쉬맘)과 키 표현을 정리할지는 메인·사용자가 정한다. 이미 사용자에게 알렸다고 메인이 전했다.
3. **회차 C 전수 회귀 NOT_RUN:** C2 판정을 막지 않는다. PASS로 세지 않는다.
   - 근거 1: §23.3이 요구하는 회귀는 기준 4(부팅 머쉬맘·규칙 [VRF])다. 위 대표 사례로 충족했다.
   - 근거 2: 나머지 54경로는 QA10 버전(b4adbdd)과 바이트가 같고(git), 회차 C 근거가 그대로 적용된다.
   - 남은 NOT_RUN(QA11 그대로):
     - 회차 C 전수(접근·복귀 구간 실제 입력, 그로기 중 사망, 패링·저스트·가드 실제 입력, V07 팝업, V10, DataSet 실패 동작)
     - Stop 뒤 새 Play에서 시험값이 남지 않는지
     - 대소문자 다른 키 스폰(QA11 재실행 없음, coder만 확인)
     - 사람 손 타이밍·실기기·모바일·다중 접속·화면 육안
4. **버전·지문:** coder·QA11·리뷰 대상이 163fc37로 같다. Bundle 재계산은 위 사유로 하지 못했고, git 동일성으로 대신했다.
5. **문서 동기화:** 누락 결함은 없다. 남은 일은 Plan §23.6에 적힌 회차 종료 정리이며, planner가 사용자 V11 뒤에 한다. 지금 낡은 곳은 다음과 같다.
   - Plan §23.7 상태가 "같은 버전 tester·reviewer 대기"로 남아 있다(QA11·이 리뷰 미반영).
   - FileStructure §5 77행에 "Name은 coder가 ModelBuilder로 바꾼다"라는 예정형이 남아 있다. 실제로는 Maker가 Name까지 바꿨다. §7 98행에는 옛 경로 문구가 남아 있다.
   - AssetList 48행 주황버섯 보관 행에 새 경로가 없다.
   - GameDesign 132행과 로드맵 153행에 C2 예정형이 남아 있다.
   - WorkRecord 머리말과 "현재 재개 지점"에 C2 진행이 반영되지 않았다.
   - Plan §23.7 갱신은 이전 회차와 같이 회차 종료 planner 동기화에 맡긴다. reviewer는 Plan을 고치지 않았다.
6. **커밋 범위:** 사용자가 직접 바꾼 범위 밖 파일은 섞이지 않았다.
   - 163fc37의 제품 변경은 사용자 Maker 이름 변경 1경로(이번 범위)뿐이다.
   - 같은 시기 [plan] 커밋 105e585 본문에도 "주황버섯 모델 이름 변경은 회차 C2 범위라 포함하지 않음"이라고 적혀 있고, git으로도 확인된다.
   - push 전 커밋은 163fc37·c02aab4 두 개다. 회차 종료 커밋 때 메인이 함께 push한다.

#### 다음 행동
- 사용자(V11, Plan §23.4):
  - Maker 작업 공간 창에 주황버섯 모델이 `OrangeMushroom` 하나로만 보이는지(옛 이름 항목이 없는지). AI 근거는 디스크·런타임 등록 1개, `castleenemy`·`주황버섯` 스폰 nil뿐이고 창 화면은 보지 못했다.
  - 플레이 화면이 회차 C와 같은지(머쉬맘, 주황버섯 미출현).
- planner(V11 수락 뒤 회차 종료): 위 5번 문서를 정리한다.
- 메인: 회차 종료 커밋 전 비밀값 검사 → push. 원장 정리 시점을 정한다(위 2번).
- coder·tester: 이번 범위의 추가 작업은 없다. V11에서 옛 항목이 보이면 Plan §23.2 대안(디스크 직접 이동·삭제 금지, 사용자 Maker 정리)대로 다시 판단한다.

### 2026-11-06 독립 리뷰 — 회차 C(CombatCore-MM-01~06·V11-F15) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). 하지 않은 것: Maker MCP 제어·Play, 제품 파일 수정, Plan 요구·QA 판정 수정, commit·push. 런타임 사실은 coder 절("2026-11-05 coder 회차 C 구현·기본 검증 인계")과 QA10 기록을 대조한 것이며, reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 일:
  - `git diff e94b981 b4adbdd`, `git diff 5a605ba b4adbdd`, `git status`로 소스 대조
  - Grep 전수 검색
  - 과거 커밋 `.model` 3개 버전(e94b981·5a605ba·b4adbdd: Mushmom·주황버섯·DefaultPlayer)을 `git show`로 scratchpad에 내보낸 뒤 **ModelBuilder.read**(listComponents·listValues)로만 비교. 내보내기는 셸 `.model` 가드가 걸리기 전에 실행했고, 그 뒤 내용 읽기는 모두 빌더로 했다.
  - AssetList·FileStructure·GameDesign·DevelopmentRoadmap 대조
- 검토 버전: HEAD **b4adbdd**, 55경로 Bundle `222e7a04…476d`(QA10 기재)
  - 5a605ba→b4adbdd 차이는 8경로다. Mushmom.model·주황버섯.model은 Maker 재저장으로 숫자 표기만 바뀌었다. ModelBuilder 비교 결과 구성요소 14개·값 45개가 완전히 같고, DefaultPlayer도 7개·65개로 같다. 나머지 `.directory` 6개는 CoreVersion만 바뀌었고 manifest 밖이다. 따라서 coder 커밋과 시험 버전의 제품 의미는 같다.
  - b4adbdd→d6c3d9a는 문서뿐이고, 작업 트리 차이는 run.md뿐이다.
  - 셸 해시는 `.model` 가드와 충돌하므로 Bundle 문자열 자체는 재계산하지 않았고, 위 git 동일성과 빌더 비교로 대신했다.
  - QA10 대상 = 이 리뷰 대상이다.
- 판정: **WAITING**. 고칠 제품 결함 없음(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 남은 것은 Plan §21 사용자 V11 직접 확인뿐이다. 이 판정은 사용자 수락·2단계 완료·회차 D 시작 승인이 아니다.

#### 요구 → 변경 대조 (모두 충족)
- **MM-01 머쉬맘 1배 모델:** `Models/Monsters/Mushmom.model`(id `mushmom`, Scale 1,1,1)
  - ActionSheet는 **정확히 5키**(stand 86015373…·move c745828d…·jump 5ecbcc40…·hit 90fee941…·die ec90f0b6…)다. attack·stun·attack1·skill1 키는 없다.
  - SpriteRUID는 stand, HitComponent BoxSize (1.2,1.1)·ColliderOffset (0,0.55), DamageSkinOffset (0,1.1)이다.
  - 구성요소 14개는 기존 주황버섯과 같은 구성이다.
  - QA10 스폰 읽기에서 같은 값으로 PASS.
- **MM-02 키·데이터 전환:**
  - MonsterData `1,머쉬맘,model://mushmom`
  - 패턴 4행: modelId만 castleenemy→mushmom, 다른 칸·Weight 2·2·2·1은 그대로
  - MonsterStatData `mushmom,100,12,3.0`(값 불변)
  - 기존 모델은 같은 경로에 id `orangemushroom`, Scale 1로 정리했다. ActionSheet에서 stun 키를 빼 5키다. Name "주황버섯"은 FileStructure대로 이동 회차 부채다.
  - 패턴이 없어 나오지 않는다(Plan과 일치).
- **MM-03 규칙 충족형 피격:**
  - 규칙 6개(currentOpponent·sameMap·notPaused·targetAlive·sameCast·targetHittableSegment)는 Play당 1회 만들어 재사용한다.
  - 예약 타격 시각에만 ResolveScheduledHit에서 1회, IsAttackTarget에서 1회 확인한다.
  - 통과하면 대상 콜라이더 중심 0.1×0.1 BoxShape로 `AttackFast`를 호출한다. 실패하면 `[VRF] PlayerHitRule fail rule=…`를 남기고 피해 0이다.
  - IsAttackTarget 오버라이드에 `@ExecSpace`가 없다(LEA-3014 회피, 올바름).
  - QA10은 규칙별 실패 이름, 접근 중 10타 전부 targetHittableSegment 실패, 그로기 중 10타 통과를 PASS로 기록했다.
- **MM-04 구간 선언:** MonsterAttackMotion에 `Segment`(none/approach/return)와 `IsSegmentHittable`(기본 true)·`IsHittableNow`를 더했다(ServerOnly). OrangeMushroomAttack의 동작:
  - `ApproachHittable=false`·`ReturnHittable=false` 속성과 override를 둔다.
  - 접근·복귀 시작 때 구간을 지정한다.
  - CompleteMotion·CancelMotion 때 none으로 되돌린다. CancelMotion은 사망·OnEndPlay·OnMapLeave·Monster_Attack 취소 경로를 덮는다.
  - QA10에서 정지 중 구간 유지와 Stop 뒤 none이 PASS.
- **MM-05 삭제:**
  - 삭제 대상: AttackRangeGizmo·AttackRangeTuner(.mlua, Maker가 지운 .codeblock 포함), `@Assist/RangeGizmo/AttackRangeGizmo.model`, AssistModel DataSet, DefaultPlayer의 두 구성요소와 값 1개
  - AttackSkillData 4칸 제거와 PlayerSkillEffectTable 필수 칸 `{Damage, AttackCount, FrameCount}`
  - PlayerCombatComponent의 attackOffset·AttackRange*·ShowAttackRangeGizmo
  - 제품 파일(Global·RootDesk·map·ui) 대소문자 무시 Grep: castleenemy·AttackRangeGizmo·AttackRangeTuner·AssistModel·ShowAttackRangeGizmo·AttackOffset·AttackRangeWidth·AttackRangeHeight·옛 RUID 27e5fe09·소문자 "stun" 키 → **남은 참조 0건**. 대문자 상태 이름 `STUN`은 정상 사용이다.
  - 빈 RangeGizmo·AttackRange `.directory`는 FileStructure대로 이동 회차까지 둔다.
- **MM-06 기절 표시:** MonsterStunComponent는 `SetVisualClip("stun")`을 `SetVisualClip("hit")`로 바꿨다. QA10 표시 시계열에서 그로기 내내 hit(90fee9)이 PASS.
- **V11-F15 플레이어 기본 능력치:** PlayerBaseStatData `default,100,12,12`(사용자 값). QA10 로드 로그 `MaxHp=100 MoveSpeed=12 ReturnSpeed=12`, `PlayerStat applied MaxHp=100 Hp=100`이 PASS.
- **범위 밖 변경 없음:** map01·`.ui`·CombatRuleData·MonsterAttackComponent·MonsterManager는 변경 없다. 판정 창·JumpDuration·JumpHeight·패턴·몬스터 수치는 그대로다. 회차 D(§22) 요소(attack1·skill1·parry.guard·이펙트·효과음)는 들어가지 않았다.

#### 중단 조건 3(coder STOPPED 인계) 판단
- **해소로 인정한다.** coder는 Refresh 뒤 옛 castleenemy 항목(Scale 2·stun 키)이 Maker에 남아 STOPPED로 넘겼다. 그 뒤 해소 경위와 근거:
  - 사용자가 월드를 다시 열고 모델을 원래 경로로 되돌렸다.
  - 그 재저장분은 `[ops]` b4adbdd이며, 위 빌더 비교로 의미 변경이 없다.
  - QA10에서 `SpawnByModelId("castleenemy"/"CastleEnemy")`가 nil(LEA-3028)이었고, mushmom·orangemushroom이 기대 내용으로 등록됐다.
- coder 구현 산출물은 완료로 받고, 남은 정리는 문서 상태 갱신뿐이다(아래).

#### 관찰 분류
1. **그로기 중 피격 때 클라이언트 HIT / 서버 STUN:** 결함 아님. QA4·이전 coder 절에 같은 구조가 기록돼 있다. 서버 그로기 기한은 줄지 않고 표시 RUID는 hit로 같다. 이번 회차가 만든 변화가 아니다.
2. **DoSpawn 재스폰 몬스터의 서버 SpriteRenderer 프레임 범위 0-0**(첫 스폰·클라이언트는 0-2147483647): **회차 C 결함 아님 → 회차 D 필수 확인 항목**으로 넘긴다.
   - 결함이 아닌 근거:
     - 회차 C 모델 값에 StartFrameIndex·EndFrameIndex가 없다(빌더 확인).
     - 이번에 쓰는 stand·jump·hit는 1프레임 클립이라 화면 영향이 없다.
     - die는 명시 프레임 설정으로 정상 재생·고정됐다(QA10 F12 PASS).
     - move는 이번 범위에서 쓰지 않는다.
   - 회차 D의 attack1·skill1은 여러 프레임 클립이므로, 재스폰 개체에서 0-0이면 첫 프레임에 멈출 위험이 있다. 회차 D에서 해야 할 일:
     - planner·coder: 클립 지정 때 프레임 범위를 초기화할지 정한다.
     - tester: 재스폰 개체의 서버·클라이언트 실제 재생을 확인한다.

#### 사소한 코드 메모 (결함 아님, 수정 강제 없음)
- ResolveScheduledHit는 규칙 확인 전에 기한을 소비하고 hitsFired를 올린다. 이전의 재시도 경로(정지·사망·맵 변경·비ATTACK)는 어느 쪽이든 피해로 이어지지 않으므로 결과는 같다.
- `_T.resolveIndex`는 기록만 하고 읽지 않는다. 정리는 다음 수정 회차에 선택.
- ApproachHittable·ReturnHittable은 모델 값으로 저장하지 않고 스크립트 기본값(false)을 쓴다. 승인 Plan과 일치한다.

#### 문서 동기화 (비차단, planner의 회차 종료 정리)
- AssetList·FileStructure는 §21과 일치한다. 머쉬맘 리소스 "사용 중·임시", 회차 D 리소스 "사용 예정", orangemushroom "보관"으로 적혀 있고, 새 파일은 Mushmom.model 하나, 삭제 목록도 일치한다.
- 낡은 상태 표기(갱신 필요):
  - Plan §21 상태 표가 "중단 조건 3 보고 대기"다.
  - 이 WR 머리말(4행)·"현재 재개 지점"(10행)이 coder 재개 대기 상태다.
  - DevelopmentRoadmap "다음 재개 지점"(2026-11-05)이 coder 시작 전 상태다.
  - GameDesign §4.2·§5 표의 "회차 C에서 바꾼다"는 아직 미래형이다. 사용자 V11 수락 뒤 완료형으로 바꾸는 것이 맞다.

#### 확인하지 않은 것
- Bundle SHA-256 재계산(위 사유)
- 런타임 재실행
- 화면·소리 육안
- QA10 NOT_RUN 1~6. PASS로 세지 않는다. 사용자 항목이 아닌 자동 검증 공백은 아래와 같고, 차단 사유로 보지 않는다.
  - move·hit1 재생 시간
  - 실제 UIPopup·마우스 클릭
  - 규칙 6의 "모션 구성요소 없음" 분기와 규칙 4의 실제 흐름
  - parry.right 대칭 착지 강제 측정·4패턴 빈도 통계
  - 실제 맵 전환
  - 실기기 지연
- F13 실제 키 사례는 판정 창 30초 시험값 근거다.

#### 남은 사용자 V11 (Plan §21)
1. 머쉬맘 모습과 클립 연결(stand·move·jump·hit1·die1)
2. 1배 크기·BattlePos1~3와 겹침
3. HP 게이지·그로기 별·데미지 숫자 위치
4. 점프 중 무적의 체감과 줄어든 반격 창(패링 약 1.5초·저스트 약 1.0초)
5. 복귀 점프 중 공격 시 보너스 소모
6. 이동 속도 12/12·플레이어 HP 100 체감(무대응 12 피해 9회 사망)
7. 키 이름 orangemushroom 수락
8. 기존 미확인 모바일·터치·사운드·CF-F07

#### 회차 D로 넘길 것
- 재스폰 개체 프레임 범위 0-0 확인. attack1·skill1 여러 프레임 클립에서 서버·클라이언트 재생, planner·coder 처리 방식 결정, tester 재스폰 사례 시험.
- 선택: `_T.resolveIndex` 정리.

#### 다음 담당
1. 메인: `[CombatCore][review] WAITING` 회차 커밋·push
2. planner: 회차 종료 문서 동기화(Plan §21 상태, WR 머리말·재개 지점, Roadmap 재개 지점)
3. 사용자: 위 V11
4. V11 수락 뒤 GameDesign 완료형 갱신, 회차 D(§22) 재개 지시

### 2026-11-05 독립 리뷰 — 회차 B(V11-F14·V11-F07) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 런타임 사실은 coder 개발절(2026-11-04 회차 B)과 QA9 기록을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git show/diff/status·소스 대조(Grep 포함)·`.d.mlua` 확인·변경 9경로 sha256 재계산뿐이다.
- 검토 버전: coder 로컬 커밋 **1b4f4ee**(부모 9eed765, push 전). `git diff --name-status 9eed765 1b4f4ee`의 제품 경로는 .mlua 4개 수정(CombatRuleCatalog·MonsterManager·PlayerHealthComponent·PlayerMoveComponent)과 새 경로(PlayerBaseStatCatalog.mlua, DataSet 4파일, Maker 생성 PlayerBaseStatCatalog.codeblock·Stat.directory)뿐이다. 변경·추가 9경로의 작업 트리 sha256(CombatRuleCatalog 0eec3975…, MonsterManager 7cc5ff3a…, PlayerHealth 276e1c50…, PlayerMove 7d9a9f41…, PlayerBaseStatCatalog f20a1121…, PlayerBaseStatData.csv 3202ac06…·.userdataset f6d8da25…, MonsterStatData.csv f9709bd8…·.userdataset b5a226f2…)는 coder 기재와 모두 같고, `git diff 1b4f4ee`의 작업 트리 차이는 run.md·이 WR·Stat.directory뿐이라 커밋 트리와 작업 트리의 manifest 대상이 같다. 나머지 50경로는 9eed765와 git 객체가 같다(9eed765 작업 트리 b321d71c…040f는 coder 재계산·회차 A 리뷰 값과 같음). 모델·UI 파일은 셸 해시가 가드로 막혀 59경로 Bundle 문자열 자체(9325c33a…cd19 / 54경로 a8c96297…c5d)는 재계산하지 않았고 위 git 동일성으로 대신했다. QA9는 Play 1 시작·재개 시작·시험 끝 세 번 같은 59경로 Bundle을 기록했으므로 coder·tester·이 리뷰는 같은 제품 버전이다.
- 범위 밖: 작업 트리 `RootDesk/MyDesk/Player/@Assist/Stat.directory` StudioVersion ""→"0.1.0.0" 한 줄(Maker 재저장, manifest 밖). 판정에 넣지 않는다. 커밋 포함 여부는 메인 결정.
- 판정: **WAITING**. 고칠 제품 결함 없음(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 남은 것: (1) V11-F14의 플레이어 최대 HP가 DataSet 값으로 실제로 바뀌는지의 런타임 근거(아래 "근거 공백", tester 추가 실행), (2) Plan §20 사용자 V11 직접 확인. 이 판정은 2단계 완료·회차 C·3단계 진행·push 승인이 아니다.

#### 요청 → Plan §20 → 실제 diff 대조
| 사용자 승인 기본안(run 2026-11-04 회차 B 시작) | 실제 변경(1b4f4ee) | 판단 |
| --- | --- | --- |
| 1. 플레이어 HP·이동 속도(6)·복귀 속도, 기본 공격 피해는 AttackSkillData 유지 | PlayerBaseStatData `default,1000,6,6`(serveronly false). 서버 PlayerHealthComponent.OnBeginPlay가 PlayerComponent.MaxHp·Hp를 쓰고, 클라이언트 PlayerMoveComponent.ApplyBaseStats가 MoveSpeed·ReturnSpeed를 쓴다. AttackSkillData.csv·.userdataset 무변경 | 일치 |
| 2. 몬스터 HP·공격력·공격 간격, 몬스터마다 고유 id 행, 빈 칸 default | MonsterStatData `default,100,12,3.0`·`castleenemy,100,12,3.0`(serveronly true). 행 id = MonsterData modelid에서 `model://`를 뺀 modelKey(MonsterManager 한 곳에서 정하고 패턴 키와 공유). 빈 칸만 default 값 | 일치 |
| 3. 몬스터 점프 제외, 4. Pos2 경계·앵커 간격 미룸 | 점프·Pos2·앵커 관련 파일·값 diff에 없음 | 일치 |
| 값 불변·범위 밖 변경 없음 | 수치 1000·6·6·100·12·3.0 그대로. 모델·맵·.ui·기존 CSV 5종·기존 .userdataset 5종 diff 없음. `.mlua` 속성 기본값(6·6·100·12·3.0)·모델 값(DefaultPlayer maxHp, 주황버섯 MaxHp 100)도 그대로 둠(Plan 지시) | 범위 밖 변경 없음 |

#### 값 출처(겹칠 때 이기는 쪽)
- 몬스터 MaxHp: 모델 Values(주황버섯 MaxHp 100)가 .mlua 기본값 위에 오지만, 이제 서버 DoSpawn이 스폰 뒤 DataSet 값을 직접 쓴다. MonsterHealthComponent.OnBeginPlay는 `Hp = MaxHp`만 하고 MaxHp를 다시 쓰지 않으므로 OnBeginPlay가 스폰 직후든 다음 프레임이든 결과는 DataSet 값이다. **런타임 근거 있음**: QA9 Play 3과 coder Play 3에서 CSV castleenemy MaxHp 150 → 서버·클라이언트 MaxHp·Hp 150. map01에는 몬스터 배치 엔티티가 없다(Grep `castleenemy`·`MonsterHealthComponent` 0건) → 모델 값으로 도는 개체 없음.
- 몬스터 AttackDamage·AttackInterval: 모델에 값 없음, DoSpawn이 씀. MonsterAttackComponent·MonsterStateControl의 OnBeginPlay는 두 값을 다시 쓰지 않는다(소스 확인). 첫 공격은 IDLE 누적 `attackTimer ≥ AttackInterval`과 대결 상대가 있어야 시작하므로 같은 서버 프레임에서 쓴 값이 첫 공격 전에 적용된다.
- 이동·복귀 속도: DefaultPlayer 모델에 값 없음, 클라이언트가 이동 시작 전(`CanStart`에서 지연 적용 포함) DataSet 값을 쓴다. **런타임 근거 있음**: CSV MoveSpeed 9 → `boot speed=9.0`, OUTBOUND 0.154~0.158초.
- 플레이어 MaxHp: 모델 `maxHp` 1000·엔진 PlayerComponent.MaxHp 기본 1000(`.d.mlua` `@Sync property integer MaxHp = 1000`)·DataSet 1000이 모두 같아 **어느 쪽이 이기는지 런타임으로 구분되지 않았다**. coder의 중도 쓰기 프로브(777)는 Play 중 쓰기 가능성만 보이고, Play 시작 시 OnBeginPlay 쓰기 뒤 엔진/모델 초기화가 다시 덮는지·부활(ProcessRevive/Respawn)이 모델 `maxHp`로 되돌리는지는 보이지 않는다. → 아래 근거 공백.

#### 코드 대조 (소스 읽기)
- 검증 규칙(ValidateStatRows·IsValidStat, 서버·클라이언트 공용): id 앞뒤 공백 제거 뒤 빈 id·중복 거부, `default` 행 없음·빈 칸·무효 값이면 표 전체 거부, default 아닌 행의 빈 칸(빈 문자열·공백)만 default 값, 비어 있지 않은 무효 값은 표 전체 거부(대체 없음), 필수 열 누락은 ReadRows가 nil, 추가 열·`#` 열은 읽지 않아 무시. MaxHp posint(`value == math.floor(value)`, "100.0" 수락), MoveSpeed·ReturnSpeed·AttackInterval 양수, AttackDamage 0 이상, NaN·±무한대는 IsFinite로 거부. Plan §20 값 검증 표와 같다.
- 실패 시 대체 진행 없음: 몬스터 표 실패는 EnsureInitialized가 규칙·패턴과 함께 전체 거부(부분 캐시 없음) → GetMonsterStats nil → DoSpawn이 스폰하지 않음, 패턴·규칙도 nil이라 공격 시작 거부. modelKey 행 없음·`default` 키 요청은 nil + WarnOnce(default로 스폰하지 않음). 플레이어 표 실패는 서버 `_T.statsReady=false` → RefreshDuelPlayer가 대결에서 제외(몬스터 공격 없음), 클라이언트 CanStart false. 경고는 CombatRuleCatalog.WarnOnce라 원인별 한 번, OnEndPlay에서 지워 다음 Play에 넘지 않는다.
- ExecSpace: 몬스터 값 쓰기(MonsterManager.DoSpawn)·플레이어 HP(PlayerHealthComponent.OnBeginPlay, IsBaseStatsReady)는 ServerOnly, 속도(ApplyBaseStats·CanStart)는 ClientOnly, 로더 PlayerBaseStatCatalog.GetStats는 선언 없음(호출한 쪽에서 실행)이고 `self:IsServer()`는 콜론 호출. MonsterStatData serveronly true는 서버만 읽고, PlayerBaseStatData serveronly false는 클라이언트도 읽는다(QA9 `side=server`·`side=client`). 새 `@Sync`·RPC 없음, 선언 없는 `self` 필드 없이 `_T`만 사용.
- 적용 시점·레이스: 몬스터는 SpawnByModelId 반환 직후 같은 서버 흐름에서 MaxHp·Hp·AttackDamage·AttackInterval을 쓰고 그 뒤 CurrentMonster로 등록하므로 등록 전 공격 경로가 없다. 클라이언트 표 로드 전 입력은 CanStart가 먼저 ApplyBaseStats를 불러 막는다(표 실패면 `rejected reason=stats`). 로더 Logic의 OnBeginPlay 캐시 초기화가 컴포넌트 OnBeginPlay보다 늦게 돌아도 재읽기만 일어나고 결과는 같다(같은 파일·같은 검증, WarnOnce 중복 없음).
- MaxHp 변경 시 Hp: 몬스터 `health.Hp = stats.MaxHp`, 플레이어 `player.Hp = player.MaxHp`로 맞춘다. 부활 Hp는 엔진 동작(QA9 (b) 1000 → 1000 관찰).
- 대결 수락 조건: RefreshDuelPlayer에 `isvalid(stat) and stat:IsBaseStatsReady()`가 추가됐고 다른 조건·순서는 그대로다. 매 OnUpdate GetComponent 한 번이 늘었을 뿐 기존 패턴과 같다.
- MonsterManager의 `attack._T.modelKey` 지정이 같은 컴포넌트 변수 `damage`로 옮겨졌고 modelKey 계산은 스폰 전 한 곳으로 이동했다. 동작 차이 없음.
- 문제로 보지 않은 점: tonumber가 `0x10`·`1e2` 같은 표기도 숫자로 받는다(유효한 유한 양수면 수락). 대소문자 다른 id(`Default`)는 default 없음으로 거부된다. 둘 다 Plan 규칙 안이며 결함 아님.

#### 개발·QA 근거 대조 (같은 버전, NOT_RUN을 PASS로 세지 않음)
| Plan §20 기준 | coder | QA9 | 판단 |
| --- | --- | --- | --- |
| 로드 [VRF] 두 표·출처 DataSet | Play 1 | Play 1·2·5 | 충족 |
| 플레이어 HP 1000·시작 1000·클라이언트 | Play 1 | 서버 값(Play 2·5 로그 포함), 클라이언트 1000은 Play 1 | 값 충족, HP 바 화면 NOT_RUN. **DataSet ≠ 1000일 때의 적용은 근거 없음**(아래) |
| 플레이어 속도 6·복귀 6, 1단계 규칙 | 실제 키 | 실제 키 0.228~0.262초, 합산·잠금 | 충족 |
| 몬스터 수치·새 상대 | Play 1 | Play 1, DoSpawn 재호출 | 충족 |
| 공격 간격 | "IDLE→ATTACK 간격 2.96~3.01" | 시작~시작 4.003~4.030, IDLE 구간 2.92~3.03 | 값 3.0·동작 불변으로 충족. Plan 문구 "시작 간격 3.0"과 coder 기재 "전환 간격"은 실제로 IDLE 대기 구간이다(아래 분류 3) |
| 피해 12·가드 4·HP=HitEvent | 있음 | Play 1 + Play 2 (b) 자연 공격 12 | 충족 |
| 처치 합계 100·DEAD·DeadEvent 1 | 실제 20 + 프로브 80 | Play 1(실제 키 1 + 논리 9), 그로기 중 사망 Play 2 | 충족(아래 신뢰도) |
| Stop → 다음 Play 재로드·시험값 비잔존 | Play 2 | Play 2·5 | 충족 |
| CSV 실제 변경 반영·원복 byte 일치 | 있음 | 있음, 해시 일치 | 충족(MoveSpeed·몬스터 MaxHp 두 값만, Plan 지정 그대로) |
| 빈 칸·default 문제·무효 값·키·필수 열 | 프로브 | 프로브 + 실제 무효 CSV(Play 4) | 충족(프로브 근거 표기 있음) |
| 플레이어 표 실패 → 이동·대결 거부 | 상태 프로브 | 실제 무효 CSV + 실제 LeftArrow | 충족 |
| 회귀 F12·F13·F06·F10·F08·V07·V08·V10 | 대표 | 대부분 + 시험값 창 30초 | 충족(F13은 시험값, V07 예고 중 팝업 NOT_RUN) |
| tester 추가 (a)·(b) | — | (a) 재현 안 됨, (b) PASS | 아래 분류 |

- **근거 신뢰도(QA9 중단·재개)**: Play 1 원본 로그는 Maker가 Play 2 시작 때 비워 남지 않았고 그 행은 tester가 당시 읽은 값을 옮긴 기록이다. Play 1에만 기대는 독립 근거는 클라이언트 PlayerComponent.MaxHp 1000, 시작~시작 4.0초, 피해 9회 합계, 처치 합계 100, (a)의 4회분이다. 이 중 클라이언트 몬스터 HP는 Play 3(150), 피해 12는 Play 2 (b), IDLE 3.0은 Play 2, (a)는 Play 3 1회로 재확인 가능한 로그가 있다. 처치 합계 100과 클라이언트 플레이어 MaxHp 1000은 독립 QA 쪽 재확인 로그가 없고 coder 결과와 값이 같을 뿐이다. 둘 다 이번 변경이 값을 바꾸지 않는 회귀 항목이고 MaxHp 100 적용 자체는 Play 2·5 로그가 있으므로 판정을 바꾸지 않는다(비차단, 신뢰도 낮음으로 기록). 버전은 중단 전후 같은 Bundle이라 Play 1 근거도 같은 버전이다.
- **QA9 문장 과장 1곳(문서)**: QA9 "ExecSpace·구현 대조"의 "모델 값(DefaultPlayer maxHp 1000·주황버섯 MaxHp 100)은 DataSet 적용 뒤 쓰이지 않음을 CSV 변경 반영(MoveSpeed 9, MaxHp 150)으로 확인"에서 MaxHp 150은 몬스터 값이라 DefaultPlayer maxHp에는 근거가 되지 않는다. QA 원장은 reviewer가 고치지 않는다 → tester가 아래 추가 실행 기록에서 바로잡는다.

#### 근거 공백 (WAITING 사유, tester 추가 실행 조건)
- 대상: CombatCore-V11-F14 중 플레이어 최대 HP. 위 출처 분석대로 현재 근거는 값 1000끼리라 "DataSet에서 읽는다"를 보이지 못한다. Plan §20 현재 값 표가 "(1)이 MaxHp로 연결되는지는 coder가 Play에서 확인한다"로 남긴 항목도 미해소다. 사용자가 V11에서 HP를 직접 바꿔 볼 수 있으므로 그 전에 확인한다.
- 조건(같은 버전 1b4f4ee, 한 Play 회차): PlayerBaseStatData.csv `default`의 MaxHp만 1000이 아닌 값(예 800)으로 바꾸고 Refresh → Play → 서버·클라이언트 PlayerComponent.MaxHp, 시작 Hp, HP 바 값(가능하면 표시 문자), 실제 HP 0 사망 → 부활 뒤 Hp·MaxHp를 기록. Stop → 백업 바이트로 복원 → Refresh, 해시 일치 기록(3202ac06…d094). maker_clear_logs 미호출. 시험 값은 커밋하지 않는다.
- 결과 처리: 서버·클라이언트·부활 모두 그 값이면 V11-F14 MaxHp 근거 충족. 엔진·모델 값(1000)으로 돌아가는 경로가 하나라도 있으면 결함 후보로 planner에 반환한다(수치·모델을 맞춰 통과시키지 않는다. 모델 값 제거는 Plan 중단 조건 (3)이라 사용자 판단).

#### tester 관찰 분류
1. **(a) 예고 없는 ↓ 홀드의 PlayerGuard start 미기록** — 재현 불가로 종결, 결함 후보 아님 분류에 동의. 근거: IDLE·예고 없음 상태 5회(부팅 직후 첫 입력 포함) 모두 서버 `g=true`·시작 기록, 클라이언트 입력 수락·Player_Guard 진입에 예고 조건 분기가 없음(QA9 소스 근거, 이번 diff에 해당 파일 없음). 원인 가설(Play 준비 전 입력)은 확인되지 않은 추정이므로 사실로 옮기지 않는다. 재발하면 같은 기록 항목(클라이언트·서버 CurrentStateName, isGuarding, 시작 기록, 입력 시점과 Play 준비 상태)으로 다시 연다.
2. **↑ 100ms 연속 탭** — 이번 회차 결함 아님, 기존 설계. 단일 100ms 탭은 시전되고, 두 번째 탭은 ATTACK 약 0.83초 동안 IDLE이 아니라 거부되는 기존 "한 동작 수락·입력 예약 없음" 규칙이다. PlayerStateControl·Player_Attack·PlayerCombatComponent는 diff 밖. coder가 남긴 "100ms 짧은 입력 문턱" 가설은 QA9 단일 탭 시전으로 부정됐다. 사용자 확인 불필요(이미 확정된 입력 규칙).
3. **자연 공격 간격 3.0 = IDLE 대기, 시작~시작 약 4.0초** — 이번 회차 결함 아님, 기존 설계. MonsterStateControl.OnUpdate는 IDLE일 때만 `attackTimer`를 누적하고 그 파일은 diff 밖이며 값 3.0도 같다. 따라서 값 동일성 회귀는 충족한다. 다만 (i) Plan §20 확인 기준 "자연 공격 시작 간격이 전투 시계 3.0초"와 coder 기재 "IDLE→ATTACK 전환 간격 2.96~3.01"은 실제 의미(공격이 끝나 IDLE로 돌아온 뒤 다음 공격까지의 대기, 적 진행 시계 기준)와 표현이 다르다 → planner 문서 정정(비차단). (ii) 이제 사용자가 CSV `AttackInterval`을 직접 고치므로 열 의미가 사용자 기대("시작~시작")와 같은지는 **사용자 확인 항목**이다. 의미를 바꾸려면 새 요구로 planner를 거친다(이번 회차에서 고치지 않음).
4. (b) 실제 HP 0 사망: 시작 위치·시각 기록 삭제, 부활 Hp = MaxHp 1000 PASS. 사망 직전 Hp −4는 이전부터 알려진 범위 밖 관찰(HP 음수 표시 가능성)이다.

#### 문서 대조 (비차단, 회차 종료 정리)
- Plan §20 상태 표가 "coder 대기"로 남아 있다 → 1b4f4ee, QA9 PASS(NOT_RUN 목록), 리뷰 WAITING(플레이어 MaxHp 근거 공백·사용자 V11). §20 확인 기준 "공격 간격" 행과 §5 MonsterStatData 설명에 AttackInterval = 공격 종료 뒤 IDLE 대기(적 진행 시계, 팝업·슬로우 규칙 그대로)임을 적는다. 수치·규칙은 바꾸지 않는다.
- 이 WR 머리 "상태·갱신일"·"현재 재개 지점"이 회차 B Plan 직후 상태다.
- run "다음 행동"에 이 판정, 1b4f4ee, 59경로 9325c33a…cd19를 적는다.

#### 검사하지 않은 범위
- reviewer는 Maker·로그·화면을 직접 보지 않았다. 59경로 Bundle 문자열은 모델·UI 파일 해시가 셸 가드로 막혀 재계산하지 않았다(git 객체 동일성과 변경 9경로 해시로 대신). .codeblock·.directory 내용은 Maker 생성물이라 대조하지 않았다.

#### NOT_RUN (PASS로 세지 않음)
- 플레이어 MaxHp ≠ 1000 DataSet 적용·부활(위 근거 공백), HP 바 화면, 사람 손 0.20초 타이밍(회차 A 사용자 수락 이력 있음), 모바일·실기기·터치·다중 접속, V07 예고 중 팝업 정지·재개 전수, F06 `parry.right` 대칭 착지·F10 출현 빈도, 실제 다른 맵 전환, 서버만/클라이언트만 표 실패 비대칭, Maker UI에서 DataSet 직접 편집, V12·CF-F07.

#### 다음 행동
1. 메인: run에 이 판정(WAITING), 검토 버전 1b4f4ee / 59경로 9325c33a…cd19를 적는다. Stat.directory 재저장 줄은 범위 밖으로 사용자에게 알리고 커밋 포함 여부를 정한다. 회차 종료 커밋 시점은 아래 2번 결과 뒤가 자연스럽다(메인 판단).
2. tester(필수, 같은 버전): 위 "근거 공백" 조건 1회 실행과 QA9 과장 문장 정정.
3. 사용자 V11(아래), 2번 결과 뒤.
4. planner(문서만, 비차단): 위 "문서 대조" 정정.
5. coder: 지금 할 일 없음. 2번에서 결함 후보가 나오면 planner·사용자 판단 뒤.

#### 사용자 V11 확인 항목
- PC에서 이동·복귀 체감이 회차 A와 같은지(값 6 그대로).
- 원하면 `PlayerBaseStatData.csv`의 MoveSpeed(또는 MaxHp)를 직접 바꾸고 Maker Refresh → Play로 바뀌는지, 표·열 이름이 고치기에 알아보기 쉬운지.
- 몬스터 HP·공격력·공격 간격도 `MonsterStatData.csv` castleenemy 행으로 고칠 수 있는지.
- `AttackInterval` 3.0은 "공격이 끝난 뒤 다음 공격까지 대기 3.0초(공격 시작~다음 시작은 약 4.0초)"로 동작한다. 생각한 "공격 간격"과 같은지. 다르면 새 요구로 정한다.
- 이동 속도 등 새 값은 사용자가 정하며 이번 회차의 값 변경이 아니다. 기존 V11 미확인(모바일·터치·음향·반격 체감·CF-F07)은 그대로 남는다.

#### 보충 확인 (2026-11-05, QA9 보충 시험 1 대조)
- 대조 대상: QA9 절 "QA9 보충 시험 1 — 플레이어 MaxHp를 DataSet이 실제로 정하는가". reviewer는 이번에도 Maker를 다루지 않았다. 직접 확인한 것은 `git status`(HEAD 1b4f4ee, 작업 트리 차이는 run.md·이 WR·Stat.directory뿐, `git diff 1b4f4ee -- RootDesk map ui Global`은 Stat.directory 한 경로)와 CSV 해시 재계산이다. PlayerBaseStatData.csv `3202ac06…d094`, MonsterStatData.csv `f9709bd8…1dc3`로 변경 전과 같다. 따라서 보충 시험은 같은 버전에서 이루어졌고 시험 값은 남지 않았다.
- 근거 판단: `default` MaxHp 800에서 서버·클라이언트 PlayerComponent.MaxHp 800, 시작 Hp 800, `PlayerStat applied MaxHp=800 Hp=800 source=DataSet`가 나왔다. 실제 피해로 HP 0 사망한 뒤 자동 부활에서도 서버·클라이언트 `Hp=800|MaxHp=800`이었고, 1000으로 돌아간 값은 없었다. 원복 뒤 다음 Play에서는 1000으로 돌아왔다. 모델 `maxHp` 1000과 엔진 기본 1000이 DataSet 값을 덮지 않는다는 런타임 근거로 충분하다. 사망 직전 Hp는 시험값(20)으로 낮췄지만 사망은 실제 피해 경로였다. HP 바는 저해상도 스크린샷이라 자릿수 확정이 제한적이지만 값 판정은 로그가 근거다(HP 바 육안은 기존대로 사용자 V11).
- QA9 과장 문장: "ExecSpace·구현 대조" 첫 항목에 정정 문장이 붙었다. 몬스터 MaxHp 150은 플레이어 근거가 아니라는 점과 플레이어 근거는 보충 시험 1이라는 점이 함께 적혀 해소됐다.
- 남은 NOT_RUN(비차단): 맵을 옮겼다 돌아오는 경우와 재접속 때의 MaxHp. 소스상 MaxHp를 쓰는 곳은 서버 PlayerHealthComponent.OnBeginPlay 한 곳이고, 엔티티 속성이라 같은 엔티티의 맵 이동에서 지워질 이유는 보이지 않는다. 현재 맵은 map01 하나라 이번 범위의 위험은 낮다. 맵이 늘어나는 단계에서 한 번 기록하면 된다.
- 결론: 앞 절의 WAITING 사유 (1) 플레이어 MaxHp 근거 공백은 **해소**됐다. 두 요구(V11-F14·V11-F07)의 AI 측 근거는 Plan §20 확인 기준을 충족한다. 고칠 제품 결함은 여전히 없다. 남은 것은 사용자 V11 직접 확인(앞 절 "사용자 V11 확인 항목", AttackInterval 의미 확인 포함)과 planner 문서 정정(앞 절 "문서 대조", 비차단)뿐이다.
- **최종 판정: WAITING**(사용자 V11). 이 판정은 2단계 완료·회차 C·3단계 진행·push 승인이 아니다.
- 다음 행동 갱신: 앞 절 "다음 행동" 2번(tester 추가 실행)은 끝났다. 메인은 run에 보충 시험 결과와 이 최종 판정을 적고, 회차 종료 커밋에 QA9 보충 시험·이 리뷰 절을 넣는다. Stat.directory는 범위 밖이니 사용자에게 알린다. 그다음은 사용자 V11이고, planner 문서 정정은 비차단이다. coder는 할 일이 없다.

### 2026-11-04 독립 리뷰 — 회차 A(V11-F12·V11-F13) WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절(2026-11-04 회차 A)과 QA8(중단분 + "QA8 재개" 소절)의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git show/diff·소스 대조(Grep 포함)·`.d.mlua` 확인과 작업 디렉터리 밖 임시 node 스크립트의 지문 재계산뿐이다.
- 검토 버전: coder 로컬 커밋 7f2d0b4(기준 5c4eda3, push 전). 일시정지 커밋 bac801b는 run·WR·GameDesign·로드맵 문서만 바꿨다(제품 경로 없음). V11-F06 절 manifest 54행을 같은 계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)으로 재계산했다. 5c4eda3 커밋 트리 = 9208e0aa…da79(지난 리뷰 값과 일치), **7f2d0b4 커밋 트리 = 7f32ae45d37aa6613db2c8de1c56ede5e0915fb5d0e0c34abb12a63340ce21e3**, **작업 트리 = b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f** — 둘 다 coder·QA8(중단분·재개분) 기재와 일치. 변경 7경로 개별 해시(CombatPause 92e0b080…, MonsterAttackComponent 5c6a7896…, MonsterAttackMotion 349d3e8a…, MonsterHealth 38d5379f…, PlayerEvade 679dc069…, PlayerGuard f8d0bd70…, PlayerHealth 9cf53db2…)는 커밋 트리와 작업 트리에서 같고 coder 절 값과도 같다. `git diff 7f2d0b4`의 RootDesk·map·ui·Global 차이는 Maker 재저장 3경로(AssistModel·AttackSkillData userdataset, 주황버섯 모델)뿐이며 지난 두 리뷰에서 의미 차이 없음을 확인한 같은 바이트다(이번 회차 범위 밖, 판정에 넣지 않음, 커밋 제외). 따라서 coder·QA8이 같은 제품 버전을 대상으로 했고 QA8 근거는 커밋 트리에도 그대로 적용된다.
- 판정: **WAITING**(사용자 V11). 고칠 결함 없음(CHANGES_REQUIRED 없음, 새 결함 ID 없음). 두 요구의 AI 측 근거는 Plan §19 완료 기준을 충족한다. 남은 필수는 Plan §19 "사용자 V11 직접 확인"이다. 이 판정은 2단계 완료·회차 B 시작·3단계 진행·push 승인이 아니다.

#### 요청 → Plan §19 → 실제 diff 대조
| 사용자 결정(run 2026-11-03 §17 V11 결과·2026-11-04 회차 A 시작) | Plan §19 | 실제 변경(7f2d0b4, .mlua 7개) | 판단 |
| --- | --- | --- | --- |
| "die animation이 반복됨. 1번만 하고 die end 모션에서 정지" | V11-F12, 공통 사망 표시 층, 자원·모델·데이터 불변, fade·완료 팝업 제외 | MonsterAttackMotion에 PlayDieOnce/TickDie·SetVisualClip 사망 뒤 차단(+48줄), MonsterHealthComponent에 사망 뒤 TickDie만 부르는 ServerOnly OnUpdate(+9줄, 주석 1줄) | 일치·최소 |
| "저스트 회피랑 패링 둘다 pos2에서만… 피격 범위에서 성공시에만", 칸 ±0.75 추천안 | V11-F13 (a) 시작 위치 Pos2 칸(앵커 중점, 경계 포함) (b) 영역의 Pos2 앵커 포함, 기존 조건 유지 | PlayerEvade/GuardComponent 시작 x 기록·ClearStart·GetStartX, CombatPause·PlayerHealth의 시각 삭제 지점을 ClearStart로 교체, MonsterAttackComponent 스냅샷 pos2Cell, EvaluateDefense 성공 분기에 `cellOk and areaOk` | 일치·최소 |
| 수치·DataSet·모델·맵·UI·입력 규칙 불변 | "바꾸지 않는 것" 목록 | 커밋의 제품 경로는 위 7개 .mlua뿐. CSV·.userdataset·.model·.map·.ui·.codeblock·.directory 변경 없음(새 .mlua 없음). 창·×0.40·반격·슬로우·그로기·AttackDamage·AttackInterval·점프·패턴·속도 값 diff에 없음. 입력 수락(PlayerStateControl·PlayerMoveComponent)·CombatInputController 무변경 | 범위 밖 변경 없음 |

#### V11-F12 코드 대조
- 모든 사망 경로가 한 곳을 지난다: HP 0 확정은 MonsterHealthComponent.ApplyDamage뿐이고(HandleHitEvent도 이것을 부름), 거기서 CancelPendingAttack → ClearCombatEffects(슬로우 PlayRate 복원) → SetStunned(false)(그로기였으면 SetVisualClip("die")) → SetVisualClip("die") → ChangeState("DEAD") 순서다. PlayDieOnce는 첫 진입만 통과(`_T.dieStarted`)하므로 그로기 경로의 die 요청과 직후 두 번째 요청이 겹쳐도 재생은 한 번이다. 슬로우 복원이 die보다 먼저라 재생 배율은 기본값으로 계산된다(Plan "슬로우 중 사망은 기본 속도"와 같음, QA8 S7 0.18/0.19초 간격).
- 클립 쓰기 경로 전수(Grep): 몬스터 SpriteRUID를 쓰는 코드는 MonsterAttackMotion 한 파일뿐이고, 그 진입점 SetVisualClip은 `_T.dieStarted`면 모든 키를 무시한다. 호출자 OrangeMushroomAttack(jump·stand)·MonsterStunComponent(stun·stand/die)·MonsterHealth(die) 모두 이 가드를 지난다. OrangeMushroomAttack은 SetVisualClip을 재정의하지 않는다. 프로젝트 코드에 프레임 이벤트(SpriteAnimPlayer*·AnimationClipEvent) 구독자는 없다.
- TickDie 위치: OrangeMushroomAttack은 MonsterAttackMotion을 상속하면서 자체 OnUpdate를 두고 `__base`를 부르지 않는다(기반 클래스에는 OnUpdate가 없음). 그래서 정지 틱을 모든 몬스터에 공통인 MonsterHealthComponent.OnUpdate(ServerOnly, IsDead일 때만)에 둔 coder 판단이 맞다. 몬스터별 모션에 들어가지 않았다(Plan 구현 경계 충족).
- 정지 방식: `.d.mlua` 확인 결과 SpriteRendererComponent.StartFrameIndex/EndFrameIndex는 `@Sync int32`이고 EndFrameIndex 기본값이 2147483647이다. 서버에서 0/MAX로 정리한 뒤 마지막 프레임 시작 시각((프레임 지연 합 − 마지막 지연)/배율, 이 클립 0.36초)에 Start=End=마지막 프레임으로 쓴다. 기한은 맵 전투 시계(CombatPauseComponent.GetCombatTime, 팝업 동안 서버 시계 정지)라 재생 도중 팝업을 열고 닫아도 남은 재생이 이어진다. 클라이언트 쪽은 SetClientTimeScale 0으로 재생이 멈춘다. 마지막 프레임 시작에 고정하므로 서버 쓰기가 늦게 도착해도 한 바퀴를 넘기기 전 여유가 마지막 프레임 길이(0.30초)만큼 있다.
- 새 상대·다음 Play: `_T.die*`는 그 엔티티 수명 값이고 MonsterManager.DoSpawn은 새 엔티티를 생성한 뒤 이전 개체를 Destroy한다. 그래서 정지 설정이 다음 상대에 남을 경로가 없다(QA8 DoSpawn 8회·Stop 뒤 Play 2 stand 0/MAX 정상 재생과 일치).
- 대체 경로: 클립을 읽지 못하거나 맵에 CombatPauseComponent가 없으면 정지 없이 die RUID만 쓴다(종전 동작, `[VRF] MonsterDie start without freeze`). 현재 map01에는 해당하지 않는다.

#### V11-F13 코드 대조
- (b) `areaIncludes`는 TelegraphCells 두 번째 문자와 같은 식(`anchorXs[2] >= minimum and <= maximum`)이라 화면 가운데 칸 표시와 판정이 어긋날 수 없다. 앵커 순서는 PrepareAttack이 이미 `a1 < a2 < a3`를 강제해 pos2Cell의 minX < maxX가 보장된다. 칸 경계 = 앵커 중점(지금 ±0.75), 경계 포함(±1e-6 허용) — Plan 기본안과 같다.
- (a) 시작 x는 기존 시작 시각과 **같은 조건·같은 순간**(서버 SetEvading(true)/SetGuarding(true)의 `not isEvading/isGuarding` 첫 진입)에 기록한다. 시각을 −1로 지우던 곳 4곳(팝업 닫기, 플레이어 사망, 회피·가드 OnMapLeave)은 모두 ClearStart로 바뀌어 위치도 함께 지운다. 직접 `= -1` 쓰기는 남지 않았다(Grep). Stop은 런타임 `_T`가 사라지고 PlayerEvade는 OnEndPlay→OnMapLeave도 탄다. 클라이언트가 보낸 위치·성공 값은 판정에 쓰지 않는다(§5 소유권 충족).
- 실패 시 결과 유지: 가드 분기는 `attribute=="PARRY" and 창 and cellOk and areaOk`만 PARRY이고 그 밖은 종전대로 SPECIAL이 아니면 GUARD ×0.40, SPECIAL이면 UNGUARDABLE이다. 회피 분기는 성공 조건 하나에 `cellOk and areaOk`를 더했을 뿐 결과 기본값 HIT와 그 뒤 RecordDefense의 영역 밖 EVADE 0 대체는 그대로다. 분기 구조가 `elseif isvalid(evade) and … then`에서 `elseif isvalid(evade) then if … end`로 바뀌었지만 그 뒤에 다른 분기가 없어 결과는 같다. EvaluateDefense 호출자는 ResolveAttack 하나(Grep).
- 판정 로그는 `Environment:IsMakerPlay()`일 때만 출력된다(배포 영향 없음).

#### 개발·QA 근거 대조 (같은 버전, NOT_RUN을 PASS로 세지 않음)
| Plan §19 완료 기준 | coder 기본 검증 | 독립 QA8(중단분 + 재개) | 판단 |
| --- | --- | --- | --- |
| F12 7개 사망 경로 1회 재생·마지막 프레임 정지, 서버·클라이언트 die 유지 | 8경로, 서버 0/MAX→2/2, 클라 프레임 0·1·2 한 번 | 8경로 서버 폴링 + 소유 클라이언트 프레임 이벤트, 7.5초 창 변화 0, 그로기 중 실제 ↑ 처치 | 충족 |
| F12 정지 뒤 세 시점 이상 화면 동일, 재생 중과 다름 | 4장 동일, stand와 다름 | 4장 완전 동일(0.000/0), stand와 29.8. **재생 중 화면은 0.36초라 캡처 못함**, 프레임 0 강제 화면과 다름, 프레임 1·2는 화면상 같은 그림 | 정지는 충족. "재생 중과 다름"은 화면으로 엄격히 보이지 못했고 프레임 이벤트·렌더러 값으로 대신함(Plan이 근거 방식을 coder 선택에 맡긴 범위). 육안은 사용자 V11 |
| F12 팝업(재생 중·정지 뒤) | IDLE 경로 | IDLE·점프 중·착지 대기·그로기 중·정지 상태에서 사망(HIT) — 프레임 0 재시작 없이 이어서 한 번 | 충족(팝업은 취소 핸들러 호출, 입력 경로는 변경 밖) |
| F12 늦은 경로 | S2~S8 제품 경로 | S9 직접 호출 다수 + S2~S8 | 충족 |
| F12 회귀(stand·jump·F08 hit·F06 착지·F02·Stop 뒤 Play·새 상대·DEAD·DeadEvent 1회·HP=HitEvent) | 대표 | 재개분에서 F08 aec950 유지, F06 착지 ±0.75, F02 그로기 10건, Stop 뒤 Play stand, DeadEvent 1, HP 감소=HitEvent 합 40 | 충족 |
| F13 parry.left/right·parry.any·special.random 칸 1/2/3·패링 1칸 끝 칸 | 회피 17·가드 15 | 회피 20·가드 20 프로브 + 실제 ↓ 6·←/→ JUST 2 | 충족(프로브 근거·시험값으로 표기돼 있음) |
| F13 ±0.75/±0.76/±0.80 경계 | 일부 | 회피·가드 모두 | 충족 |
| F13 회피 이동 중 경계·창 밖 시작 | E15 | E15·K4(기본 창)·K5 | 충족 |
| F13 위치 기록 삭제(팝업 닫기·플레이어 사망·Stop) | 4경로 | 팝업 닫기(실제 UIPopup), 사망(서버 ChangeState DEAD), Stop 뒤 Play 2 | 충족. 단 사망은 상태 전환 근거이고 **HP 0 실제 사망·실제 맵 이동(OnMapLeave)은 NOT_RUN**. 같은 삭제 함수가 DEAD 상태 이벤트에서 불리므로 HP 0 경로 차이는 상태가 DEAD가 되는지뿐이다(비차단) |
| F13 서버 기록 x 대 클라이언트 segment.startX | 실제 키 5건 0.000 | 실제 키 6건 0.000 | 충족(단일 접속 Maker 11건) |
| 실제 키 LeftArrow·RightArrow·DownArrow 각 1회 이상 | 있음 | 있음 | 충족 |
| maker_clear_logs 미호출 | 기재 | 중단분·재개분 모두 기재 | 계약 준수(reviewer는 Maker 로그를 직접 보지 않음) |

- 시험값 영향: 실제 키 사례의 창 확대(3.0·30·40초)와 판정 앞당김은 Play 내부 캐시만 바꿨고 재Play에서 0.20·0.20·2.0 복원이 확인됐다. 이번 diff는 IsInWindow와 창 값을 건드리지 않았으므로 넓힌 창은 (a)·(b)와 결과 종류 확인에 충분하다. 기본 창 0.20의 사람 손 성공 사례는 NOT_RUN이며 사용자 V11로 넘긴다.
- QA8 시험 오류(K1 첫 실행의 서버 MOVE 순번 오염, 팝업 감시 대상 착오, 프로브 지역 변수 경고)는 시험 스크립트 쪽 원인으로 기록됐고 재실행 결과로 대체됐다. 제품 판정에 섞이지 않았다.

#### 알려진 위험·관찰 분류
1. **서버 기록 위치와 클라이언트 위치 차이(칸 경계 넘김 가능성)** — 결함 아님. Plan §19 기본안(서버 상태 진입 순간 위치 기록, 클라이언트 값 불신)을 그대로 구현했고, 실측 11건(coder 5·QA8 6)에서 서버 기록 시각이 클라이언트 시작보다 0.085~0.095초 늦었지만 기록 x는 0.000이었다. 서버가 보는 상태와 위치가 모두 소유 클라이언트 동기화로 들어오므로 위험은 절대 지연보다 "상태 도착과 위치 도착의 순서 차이"에 가깝다. 단일 접속 Maker 근거뿐이라 실제 네트워크·다중 접속 오차는 미확인이다 → **후속 확인 항목**(V12 외부 환경 또는 실기기 회차에서 서버 기록 x·클라이언트 startX를 다시 기록). 사용자 V11에서 "Pos2에서 정확히 눌렀는데 저스트가 안 난다"는 보고가 나오면 기준을 바꾸지 말고 이 로그로 원인부터 확인한다(Plan 지시 그대로).
2. **정지 시점 프레임 2 이벤트 1회 추가** — 결함 아님(엔진 동작). 이미 프레임 2를 그리는 중에 Start/End 범위를 2/2로 바꾸면 같은 프레임 이벤트가 한 번 더 온다. 렌더러 값 2/2·화면 픽셀 동일·이후 이벤트 0건으로 보이는 결과는 변하지 않고, 프로젝트 코드에 프레임 이벤트 구독자가 없다. 후속 메모만: 4단계 암전·스테이지 완료 팝업을 붙일 때 "die 끝" 신호로 프레임 이벤트 횟수를 세지 말고 서버 정지(TickDie) 시점을 쓴다.
3. **예고가 없을 때 DownArrow 홀드가 PlayerGuard start를 남기지 않은 관찰**(QA8 재개, 원인 미조사) — 이번 변경 결함 아님, 원인 미확인 관찰. 소스상 클라이언트 입력 수락(PlayerStateControl.RequestChangeState·PlayerInputComponent)에는 예고 조건이 없고, 시작 x 기록은 5c4eda3부터 있던 시작 시각 기록과 같은 조건 한 줄에 붙어 있어 F13이 이 동작을 만들 수 없다. 패링 성공은 판정 직전 0.20초 안 시작만 인정하므로 예고 전 시작은 원래 성공 대상이 아니라 F13 판정에는 영향이 없다. 다만 그 순간 서버가 GUARD 상태에 들어가지 않은 것이면 일반 가드 ×0.40 적용에도 영향이 있을 수 있어 확인 가치는 있다 → **비차단 후속 확인**: 다음 tester 회차(회차 B)에서 예고 없는 IDLE 상태로 ↓ 홀드 시 클라이언트·서버 CurrentStateName, `isGuarding`, `[VRF] PlayerGuard start` 유무를 같이 기록한다. 이미 GUARD/isGuarding인 상태의 재홀드(같은 홀드 합산)였을 가능성도 함께 가른다. 재현되면 새 결함 후보로 planner에 넘긴다.
4. 그 밖의 관찰: 맵 배치 몬스터 0/MAX와 DoSpawn 직후 0/0 초기값 차이(기존, 사망 때 0/MAX로 정리), die 프레임 1·2가 같은 그림이라 화면으로는 재생 구간이 0.18초만 구별됨(자원 특성, 육안은 사용자), 죽은 몬스터에 프로브가 ChangeState를 직접 호출하면 IDLE로 바뀌는 엔진 동작(제품 경로는 모두 IsDead 확인, 그때도 렌더러 2/2 유지) — 모두 결함 아님.

#### 문서 대조
- GameDesign §4.2(109·102행)는 회차 A 사용자 결정 문구와 Plan §19를 정확히 옮겼다. 무효화된 기존 서술(D01 ANY 끝 칸 한 방향, §15 끝 칸, §17 F10 planner 해석)은 Plan 각 위치에 "§19가 대체" 표기가 이미 있다. 코드 주석의 validDirs 설명(끝 칸 중앙 쪽 한 방향)은 탈출 검증용 값 설명이라 틀리지 않다.
- 비차단 문서 동기화(planner·메인, 회차 종료 정리): (1) Plan §19 상태 표가 "로컬 커밋 전, 독립 QA·리뷰 대기"로 남아 있다 → 7f2d0b4, QA8 PASS(NOT_RUN 목록), 리뷰 WAITING, 사용자 V11 대기로. (2) 이 WR 머리 "상태·갱신일"과 "현재 재개 지점"이 2026-11-03/회차 A Plan 직후 상태다. (3) run "다음 행동"에 이 판정과 커밋 트리 7f32ae45…·작업 트리 b321d71c…를 적는다. 규칙·수치·기준은 바꾸지 않는다.

#### 검사하지 않은 범위
- reviewer는 Maker·로그·화면을 직접 보지 않았다. 런타임 사실은 위 coder·QA8 기록에 의존한다. 클라이언트 실제 그리기를 읽는 API가 없어 F12 근거는 렌더러 값·프레임 이벤트·스크린샷이다. 이번 diff 밖 코드(입력 수락·이동·반격·HUD)는 회귀 근거만 대조했다.

#### NOT_RUN (PASS로 세지 않음)
- 사람 손 기본 0.20초 타이밍 성공, HP 0 실제 플레이어 사망과 실제 다른 맵 전환에서의 위치 기록 삭제, 재생 중(0.36초) die 화면 캡처와 육안, CSV 파일 변경 반영, 실제 마우스·터치 팝업 클릭·실기기·모바일, 다중 접속·실제 네트워크 지연의 위치 오차, V12 외부 환경, CF-F07 연출.

#### 다음 행동
1. 메인: run 대상 버전에 7f2d0b4 커밋 트리 7f32ae45…e21e3 / 작업 트리 b321d71c…040f와 판정 WAITING을 적는다. 회차 종료 커밋(`[CombatCore][review] WAITING`)에 QA8(재개 소절 포함)·이 리뷰 절·run·planner 문서 동기화를 넣고 Maker 재저장 3경로는 넣지 않고 사용자에게 알린다. push 전 비밀값·개인정보 검사는 메인 몫이다.
2. 사용자 V11 확인(아래).
3. planner(문서만, 비차단): 위 "문서 대조" 동기화 3건.
4. tester(다음 회차 때, 비차단): 위 분류 3번(예고 없는 ↓ 홀드) 재현 기록, 가능하면 HP 0 실제 플레이어 사망 뒤 위치 기록 삭제 1건.
5. coder: 지금 할 일 없음. 회차 B·§18은 사용자 재개 지시 뒤.

#### 사용자 V11 확인 항목
- PC에서 몬스터를 처치하면 die가 한 번만 재생되고 끝 모습에서 멈춰 있는지(그로기 중 처치, 재생 도중·정지 뒤 팝업 열고 닫은 뒤 포함). 가능하면 모바일도.
- Pos2(가운데)에 있을 때 가운데 칸이 켜진 공격에서만 저스트·패링이 나는지, 0.20초 창을 손으로 맞출 수 있는지.
- 끝 칸 1칸 공격(특히 특수 무작위가 끝 칸을 고르는 약 2/3)에 저스트·패링 보상이 없는 난이도가 괜찮은지.
- 정상적으로 Pos2에서 눌렀는데 저스트·패링이 안 나는 경우가 있으면 알려 주기(위 위험 1번 확인용).
- 그 밖의 기존 V11 미확인 항목(모바일·터치·음향·반격 체감·CF-F07)은 그대로 남는다.

### 2026-11-03 독립 리뷰 — REV-F02·V11-F10·F11 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절(REV-F02·V11-F10·V11-F11)과 QA7의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git diff·소스 대조(Grep 포함)와 작업 디렉터리 밖 임시 node 스크립트의 지문 재계산뿐이다.
- 검토 버전: coder 로컬 커밋 5c4eda3(기준 a921c76, push 전). QA7은 미커밋 작업 트리(WR QA 절·Plan §17 상태). V11-F06 절 manifest 54행을 같은 계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)으로 재계산했다. a921c76 커밋 트리 = 38e7aa22…0ba53(이전 리뷰 값과 일치), **5c4eda3 커밋 트리 = 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79**(새 값), 작업 트리 = **fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80**(coder·QA7 기재와 일치). a921c76→5c4eda3 차이 경로는 제품 6개뿐이고 개별 해시가 coder 절 값과 모두 같다. 5c4eda3→작업 트리 차이는 Maker 재저장 3경로뿐이며 해시(주황버섯 모델 d8f79eb5…, AssistModel a933d30a…, AttackSkillData c6b692fd…)가 지난 리뷰(43c5c63)에서 의미 차이 없음을 확인한 바이트와 같다. 따라서 QA7 근거는 커밋 트리에도 그대로 적용된다. 전체 저장소 diff a921c76..5c4eda3의 RootDesk·map·ui·Global 변경은 위 6경로뿐이고 .codeblock·.directory·.userdataset·.map·.ui 변경과 추적 안 된 파일은 없다. CSV는 BOM·CRLF 유지(머리말+4행, 줄마다 CR).
- 판정: **WAITING**. 고칠 결함 없음(CHANGES_REQUIRED 없음). 세 요구의 AI 측 근거(소스 대조·coder 실측·QA7 서버/클라이언트 시계열·스크린샷 픽셀·실제 키 입력)는 Plan §17 완료 기준을 충족한다. 남은 필수는 사용자 V11 직접 확인이다. 이 판정은 2단계 완료·3단계 진행·push 승인이 아니다.

#### 사용자 결정 → Plan §17 → 변경 대조
| 사용자 결정(run 2026-11-03 절) | Plan §17 | 실제 변경 | 판단 |
| --- | --- | --- | --- |
| "1. 너 의견대로": 사망 시 die 고정만, fade·스테이지 전환은 4단계 | REV-F02, fade·처치 연출 제외 | MonsterHealthComponent.ApplyDamage 사망 확정 경로에 기존 MonsterAttackMotion:SetVisualClip("die") 한 번(4줄). fade·전환·새 연출 없음 | 일치·최소 |
| "안 2 보라+특수 1칸", 특수 "약 1/7", 대상 "랜덤으로" | F10 4행·Weight 2·2·2·1·AreaTarget FIXED/NEAREST/RANDOM | CSV 4행, Catalog 검증 3줄+필수 열 1개, MonsterAttackComponent RANDOM 분기와 SelectRandomCell | 일치. 보라 셋의 2:2:2는 planner 기본안(Plan에 그렇게 적힘) |
| 특수=가드·패링 불가 유지 + "가드 불가" 문구, 범위 밖 회피 0 유지 | F11 UNGUARDABLE rate 1, RecordDefense EVADE 대체 유지 | PlayerHealthComponent else 분기 3줄, CombatInputController 문구 1줄 | 일치·최소 |
| 끝 칸 홀드 + 1칸 특수 가설은 tester 확인만 | H1 | 코드 변경 없음, QA7 확인 | 일치 |

#### REV-F02 대조
- 위치·역할 분리: 공통 층(MonsterHealthComponent)에서 모든 HP 0 경로가 지나는 ApplyDamage 한 곳에 넣었고, 주황버섯 전용 OrangeMushroomAttack에는 넣지 않았다(Plan 지시대로). 새 RUID·Sync 값·모델 변경 없이 ActionSheet["die"]를 읽는다.
- 순서: IsDead=true → CancelPendingAttack(실행 무효화, CancelMotion은 stand를 쓰지 않음) → ClearCombatEffects → SetStunned(false)(그로기였다면 IsDead를 보고 die, 아니면 무동작) → SetVisualClip("die") → ChangeState("DEAD")(DEAD 잠금). 늦은 stand 쓰기 후보를 소스로 확인했다: OrangeMushroomAttack.CompleteMotion은 JumpActive일 때만 stand를 쓰는데 OnUpdate가 ATTACK이 아니면 CancelMotion만 하고, 활성 실행은 CancelExecution으로 무효화된다. MonsterStunComponent는 사망 시 die를 남긴다. HandleHitEvent는 IsDead면 반환한다. 추가 차단이 필요 없다는 coder 판단과 맞다.
- QA7 근거: 7경로(IDLE 실제 ↑·ATTACK 시작/점프/착지 대기/복귀·HIT·슬로우+점프·그로기 실제 ↑) 서버 +2.5초(그로기 +8초)까지 die, 클라이언트 `DEAD|die` 뒤 변경 없음, 실제 UIPopup 열기(_UIPopup:Open)·닫기(취소 핸들러) 중·후 die, Stop 뒤 재Play stand. Plan 완료 기준 항목을 모두 덮는다. 팝업 버튼 마우스 클릭은 핸들러 호출로 대체했다(입력 경로는 이번 변경 밖이라 판정에 영향 없음).

#### V11-F10 대조
- 데이터 주도: 대상 칸 방식이 CSV 열(AreaTarget)이고 공통 층에 modelId 분기·주황버섯 규칙이 없다. 주황버섯 착지(영역 중앙)는 기존 OrangeMushroomAttack 그대로라 고정 칸에 착지한다. 칸 수 3은 기존 BattlePos 3앵커 전제와 같다.
- 검증: 세 값 외(빈 값·알 수 없는 값·nil) 거부, `(ANY)==(FIXED)` 한 줄로 ANY+FIXED와 비ANY+NEAREST/RANDOM을 함께 거부, 앵커는 기존 검사(ANY 0/0, 그 밖 1~3 정수·From≤To)로 거부. 열 누락은 ReadRows 필수 열로 전체 거부. 부분 행·기본값 대체 없음. Plan 검증 목록과 같다.
- 무작위 칸: `SelectRandomCell(unit)`은 결정적 단위 함수라 경계 프로브가 가능하고, 결과는 기존 ANY 경로(영역·cells·유효 방향·탈출 검증·스냅샷 고정)를 그대로 지난다. 예고 중 재선택이 없다(PrepareAttack 1회). QA7 경계값·600/700표본 분포·플레이어 위치 무관·예고 뒤 이동/팝업에도 영역 불변 PASS.
- 판정 회귀: NEAREST·FIXED 경로 코드 불변. QA7 parry.any(Pos1·2·3)·parry.left/right(2칸 중간 착지·복귀 뒤 그로기·hit) PASS. NORMAL·GUARD 유형은 실제 데이터에 없어 시험 데이터 근거로만 확인(Plan 허용).

#### V11-F11 대조
- 가드+SPECIAL만 새 종류 UNGUARDABLE(rate 1, success false)로 갈린다. 결과 종류를 읽는 곳을 Grep으로 다시 확인했다: ResolveAttack의 RecordDefense(성공 아님·nativeHit 없음이면 EVADE)·JUST·PARRY 분기, Monster_Attack의 PARRY 분기, 로그, HUD. UNGUARDABLE은 슬로우·반격·그로기 어느 분기에도 걸리지 않고 범위 밖이면 "회피"로 대체된다. 피해 계산(ResolveIncomingDamage = floor(damage×rate))은 바뀌지 않아 원래 피해다. 문구 색은 기존 피격 색, 지속은 SetSignal 기존 규칙. .ui 무변경.
- QA7: 범위 안 "가드 불가" 12=HitEvent 12·약 1.0초, 범위 밖 "회피" 0, 무가드 "피격", 일반 가드 40%, 패링 늦은 가드 40%, 패링 성공 문구 유지 PASS.

#### 범위 밖 변경 없음
- 규칙·수치: CombatRuleData·AttackSkillData·MonsterData CSV, IsInWindow·창 0.20·×0.40·반격·슬로우·그로기·AttackDamage·AttackInterval·점프 값 불변(diff에 없음). 기존 행의 패딩·높이·오프셋·선행 시간 유지, Weight만 사용자 결정대로 2로.
- .ui·.map·.model·.codeblock·.userdataset 변경 없음. 3단계·V11-F07(수치 DataSet화)·§18(머쉬맘 리소스·이름 변경, 모델·OrangeMushroomAttack·modelId castleenemy 그대로) 착수 없음. §18은 Plan에 후보 등록만 있고 구현 승인 전 상태로 적혀 있다.

#### QA7 시험값 한계가 판정에 미치는 영향
- 창 3.0(실제 키 시험)·반격 8초: Play 내부 rules 캐시만 바꿨고 재Play에서 기본값 복귀를 확인했다. 이번 diff는 IsInWindow와 창 값을 건드리지 않았으므로 넓힌 창은 결과 종류·방향·속성 분기 검증에 충분하다. 0.20초 경계 자체는 이번 변경 경로 밖이라 재시험이 필요 없고, 손 타이밍 체감만 사용자 V11로 남는다.
- H1 해제 시점을 `ReleaseHeldState`(키 해제 핸들러가 부르는 같은 함수) 호출로 대체: 결과는 판정 순간 콜라이더와 영역의 겹침(서버 네이티브 판정)으로 정해지므로 규칙 판정에는 충분하다. 실제 손으로 떼는 시점의 난이도만 사용자 몫이다.
- 반격 소비는 입력 수락 지점 호출(논리 경로)로 확인했다. 반격 소비 코드는 이번 변경 밖이다.
- 시험 행의 TelegraphLeadSec(0.6~6.0)은 Play 내부 값이다. 실제 데이터 0.5에서의 반응 여유는 사용자 V11이다.

#### H1 결론
- 규칙대로 동작한다. 판정 순간 겹치면 HIT·원래 피해, 안 겹치면 EVADE·0이며, 겹치지 않는데 피해가 난 사례가 없다. R02 결함 아님. 사용자 결정(범위 밖 회피 0 유지)과 맞고 코드·입력 규칙은 바꿀 필요가 없다.
- 체감 참고(사용자 V11 평가 대상, 결함 아님): QA7 측정상 끝 칸 홀드 중 special.random이 그 칸에 오면 예고 남은 시간 약 0.37초 이상에서 떼야 피하고 약 0.29초 이하이면 맞는다(H1b-1 겹침 여유 0.04). 실제 선행 0.5초에서는 떼는 반응 여유가 짧다. 1/7 × 1/3 확률로만 생기는 경우다.

#### clear_logs 확인
- coder 절과 QA7 절 모두 maker_clear_logs 미호출을 적었고 run 235·238도 같다. QA7이 coder 시각대(19:36~19:40) 경고·LEA-3051을 그대로 읽어 구분한 기록은 로그가 지워지지 않았다는 정황과 맞다. reviewer는 Maker 로그를 직접 보지 않았다.

#### 미커밋 문서 대조
- GameDesign §4.2·§5·§8 미커밋 diff: 현재 상대=1번 마을(헤네시스) Stage 10 최종보스 머쉬맘, 현재 구현은 주황버섯 리소스, 리소스 교체·이름 변경은 §18 다음 회차, 일반 몬스터 주황버섯·초록버섯은 §5대로 남음, 마을 표기 "1번 마을(헤네시스)", 중간보스 미정. run "2026-11-03 일시정지"·"재개" 절의 사용자 말과 일치한다. 규칙·수치 변경 없음.
- 로드맵 미커밋 diff: 같은 내용과 §18 후보·6단계 일반 몬스터 질문 절차. 일치한다.
- 비차단 메모: (1) GameDesign §4.2 "보라 세 가지가 나머지를 같게 나눈다"는 planner 기본안(Plan §17·run 220)인데 "사용자 결정" 문장 안에 있다. 이 문장은 이번 diff 이전부터 있던 것이며 사용자 V11 때 확인하면 된다. (2) 로드맵 "다음 재개 지점"과 Plan §17 상태 칸이 "reviewer 대기"로 남아 있다. 회차 종료 정리 때 planner·메인이 맞춘다. (3) run 232는 planner 문서를 coder 로컬 커밋에 묶는다고 적었지만 5c4eda3에는 Plan·WR만 들어 있고 GameDesign·로드맵은 아직 미커밋이다. 회차 종료 커밋에 넣어야 한다.

#### NOT_RUN (PASS로 세지 않음)
- 사람 육안(die 모습·"가드 불가" 문구·특수 칸 구별), 0.20초 손 타이밍·실제 키 해제 타이밍, CSV 파일을 바꿔 Refresh로 반영하는 시험, 실제 마우스·터치 팝업 클릭·실기기, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출.

#### 다음 행동
1. 메인: run 대상 버전에 5c4eda3 커밋 트리 9208e0aa…da79 / 작업 트리 fdca556d…ee80과 이 판정 WAITING을 적는다. CLAUDE.md 회차 단위 기준에 따라 회차 종료 커밋에 QA7 절·이 리뷰 절·Plan §17 상태·미커밋 GameDesign·로드맵을 넣고, Maker 재저장 3경로는 넣지 않고 사용자에게 알린다. push 전 비밀값·개인정보 검사는 메인 몫이다.
2. 사용자 V11 확인(아래).
3. planner(문서만, 비차단): Plan §17 상태 칸·WR 머리·로드맵 재개 지점을 리뷰 WAITING과 사용자 V11 대기로 맞춘다. 규칙·수치·기준은 바꾸지 않는다.
4. coder/tester: 지금 할 일 없음. §18은 사용자 재개 지시와 §18 질문 답 뒤에 시작한다.

#### 사용자 V11 확인 항목
- HP 0 뒤 die 모습이 사망 경로와 관계없이 유지되는지(팝업 열고 닫은 뒤 포함).
- 보라 중심 4패턴과 특수 1칸 무작위의 난이도·구별, 특수 비중 약 1/7과 보라 셋 2:2:2 비중의 체감.
- 특수 가드 때 "가드 불가" 문구가 보이고 이해되는지.
- 범위 밖에서 시작한 저스트 인정 체감: 특수 칸이 다른 칸일 때 그 칸에서 멀어지는 방향으로 움직이면 위험 없이 저스트(슬로우·반격 ×2.2)가 된다. planner 해석이며 너무 쉬운지 판단이 필요하다.
- 끝 칸 홀드 중 그 칸 특수가 오면 짧은 반응 시간 안에 떼야 피하는 점(H1 체감).

### 2026-11-03 독립 리뷰 — V11-F08·F09 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절(2026-11-03 V11-F08·F09)과 QA6의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git diff·소스 대조, node 스크립트(작업 디렉터리 밖 임시 스크립트)의 지문 재계산, ModelBuilder 읽기와 userdataset JSON 비교뿐이다.
- 검토 버전: coder 커밋 a921c76(기준 b89de46), QA 커밋 5a6ec07. V11-F06 절 manifest 54행을 같은 계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)으로 재계산했다. b89de46 = b985aa4b…4dbf(표 54행 개별 해시 0건 불일치), 작업 트리 = **377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363**(coder·QA6 기재와 일치, coder가 적은 변경 6경로 개별 해시도 일치). 커밋 트리 자체(a921c76 = 5a6ec07 = HEAD)는 38e7aa22e05a0a71cc90ca6680278f4352315788cedbfabc7256e4d44dd0ba53이다. b89de46→a921c76 제품 변경은 mlua 3개(AttackAreaMarkComponent·MonsterStunComponent·CombatInputController)뿐이고, a921c76→작업 트리 차이는 미커밋 Maker 재저장 3경로뿐이다. a921c76..HEAD는 run·Plan·WR 문서만 바뀌었다(QA6 제품 무수정). .codeblock·.ui·.map·.model·CSV 변경 없음. 검토 시 git status는 그 3경로(M)뿐.
- 판정: **WAITING**. 새로 고칠 결함 없음(CHANGES_REQUIRED 없음). F08·F09의 AI 측 근거(코드 대조·coder 실측·QA6 서버/클라이언트 SpriteRUID 시계열·스크린샷 픽셀)는 Plan §16 완료 기준을 충족한다. 남은 필수는 사용자 V11 육안 확인이다. 이 판정은 2단계 완료·3단계 진행 승인이 아니다.

#### 미커밋 Maker 재저장 3경로 — 의미 차이 없음, 커밋 제외 타당
- AssistModel·AttackSkillData userdataset: JSON 전체 비교에서 차이는 `CoreVersion` 26.7.0.0 → 26.10.0.0 한 값뿐이다.
- 주황버섯 모델(ModelBuilder.read, HEAD 대 작업 트리): 컴포넌트 14개 목록 동일, properties·children·이름·id 동일, ActionSheet 6키(move·stand·jump·hit·die·stun, stun=hit RUID aec950…) 동일. 값 차이는 (1) HitComponent.ColliderOffset x 0.045 → 0.0449999869(float32 표기, 같은 값), (2) 스크립트 컴포넌트 값 17개 새 직렬화 — MonsterStateControl·MonsterAttackComponent·MonsterDefenseComponent·MonsterStunComponent·OrangeMushroomAttack의 Enable=true와 attackTimer 0·isDefending false·isStunned false·stunDeadline -1·scheduledId 0·executionId 0·Home (0,0)·HomeCaptured false·JumpActive false·JumpStartX/TargetX/StartTime 0. 모두 해당 .mlua 선언 기본값과 같다(Grep 대조). (3) 값은 같고 형식 버전 문자열만 바뀐 항목 7개. 런타임 의미 차이 없음.
- 판단: coder가 이 파일들을 쓰지 않았고(F08은 .mlua로 해결) 사용자 V11 중 Maker 저장으로 보이므로, 제품 커밋에 섞지 않은 처리는 CLAUDE.md "사용자가 직접 바꾼 파일은 범위가 아니면 섞지 않고 알린다"에 맞다. QA6는 이 3경로가 포함된 작업 트리를 시험했지만 의미 차이가 없어 근거가 커밋 트리(38e7aa22…)에도 그대로 적용된다. 이 리뷰의 [review] 커밋에도 넣지 않는다. 처리(별도 커밋 또는 유지)는 사용자에게 알리고 사용자가 정한다. 참고: 스크립트 기본값이 모델에 고정됐으므로 이후 해당 .mlua 기본값을 바꾸면(예: V11-F07 DataSet화) 모델 값이 우선한다. 지금 값은 모두 기본값과 같아 영향 없음.

#### V11-F08 대조 (MonsterStunComponent.SetStunned)
- 원인 근거와 수정의 일치: coder 실측은 "ActionSheet stun 키·RUID는 정상이고 ACE clip=stun도 오지만 hit가 비반복 클립이라 한 번 재생 뒤 렌더러 기본 표시(SpriteRUID=stand, 복귀 완료 CompleteMotion이 씀)로 돌아간다"이다. 수정은 그로기 동안 서버 SpriteRUID를 ActionSheet "stun"(=hit RUID)으로 고정하는 것이라 원인과 직접 맞는다. 이미 있던 MonsterAttackMotion.SetVisualClip(ActionSheet 값 재사용)만 써서 새 RUID·Sync 값·모델 변경이 없다. 변경은 SetStunned 한 메서드 12줄이다. 최소 범위로 판단한다.
- 서버 상태·HIT·수치 불변: Monster_Stun·MonsterHealthComponent·MonsterManager·HitComponent 경로 byte 불변. SetStunned는 isStunned 쓰기 순서를 그대로 두고 표시 클립만 덧붙였다. ApplyGroggy·BeginStunTimer·OnUpdate 만료·HandleHitEvent의 HIT 진입 조건(STUN 제외)은 diff에 없다. QA6에서 STUN 유지·GroggyRemaining 감소·HP=HitEvent=숫자 대표 PASS.
- 정리 경로 잔존: 호출처 5곳을 확인했다. (1) Monster_Stun.OnEnter → stun, (2) OnExit(자연 만료·ClearOpponentExecution의 IDLE 전환) → stand, (3) ApplyDamage 사망: IsDead=true 뒤 SetStunned(false) → die, 이어지는 DEAD 전환의 OnExit는 wasHeld=false라 아무것도 쓰지 않아 die를 덮지 않는다, (4) MonsterManager.ClearOpponentExecution → stand(사망이면 die), (5) MonsterStunComponent.OnMapLeave/OnEndPlay 서버 분기 → stand. 그로기가 아니던 SetStunned(false)는 즉시 반환해 공격 취소·정리 때 jump/stand를 덮지 않는다. 그로기 중 ApplyGroggy 재호출은 같은 RUID를 다시 쓴다(QA6 연장 그로기에서 hit 유지 확인). QA6가 상대 교체·DoSpawn·OnMapLeave 직접 호출·Stop 두 경로를 실행했고 잔존 없음(맵 이탈은 논리 경로, 실제 맵 이동 NOT_RUN).
- QA6 근거 수준: 세 조건 모두 서버·클라이언트 SpriteRUID 시계열과 스크린샷 픽셀(그로기 구간 vsHit 0~8.8, vsStand 73 이상)로 판정했고 이벤트 로그만으로 PASS하지 않았다. Plan §16 완료 기준("실제로 보이는 표시")과 맞다. 한계(클라이언트 실제 클립 이름 API 없음, 스크린샷 약 0.18초 간격, 정렬 ±0.15초, 사람 육안 아님)는 QA6에 그대로 적혀 있다.

#### V11-F09 대조
- 문구: CombatInputController에서 예고 문구 계산 블록만 지우고 telegraphText에 항상 빈 문자열을 쓴다. .ui 엔티티·바인딩 유지(.ui 무변경). defenseText(저스트 회피 성공·패링 성공·가드·피해 경감·회피·피격)·counterText(반격 준비)·effectText(상대 그로기·슬로우)의 문구·색·지속 코드는 byte 불변. 사용자 결정 "결과·상태 문구는 그냥 두는 걸로"와 맞다.
- 색·알파: NORMAL (1, 0.85, 0.4) / SPECIAL (1, 0.43, 0.36) / PARRY (0.88, 0.65, 1), 알파 CellAlpha 0.45 — Plan 표·이전 문구 색과 같다. 기존 빨강(1, 0.12, 0.12)은 남지 않았고 투명 기본색만 (1,1,1,0)으로 바뀌었다(알파 0이라 화면 차이 없음).
- 켜고 끄는 시점: 켜짐 판단은 그대로 서버 TelegraphCells의 칸 문자이고, 숨김 경로(대결 없음·상대 없음·OnMapLeave)는 기존 호출에 속성 인자만 더했다. TelegraphAttribute는 PrepareAttack에서 TelegraphCells 바로 앞에 같은 실행으로 설정된다(MonsterAttackComponent 140·142행), MonsterAttackComponent 무변경 조건 충족.
- 속성 미상 숨김: 세 값이 아니면 칸을 숨기고 0.25초를 넘기면 `[VRF]` 한 번(Maker Play만). 캐시는 켜짐과 속성을 함께 비교한다. QA6 "XYZ" 숨김·같은 칸 NORMAL→SPECIAL→PARRY 갱신 PASS.
- 가드형: 주황버섯 데이터에 없고 GUARD 처리는 바뀌지 않았다. 색은 속성만으로 정해지므로 가드형도 속성색이다. QA6 색값 픽셀 근거는 normal.left 단일 행에 속성을 직접 바꾼 시험값이며, Plan이 말한 "가드형(111) 시험 행"은 coder 기본 검증에서만 실행됐다. 색 결정 코드가 칸 집합·대응 유형을 보지 않으므로 같은 근거로 본다(공백 아님).
- 잔여 위험(비차단, 결함 아님): 공격 종료 뒤 TelegraphAttribute가 이전 값으로 남는다(기존 동작). 다음 공격에서 칸 동기가 속성 동기보다 먼저 클라이언트에 닿으면 이전 속성색이 1프레임 보일 수 있다. 서버는 속성을 먼저 쓰고 QA6에서 관측되지 않았다. 사용자 V11에서 색 깜빡임이 보이면 공격 종료 시 속성 초기화를 후보로 둔다.

#### 범위 대조
- 규칙·수치(창 0.20, 가드 ×0.40, 반격 ×2.2, 슬로우, 그로기 1.5, AttackDamage 12 등)·9패턴·Weight·CSV·.ui·.map·.model 변경 없음. 3단계·V11-F07(몬스터 수치 DataSet화) 착수 없음. 요구가 Plan §16에서 빠지거나 늘어난 곳은 없다.
- Plan §16 NOT_RUN 공백(2칸 패턴 복귀 중 팝업 V07·Stop 재Play V08)은 QA6에서 parry.left·parry.right로 메워졌다. 2026-11-03 F01~F06 리뷰가 남긴 비차단 공백은 해소로 본다.

#### tester 관찰 분류
- **일반 사망(IDLE·공격 중) 화면 stand 유지 → CombatCore-REV-F02로 추적(결함 후보, 이번 변경 범위 밖, 사용자 범위 결정 필요, 비차단).** 근거: coder 기준선(b89de46)과 QA6 재현 모두 DEAD에서 서버 SpriteRUID가 stand로 남고 ACE clip=die는 한 번만 나온다. 원인은 F08과 같은 구조(die도 비반복 클립이라 한 번 재생 뒤 렌더러 기본 표시로 돌아감)로 보이며, 몬스터 재생성 경로가 없어 HP 0 상태의 몬스터가 stand로 계속 보인다. a921c76이 만든 회귀가 아니라 이전부터의 동작이지만, 이번 변경으로 그로기 중 사망만 die가 고정돼 두 경우의 표시가 갈라졌다. Plan §7 V06 "기존 hit/die 가시성 보존"·V11 "die 구별"·CF-F07 피격/die 연출과 직접 닿으므로 V11 주관 평가로만 두지 않고 ID로 추적한다. 다만 수정은 §16 승인 범위(그로기 표시) 밖이고 Plan §16 "바꾸지 않는 것"의 DEAD 흐름 근처를 건드리므로 사용자가 (a) 2단계 V11 회차에 포함(예상 범위: DEAD 진입 시 기존 SetVisualClip("die")로 표시 고정, 서버 상태 흐름·수치 불변, .mlua만) 또는 (b) CF-F07·이후 몬스터 모션 단계로 미룸을 정한다. planner가 사용자 답을 받아 Plan에 기록한다.
- 그로기 만료와 타격이 겹칠 때 0.5초 HIT(stand 표시): 서버가 STUN→IDLE→HIT로 기존 HIT 규칙대로 지나간 결과다. F08 완료 기준(그로기 구간 hit)과 충돌하지 않는다. HIT 클립도 같은 비반복 구조라 짧게만 보이는 것은 REV-F02와 같은 표시 계열이므로 REV-F02 결정 때 함께 볼 수 있다. 별도 ID 없음.
- 생성 직후 0.3초 연출 프레임: DoSpawn 직후 네이티브 생성 표시로 보이며 이번 변경과 무관. 결함 아님.
- TelegraphAttribute 잔존: 이전 리뷰 분류 유지(판정이 읽지 않음). 이번 F09로 칸 색이 이 값을 읽게 됐지만 칸이 꺼진 동안은 보이지 않는다. 위 잔여 위험 1프레임만 남는다.

#### clear_logs 확인
- QA6 절과 run 198행 모두 maker_clear_logs 미호출을 적었다. coder 절도 미호출을 적었다. reviewer는 Maker 로그를 직접 볼 수 없으므로 담당 기록과 메인 확인을 근거로 한다. QA6가 coder 시각대 로그(14:38 LEA-2007)를 그대로 읽어 구분한 기록은 로그가 지워지지 않았다는 정황과 맞다.

#### NOT_RUN (PASS로 세지 않음)
- 사람 육안: 그로기 hit 모션, 노랑·적색·보라 칸 가독성과 색만으로의 속성 구별, 색약 접근성, 별·접촉 파티클.
- 0.20초 창 손 타이밍, V09 CSV 변경 반영, 실기기·터치(좌·우 버튼 전체 면적), 플레이어 사망 중 칸 정리, 실제 다른 맵 이동, V12 외부, CF-F07 연출.

#### 다음 행동
1. 메인: run 대상 버전을 a921c76(커밋 트리 38e7aa22…, 작업 트리 377a5ccc…)과 이 판정 WAITING으로 갱신하고 이 절만 `[CombatCore][review] WAITING`으로 커밋한다. 미커밋 Maker 재저장 3경로는 넣지 않고 사용자에게 알린다.
2. 사용자 결정: CombatCore-REV-F02(일반 사망 die 미유지)를 V11 회차에 포함할지 미룰지.
3. planner(문서만, 비차단): Plan §16 상태 칸 "reviewer 대기" → 리뷰 WAITING, REV-F02 추적 위치, WR 머리 "현재 재개 지점"(b89de46 기준으로 남음)과 로드맵 "다음 재개 지점"(F08·F09 미반영) 동기화. 규칙·수치·검증 기준은 바꾸지 않는다.
4. coder/tester: 지금 할 일 없음. 사용자가 REV-F02 포함을 정하면 그 ID만 coder→tester→reviewer로 돈다.
5. 사용자 V11(PC·모바일 직접): 그로기 동안 hit 모션이 실제로 보이는지(피격 없음·그로기 중 공격·슬로우 겹침), 예고 문구 없이 칸 위치·색만으로 방향·속성(일반 노랑·특수 적색·패링 보라)을 구별할 수 있는지와 가독성, 공격 사이 칸 색 깜빡임 여부, 결과·상태 문구 유지 확인, 일반 사망 때 몬스터 표시(REV-F02). 이전 리뷰의 V11 항목 중 (1)·(3)의 문구·빨간 칸 평가는 Plan §16대로 이것으로 대체되고 나머지는 유지된다.

### 2026-11-03 독립 리뷰 — V11-F01~F06 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 1447ff8 대상 이전 reviewer 호출은 기록 없이 중단돼 F01~F05 몫까지 이번에 한 번에 판정했다. 아래 런타임 근거는 coder 개발절(2026-11-02 V11, 2026-11-03 F06)과 QA4·QA5의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: coder 커밋 b89de46 / 54경로 Bundle b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf. reviewer가 F06 절 manifest 54행을 node 스크립트(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)로 작업 트리·b89de46·a43b1b5(QA5)·HEAD에서 재계산해 54/54·Bundle 동일을 확인했다. 같은 manifest로 1447ff8·f7b3244(QA4)는 d2b57802…0fbb, a289eb7·6614b20은 1ac324e6…9de4가 재현된다. 1447ff8..b89de46에서 바뀐 manifest 경로는 coder 기재대로 10개다. 검토 시 git status 깨끗.
- 판정: **WAITING**. 새 결함 ID 없음. F01~F06의 AI 측 근거(코드 대조·QA4/QA5 수치·로그)는 승인 범위를 충족한다. 남은 필수는 사용자 V11 직접 확인, CF-F07 실제 연출, V12 외부 환경이다. 이 판정은 2단계 완료·3단계 진행 승인이 아니다.

#### 같은 버전 확인 — F01~F05 근거가 F06 변경 뒤에도 유효한가
- QA5(b89de46)에서 다시 확인됨: F01 칸 표시(1칸·2칸·ANY 고정 칸), F02 대표(ANY 패링→복귀→Home x=3.0 STUN→약 1.5초→IDLE), F03 접촉 파티클 로그 1회, F05 전체, V02·V04~V08·V10 대표.
- QA4(1447ff8)에서만 확인되고 이월된 것과 이월 근거:
  - F04 STUN hit 클립·사망 die 우선: 주황버섯 model·Monster_Stun·MonsterStunComponent 해시가 두 manifest에서 같고, 아래 구조 비교에서 model 의미 차이도 0이다. 이월 타당.
  - F03 별 크기·높이, 파티클 재생 경로: MonsterStunComponent byte 불변. 이월 타당(육안은 원래 NOT_RUN).
  - F02 복귀 중 팝업·피격·슬로우·사망·Stop 조합: **재확인 공백(차단 아님)**. Monster_Attack은 모션 호출 1줄만 바뀌었고 OrangeMushroomAttack의 복귀(PerformReturnMotion→Home)·CompleteMotion·CancelMotion·OnUpdate는 byte 불변이다. 다만 2칸 패턴의 복귀 출발점이 착지 x(±0.75)로 바뀌었고 QA5의 복귀 대표는 ANY(1칸) 1건이다. 같은 시계·같은 상태 경로라 위험은 낮다고 판단하며 필수 재시험으로 두지 않는다. tester를 다시 부를 일이 생기면 함께 볼 조건: 2칸 패턴 패링→복귀 중 팝업 정지·재개, 복귀 중 Stop→재Play 기본값.
- .codeblock: 1447ff8..b89de46에 변경 없음. MonsterAttackMotion·OrangeMushroomAttack .codeblock에는 메서드 이름이 들어 있지 않아(Grep 0건) PerformAttackMotion 서명 변경과 무관하다. QA5 build 로그 80건 오류·경고 0.

#### 구조 파일 의미 비교 (ModelBuilder/MapBuilder 읽기, node)
- 주황버섯 model a289eb7→b89de46: 차이 2개뿐. ActionSheet에 `stun` = aec9504d5dc24aceb5646b79d30abad4(hit와 같은 RUID) 추가, 그 값의 ValueType 형식 버전 문자열 26.7.0.0→26.10.0.0. 1447ff8→b89de46 차이 0. 줄 끝 CRLF→LF는 의미 차이 아님. F04 의도 범위 안이다.
- map01 a289eb7→1447ff8: BattlePosMark1~3 엔티티 3개 추가뿐(modelId attackareamark, x -1.5/0/1.5, y 0.98, Scale 25×25×1, PixelRenderer, AttackAreaMarkComponent CellIndex 1/2/3). 기존 엔티티 의미 차이 0. 1447ff8→b89de46(Maker 재저장): 같은 세 엔티티의 Transform에서 Scale `$type` 표기 제거와 기본값 Rotation (0,0,0)·ZRotation 0 명시뿐. 값 변화 없음.
- AttackAreaMark model은 1447ff8에서 새로 생겼다(a289eb7에 없음). 1447ff8→b89de46 의미 차이 0. Components는 Transform·PixelRenderer·script.AttackAreaMarkComponent, Values는 Scale 하나.
- MapObjects.directory도 1447ff8에서 새로 생겼고 b89de46에서는 StudioVersion "" → "0.1.0.0" 한 줄만 바뀌었다.
- 결론: 구조 파일 변경은 F01·F04 의도 범위와 Maker 재저장 표기 차이뿐이다. raw JSON 편집이나 수정은 하지 않았다.

#### F06 승인 범위 대조 (Plan §15·사용자 결정 1~4)
- ANY 조준: PrepareAttack에서 FindNearestCell로 예고 시작 순간 최근접 칸을 한 번 고정한다(동률 순서 2→1→3, epsilon 1e-6, 추적 없음). 유효 방향은 Pos2 좌·우, Pos1 오른쪽, Pos3 왼쪽(targetCell ≥2 → LEFT, ≤2 → RIGHT)이다. 기존 LEFT/RIGHT 탈출 검증은 그대로이고, ANY는 각 유효 방향 도착 x ± (|offset| + halfWidth)가 [minX, maxX] 밖인지 따로 검사한다. ResolveAttack은 snapshot.validDirs를 EvaluateDefense에 넘기고, 회피 분기는 `validDirs[EvadeDirection] == true`와 창 안 시작일 때만 JUST다. 가드 분기는 byte 불변이다. QA5의 Pos1/2/3·동률·경계·이동 뒤 조준 불변·중앙 복귀 비저스트 근거와 일치한다.
- 2칸 중앙 착지: OrangeMushroomAttack.PerformAttackMotion(cells, minX, maxX)만 영역 중앙 `(minX+maxX)/2`를 부모 로컬 x로 바꿔 JumpToLocalX한다(NaN·역순이면 -1). 공통 층의 Monster_Attack·MonsterAttackMotion 기본 구현은 칸 문자열과 x 범위만 전달·반환 0이다. 착지 위치 규칙은 주황버섯 모션에 한정되고, 이후 보스 모션이 같은 인자로 다른 착지를 정할 수 있다. 공통 snapshot의 landing 필드와 CSV LandingAnchor는 제거됐다.
- Weight: CSV 필수 열, 로더가 ≤0·비수치를 거부(전체 카탈로그 거부·경고 1회). SelectPattern은 r = unit × 합계를 CSV 행 순서로 누적 비교하고 마지막 행을 끝값 처리한다. 9행 모두 1이라 균등이다. QA5의 거부 시험과 900회 선택 분포와 일치한다.
- 가드형 제외: CSV에서 normal.guard·parry.guard 2행이 빠졌고 GUARD 처리 코드는 남아 있다. QA5의 가드형 확인은 Play 내부 메모리 시험 행으로 "시험 데이터 근거"라고 표시돼 있어, 실제 데이터 PASS로 섞이지 않았다.
- 바뀌지 않아야 할 것: CombatRuleData·AttackSkillData CSV는 a289eb7..b89de46 변경 없음(CSV 변경은 MonsterAttackPatternData뿐). 패턴 CSV의 padding 0.5·height 1·offset 0.4·lead 0.5, 기존 LEFT 2-3·RIGHT 1-2 앵커는 그대로다. JumpHeight 0.8·JumpDuration 0.5와 공격 수치·창 0.20·가드 0.40·반격·슬로우·그로기 수치를 바꾸는 diff는 없다. F06 변경은 승인된 1~4 범위를 넘지 않는다. .ui·.model·.map 변경은 Maker 재저장 3개 파일뿐이다.

#### QA 관찰 분류 (모두 결함 아님, 새 ID 없음)
- ANY 끝 칸 문구 "[좌·우]"와 실제 한 방향 차이: Plan §15가 허용한 일반형 표현이고, 칸 표시가 조준 칸을 알린다. 사용자 V11의 가독성 판단 대상. 바꾸려면 planner 문구 결정이 필요하다.
- 끝 칸 홀드 중 새 저스트 불가, 복귀 중 반대 입력 무시: §15 설계와 기존 이동·복귀 잠금(입력 예약 없음) 그대로다. 난이도는 V11 판단.
- TelegraphAttribute 잔존: 공격 종료 뒤 마지막 값이 남지만 Response가 비어 HUD에 나오지 않는다. 이전 버전부터의 동작이며 판정이 이 값을 읽지 않는다. 정리 여부는 후속 선택 사항.
- UI 뒤·앞 버튼이 시뮬레이터에서 가장자리(x=805/1115)에서만 눌림(QA4): 제품 결함인지 시뮬레이터 좌표 재매핑인지 근거가 없다. F06은 .ui·버튼 코드를 바꾸지 않았다. 사용자 실기기 V11에서 전체 면적을 확인한다. 실기기에서도 재현되면 그때 결함으로 등록한다.
- 복귀·그로기 중 피격 시 클라이언트 로컬 HIT·hit 클립(QA4): 서버 상태(ATTACK/STUN)와 규칙은 정상이다. 이번 변경 이전부터 있는 클라이언트 표시 구조이고, 그로기 중에는 RUID가 같아 화면이 같다. 복귀 중 jump→hit 전환이 거슬리는지는 V11·CF-F07 연출 판단 대상.
- 플레이어 사망 직후 HP 문자 음수 가능성: 2026-11-02 리뷰 분류 유지(결함 아님, 3단계 계획 후보, V11에서 함께 확인).

#### QA4 계약 위반 기록
- QA4 tester가 시작 직후와 회차 사이에 maker_clear_logs를 호출해 이전 Play의 normal 로그 36건을 보존 확인 없이 지웠다(build 로그는 유지, QA4 절 시험 오류 (4)(5)·run 144행). 사용자 로그 무단 삭제 금지 위반이다. 메인이 사용자에게 보고했고 QA5 지시에 금지를 명시했으며, QA5는 미호출을 기록했다(QA5 절·run 167행).
- 판정 영향: 지워진 것은 이전 Play 로그이고, QA4 판정에 쓴 근거는 지운 뒤 새로 실행한 회차의 로그다. 결과를 잃은 J2는 새 몬스터로 다시 실행한 결과만 썼다. QA4 PASS는 무효로 보지 않는다. 다만 지워진 36건의 내용은 복구·확인할 수 없다.

#### NOT_RUN (PASS로 세지 않음)
- 실제 입력으로 0.20초 창 안 손 타이밍 저스트·패링 성공(실제 키 성공은 시험 한정 창 8.0/0.9, 창 0.2 안은 서버 프로브), 0.200 등호 경계.
- V09 CSV 파일 변경→Refresh→Play 반영(시험 행 ValidateRows로 대체).
- F04 클립 재계측(QA5), 그로기 중 hit 클립 재생 재시작 여부(QA4).
- 육안 전체: 별 크기·가시성, 접촉 파티클, 1칸 공격 구별, 2칸 중간 착지 모션, 칸 색·가독성.
- 위 F02 복귀 중 조합의 2칸 패턴 재확인.
- V11 사용자 직접, CF-F07 실제 연출, V12 외부(두 사용자·비전투 몬스터·다른 맵).

#### 다음 행동
1. 메인: run 상태·대상 버전을 b89de46 / b985aa4b…74dbf와 이 리뷰 판정 WAITING으로 갱신한다. 이 절을 `[CombatCore][review] WAITING`으로 커밋한다.
2. planner(문서만, 차단 아님): 이 WR 머리 "현재 재개 지점"(6614b20 기준으로 남음)과 Plan 머리·§15 끝의 "다음 흐름"을 리뷰 완료·사용자 V11 대기로 맞춘다. 규칙·수치·검증 기준은 바꾸지 않는다.
3. coder/tester: 지금 할 일 없음. V11에서 새 요구나 실기기 재현 결함이 나오면 해당 ID만 다시 돈다.
4. 사용자 V11(PC·모바일 직접):
   - 1칸(ANY) 공격이 칸 표시로 구별되는지, "[좌·우]" 문구가 끝 칸에서 헷갈리지 않는지, 끝 칸 홀드 중 대응 불가 난이도.
   - 2칸 공격의 두 칸 중간 착지 모션 모양.
   - F01 빨간 칸 표시의 색·가독성, F02 복귀 후 그로기 흐름, F03 별 크기·높이와 패링 접촉 파티클, F04 그로기 hit 모션.
   - 복귀 중 피격 시 jump→hit 클립 전환이 거슬리는지.
   - 좌·우 UI 버튼 전체 면적이 눌리는지(실기기·터치).
   - 0.20초 창 손 타이밍 체감, 패턴 선택(Weight 균등) 체감.
   - 플레이어 사망 직후 HP 문자 표시.
5. 외부 대기: V12, CF-F07 연출, 기존 외부 후속 ID는 기존 추적 유지. P01b~P06 🟡 유지, 3단계 자동 시작 없음.

### 2026-11-02 독립 리뷰 — WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절과 tester QA3의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: coder 커밋 6614b20 / 52파일 Bundle 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4. reviewer가 2026-11-02 manifest 52행을 작업 트리·6614b20·13fe548 각각에서 byte SHA-256으로 재계산해 52/52 일치·Bundle 동일을 확인했다. 6614b20~1(eedeefb)에서는 두 파일만 달라 이전 Bundle e8a20728…a49가 재현된다. eedeefb..HEAD 제품 변경은 아래 두 .mlua뿐이고 나머지는 run/Plan/WR/EnvGuides 문서다. 두 .codeblock은 내용 변경 없음(Refresh 시각만 갱신).
- 판정: **WAITING**. CombatCore-REV-F01은 해소됐다(코드·QA3 근거 충족). 현재 승인 범위의 AI 측 필수 근거는 충족됐으나 사용자 직접 확인 V11과 CF-F07 실제 연출 평가, V12 외부 환경이 필수로 남는다. DOC-01은 planner 문서 정리로 남는다(제품·재검증 불요). 이 판정은 단계 완료·3단계 진행 승인이 아니다.

#### CombatCore-REV-F01 — 해소 확인
- 실제 소스: MonsterAttackComponent.mlua:134 `ResolveIncomingDamage(self.AttackDamage, attacker)`로 number 원값을 넘기고, PlayerHealthComponent.mlua:38 인자가 `number damage`, :45 `math.max(0, math.floor(damage * result.rate))`가 유일한 내림이다. D02 "합성 뒤 정수 내림·음수 0 제한"과 일치한다. 호출자는 :134 하나(Grep), 반환 integer·@ExecSpace("ServerOnly")·native CalcDamage 서명(@ExecSpace 없음) 유지, AttackDamage는 PrepareAttack에서 finite·비음수 검증 그대로다.
- 범위 밖 변경 없음: diff는 두 파일 각 1줄이며 EvaluateDefense/IsInWindow·PlayerCombatComponent.CalcDamage(QA-F01 상한)·MonsterHealth·DataSet·기본 AttackDamage=12는 byte 불변이다.
- QA3 대응(2026-10-29 리뷰의 독립 재검증 항목): 12.7 무가드=12·특수 무가드=12·특수+가드 홀드=12, 일반 가드=5·실패 패링 가드=5(창 밖 두 시점+실제 DownArrow), 유효 패링=0·유효 저스트=0, 기본12 무가드12/가드4/특수+가드12/패링0/저스트0, QA-F01 HP5·Weapon10 처치 5/5/5·DEAD 1회, HP25 10·10·5 합25·후속 제외를 같은 Bundle의 native AttackFast→CalcDamage→HitEvent·HP에서 HP delta=TotalDamage=Damages 합계로 확인했다. 항목 누락 없음.
- 실제 입력 범위의 충분성: 이번 결함은 방어 판정 결과(rate) 뒤 합성·내림 위치뿐이며, 성공 rate=0은 창 폭과 무관하게 0으로 내림된다. .2초 창 경계 코드(IsInWindow)는 byte 불변이고 경계 직전/정확/안/공격시점/직후는 QA1 V03(당시 동일 함수 내용)의 근거 범위다. QA3는 (A) 서버 프로브로 .2창 안 시작(hit-.103s 패링, 잔여 .12s 이하 저스트)의 PARRY/JUST 0피해를, (B) 실제 DownArrow/RightArrow/LeftArrow로 입력→상태→판정→피해 경로를 확인했고 (B)의 성공 창 .9는 Play 내부 시험 값으로 명시·Stop 폐기·기준값 재확인됐다. REV-F01 수락에는 충분하다. 손 타이밍 .2초 성공의 체감·가독성은 AI로 대신하지 않으며 V11에 남는다. 실제 입력 저스트 성공은 범위 밖 이동이라 native 이벤트 없음(HP 0)이고 범위 안 JUST 0피해는 (A)가 덮는다.

#### 플레이어 쪽 남은 HP 상한 부재 — 결함 아님(범위 밖 관찰)
- 관찰: 플레이어 HP5에 12.7 무가드 → Hp 5→-7, delta 12, HitEvent 12, Damages 12, DEAD 1회(QA3). QA1 V08 특수12 HP5→-7도 같은 동작이다.
- 분류 근거: V02/R02의 문자 기준은 "최종 HP 감소=HitEvent 합계=피해 숫자, 네이티브 HP 한 번 적용"이며 플레이어 쪽은 PlayerComponent.Hp가 0에서 clamp되지 않아 세 값이 12로 일치한다. QA-F01은 MonsterHealth가 이벤트 뒤 0으로 clamp해 감소5≠이벤트10이 된 경우라 성격이 다르다. D02는 "합성 뒤 내림·음수 0"만 정하고 남은 HP 상한 규칙을 두지 않는다. 따라서 승인 요구상 결함이 아니고 새 ID를 만들지 않는다. 상한을 추가하면 새 규칙이 되어 승인 범위 밖이다.
- 남는 점(현재 진행 차단 아님): CombatHpBarController.mlua:26이 `tostring(math.floor(current))`라 사망 직후 플레이어 HP 문자가 "-7 / 최대"로 보일 수 있다(막대 비율은 :24에서 0 clamp). 실제 화면 관찰은 이번 근거에 없다. 표시를 0으로 맞출지·피해를 남은 HP로 상한할지는 사용자/planner 판단 사항이며, GameDesign §4의 "플레이어 HP 0이면 한 판 종료"·승패는 3단계 범위다. V11 평가 때 사용자가 확인하거나 3단계 계획에서 다룬다.

#### 이전 근거·미실시 표시 대조
- QA2(e8a20728…a49)·2026-10-29 리뷰·QA1(8be49440…e21)은 Plan §13·WR 머리·QA3에서 이전 버전 근거로만 표시돼 있고 이번 PASS로 다시 세지 않았다. QA3의 "나머지 V01~V12 회귀 재실행 안 함"은 두 파일 외 byte 불변을 근거로 명시돼 있다.
- 미실시가 PASS로 위장되지 않음: V11, CF-F07 연출, V12 외부(두 사용자·비전투 몬스터·다른 맵), 실제 mouse/touch, 손 입력 .2창 성공은 coder·QA3·Plan §13에 NOT_RUN/미완료로 남아 있다. 플레이어 사망 경계는 "경계만"으로 별도 표시됐다.
- 문서 불일치(DOC-01에 포함): Plan 머리 3행("갱신 2026-10-29… 독립 리뷰 남음")과 §8 167행("다음 담당 reviewer, QA2"), WR "현재 재개 지점" 10행(e8a20728 기준 reviewer 대기)이 현재 상태와 다르다. 2026-10-29 리뷰가 든 DevelopmentRoadmap.md:13·:45·:103, WorkRecords/README.md:58, ChatRoles/README.md:37(당시 :36) "WorkRecord 생성 예정"도 그대로다. run.md 15·18~21행(리뷰 결과 없음·대상 버전 e8a20728)은 메인 담당이다.

#### 다음 행동
1. planner(msw-planner): CombatCore-DOC-01 — 위 현황·날짜·버전·링크만 Plan/WR 원본에 맞춘다. QA-F01 과거 FAIL→QA2 PASS, REV-F01→QA3 PASS 연결, CF-F07 수치/연출 분리, P01b~P06 🟡 유지. 규칙·검증 기준·단계 순서 변경과 결과 전문 복제 없음. 제품·Maker 변경이 없으므로 coder/tester 재실행은 필요 없다.
2. 메인: run 상태·대상 버전 줄을 6614b20/1ac324e6…9de4와 이 리뷰 판정으로 갱신.
3. 사용자 V11: PC·모바일에서 예고 방향/속성·.20초 체감·저스트/패링/반격 준비·소비·슬로우/어지러움·피격/die·키/버튼/터치 혼합·화면 잘림·음향을 직접 평가. 이때 플레이어 사망 직후 HP 문자 표시도 보면 된다. 새 규칙·수치 요구가 생기면 관련 D/R/V만 planner로 재검토한다.
4. 외부 대기: V12 실제 두 사용자·비전투 몬스터·다른 맵 환경, CF-F03/CombatPause-F01 실제 맵 전환, 기기/음향·재시작·배포·성능 후속 ID는 기존 추적 유지. Plan/WR/run 보존, 3단계 자동 시작 없음.

### 2026-10-29 독립 리뷰 — CHANGES_REQUIRED
- 담당: /root/combat_core_reviewer_v2. coder_v4→tester_v2 실제 종료 뒤 별도 실행. Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음. 아래 런타임 근거는 해당 개발/QA 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: 52파일 Bundle SHA-256 e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49. reviewer도 manifest의 52/52 byte와 Bundle 일치를 확인했다. QA2는 같은 버전, 이전 QA는 당시 조건/무변경51파일 범위로만 유지됐다.
- 판정: **CHANGES_REQUIRED — CombatCore-REV-F01**. QA-F01 처치 상한 수정은 타당하며 해당 수치 재시험 PASS를 인정한다. 별개로 몬스터 기본 피해를 경감 전에 내림하는 기존 호출이 승인 D02/R02와 어긋나 coder 최소 수정·독립 재검증이 필요하다. 이 수정 뒤에도 V11·CF-F07 실제 연출·V12 외부 환경은 WAITING 항목이다.

#### CombatCore-REV-F01 — 몬스터 피해가 경감 전에 한 번 더 내림됨
- 요구: Plan D02/R02/V02는 기본 피해와 경감을 합성한 뒤 최종 피해를 정수 내림한다.
- 실제 소스: RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua:134에서 ResolveIncomingDamage(math.floor(self.AttackDamage), attacker)를 호출한다. RootDesk/MyDesk/Player/PlayerHealthComponent.mlua:38의 인자도 integer damage이며 :45에서 다시 math.floor(damage * result.rate)를 한다. AttackDamage는 number이고 PrepareAttack은 finite·비음수만 검증하므로 소수는 현재 허용된 입력이다.
- 재현 조건/기대·실제: 유효한 일반 또는 실패 패링 공격, AttackDamage=12.7, 가드 잔여율=.40. 승인 기대는 floor(12.7×.40)=5, 현재 코드는 floor(floor(12.7)×.40)=4. 이는 소스/산술로 확인한 결함이며 reviewer의 새 Maker 실행 결과로 표시하지 않는다. 기본12만 시험한 QA와 충돌하지 않는다.
- 최소 수정 범위: 원래 number 기본 피해를 최종 경감 소유자까지 보존하고 경감 합성 뒤 한 번만 floor한다. 위 호출자·메서드 인자 형식을 함께 맞추고 native CalcDamage 반환은 integer, HP 소유는 기존 PlayerComponent로 유지한다. 기본12·DataSet 규칙·새 스탯/치명타/피해 프레임워크를 바꾸지 않는다.
- 독립 재검증: 실제 native 몬스터 타격에서 12.7의 무가드/특수=12, 일반 가드·실패 패링 가드=5, 유효 저스트/패링=0의 HP delta/TotalDamage/Damages 합계를 대조한다. 기본12의 가드4/특수12·성공0, QA-F01의 몬스터 처치 상한·사망1회/후속 제외를 관련 회귀로 확인한다. 시험값은 Play 내부만, 수정한 두 파일/새 Bundle을 고정한 뒤 tester→reviewer로 인계한다.

#### 승인 요구·실제 경계 대조
- QA-F01 / R02: PlayerCombatComponent.CalcDamage는 보너스·실제 DEFENSE 합성/floor 뒤 남은 몬스터 HP 상한을 적용한다. native AttackComponent.CalcCritical 기본false·GetDisplayHitCount 기본1이며 이 컴포넌트는 둘을 override하지 않는다. native AttackFast→OnHit→HitEvent를 유지하고 MonsterHealth의 한 소유자만 HP를 차감한다. Health/IsAttackTarget의 DEAD 차단·사망1회 경계를 실제 코드와 QA2의 5/25/100/220/150/DEFENSE치명/0피해 및 후속0 근거로 대조했다. 숫자 화면의 가시성은 여기서 인정하지 않는다.
- R01/R02: MonsterAttack의 실행 ID·현재 쌍·패턴/영역/규칙 스냅샷, resolved 1회 확정·native resolving 범위를 확인했다. EvaluateDefense는 t-window≤start≤t와 실제 가드 상태·수락 방향을 사용하고 범위 밖 성공도 CalcDamage 밖에서 처리한다. 틀린 입력만으로 범위 밖에 추가 피해를 만들지 않는다. REV-F01 외 승인 대응표의 새 불일치는 확인되지 않았다.
- R03: GrantCounter는 현재 상대/생존/정지 여부를 확인하며 실행 중 cast와 별도 권한을 둔다. 유효 ATTACK·데이터/대상/공격력 검증 뒤 스냅샷과 예약을 만들고 소비한다. 만료 now<until·비중첩 갱신·whiff 소비·실패 보존·중간 시전 비소급은 소스와 과거 QA/QA2에 대응한다. 자동 공격 호출은 없다.
- R04/R05: MonsterStateControl은 맵 전투 시간의 slow 시작/종료 구간을 적분하고 모션·대기·공격/복귀가 같은 GetActionTime을 사용한다. 효과/그로기는 맵 시계로 만료하며 native PlayRate 저장·복원한다. STUN 진입은 ATTACK 이탈/CancelExecution으로 미실행 공격·이동을 취소하고 Health의 조건부 HIT는 STUN을 조기 종료하지 않는다. 사망 먼저 무효화/DEAD하며 이전 완료의 ID·생존/state 조건을 확인했다. QA2의 접근/실타격/복귀 양성은 유효하고 다음 대기의 정확 deadline은 정밀 PASS로 확대하지 않았다.
- R06: 신규 두 DataSet wrapper의 이름/UUID/serveronly·동명 CSV, 확정 수치(.20/.40/2/2.2/2/.5/1.5)와8패턴·기존 player.basic10타/3×1을 읽었다. CombatRuleCatalog는 전체 정상화 성공 후 캐시를 교체하고 invalid 시 임의 기본값/부분 행으로 진행하지 않는다. modifier→동일 검증→실행 복사와 OnEndPlay 캐시 정리를 확인했다. coder의 실제 CSV .30→NaN→원본복원은 독립 CSV 재편집 시험과 구분돼 있다.
- R07/R08: CombatInputController의 UI 필드/이벤트는 ClientOnly이며 현재 로컬 대결의 서버 Sync 결과만 표시한다. PlayerStateControl의 단일 수락·출처 합산·복귀 잠금, PlayerEvade의 sender 소유자·epoch/sequence/closed 경계, popup의 서버 승인·동결·홀드 시각 폐기, Manager의 유일 사용자/상대 확인·교체/사망 시 이전 실행 정리를 대조했다. 원래4버튼·이동6/복귀6·점프.5/.8과 native HP 경로를 보존한다. 이것은 실제 Run 격리/다중 접속 검증 완료가 아니다.
- 검토한 실제 소스는 위 소유자들과 Player_Attack/Player_Move/Monster_Attack/Monster_Stun, OrangeMushroomAttack, PlayerSkillEffectTable 및 native AttackComponent/HitComponent/StateComponent/HitEvent 정의다. 구조 파일은 raw JSON으로 검토/수정하지 않았으며 기존 빌더 사전 표·실제 QA 연결 결과와 byte 불변성을 보조 근거로 사용했다. 새 자원 선택·전면 모션/사망 프레임워크·수동 피해·핫바 도입은 승인 범위가 아니다.

#### CombatCore-DOC-01 — 현황·인계 링크 동기화
- DevelopmentRoadmap.md:13의 현재 자동 반격 설명, :45의 P01b 시작 예정, :103의 구현/Play/QA/리뷰 미착수·2026-10-20 재개 지점이 실제 기록과 다르다.
- ChatRoles/README.md:36의 WorkRecord 생성 예정, WorkRecords/README.md:58의 규칙 결정 대기/WorkRecord 생성 예정도 현재 Plan/WR로 연결해야 한다.
- 다음 담당은 planner. 제품 수정/재검증/리뷰 결과가 확정된 뒤 위 현황·날짜·링크만 원본 Plan/WR에 맞춘다. 규칙/검증 기준·단계 순서 변경이나 결과 전문 복제 없이 정리한다. 메인의 run도 같은 실제 담당/버전에 맞춘다.

#### 수정 후에도 남는 필수 확인·다음 행동
1. coder: REV-F01의 두 경계만 최소 수정·실제 기본 검증·새 버전/사용 종료 기록. tester: 새 버전의 소수 기본 피해와 관련 native 회귀. reviewer: 변경·QA·동일 버전 재대조. 제품을 바꾼 뒤 이번 QA2가 모든 변경 경로에 그대로 적용된다고 표시하지 않는다.
2. planner/메인: DOC-01 정리, QA-F01의 과거 FAIL과 새 수치 PASS 연결, CF-F07 수치/연출 분리·잔여 ID 추적 유지. 현재 P01b~P06은 🟡 유지가 타당하며 문서 존재나 대표 양성만으로 P06/단계 전체를 완료 처리하지 않는다.
3. 사용자 V11: 실제 PC·모바일의 예고 방향/속성·.20초 체감·저스트/패링/반격 준비·소비·적 슬로우/별 표시·피격/die·키/버튼/터치 혼합·화면 잘림·음향을 직접 확인한다. 새 수치/규칙 변경 요구가 없으면 재승인 질문은 불필요하다.
4. V12 외부 환경: 실제 두 사용자·비전투 몬스터/다른 맵이 있는 환경의 비전파는 NOT_RUN. 단일 참조/무효화 정적 검사와 현재 맵의 교체·사망 시험으로 이를 대신하지 않는다. 실제 맵 전환은 기존 CF-F03/CombatPause-F01, 기기/음향·재시작·배포·성능은 기존 후속 ID와 실행 시점을 유지한다. 이를 위해 새 Run/맵/다중 전투 체계를 만들지 않는다.
5. 현 조건의 종착점은 REV-F01와 DOC-01 처리 후 사용자/환경 WAITING 경계다. V11·CF-F07 연출·외부 필수 확인이 남은 Plan/WR/run은 보존하고 3단계를 자동 시작하지 않는다.

## 완료 시 이관할 내용

현재 기능·설정·사용자 선택·짧은 검증/미검증 범위를 Features에, 미완료 추적은 Plan에 유지한다.

## 2026-10-24 재개 인계
사용자가 "2단계 중단 시점 부터 작업 재개해줘."라고 명시 요청했다. 기존 규칙을 유지하고 P01b부터 진행한다. 제품 편집 전 실제 Maker 맵·모드와 소스/API·연결을 확인한다. 브리지 TCP 연결 성공은 Maker 도구/실제 맵 확인과 구분한다. 이전 개발·QA·리뷰 미실시를 새 결과로 변경하지 않는다.

### P01b 사전 점검 (2026-10-24 / coder)
- 실제 Maker 도구가 coder 문맥에 노출됨. maker_get_current_map: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. maker_get_world_info: worldId=970621b29ba945369d3dc8e90c301186. MapBuilder mode=0과 일치. 아직 제품 쓰기/Play 없음.
- MonsterManager.CurrentMonster가 단일 상대 소유자. 현행 MonsterData는 castleenemy 한 행, 실제 주황버섯 모델에 DEFENSE/Stun/Attack/OrangeMotion 연결. 현재 상대·현재 사용자 1명만 허용하는 최소 fail-closed 경계를 같은 소유자에 추가하며 독립 Run 격리 완료로 보지 않는다.
- 최소 데이터: CombatRuleData 기본1행 + MonsterAttackPatternData 유효 대응×속성8행. LEFT/RIGHT는 중앙·반대 방향 영역을 타격하고 예고 방향으로 피할 수 있게 앵커 기반 범위 구성. 특수+GUARD는 거부. JumpDuration=0.5/JumpHeight=0.8과 기본 공격 행은 유지한다.
- 핵심 위험: 범위 밖 저스트가 CalcDamage를 거치지 않는 점, 슬로우 배율 변경 시 모션/예약이 점프하는 점, 기존 실제 DEFENSE의 HitEvent 후 경감으로 숫자와 HP가 어긋나는 점. 공격 실행1회 결과·적 적분 진행 시계·CalcDamage 전 경감으로 해결한다.
- StateComponent.d.mlua의 DisconnectHitEvent를 확인했다. HP는 기존 HitEvent 한 경로로 유지하며 기존 Health 소유자에서 STUN/ATTACK 보호 조건부 HIT만 처리한다. 새 수동 피해/핫바/컨트롤러/사망 연출 프레임워크는 승인 Plan 우선으로 도입하지 않는다.
- 구현 원장: 프로젝트 루트 .maplestory-skill-maker-ledger.md에 DATA/PAP/PAJ/MHP별 소유자·위치·검증 시나리오·승인 예외를 OPEN으로 생성.

### P02~P05 작성 및 통합 기본 검증 진행 (2026-10-24)
- CombatRuleCatalog 원자적 로드/검증, 기본1·8패턴 데이터, MonsterManager 단일 CurrentPlayer, 공격 실행 스냅샷/1회 판정, 수동 보너스, 적 행동 적분·그로기·서버 결과 HUD를 작성했다. Plan P01b~P05는 🟡이며 실행 완료를 뜻하지 않는다. 기존 AttackSkillData/이동 수치/점프 수치/4버튼/네이티브 타격을 유지했다.
- 16:42 Refresh→build는 오류0, 문자열 치환 다중 반환 경고1 및 기존 동적 참조 Info. normal 변환 오류0. Play에서 catalog ready rules=1 patterns=8, HUD bound=true, duel player, 이동 speed=6 return=6 확인.
- 첫 통합 회차: 유효8패턴 예고와 중복 ResolveAttack 1회 판정, 실제 HP=HitEvent 합계 normal guard4/special guard12/parry0/parry early4/wrong12 확인. 그로기 잔여는 같은 호출 중에도 프레임 진행해 1.483으로 계측되므로 1.5 정확등가 검사 대신 허용 오차로 검사한다(제품 수치 변경 아님).
- 실패: justinside 슬로우 적용에서 MonsterStateControl.ApplySlow savedPlayRate nil 산술 오류. Stop 후 수정: native 재생률은 로컬 스냅샷으로 읽고 유효 수 검증, 만료 정리와 충돌하지 않게 활성 시각을 먼저 설정한 뒤 저장값·재생률 적용. 실패 이력을 보존하고 수정1 회차에서 전체 통합 재검증 중이다. 범위 밖 비성공은 피격 대신 회피 표시로 구분했다.


## 2026-10-25 coder 재개·기본 검증 인계

### 실제 실행·변경·종료
- 담당: 독립 coder /root/combat_core_coder_v3. 기존 v2 사용량 한도 중단 뒤 현재 파일을 이어 검증했다. 사용자 재개 승인 범위는 기존 R01~R08이며 새 규칙·3단계·배포는 추가하지 않았다.
- 연결: 실제 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root id·TileMapMode=0 일치. Play context=server_main/client.
- 이번 영구 제품 수정은 MonsterManager.mlua의 model:// 접두어 제거 한 곳이다. 다중 반환 string.gsub를 단일 반환 string.sub 분기로 바꿔 DoSpawn LWA-1111 경고를 제거했다. 기존 v2의 전투 구현을 재구현하거나 기존 수치를 바꾸지 않았다.
- CombatRuleData.csv는 승인된 V09 시험 동안만 0.40→0.30→NaN→원본을 적용했다. 모든 파일 쓰기는 edit에서 수행하고 각 값마다 Refresh→build→Play를 거쳤다. 원본 복원 bytes 일치, SHA-256 fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f.
- 최종 실제 관찰(2026-10-25 11:00:32 Maker 로그 시각): 기본값 복원 Play의 build 오류0/경고0, normal 오류0. 과거 invalid 데이터 시험 경고는 보존했고 무단 clear_logs는 호출하지 않았다. 초기 경고가 잠시 과거 시각으로 남았으나 변경 뒤 Play에서 새 build 결과는 오류0/경고0이다.
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01/edit 확인. Maker 사용 종료. 시험 입력 키는 모두 up/tap 종료. 임시 컴포넌트·파일·로그 삭제는 하지 않았다. Play 내부 값/참조/시험 이벤트 연결은 Stop으로 폐기했고 별도 HitEvent 시험 핸들러도 명시 Disconnect했다. 최종 재진입의 상태가 정상임을 확인한 뒤 다시 Stop했다.

### 기본 검증 결과와 한계
아래는 coder의 실제 MCP 개발 검증이며 독립 QA나 사용자 수락이 아니다. 시각은 Maker 로그 시각이다. 일부 항목의 남은 세부 경우는 tester가 독립 보완하며, 확인한 일부만으로 V 전체를 통과 처리하지 않는다.

| 기준 | 이번 확인·양성 근거 | 남은 독립 보완·미실시 |
| --- | --- | --- |
| V01 | 10:52:22~23: 유효 8패턴의 Prepare→실제 native Resolve를 각각 강제 선택한 Play 값으로 확인. id/유형/영역 스냅샷 일치, Resolve 2회 호출에도 resolutionCount +1. 각 HP=HitEvent 12. SPECIAL+GUARD 검증 거부 | 동기화된 문구·색·다른 공격 시각의 표시 대조는 tester, 실제 읽기 편함은 V11 |
| V02 / CF-F07 | 10:52~55: 일반 가드4/특수 가드12/패링0/이른 패링 가드4/짧은 일반 가드4. actual W 시전은 10타·최종2·HP=event20. 실제 DEFENSE 진입+runtime WeaponAttack7.5+보너스2.2에서 첫 경감타6, HIT로 DEFENSE 종료 뒤 후속16×9, HP=event150. 네이티브 이벤트만 HP를 차감 | 피해 숫자의 실제 화면 가시성은 V11. tester가 최종 native 표시 인자/HP 단일 적용 및 치명 경계를 독립 대조. CF-F07 선종결 안 함 |
| V03 | health.IsInWindow의 -0.200001/-.20/-.1/0/+0.000001 결과 false/true/true/true/false. 실제 LeftArrow 서버 MOVE·LEFT epoch=bound1, A 추가 홀드에도 start37.297 유지. 범위 밖 x=-1.5에서 JUST nativeHit0·피해0·권한1회, wrong/early 피해0·권한0·자동 적피해0 | 모든 네트워크 도착 순서, 해제 후 유효 창·거부 상태·death/leave 메타데이터는 tester 추가 확인 |
| V04 | 실제 ↑/W keyboard_input과 기존 UI ButtonClickEvent 주입으로만 수동 시전. count10·factor2.2·소비1. 진행 중 성공 시 cast factor1→1 유지, 중복 DoAttack 거부에도 권한 유지. 실제 whiff 피해0·소비1, 정확한 만료 UpdateCounter는 Ready=false | 시전 데이터 실패, 만료 직전·재성공 모든 경계는 tester 보완. UI 이벤트 주입은 실제 mouse/touch 클릭이 아님 |
| V05 | ApplySlow rate=.5/renderer=.5. 실제 popup 중 적 action/map clock·monsterX·효과·보너스 잔여 불변. 닫기 후 만료에서 SlowRemaining0/ActionRate1/native rate 원래값/저장값nil. 플레이어 move/return6 보존 | 접근·복귀·대기 전 구간의 시간 적분 계측·refresh 비중첩 전수, 오디오/플레이어공격 속도는 tester/사용자 범위 구분 |
| V06 | 10:56: groggy 진입 STUN·기한1.5, 미실행 공격 activeState와 JumpActive 폐기. 타격 중 STUN/기한 유지, 종료 IDLE. 이전 state completion을 재호출해도 resolution 추가0·옛 snapshot unresolved. slow 잔여는 groggy 뒤에서도 경과 | groggy 재적용·정지 중 groggy와 모든 상태 조합은 tester 보완. 머리 별 표시 생성 로그는 있으나 가시성은 V11 |
| V07 | 실제 _UIPopup.Open→RequestPopupPause로 owner=true/paused=true. 약9초 후 clockDelta0, 회피 위치 불변. Close 후 evadeStart=-1/isEvadingfalse/pendingfalse·중앙 x0·InputBlockedfalse. 효과 시험: frozen counter1.514/slow1.389/예고.288과 monsterX/action clock이 2.3초 실시간 후 동일 | 플레이어 다중타격 중 정지·groggy 정지·응답 도착 순서 전수는 tester 보완 |
| V08 | 10:58~11:00: monster native lethal HP0/IsDeadtrue/DEAD/slow0/stunfalse/bonusfalse, 옛 return 완료로 IDLE 복구 없음. 기존 DoSpawn 교체 시 oldValidfalse/new opponent 연결. player native lethal HP5→-7=피해12, native IsDeadtrue 후 보너스/slow/현재 target 제거·옛 콜백 피해0. 실제 Stop→다음Play에서 권한false/회피-1/pendingfalse/slow·groggy0 | player native lethal 직후 state는 IDLE로 관측됨(죽음 연출 통과 주장 안 함). 실제 다른 맵 전환은 기존 후속 ID, player removal/모든 외부 상태 이탈은 tester 보완 |
| V09 | 기본 실제 DataSet rules1/patterns8. ValidateRows 무효값/빈값/NaN/inf/음수·rate·중복·누락·유형·anchor 등19/19 거부, invalid modifiers3개 거부, 기존 정상 캐시 불변. 실제 CSV .30 로드 확인, 실제 NaN Play Ready=false/empty rules·patterns/SkillReadyfalse. Ensure/GetRules 반복5회 동일 key 경고1회. 원본 .40 복원+다음Play 확인 | 실제 누락 테이블/열 asset 시험 등 남은 스키마 경계는 tester 보완. 정적 검증과 실제 CSV 초기화 결과를 구분 |
| V10 | keyboard_input 실제 Left/A/Right/Down/↑/W. endpoint LEFT+UI ButtonStateChangeEvent 홀드 합산→키해제 후 UI 홀드 유지, UI해제 즉시 RETURNING/새RIGHT거부/sequence유지. 그 후 실제Right가 서버 RIGHT epoch=bound7/pendingfalse. 마지막 정상 재진입 Left tap 뒤 IDLE/LEFT epoch=bound=closed1/x0. 최종10타·range3×1·jump.5/.8·이동복귀6 | UI 시험은 Entity:SendEvent 이벤트 주입이며 실제 mouse_input/물리 터치 아님. 기기 터치는 V11, 모든 동시 입력은 tester 추가 |
| V11 | NOT_RUN — 사용자 직접 평가 | PC/모바일 예고·성공·보너스·slow·별·피격/die·타이밍·터치/잘림/음향 |
| V12 | 현재 대결만 Resolve/수동 target. player 사망 후 GetOpponent=nil로 거부, DoSpawn 실제 교체는 옛 엔티티 폐기·새 참조 연결 | 실제 두 사용자·비전투 몬스터 환경 NOT_RUN. 독립 Run 격리 완료로 표시하지 않음 |

### 프로브 오류와 제품 오류의 구분
- 기존 v2 savedPlayRate nil/방향 RPC 순서 수정은 현재 소스에 유지했고 이번 slow/실제키 경로에서 재발하지 않았다. 이번 v3 새 제품 런타임 오류는 관측되지 않았다.
- F07 첫 프로브의 HitEvent0은 몬스터를 y=0(실제 발판 y=.581 아래)에 배치해 낙하한 시험 오류였다. Home.y=.581로 올바르게 배치한 후 native 10타20/DEFENSE150을 확인했다. 해당 첫 결과를 제품 실패 또는 PASS로 세지 않는다.
- 첫 같은 프레임 UI release/return 프로브는 중앙에서 즉시 복귀 완료가 가능한 조건이라 새 입력이 수락됐다. 실제 endpoint x=-1.5에서 다시 시험하여 RETURNING 동안 새 입력 거부를 확인했다. 제품 정책을 바꾸지 않았다.
- UI 출처 문자열을 key:A로 조회한 초기 nil은 조회 키 오기이며 실제 코드는 key. + enum이다. 실제 추가 홀드 시간 불변과 이후 UI 출처 합산 근거를 사용한다.
- invalid 데이터 시험 경고는 의도한 입력 거부 근거이며 일반 runtime 오류와 분리한다. 최종 정상 데이터 Play에는 새 경고/오류가 없다.

### 다음 담당에게
같은 버전 독립 tester가 위 미실시·부분 근거를 보완하고 R/V 전체 판정을 기록한다. 특히 MOVE metadata의 거부/빠른해제/return/popup/death/leave 도착 순서, 타이밍/보너스 실패·만료·재성공, slow 적분·groggy refresh/정지, native 숫자/DEFENSE/죽음 경계, CSV 누락열 거부를 확인한다. 제품/CSV 수정은 coder로 반환하고 시험용 값은 Play 내부만 사용한다. V11 및 실제 다중 사용자/다른맵/배포/성능은 NOT_RUN 유지. 리뷰·사용자 확인 전 단계 완료/Features 이관·기록 삭제를 하지 않는다.

### 최종 제품 버전 묶음
- 52파일 byte SHA-256 manifest. 대상은 현재 authored mLua/모델/StateSet/DataSet·CSV, Global 모델·설정·충돌그룹, map/ui. Maker 자동 .codeblock/.directory 및 문서는 포함하지 않는다. 이 표는 변경 목록이 아니라 검증 대상 전체의 지문이다.
- 묶음 계산: 아래 표 순서(경로 ASCII/JS sort)로 각 행을 경로 + TAB + sha256 + LF로 연결한 UTF-8 문자열의 SHA-256.
- Bundle SHA-256: 8be49440a9ebbda62fc38df333fb09673db66d2e60a8f873aa38012d7b505e21.
- v3 영구 제품 변경: RootDesk/MyDesk/Managers/MonsterManager.mlua (아래 지문). CSV는 위 원본 지문으로 복원됐다. v2 제품 변경 이력은 앞 절 및 현재 원장 매핑을 따른다.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | bae907a8acecd4aafe8d8c97681facdfb36ba17f36461b718d75dc0b92b142fd |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | da35d0645b2658521d9229b59bb7e4023934bb331cc1e19123dec59b433c55ff |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 9265965f9d6a30920e6675068e0e9c4d2bcafc674340268dbf0fe72c75c49af9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | c76bd5d51d9bebbed532f17c67daab28982487e243213b53c67f7be7e4e7aa3b |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 874b96b0a5af7d8be282ff53ba1162cf516cba75270bb2ab660e5c2eb09ef990 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |


## 2026-10-29 coder QA-F01 수정·기본 검증 인계

### 범위·원인·실제 변경
- 담당: 독립 coder /root/combat_core_coder_v4. 사용자 현재 재개 요청에 따라 같은 2단계 승인 범위의 CombatCore-QA-F01(R02/V02/CombatFoundation-F07)만 수정했다. 이전 독립 QA의 FAIL 기록은 보존한다. 이 절의 결과는 coder 기본 검증이며 새 독립 QA나 사용자 수락이 아니다.
- 실제 연결: maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root id·TileMapMode=0 일치. runtime contexts server_main/client 확인.
- 제품 변경은 RootDesk/MyDesk/Player/PlayerCombatComponent.mlua의 CalcDamage 한 곳이다. 보너스·DEFENSE 합성 후 정수 내림한 피해에 현재 몬스터의 남은 정수 HP 상한을 적용해 native HitEvent 이전 최종 피해를 확정했다. 몬스터 HP를 직접 추가 차감하거나 HitEvent/Damages를 사후 수정하지 않았다. HP 단일 소유자·사망 전환·원래 개별 타격 예약은 그대로다. Maker 한정 cap 발생 [VRF] 로그를 추가했다.
- 소스 근거: AttackComponent.d.mlua의 CalcCritical 기본false, 현재 PlayerCombatComponent에는 CalcCritical override가 없다. GetDisplayHitCount 기본1인 현행 native 개별 타격 경로를 유지했다. 치명타 시스템·수동 피해/사망 프레임워크를 새로 만들지 않았다. PlayerComponent의 기존 음수 HP 사망 처리도 변경하지 않았다.
- 새 스킬/모델/맵/UI/DataSet/CSV/설정 변경 없음. 52개 기준 파일 비교에서 이 mLua 1개만 달라졌고 나머지 51개 byte 동일. 10타·범위3×1·HitInterval.045·기본Weapon1·이동/복귀6·점프.5/.8·4버튼은 보존했다.

### 실제 기본 검증 (한 통합 Play + 필수 Stop 재진입)
- edit에서 패치→maker_refresh_workspace 성공→build 오류0/경고0(동적 참조 Info79)→Play. 실제 keyboard_input W로 수동 공격을 실행했다. 각 조건의 HP/WeaponAttack/보너스·DEFENSE·배치는 Play 내부 fixture이며 제품 데이터가 아니다. 보너스 부여 자체는 GrantCounter 논리 프로브, 공격 수락은 실제 W로 구분한다.
- 로그 시각 2026-10-29 21:13~21:15. 네이티브 HitEvent.TotalDamage와 각 이벤트 Damages 합계를 실제 읽고 단일 Health의 HP delta와 대조했다. 모든 아래 타격의 IsCritical=false 관측. 화면에서 숫자가 읽히는지·die/효과가 자연스러운지는 이 계측으로 PASS 처리하지 않는다.

| 조건 | 실제 HP 감소 / TotalDamage 합계 / Damages 합계 | 추가 근거 | 기본 결과 |
| --- | --- | --- | --- |
| QA-F01 원재현 HP5·Weapon10 | 5 / 5 / 5 | cap10→5, native 1타·DeadEvent1회·DEAD, 나머지 타격 제외 | PASS |
| 후속 치명 HP25·Weapon10 | 25 / 25 / 25 | native10,10,5의3타·DeadEvent1회, 이후 제외 | PASS |
| 비치명 HP5000·Weapon10 | 100 / 100 / 100 | 원래10타·각10·사망0 | PASS |
| 비치명 보너스×2.2·Weapon10 | 220 / 220 / 220 | 10타 전부22·사망0 | PASS |
| 실제 DEFENSE·보너스·Weapon7.5 | 150 / 150 / 150 | 첫 경감6, HIT 뒤 후속16×9, 기존 전환 보존 | PASS |
| Weapon0 | 0 / 0 / 0 | native0피해10타·사망0·HP5000 유지 | PASS |
| DEFENSE 치명 HP5·보너스·Weapon7.5 | 5 / 5 / 5 | 경감 계산6→최종5, native1타·DeadEvent1회 | PASS |
| 위 사망 뒤 native 공격/예약 재호출 | 추가0 / 추가0 / 추가0 | extraHits0·HP0·deaths1·DEAD 유지 | PASS |

- fixture HitEvent/DeadEvent 핸들러를 명시 Disconnect하고 fixture 참조 해제. W는 tap/up 종료. 사용자 로그 clear 없음. 이 통합 회차 normal 오류0/경고0, Play 뒤 build 오류0/경고0을 다시 확인했다.
- actual Stop→다음 actual Play(21:16:01)에서 ready=true, WeaponAttack1, count10, HitInterval.045, range3×1, CounterReadyfalse, fixture nil, Monster AttackInterval3, Enabletrue, ActionRate1 확인. 이 재진입은 시험값/핸들러가 다음 세션에 남지 않는 양성 근거다.
- 최종 actual maker_stop 성공 뒤 maker_get_current_map=map01/edit 확인. Maker 사용 종료.

### 한계·다음 담당
- 독립 tester는 새 버전에서 QA-F01 원재현·후속 치명·DEFENSE/보너스·0피해·단일 사망/후속 제외를 재검증한다. 변경이 없는 다른 V 전체를 이번 개발 회차에서 다시 실행했다고 표시하지 않는다. 일반/특수/패링/가드의 플레이어 피해 경로는 이번에 변경하지 않았으며 이전 QA 근거와 구분해 독립 QA가 필요한 영향을 판단한다.
- 사용자 V11의 실제 PC/모바일 화면·터치·음향·피격/die 체감과 기존 NOT_RUN은 그대로 남는다. CF-F07은 수치 기본 확인만 추가됐으며 독립 QA/실제 연출 평가 전 종결하지 않는다. 스킬 원장 해당 PAJ/MHP 행은 OPEN 유지.
- 3단계·Features 완료 이관·Plan/WR/run 삭제·commit/push/배포는 하지 않았다.

### 2026-10-29 최종 제품 버전 묶음
- 이전 2026-10-25 묶음의 동일 52경로를 같은 순서로 byte SHA-256 계산했다. 문서·Maker 자동 .codeblock/.directory는 포함하지 않는다. 이는 변경 목록이 아닌 전체 검증 대상 지문이다.
- 계산법: 표 순서의 경로 + TAB + sha256 + LF를 연결한 UTF-8 문자열의 SHA-256.
- Bundle SHA-256: e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | bae907a8acecd4aafe8d8c97681facdfb36ba17f36461b718d75dc0b92b142fd |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | da35d0645b2658521d9229b59bb7e4023934bb331cc1e19123dec59b433c55ff |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 9265965f9d6a30920e6675068e0e9c4d2bcafc674340268dbf0fe72c75c49af9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | ebbe5f75a580523619c35729f4965ea170deef0e82b8cbc4f2443d229f90d612 |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 874b96b0a5af7d8be282ff53ba1162cf516cba75270bb2ab660e5c2eb09ef990 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |


## 2026-11-02 coder REV-F01 수정·기본 검증 인계

### 범위·원인·실제 변경
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 CombatCore-REV-F01(R02/V02/D02)뿐이다. 새 규칙·수치·기본 AttackDamage=12·DataSet·EvaluateDefense 대응표·PlayerCombatComponent.CalcDamage(QA-F01 처치 상한)·native HP 단일 소유는 바꾸지 않았다. 기준 저장소 커밋 eedeefb, 기준 Bundle e8a20728…a49.
- 원인: 몬스터 기본 피해가 경감 전에 한 번 내림(MonsterAttackComponent)되고 PlayerHealthComponent에서 경감 뒤 다시 내림되어, 소수 AttackDamage에서 D02 "합성 뒤 한 번 내림"과 어긋났다(12.7 가드: 4).
- 실제 변경(제품 mLua 2파일, 각 1줄):
  - RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua:134 — `ResolveIncomingDamage(math.floor(self.AttackDamage), attacker)` → `ResolveIncomingDamage(self.AttackDamage, attacker)`. CalcDamage 서명·integer 반환 유지(override이므로 @ExecSpace 미추가).
  - RootDesk/MyDesk/Player/PlayerHealthComponent.mlua:38 — `ResolveIncomingDamage(integer damage, Entity attacker)` → `ResolveIncomingDamage(number damage, Entity attacker)`. 반환 integer·@ExecSpace("ServerOnly") 유지, :45 `math.max(0, math.floor(damage * result.rate))`가 유일한 최종 내림. 호출자는 MonsterAttackComponent:134 하나(Grep 확인).
- 플레이어 쪽 HP 상한(남은 HP 대비 overkill) 부재는 이번 범위 밖 관찰이며 건드리지 않았다.

### 실제 기본 검증 (한 통합 Play)
- 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186 일치. MapBuilder는 사용하지 않았고 기존 기록의 TileMapMode=0(MapleTile)을 따른다. 맵·모델·UI 파일 변경 없음.
- 순서: edit에서 패치 → maker_refresh_workspace(ok) → build 로그 오류0/경고0(Info 79, 기존 동적 참조 Info만) → Play → server_main maker_execute_script 한 회차 → Stop. Play 후 normal 로그에 Info 이외 로그 없음(오류/경고0). 제품 [VRF] 추가 없음(기존 CombatCore defense 로그 사용).
- 시험 방식: Play 내부 server_main 프로브가 몬스터 AttackInterval을 일시 크게 올려 자연 공격을 막고, 기존 패턴 행에서 지정 id 1행만 해당 회차에 사용하도록 `_CombatRuleCatalog.patterns`를 임시 교체한 뒤, 실제 `StateComponent:ChangeState("ATTACK")`→PrepareAttack→시전 대기→ResolveAttack→native AttackFast/HitEvent 경로를 실행했다. 가드는 플레이어 `ChangeState("GUARD")`(PlayerGuardComponent.guardStartTime 서버 기록), 저스트는 PlayerEvadeComponent.SetEvading+EvadeDirection 설정으로 부여했다. 이 방어 입력은 키보드 입력이 아니라 서버 프로브이며 판정(EvaluateDefense)·피해(CalcDamage→ResolveIncomingDamage)·HitEvent·HP는 제품 경로다. HP delta는 PlayerComponent.Hp 전후, TotalDamage·Damages 합계는 플레이어 엔티티 HitEvent 핸들러로 읽었다.
- 로그 시각 2026-11-02 19:06:17~19:06:34 (Maker 로그). 시험값(AttackDamage 12.7, AttackInterval, patterns 임시 교체)은 프로브 종료 시 즉시 복원: rows=8, interval=3.0, dmg=12.0 확인. HitEvent 핸들러는 Disconnect.

| 조건 | AttackDamage | 판정 kind / rate | HP delta | HitEvent.TotalDamage | Damages 합계 | 결과 |
| --- | --- | --- | --- | --- | --- | --- |
| T1 무가드 일반 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T2 특수 무가드 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T3 특수+가드 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T4 일반 가드 | 12.7 | GUARD / .4 | 5 | 5 | 5 | PASS (기대 5, 구 코드 4) |
| T5 패링 실패 가드(가드 .5초 전 시작) | 12.7 | GUARD / .4 | 5 | 5 | 5 | PASS (기대 5) |
| T6 유효 패링(가드 시작이 타격 .089초 전) | 12.7 | PARRY / 0 | 0 | 0 | 0 | PASS (기대 0, native 이벤트1·0피해) |
| T7 유효 저스트(회피 시작이 타격 .102초 전, RIGHT) | 12.7 | JUST / 0 | 0 | 0 | 0 | PASS (기대 0) |
| R1 무가드 | 12 | HIT / 1 | 12 | 12 | 12 | PASS 회귀 |
| R2 일반 가드 | 12 | GUARD / .4 | 4 | 4 | 4 | PASS 회귀 (기대 4) |
| R3 특수+가드 | 12 | HIT / 1 | 12 | 12 | 12 | PASS 회귀 |
| R4 유효 패링 | 12 | PARRY / 0 | 0 | 0 | 0 | PASS 회귀 |
| R5 유효 저스트 | 12 | JUST / 0 | 0 | 0 | 0 | PASS 회귀 |

- 각 회차 resolved=true·nativeHit=true·native 이벤트 1건. PlayerHealthComponent의 마지막 확정 피해(lastResolved)도 HP delta와 일치.
- 이번에 실행하지 않은 것: 실제 keyboard_input/mouse_input 방어 입력, QA-F01 몬스터 처치 상한·사망1회/후속 제외 회귀(PlayerCombatComponent·MonsterHealth 변경 없음, 소스 무변경으로 독립 QA가 확인 필요), 플레이어 사망 경계, 슬로우/그로기/팝업/DataSet 로드 회귀, 두 파일 외 경로의 전수 재실행, V11 화면 가시성·체감. 이 항목은 새 전수 실행으로 표시하지 않는다.
- 시험 오류·한계: 프로브 중 몬스터 자연 공격(시험 전 약 4초 간격)이 프로브 전후에 몇 번 있었으나 회차 판정 로그와 분리되어 측정에 섞이지 않았다(회차마다 snapshot id·pattern·hit 시각 기록). 제품 오류는 관측되지 않았다.

### 사용 종료·다음 담당
- 최종 maker_stop 성공 후 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. 사용자 로그 clear·파일/CSV 추가 변경 없음. commit·push는 하지 않았다.
- 다음은 독립 tester: 새 Bundle에서 소수 기본 피해(12.7)의 무가드/특수=12, 일반·패링실패 가드=5, 유효 저스트/패링=0를 실제 입력 경로로 재확인하고 기본12 회귀와 QA-F01 처치 상한·사망1회/후속 제외를 관련 회귀로 확인한다. 이전 QA2를 이 변경 경로에 그대로 적용된다고 표시하지 않는다. V11·CF-F07 연출·V12 외부 환경은 NOT_RUN/WAITING 유지, 단계 완료·3단계 진행·Features 이관 아님.

### 2026-11-02 최종 제품 버전 묶음
- 이전 2026-10-29 묶음과 같은 52경로·순서. byte SHA-256을 다시 계산해 변경 파일은 아래 두 개뿐임을 확인했다(나머지 50개는 기존과 동일). 계산법: 표 순서의 경로 + TAB + sha256 + LF를 연결한 UTF-8 문자열의 SHA-256.
- 직전 Bundle(e8a20728…a49) 재계산도 일치. 변경 전 지문: MonsterAttackComponent eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d, PlayerHealthComponent 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8.
- Bundle SHA-256: 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | bae907a8acecd4aafe8d8c97681facdfb36ba17f36461b718d75dc0b92b142fd |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | da35d0645b2658521d9229b59bb7e4023934bb331cc1e19123dec59b433c55ff |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 13d0db06277f2d1f215dbd9df73f348181b00ac53a7e5aa0ebaffe0cb6d69eed |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 9265965f9d6a30920e6675068e0e9c4d2bcafc674340268dbf0fe72c75c49af9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | ebbe5f75a580523619c35729f4965ea170deef0e82b8cbc4f2443d229f90d612 |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1ee406d747b8a3edece94fc7b4f74500f94c65e6fb3d398df531332f284f5d79 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 874b96b0a5af7d8be282ff53ba1162cf516cba75270bb2ab660e5c2eb09ef990 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |


## 2026-11-02 coder V11-F01~F05 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §14의 CombatCore-V11-F01~F05뿐이다. 모든 수치(0.20, ×0.40, 반격 2.0·×2.2, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0)·CSV 3종·D01~D03 판정 규칙·8패턴 영역·LandingAnchor·피해 합성/내림·플레이어 애니메이션·.ui는 바꾸지 않았다. 기준은 커밋 a289eb7(제품은 6614b20과 동일) / Bundle 1ac324e6…9de4(52경로)이며 시작 전 같은 방법으로 재계산해 일치를 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder TileMapMode=0(MapleTile). Maker 로그 시각 22:48~23:03.
- 시험값(AttackInterval 일시 상향, 패턴 목록 단일 행 교체, 그로기 6초 시험값)은 모두 Play 내부 서버 프로브이며 Stop으로 폐기했다. 반영한 영구 변경은 아래 제품 변경뿐이다.

### F05 원인 판정 — 규칙상 정상, 제품 무수정 (변경 전 기준 버전에서 실행)
- 방법: 실제 `maker_keyboard_input`으로 LeftArrow를 홀드해 Pos1(x=-1.5)에 머문 채(서버 상태 MOVE 유지) 서버 프로브로 8패턴을 한 번씩 강제 공격시키고, 패턴 ID·판정 순간 플레이어 x·서버 상태·kind·HP·HitEvent 합계를 기록했다. 패턴 행만 단일 행으로 교체했고 판정·영역은 제품 경로 그대로다.

| 대응형 | 패턴 | 서버 영역 | 판정 순간 x / 서버 상태 | 네이티브 피격 | HP 감소 / HitEvent 합계 | 결과 |
| --- | --- | --- | --- | --- | --- | --- |
| 뒤 회피형(LEFT) | normal/special/parry.left | -0.5~2.0 | -1.5 / MOVE | 없음 | 0 / 0 | 피해 없음, HUD 회피(EVADE) |
| 앞 회피형(RIGHT) | normal/special/parry.right | -2.0~0.5 | -1.5 / MOVE | 있음 | 12 / 12 | HIT |
| 가드형(GUARD) | normal/parry.guard | -2.0~2.0 | -1.5 / MOVE | 있음 | 12 / 12 | HIT(가드 없음) |

- 판정: 뒤 회피형은 Pos1에서 기대대로 EVADE·피해 0이다. 앞 회피형·가드형이 Pos1에서 맞는 것은 D01의 정상 동작이다(영역이 Pos1을 포함한다). 사용자 사례의 패턴은 미상이므로 앞 회피형·가드형이었다면 정상이고, 뒤 회피형에서 맞는 재현은 나오지 않았다(결함 아님).
- 입력 지연 점검(키보드): 같은 키 이벤트의 클라이언트 시각 78.363에 클라이언트 상태 IDLE→MOVE가 같은 프레임에 일어났고, 서버 상태 IDLE→MOVE는 서버 시계 77.890이다. 같은 프로브의 MOVE→IDLE 복귀(클라이언트 82.244 / 서버 81.755)에서 시계 차 ≈0.49초가 나와 진입 시 차 0.473초와 같다. 따라서 서버 수락 지연은 약 1프레임 이내로 본다. 홀드 중에는 RETURNING으로 넘어가지 않았고 해제 뒤에만 복귀했다(OUTBOUND 0.243초 도착→HOLD, 해제 뒤 RETURNING 0.24초). 미실시: UI 버튼 누름 경로의 수락 지연 측정(Entity 이벤트 주입이 실제 터치가 아님), 예고 시작 뒤 플레이어 방향 전환이 시작 시 Scale 기준 검증과 어긋나는지 시험.

### 항목별 실제 변경
| ID | 변경 파일 | 요약 |
| --- | --- | --- |
| F02 | RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua, RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 패링 성공 판정(PARRY) 시 ResolveAttack은 더 이상 즉시 ApplyGroggy를 호출하지 않는다. Monster_Attack이 ResolveAttack 직후 결과가 PARRY면 groggyAfterReturn(지속시간은 스냅샷 규칙값)을 기록하고 기존 복귀 모션을 그대로 수행한다. 복귀 완료(OnReturnComplete) 또는 복귀 모션 거부 시 FinishAttack이 ApplyGroggy를 호출해 STUN으로 가고, 거부되면 IDLE로 간다. 반격 창은 기존 GrantCounter(성공 시점)를 그대로 쓴다. 취소(CancelExecution) 때 플래그를 초기화한다. |
| F04 | RootDesk/MyDesk/Models/Monsters/주황버섯.model(ModelBuilder) | 방식 (a). StateAnimationComponent.ActionSheet에 "stun" 키 하나를 추가하고 기존 hit RUID(aec9504d5dc24aceb5646b79d30abad4)를 연결했다. move·stand·jump·hit·die 다섯 키의 값은 그대로다. .mlua 변경 없음. 새 클립·자원 검색·제작 없음. |
| F01 | RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua(신규, Maker가 .codeblock 생성), RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model(ModelBuilder 신규), map/map01.map(MapBuilder: BattlePosMark1~3 3개 배치), MonsterAttackComponent.mlua, Monster_Attack.mlua | MonsterAttackComponent에 @Sync TelegraphCells("111" 형식, 칸1~3 중 앵커 x가 서버 영역 min~max 안에 있으면 "1")를 추가해 PrepareAttack에서 TelegraphResponse와 함께 설정하고 ResolveAttack·CancelPendingAttack·Monster_Attack.CancelExecution에서 같이 비운다. 맵에 3개 표시 엔티티(model AttackAreaMark: TransformComponent·네이티브 PixelRendererComponent·AttackAreaMarkComponent, 위치 x=-1.5/0/1.5, y=0.98, z=0, Scale 25 = 4×4 논리 픽셀 → 1.0×1.0 월드 단위)를 두고, 소유 클라이언트가 MonsterManager의 현재 몬스터·대결 플레이어를 확인한 뒤 자기 CellIndex 칸만 반투명 빨강(알파 0.45)으로 칠한다. 새 RUID·.ui 없음. 표시는 서버 동기 값만 읽으며 판정·피해에는 관여하지 않는다. |
| F03 | RootDesk/MyDesk/Monster/MonsterStunComponent.mlua, MonsterAttackComponent.mlua | 별 StarVortex 부착 파티클을 크기 0.2→0.5, 부착 높이 0.65→0.9로 키웠다. 서버 확정 PARRY에서만 MonsterAttackComponent가 stun:NotifyParry(접촉 지점 x=(플레이어 x+몬스터 x)/2, y=몬스터 y+패턴 AreaOffsetY)를 호출하고, MonsterStunComponent의 @Sync ParryEffect(Vector3, z는 같은 위치 반복에도 동기화되도록 한 순번)가 바뀌면 소유 클라이언트가 네이티브 BasicParticleType.SparkRadialExplosion(크기 1.5, 1회)을 재생한다. 저스트·가드·패링 실패에는 호출하지 않는다. 맵 이탈·종료 시 파티클을 제거한다. HUD 문구·.ui 무변경. |
| F05 | 없음 | 위 판정대로 무수정. |

- 건드리지 않은 것: CombatRuleData·MonsterAttackPatternData·AttackSkillData CSV, 주황버섯 ActionSheet의 기존 다섯 키, HitComponent·MonsterHealthComponent의 HIT 진입 조건, PlayerStateControl 등 플레이어 쪽, CombatInputController(HUD 문구 포함).
- Maker 부산물: Models/MapObjects.directory, Combat/AttackAreaMarkComponent.codeblock이 refresh로 생겼다. 이 둘은 지문 대상 외(이전 묶음 정의 유지)다. 빌더가 주황버섯.model을 다시 쓰며 줄 끝이 CRLF→LF로 바뀌고 변경한 ActionSheet 값의 형식 버전 문자열이 26.7.0.0→26.10.0.0이 됐다. 의미 비교(JSON)에서 이외의 차이는 없음을 확인했다(stun 키 제거 후 형식 버전 문자열 1곳만 다름).

### 실제 기본 검증 (Maker MCP, 같은 Bundle 기준 통합 Play를 여러 회차로 수행)
- 빌드: Refresh 후 build 로그 80건, 모두 Info(LIA 1114/1115, 기존 동적 참조 노이즈 유형 — 새 NotifyParry 항목 포함). 오류 0·경고 0. 별도 normal 로그의 제품 오류 없음.
- F02 패링 흐름(서버 프로브, 제품 경로 판정): 패턴 parry.guard, 가드 시작이 타격 0.10초 전. 결과 PARRY·피해 0, 타임라인(전투 시계 기준): 0.00 시작 x=3.00(Home 3.00)→0.55 판정 PARRY·반격 가능→0.55~1.07 ATTACK 상태로 복귀(그로기 아님, 별 표시 없음)→1.07 STUN x=3.00(GroggyRemaining 1.48)→2.53 잔여 0.02→2.57 IDLE. 그로기 길이 ≈1.50초(복귀 완료부터), 반격 창은 성공 시점 0.55부터 약 2.0초(2.55에 CounterReady false). 다음 공격(case2)은 x=3.00(Home)에서 시작해 착지 x=0.10으로 점프했다. 그로기 진입 로그는 Monster_Attack.FinishAttack 호출이다.
- F02 대조: 가드 0.45초 전(패링 창 밖) → GUARD·HP -4(12×0.4 내림)·그로기 없음·접촉 파티클 없음. 저스트(RIGHT 회피 시작 0.12초 전) → JUST·슬로우 적용·그로기 없음·접촉 파티클 없음(case3 요약 줄은 clear_logs로 잃었지만 같은 구간 로그에 slow applied·defense JUST가 있고 groggy applied·parry effect 로그는 없었다).
- F03: PARRY 판정마다 `parry effect serial=N x=0.0 y=0.981`이 한 번만 나왔고(소유 클라이언트), GUARD·JUST에는 없었다. 육안 확인은 아래 한계.
- F04: 클라이언트 AnimationClipEvent 추적: HIT→clip=hit, IDLE→clip=stand, STUN→clip=stun(ActionSheet "stun"=hit RUID), 종료 IDLE→clip=stand. 실제 패링 흐름에서도 STUN 진입에서 clip=stun, 그로기 종료에서 clip=stand를 확인했다. 복귀 중에는 stun 클립이 나오지 않았다(복귀 중 기존 모션 유지). SpriteRUID 속성 읽기는 클립 파이프라인이 속성을 바꾸지 않아 근거로 쓰지 않았다.
- F01: 8패턴 서버 영역→TelegraphCells: normal.left/special.left/parry.left(-0.5~2.0)=011, normal.right/special.right/parry.right(-2.0~0.5)=110, normal.guard/parry.guard(-2.0~2.0)=111. 같은 프로브의 클라이언트 표시 판정 로그가 각 패턴의 칸과 일치하게 켜졌고 판정 직후 모두 꺼졌다(제품 로그 `area mark cell=…` — 이후 로그 소음을 줄이려 제거). 예고 중 슬로우·팝업·사망·Stop에서 칸이 유지·제거되는 경로는 별도 시험하지 않았다(표시는 서버 동기 TelegraphCells 값에만 묶여 있고, 복귀 중 정지 뒤 Stop→재Play에서 칸이 모두 꺼져 있음은 V08에서 확인). 스크린샷에서 칸 1·3이 반투명 빨강(배경과 섞여 주황빛)으로 보이고 몬스터 판정 높이(몬스터 y+0.4 중심, 높이 1.0)와 맞는 위치임을 확인했다.
- V02: 중앙(x=0)에서 8패턴 모두 HIT, HP 감소=HitEvent 합계=12. 가드 4.8→4(경감 뒤 한 번 내림) 일치.
- V03: 패링 창 경계 대표 두 점(0.10초 전 PARRY, 0.45초 전 GUARD)과 F05 8패턴(범위 밖 EVADE 포함)을 확인했다. 전체 경계 열(정확히 0.20·직후 등)은 이번에 다시 하지 않았다.
- V04: 패링 성공 뒤 실제 ↑ 입력으로 수동 공격 `manual cast count=10 factor=2.2`, 이후 CounterReady false(소비). 반격 보너스 규칙 전체 경계는 재시험하지 않았다.
- V06: (1) 패링→복귀→그로기(2.57 IDLE). (2) 그로기(시험 6초) 중 실제 ↑ 공격: 서버 상태 STUN 유지, 몬스터 HP 100→80(10타), GroggyRemaining이 계속 감소해 시작 +6.0초(전투 시계 7.05)에 IDLE, 조기 해제·연장 없음. 클라이언트에서 같은 피격으로 로컬 상태가 HIT로 보인 순간에 hit 클립 이벤트가 한 번 관측됐으나 서버 상태는 STUN이고 hit RUID가 stun RUID와 같아 화면 변화는 없다(기존 구조의 클라이언트 쪽 HIT 신호로 보이며 이번에 바꾸지 않음, tester가 화면 확인).
- V07: 패링 뒤 복귀 중 popup 열기(x≈0.31에서 정지, 전투 시계 12.87 고정, 약 24초 정지). 닫은 뒤 전투 시계가 이어져 x가 0.31→0.41…→3.00으로 복귀하고 STUN 진입(GroggyRemaining 시험값 6.00)했다. 정지 중 위치·그로기 값 불변. 닫기는 팝업 실시간이 아니라 프로브가 `_UIPopup:Close()`를 직접 호출했다(client TimerService가 정지해 타이머로 닫을 수 없었음, 제품 문제 아님). 슬로우·예고 중 팝업의 칸 유지·재개는 이번에 다시 하지 않았다.
- V08: (1) 복귀 중(x=0.10) 몬스터 치명 피해(MonsterHealthComponent.ApplyDamage): 0.04초 뒤 DEAD, STUN·그로기 진입 없음(isStunned false, GroggyRemaining 0), 3초 동안 변화 없음. (2) 팝업 정지 중 복귀(패링 직후)에서 실제 maker_stop → 새 Play: 몬스터 IDLE x=3.00, isStunned false, GroggyRemaining 0, 칸 표시 없음(서버 cells='', 클라이언트 3칸 모두 false), 슬로우 0·배율 1, pause false, 반격 false, ParryEffect 순번 0, popup 닫힘, 첫 자연 공격 정상. 플레이어 사망·다른 맵 전환은 이번에 하지 않았다.
- V10: 실제 키 입력으로 Right(MOVE→복귀→IDLE, x 0→1.5→0), Down 2초 홀드(GUARD, isGuarding true, 서버 GUARD→IDLE), ↑ 탭(ATTACK 10타 factor 1, 반격 없음 시 ×1)과 Left 홀드(F05)를 확인했다. UI 버튼 경로·동시 입력 전 조합은 재시험하지 않았다.
- 미실시: V05 슬로우 전 구간 적분 재확인, V09 CSV 변경 시험(CSV 무변경, 로드 `rules=1 patterns=8` 확인만), V12.

### 화면 근거와 한계(F03 값 제안)
- 해상도 558×314 스크린샷으로 확인한 것: BattlePos 칸의 위치·크기·반투명 빨강(F01), 부착 파티클의 로컬 좌표·스케일이 부모(몬스터 Scale 2)에 곱해진다는 사실(attached Nova local y=1.5가 몬스터 발 기준 약 3.0~3.2 위에 중심). 별 스파크·접촉 폭발은 이 해상도·캡처 타이밍에서 형태를 확정할 수 없었다(작은 스파크가 희미하게만 보임).
- 제안값(사용자 V11에서 판단): 별 크기 0.5, 높이 0.9(몬스터 월드 기준 머리 위 약 0.7). 접촉 효과는 SparkRadialExplosion 크기 1.5, 위치는 패링 판정 순간 플레이어·몬스터 x의 중간, 높이는 몬스터 y+0.4(공격 영역 중심). 더 눈에 띄는 형태·색을 원하면 사용자가 선택한다(자원 검색·제작은 하지 않았다).
- F01 칸 알파는 0.40으로 화면을 확인한 뒤 0.45로 올렸고 최종 값의 화면 재확인은 하지 않았다.

### 프로브 오류와 제품 오류의 구분
- 보정용 프로브에서 `Dictionary()` 생성자 사용 오류(LEA-2011 3건)와 Stop 시 남은 프로브 타이머의 LEA-3051 MemoryLeak 1건이 났다. 모두 시험 스크립트 문제이며 제품 오류는 관측되지 않았다.
- 칸·파티클·클립 확인은 로그 중심이고 육안 확인은 위 한계가 있다. V11(체감)·CF-F07 연출·V12 외부 환경은 이번에도 미실시다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F05를 같은 조건(실제 LeftArrow 홀드 Pos1)에서 8패턴 독립 재확인하고 UI 버튼·방향 전환 시나리오 추가. (2) F02: 패링→복귀→그로기 순서·1.5초·다음 공격 Home 시작·복귀 중 슬로우/팝업/피격/사망/Stop. (3) F04: 그로기 중 hit 클립(복귀 중에는 아님)·종료 후 stand·그로기 중 피격 시 클라이언트 HIT 신호가 화면을 바꾸지 않는지. (4) F01: 8패턴 칸과 예고 중 슬로우·팝업·사망·Stop 제거를 육안으로. (5) F03: 패링에만 접촉 파티클, 별 크기·높이의 가시성. (6) 회귀 V01·V02·V03·V06~V08·V10과 관련 경로의 V04·V05·V09. 사용자 V11 재확인과 V12 외부 환경은 AI 결과로 대신하지 않는다.

### 2026-11-02 최종 제품 버전 묶음 (V11-F01~F05)
- 이전 묶음(1ac324e6…9de4, 52경로)의 경로 표에 신규 2경로(Combat/AttackAreaMarkComponent.mlua, Models/MapObjects/AttackAreaMark.model)를 더한 54경로. 계산법은 이전과 같다(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256). 이전 묶음을 HEAD(a289eb7)에서 같은 방법으로 재계산해 1ac324e6…9de4와 일치함을 확인했다. 변경·추가 파일은 7개: AttackAreaMarkComponent.mlua(신규), AttackAreaMark.model(신규), 주황버섯.model, Monster_Attack.mlua, MonsterAttackComponent.mlua, MonsterStunComponent.mlua, map/map01.map. 나머지 47개는 이전과 같다.
- Bundle SHA-256: d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 9c0e9b5bbc2ba588e021aeca0ac9f9dcaacdc6223ddae17ea955dcf2c8544907 |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model | 954a3ef24d26150150de52b5fe6a738276561b18da0129c762e3899e72a1466b |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | 1b7686acda7c84412676a7157681156cbef5f693e4b3c0872d609c5cf61c3b9d |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 578acaa625570909d0eebf2a46332d7f429b3aed351c0b098c7fc6f3d6a60db8 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | a1735e7f50fc694a08133bfd2a012b2438051fe7b0fa45e55e7bc123b9d9a164 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 69ad2f52be603d7fedde3223678094968d859cd209f9771895ab1175ce29e3c9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | ebbe5f75a580523619c35729f4965ea170deef0e82b8cbc4f2443d229f90d612 |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1ee406d747b8a3edece94fc7b4f74500f94c65e6fb3d398df531332f284f5d79 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 1e9dbe01ec2139a7da3a2129399620b187592559856a5d4959b537b72d11fa65 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |

## 2026-11-03 coder V11-F06 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §15 CombatCore-V11-F06뿐이다. JustWindowSec 0.20, GuardDamageRate 0.40, 반격 2.0·×2.2, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8, 기존 패딩 0.5·높이 1·오프셋 0.4·선행 0.5, CombatRuleData·AttackSkillData CSV, D02~D04, 입력 규칙, LEFT/RIGHT 영역, GUARD 판정 규칙·코드, F01~F05 동작, .ui, 주황버섯 모델, 몬스터 수치 DataSet화(F07)·3단계는 바꾸지 않았다.
- 기준 버전: coder 커밋 1447ff8(54경로 Bundle d2b57802…0fbb). 시작 전 같은 방법(아래 계산법)으로 1447ff8의 54경로를 재계산해 d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb와 일치함을 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder 읽기 TileMapMode=0(MapleTile). Maker 로그 시각 10:05~10:17. maker_clear_logs는 한 번도 호출하지 않았다.

### 미커밋 Maker 재저장 3파일의 의미 비교 (제품 수정 전, 빌더 읽기)
- 방법: git show로 1447ff8 판을 임시 경로에 꺼내 MapBuilder.read(...).build()/ModelBuilder.read(...).build()로 읽고, 문자열로 직렬화된 jsonString을 풀어 키 순서·숫자 표기(1↔1.0)·줄 끝을 무시한 깊은 비교를 했다(StudioVersion은 별도 보고).
- map/map01.map: 엔티티 13개 동일. 차이는 BattlePosMark1~3(Entities[10~12]) TransformComponent 3곳에서 (a) Scale의 형식 메타 `$type`(MOD.Core.MODVector3) 제거, (b) 기본값 Rotation(0,0,0)·ZRotation 0 명시 추가뿐이다. Position(-1.5/0/1.5, 0.98, 0)·Scale(25,25,1)·QuaternionRotation·Enable·컴포넌트 목록·path/id 등 값은 동일하다. 의도하지 않은 의미 차이 없음 → Maker 재저장 형식 차이로 판정, 그대로 둔다.
- RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model: 차이 0건(의미 동일).
- RootDesk/MyDesk/Models/MapObjects.directory: StudioVersion `""` → `"0.1.0.0"` 한 곳뿐(나머지 동일).
- 세 파일은 되돌리거나 직접 수정하지 않았다. map·model은 54경로 Bundle 대상이라 지문이 1447ff8과 달라졌다.

### 결정 사항 (Plan이 coder에게 맡긴 항목)
- 동률 칸 선택(ANY): 플레이어 WorldPosition.x와 BattlePos 3칸 x의 거리가 가장 작은 칸. 거리가 같으면(차이 1e-6 이하) 중앙(2)→왼쪽(1)→오른쪽(3) 순서로 먼저 본 칸을 유지한다. 같은 입력은 항상 같은 칸이다. 실제 간격(-1.5/0/1.5)의 중간점에서 -0.750→2, -0.760→1, -0.740→2, 0.750→2, 0.760→3.
- ANY 영역 표현: CSV AreaFromAnchor=AreaToAnchor=0. 로더는 ANY에서만 0/0을 허용하고, ANY의 0이 아닌 값과 LEFT/RIGHT/GUARD의 0 또는 범위 밖·역전 값은 전체 거부한다.
- LandingAnchor: 열을 CSV에서 제거하고 로더 필수 열·검증에서도 제거했다(무시가 아니라 제거). 착지는 데이터가 아니라 모션이 영역에서 도출하므로 데이터와 모션이 어긋날 수 없다. 다른 코드의 참조는 PrepareAttack의 `landing` 하나뿐이었고 함께 제거했다.
- Weight: 필수 열, 유한한 양수만 허용(누락·빈 값·숫자 아님·0·음수·NaN/무한대는 카탈로그 전체 거부·1회 경고). 선택은 MonsterAttackComponent.SelectPattern(rows, unit): r=unit×가중치 합, CSV 행 순서 누적, r<누적합인 첫 행, 끝까지 못 고르면 마지막 행. unit은 PrepareAttack에서 math.random()을 넘긴다(프로브가 경계 난수를 직접 넣을 수 있도록 분리). 판정 규칙·수치가 아니라 선택 방식만 바뀌었다.
- 저스트 방향 집합: 실행 스냅샷에 validDirs({LEFT=true}/{RIGHT=true}/ANY는 고정 칸에서 멀어지는 방향/GUARD는 빈 집합)를 고정하고 PlayerHealthComponent.EvaluateDefense(5번째 인자)가 `validDirs[evade.EvadeDirection]`과 0.20초 창으로 JUST를 판정한다. LEFT/RIGHT도 같은 집합을 쓰도록 통일해 가드 분기와 창 경계는 byte 불변이다. ANY: Pos2 조준 {LEFT,RIGHT}, Pos1 {RIGHT}, Pos3 {LEFT}.
- ANY 탈출 검증: 유효 방향마다 도착 칸(LEFT=조준 칸-1, RIGHT=조준 칸+1)에 선 플레이어 콜라이더(오프셋 절댓값+반폭, 좌우 반전 대비)가 고정 칸 영역 [x-0.5, x+0.5]을 완전히 벗어나는지 확인하고 실패하면 시작하지 않고 1회 경고한다. 현재 간격·패딩(반폭 0.25, 오프셋 0)에서는 모두 통과한다(중단 조건 아님).
- 공통 계층과 모션의 역할: MonsterAttackComponent는 스냅샷 area={cells("010" 형식), minX, maxX}만 만들고 Monster_Attack이 PerformAttackMotion(string cells, number minX, number maxX)로 모션 담당에 넘긴다. 영역 중앙 착지((minX+maxX)/2)는 OrangeMushroomAttack 안에만 있다. 로더·MonsterAttackComponent에는 착지점 규칙이 없다. 보스용 다중 이펙트는 이 cells를 쓰는 별도 모션이 맡는다(떨어진 칸·칸별 다중 타격 형식은 구현하지 않음).
- 예고 문구(.ui 무변경, CombatInputController): ANY는 "방향 무관 회피 [좌·우]"로 표시하고 속성 접두·접미는 기존과 같다(예: 일반 · 방향 무관 회피 [좌·우] / 가드, 특수 · … · 가드 불가, 패링 · … / 정확히 가드). 끝 칸 조준 시 실제 유효 방향은 한쪽뿐이지만 문구는 일반형으로 두고 칸 표시(F01)가 조준 칸을 알린다. 아이콘 등 .ui 요소는 필요하지 않다고 판단했다.

### 변경 파일
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | 8행→9행(가드형 2행 제거, ANY 3행 추가), LandingAnchor 열 제거, Weight 열 추가(모두 1). BOM·CRLF 유지. .userdataset 무변경 |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | ANY 응답 허용, 앵커 0/0 규칙, Weight 검증, LandingAnchor 제거 |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | SelectPattern·FindNearestCell 추가, ANY 칸 고정·영역·유효 방향·탈출 검증, 스냅샷 area/validDirs/targetCell, landing 제거, 텔레그래프 [VRF]에 target·dirs 추가 |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | EvaluateDefense에 validDirs 인자 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 모션 호출을 영역 전달로 변경 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | PerformAttackMotion 시그니처(cells, minX, maxX) |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 영역 중앙 착지(주황버섯 한정) |
| RootDesk/MyDesk/UI/CombatInputController.mlua | ANY 예고 문구 |
| map/map01.map, RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model, RootDesk/MyDesk/Models/MapObjects.directory | 이번 회차에 수정하지 않음. Maker 재저장 형식 차이만(위 비교). Bundle에는 map·model이 들어 있어 지문만 달라짐 |

### 실제 기본 검증 (Maker MCP, Play 2회: 최초 Play 통합 + 예고 도중 Stop 뒤 재Play)
- 빌드: Refresh 2회. 첫 build 로그에 Monster_Attack의 `LEA-1102 number PerformAttackMotion(Entity target)`(시그니처 변경 직후 낡은 결과)가 있었고, 호출 파일에 주석만 고쳐 다시 Refresh하자 사라졌다. 이후 build 로그 80건 모두 Info(LIA 1114/1115 동적 참조 노이즈), 오류 0·경고 0.
- 방법: 모든 판정 경로는 Play 내부 server_main 프로브가 제품 경로(PrepareAttack→Monster_Attack→ResolveAttack→EvaluateDefense→네이티브 AttackFast→HitEvent)를 그대로 실행하게 했다. 패턴 목록을 단일 행으로 교체하고 몬스터 상태를 ATTACK으로 보냈으며, 저스트/패링 입력은 회피 방향·시작 시각, 가드 시작 시각 필드를 판정 전에 기록했다. 가드·좌우 홀드는 클라이언트 PlayerStateControl.RequestChangeState("…","probe.…")로 실제 입력 수락 지점을 거쳐 걸었다(키보드 이벤트가 아님). 대표 실제 키 입력은 maker_keyboard_input LeftArrow 1회(아래 K1b). 시험값(AttackInterval 9999, 단일 행 교체, K1b의 JustWindowSec 4.0, 선행 4~6초)은 모두 Play 내부이며 Stop으로 폐기했다. CSV는 시험용으로 바꾸지 않아 원복할 것이 없다.

| 항목 | 결과 |
| --- | --- |
| 로드(V01·V09) | `catalog ready rules=1 patterns=9`, 9행 id·유형·속성·앵커·Weight=1 확인, 가드형 0행, LandingAnchor 값 nil. 재Play에서도 동일 |
| 검증 거부(V09, ValidateRows 시험 행 19건) | 허용 4건(LEFT, ANY 0/0, GUARD 일반, GUARD 패링)은 통과. Weight 누락·빈 값·abc·0·-1·nan·inf·1e999, ANY 1/1, ANY 0/2, LEFT 0/0, 역전 3/2, SPECIAL+GUARD, 잘못된 유형, 선행 시간 부족, 중복 id는 모두 거부되고 거부마다 경고 정확히 1회. 열 누락(`NoSuchColumn`)은 ReadRows nil, 실제 CSV의 Weight 열은 9행 읽힘 |
| Weight 선택(V09) | 9행 균등 가운데값 (i-0.5)/9 → 1~9행 순서대로 선택. 경계 u=0·1/9-1e-9→normal.left, 1/9+1e-9→special.left, 2/9+1e-9→parry.left, 1-1e-12·1.0·1.5→마지막 행(parry.any). 가중치 1,2,3 행: u=0·0.1666→w1, 0.17·0.49→w2, 0.5·0.9999→w3, 1.0→마지막 w3. math.random 900회: 9행 각 82~118회(전부 선택됨), 200회 16~30회 |
| 동률 규칙 | anchors -1.5/0/1.5: -1.5→1, 1.5→3, 0→2, -0.750→2(동률), 0.750→2(동률), -0.760→1, -0.740→2, 0.760→3, ±9→끝 칸 |
| 2칸 착지(V01) | normal/special/parry.left 착지 x=0.75, .right는 -0.75(두 칸 중간). 판정 시각 hitDt≈0.50~0.52초, JumpDuration 0.5, 피해 12=HitEvent 합계 12 |
| ANY Pos2 조준(플레이어 x=0) | tgt=2 cells=010 영역 -0.5~0.5 dirs=LR 착지 x=0.0. 무대응 HIT 피해 12(=HitEvent 12). 일반 LEFT/RIGHT 저스트 각각 JUST·피해 0·슬로우 ≈2.0초·반격 true. 창 밖 이른 입력(0.45초 전)은 HIT 12. 특수·패링 속성도 JUST |
| ANY Pos1 조준(LEFT 홀드, x=-1.5) | tgt=1 cells=100 영역 -2.0~-1.0 dirs=R 착지 x=-1.5. 무대응 HIT 12, RIGHT 저스트 JUST 0(특수도), 조준 칸 쪽 LEFT는 HIT 12(저스트 아님), 패링 속성 무대응 HIT 12 |
| ANY Pos3 조준(RIGHT 홀드, x=1.5) | tgt=3 cells=001 영역 1.0~2.0 dirs=L 착지 x=1.5. 무대응 HIT 12, LEFT 저스트 JUST 0(패링 속성도), 조준 칸 쪽 RIGHT는 HIT 12 |
| 가드 분기(ANY, 아래 홀드) | 일반+가드=GUARD 피해 4(12×0.4 내림, =HitEvent 4), 특수+가드=HIT 12(가드 불가), 패링+창 안 가드=PARRY 0·반격 true·그로기 진입(2.5초 뒤 IDLE, 판정 0.5+복귀 0.5+그로기 1.5), 패링+창 밖 가드=GUARD 4 |
| 가드형 시험 데이터(V01 "시험 데이터 근거", 제품 CSV 밖의 Play 내부 단일 행) | 영역 -2~2 cells=111 착지 x=0.0, dirs 빈 집합. 일반+가드=GUARD 4, 패링+창 안 가드=PARRY 0·그로기, 패링+창 밖=GUARD 4. 기존 판정과 같음 |
| LEFT/RIGHT 회귀 | 올바른 방향 회피 JUST 0, 반대 방향(RIGHT 행에 LEFT 회피)은 HIT 12, 무대응 HIT 12 |
| 실제 키 입력 + 예고 뒤 이동(V03, K1b) | ANY(선행 4.0초, 시험 한정 창 4.0)를 Pos2에 조준한 뒤 maker_keyboard_input LeftArrow 홀드: tgt=2 cells=010 영역 -0.5~0.5가 판정 때까지 불변, 플레이어는 판정 순간 x=-1.5로 이동해 영역 밖 → 피해 0·HitEvent 없음, kind=JUST·슬로우 1.967·반격 true. 창을 확대하지 않은 첫 시도(K1)는 입력이 사례 시작 직후(창 밖)라 kind=HIT(저스트 아님)·피해 0(영역 밖)·같은 칸 고정이었다 |
| 탈출 검증 실패(V01) | 시험 행 AreaPaddingX=2.0의 ANY: 시작 거부, `telegraph escape area invalid: normal.any` 경고 1회, AttackSequence 불변, 몬스터 IDLE 유지, 칸 표시 없음 |
| 팝업 중 ANY 예고(V07) | 선행 6.0초 예고 중 팝업을 열어 전투 시계 346.829가 고정(샘플 3회), cells=010·resp=ANY·remaining 5.262 불변. 닫은 뒤 이어서 진행해 hitDt=6.003, HIT 12=HitEvent 12 |
| 예고 도중 Stop→재Play(V08) | 재Play 직후 TelegraphCells='' · Response='' · remaining 0 · pause false · AttackInterval 3.0 · 패턴 9행 · JustWindow 0.2 · evade '' · 반격 false · AttackSequence가 새로 시작(이전 값 비계승, 자연 공격 4회 뒤 4). 클라이언트 BattlePosMark 1~3은 ANY 예고 중 2번만 켜짐(cells=010), 판정 뒤·종료 뒤 모두 꺼짐 |
| 자연 공격 | 최초 Play에서 선택된 7회 가운데 ANY·LEFT/RIGHT가 섞여 나오고 모두 정상 판정·HUD 피드백이 났다 |

### 실패/미확인/미실시
- 프로브 오류와 제품 오류의 구분: 예고 도중 Stop한 프로브의 폴링 타이머 때문에 `LEA-3051 MemoryLeak`(MakerScript 라인) 1건이 났다. 시험 스크립트 문제이며 제품 오류는 관측되지 않았다. 팝업 시험에서 클라이언트 타이머가 팝업 정지로 멈춰 첫 시도가 무산돼 직접 호출로 닫았다(제품 문제 아님).
- 사람 손 타이밍의 0.20초 창 성공은 AI로 재현하지 않았다(저스트 입력은 시험 한정 창 확대 또는 필드 기록). 체감·가독성은 V11 몫이다.
- V04(ANY 성공의 반격 권한 부여는 확인, 소비·만료 경계는 기존 QA 근거 범위), V05(슬로우 ≈2.0초 부여는 확인, 전 구간 적분 재시험 안 함), V06(패링 그로기 진입·종료는 확인, 복귀 중 피격·팝업 조합은 재시험 안 함), V08(플레이어/몬스터 사망·다른 맵 전환 미실시), V10(UI 버튼 전 조합·동시 입력 미실시), 모바일 화면, 화면 육안(칸·예고 문구 색, 2칸 중간 착지 모션 모양)은 미실시다. V12 외부 환경은 NOT_RUN 유지.
- 끝 칸 ANY 난이도(방향 홀드 중에는 중앙 복귀로만 피함 → 저스트 보상 없음)는 Plan §15 설명대로 구현했고 체감 평가는 사용자 V11이다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) 로드·검증 거부·Weight 선택(경계 난수, 필요하면 임시 CSV 시험 후 원복), (2) ANY Pos1·Pos2·Pos3 조준과 유효 방향 집합·범위 밖 EVADE·무대응 HIT, 실제 키 입력, 예고 뒤 이동 불변, (3) 가드·패링·그로기 분기와 새 착지점에서의 복귀, 슬로우·반격 권한, (4) 2칸 착지 중간 위치, 가드형 시험 데이터, (5) 팝업·Stop 회귀와 F01 칸 표시, F02~F05 회귀(공유 경로). 사용자 V11 재확인(1칸 공격 구별·난이도, 2칸 중간 착지 모션, F01~F04)과 V12는 AI 결과로 대신하지 않는다.

### 2026-11-03 최종 제품 버전 묶음 (V11-F06)
- 이전 묶음(d2b57802…0fbb, 54경로)과 같은 경로 집합·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)이다. 1447ff8을 같은 방법으로 재계산해 d2b57802…0fbb 일치를 확인한 뒤 작업트리를 계산했다. 변경된 경로는 10개: MonsterAttackPatternData.csv, CombatRuleCatalog.mlua, AttackAreaMark.model·map/map01.map(Maker 재저장 형식 차이, 위 비교), Monster_Attack.mlua, MonsterAttackComponent.mlua, MonsterAttackMotion.mlua, OrangeMushroomAttack.mlua, PlayerHealthComponent.mlua, CombatInputController.mlua. 나머지 44개는 이전과 같다. .codeblock·.directory는 대상 외다.
- Bundle SHA-256: b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | fd557b85435ee92bd2616db605d5ce88a27c1a16e79e058eb9af7fa15cf49cd5 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 9c0e9b5bbc2ba588e021aeca0ac9f9dcaacdc6223ddae17ea955dcf2c8544907 |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | bf287ec4e51466a827b9093d58e052c7e0eb6fe5bd22e43fcd8aa00b286c7020 |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model | 965f107350f59e76497a1b0a3b16cad58c11bdeaf594157e76e5b480f3f3fa29 |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | 1b7686acda7c84412676a7157681156cbef5f693e4b3c0872d609c5cf61c3b9d |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 9c04d255fd0af81b42eb798c1e39af2b3e3de7241621504d8490d7783d06fb62 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 9ef869fadce5fe12a111df55d4bf6a78812dcc5e74cc9a18567a4a523c252574 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | e54d144379d8b30f9510295754388faca43c124d1d52590e9257feb46e4b4691 |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 69ad2f52be603d7fedde3223678094968d859cd209f9771895ab1175ce29e3c9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 88a738ebc9f5aa7b4b78d74e4164a4f103cfff690fc7e1ccbb2ce2bde5035518 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | ebbe5f75a580523619c35729f4965ea170deef0e82b8cbc4f2443d229f90d612 |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | ede3e85448ba374cd288332c1727ff9f34fdcb995767de150d888845b230bc71 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | c66b26266b3a57ebcaae08d481b4bd296183f6c5e1f1e455eeaa83b7c3a6dded |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 02e41f3c81c09e95c49e0eb69c05e0d80d1f04845112be62d78cdda638250125 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |

## 2026-11-03 coder V11-F08·F09 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §16의 CombatCore-V11-F08(그로기 중 hit 모션 실제 표시)·V11-F09(예고 문구 제거·칸 속성색)뿐이다. 규칙·수치(0.20, ×0.40, 반격, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8), CSV·DataSet, 9패턴·Weight, D01~D04, 서버 상태 흐름(IDLE/HIT/ATTACK/STUN/DEAD)과 HitComponent·MonsterHealthComponent의 HIT 진입 조건, 주황버섯 ActionSheet 값, 결과·상태 문구(defenseText·counterText·effectText), .ui·.map·모델, V11-F07, 3단계는 바꾸지 않았다. 새 클립·자원은 쓰지 않았다(기존 hit 클립 RUID aec950… = ActionSheet "stun"·"hit").
- 기준 버전: 커밋 b89de46. 같은 방법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)으로 b89de46의 54경로를 git show로 재계산해 b985aa4b…4dbf 일치를 확인했다. 시작 시 작업트리 Bundle은 b0019098…f5b0이었고 차이는 Maker 재저장 미커밋 3파일(아래)뿐이다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록; 이번에는 구조 파일을 바꾸지 않아 MapBuilder를 다시 읽지 않았다). Maker 로그 시각 14:29~14:43. **maker_clear_logs는 한 번도 호출하지 않았다.** 로그는 시각·`[VRF8]`(이번 회차 임시 계측 표지)·`[VRF]` 표지로 파일에 저장해 걸러 읽었다.
- 미커밋 Maker 재저장 3파일(AssistModel.userdataset·AttackSkillData.userdataset의 CoreVersion 한 줄, 주황버섯 모델의 형식 버전·부동소수 표기·스크립트 기본값 직렬화)은 되돌리거나 건드리지 않았다. **주황버섯 모델을 빌더로 다시 쓰지 않았다**(F08은 .mlua로 해결, 모델 무수정). 따라서 이 세 파일은 이번 변경이 아니며 지문에는 포함된다.

### V11-F08 원인 확정 (실측)
- 방법: 패링(가드 시작이 타격 0.12초 전, 패턴 단일 행 교체) → 복귀 → 그로기 → IDLE을 서버 프로브(상태·SpriteRUID·isStunned·GroggyRemaining)와 소유 클라이언트 프로브(StateComponent.CurrentStateName·SpriteRendererComponent.SpriteRUID·PlayRate·AnimationClipEvent·StateChangeEvent)로 같은 시간축(ServerElapsedSeconds)에 기록했다. 클라이언트에서 "화면에 실제로 보이는 값"을 읽는 API는 없다(SpriteRendererComponent.ClipName은 deprecated로 항상 빈 문자열, SpriteRUID는 서버 쓰기만 따라가고 AnimationClipEvent는 속성을 바꾸지 않는다). 그래서 실제 표시는 play 카메라 스크린샷(maker_screenshot)에서 몬스터 영역 픽셀을 IDLE(stand) 기준 영상과 비교해 판정했다(같은 위치·정지 프레임이면 차이 평균 0, 고통 얼굴 hit 끝 프레임은 차이 ≈78~80, 중간 프레임은 ≈50, 확대 그림과 눈으로 대조).
- 관측 1 (이벤트 vs 속성): IDLE에서 서버 ChangeState("HIT")만 해도 클라이언트에 ACE clip=hit가 오지만 SpriteRUID는 stand로 그대로다(IDLE→HIT 0.5초 사이 stand 유지). 그로기 진입도 같다: ACE clip=stun(=hit RUID) 직후 클라이언트 SpriteRUID는 stand(복귀 완료 CompleteMotion이 쓴 값)였다.
- 관측 2 (화면): ApplyGroggy(30)을 IDLE에서 바로 준 경우(SpriteRUID 변화 없음) 직후 스크린샷은 hit 중간 프레임(차이 49.8)이고, 같은 방식의 그로기 중 플레이어 실제 ↑ 공격 뒤(약 2초 후) 스크린샷은 stand(차이 4.25)였다. 실제 패링 흐름(복귀→그로기, 그로기 연장 30초)의 그로기 중 스크린샷도 stand(차이 0.85)였다. 서버가 SpriteRUID에 hit 클립을 직접 쓴 경우(IDLE 시험)는 직후 0, 이후 세 장 모두 78.57 고정(고통 얼굴 끝 프레임을 유지)이었다.
- 관측 3 (피격 중 클라이언트 상태): 그로기 중 플레이어 ↑ 공격에서 서버 상태는 STUN을 유지하지만 클라이언트 로컬 상태가 STUN→HIT로 바뀌고 ACE clip=hit가 한 번 나온 뒤 서버 그로기 종료(ACE stand, HIT→IDLE)까지 HIT로 남았다(자동 IDLE 복귀 없음, 화면은 이미 stand).
- 확정: 원인은 Plan 후보 3·4의 변형이다. ActionSheet "stun" 키·RUID는 정상(stun=aec950…, 그로기 진입마다 ACE clip=stun)이지만 hit는 짧은 비반복 클립이라 상태 이벤트로는 한 번 재생된 뒤 렌더러 기본 표시(SpriteRUID=stand)로 돌아간다. 그로기 1.5초 동안 hit 모습이 남지 않으며, 복귀 완료 직전 서버가 stand를 써 두는 것도 같은 결과로 이어진다. 후보 2(클라이언트 로컬 HIT)는 관측됐지만 stand 복귀 원인이 아니라(자동 IDLE 없음) 결과를 바꾸지 않는다. 후보 1(동기값 덮어쓰기 순서)은 단독으로 분리해 확인하지 않았다(위 설명만으로 모든 관측이 설명된다).

### V11-F08 수정 (최소 범위, .mlua 한 곳)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | SetStunned(boolean)에서 그로기가 켜지면 기존 MonsterAttackMotion.SetVisualClip("stun")으로 서버 표시 클립을 ActionSheet "stun"(=hit RUID)로 고정하고, 실제로 그로기였다가 꺼질 때 stand로 되돌린다(사망으로 끝나면 "die"를 남긴다, health.IsDead는 ApplyDamage가 상태 변경 전에 먼저 true로 둔다). 그로기가 아니던 SetStunned(false) 호출(공격 취소·정리)은 아무것도 쓰지 않는다. 복귀 중 jump(JumpToLocalX)·CompleteMotion의 stand 쓰기는 그대로라 그로기 시작 시점에만 hit로 바뀐다. 상태 규칙·타이머·서버 HIT 진입 조건·ActionSheet 값·모델은 무변경. |
- 모션 클래스가 없거나 유효하지 않으면 아무것도 하지 않는다. 새 Sync 값·새 RUID 없음.

### V11-F08 수정 후 확인 (Play 내부, 서버·클라이언트 동시 기록)
| 조건 | 결과 |
| --- | --- |
| (a) 피격 없는 실제 흐름(자연 1.5초) | 서버 상태 ATTACK(jump)→STUN 14.04에 SpriteRUID hit(stun) + 클라이언트 같은 시각 ACE clip=stun, 클라이언트 SpriteRUID hit(stun) 유지 → 그로기 1.5초 뒤 서버 IDLE\|stand, 클라이언트 ACE clip=stand·IDLE\|stand. 복귀 중에는 jump 유지(ATTACK\|jump), 그로기 시작 시점에만 hit. 스크린샷(그로기 연장 중): 고통 얼굴 hit 프레임 유지 |
| (b) 그로기 중 실제 ↑ 공격 | 클라이언트 STUN→HIT(ACE clip=hit 1회) 뒤에도 SpriteRUID hit(stun) 유지, 공격 이펙트·피해 숫자와 함께 스크린샷 모두 hit 프레임. 그로기 종료 뒤 스크린샷 stand. 서버 상태 STUN 유지·GroggyRemaining 감소(조기 해제 없음)·몬스터 HP는 HitEvent 경로(수동 공격 10타씩) 그대로 |
| (c) 슬로우 겹침(ApplySlow 8초×0.5) | PlayRate 0.5가 되었으나 SpriteRUID hit(stun) 유지, 스크린샷 hit. 서버 그로기 기한은 전투 시간 기준 그대로 |
| 그로기 중 사망(ApplyDamage 999) | 서버 STUN→DEAD, isStunned false, SpriteRUID die. 클라이언트 ACE clip=die·SCE HIT→DEAD, 스크린샷은 die 프레임이 고정(HP 0). die가 hit보다 우선한다 |
| 2칸 패턴(parry.left) 복귀 중 팝업(V06·V07) | 판정 PARRY 직후 x=0.75에서 팝업 → 서버 paused 5초 동안 ATTACK\|jump 유지·위치 고정 → 닫은 뒤 복귀가 이어져 STUN 진입 시 hit(stun)로 바뀌고 1.5초 뒤 IDLE\|stand |
| Stop 뒤 재Play(V08) | (1) 그로기(30초) 중 maker_stop → 재Play: 몬스터 IDLE·SpriteRUID stand·isStunned false·GroggyRemaining 0·ParryEffect (0,0,0)·칸 표시 없음·패턴 9행·AttackInterval 기준값. (2) 2칸 패턴(parry.right) 복귀 중 팝업 정지(x=-0.75)에서 maker_stop → 재Play: paused false·칸·응답·반격 false·패턴 9행·플레이어 IDLE, 팝업 닫힘, 클라이언트 IDLE·stand·칸 표시 없음. 런타임 오류 로그 없음 |
- HP=HitEvent=숫자(V02 대표, 제품 경로): 일반 무대응 HIT 12/12, 저스트 JUST 0/0, 가드 GUARD 4/4(12×0.4=4.8→4), 패링 PARRY 0/0 후 그로기 진입(V03 대표 경계). 이번 변경은 이 경로에 관여하지 않는다.

### V11-F09 변경
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 공격 예고 문구(telegraphText) 계산 블록을 삭제하고 항상 빈 문자열("", 흰색)로 둔다. .ui 엔티티·바인딩은 그대로(.ui 무변경). defenseText·counterText·effectText(저스트 회피 성공·패링 성공·가드·피격·회피·반격 준비·상대 그로기·슬로우)는 문구·색·지속 그대로 |
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 칸 색을 서버 동기 MonsterAttackComponent.TelegraphAttribute로 정한다: NORMAL (1, 0.85, 0.4) / SPECIAL (1, 0.43, 0.36) / PARRY (0.88, 0.65, 1), 알파는 기존 CellAlpha 0.45. 표시 캐시는 켜짐 여부와 속성을 함께 비교해(같은 칸에 속성이 바뀐 연속 공격도 새 색 반영) 속성 값이 달라질 때만 FillColor한다. 켜져야 하는데 속성이 세 값이 아니면(빈 값·동기화 순서 차이 포함) 그 칸을 숨기고, 0.25초를 넘겨 계속되면 `[VRF] AttackAreaMark unknown attribute` 한 번만 남긴다. 기존 단일 빨강(1, 0.12, 0.12)은 더 쓰지 않으며 투명 기본색은 (1,1,1,0). 칸 선택(TelegraphCells)·켜는 시점·끄는 조건은 F01과 같다(MonsterAttackComponent 무변경 — 같은 실행의 속성 동기값이 칸 정보와 함께 PrepareAttack에서 설정됨을 확인) |
- 확인(Play 내부): (1) 9패턴 각각을 제품 경로로 한 번씩 실행(패턴 단일 행 교체): 클라이언트 칸 속성 표시 normal.left -NN / special.left -SS / parry.left -PP / normal.right NN- / special.right SS- / parry.right PP- / normal.any -N- / special.any -S- / parry.any -P-(서버 TelegraphCells 011·110·010과 일치), 모든 구간에서 telegraphText.Text는 빈 문자열, 판정 뒤 칸이 꺼졌고 결과 문구(피격)는 이전처럼 표시됐다. (2) 가드형 시험 데이터(Play 내부 단일 행, 칸 111·예고 40초): NORMAL·SPECIAL·PARRY 순으로 켜 스크린샷의 칸 픽셀을 배경(칸 없는 같은 프레임)과 알파 0.45로 역산해 색을 확인했다 — 노랑 (1, 0.85, 0.4)·적색 (1, 0.43, 0.36)·보라 (0.88, 0.65, 1)가 세 칸 모두에서 오차 ±0.01로 일치("시험 데이터 근거"). 같은 칸 연속 공격에서 속성이 NORMAL→SPECIAL→PARRY로 바뀌면 칸이 계속 켜진 채 새 색으로 갱신됐다. (3) 속성 미상: 서버에서 TelegraphAttribute를 "XYZ"로 바꾸자 칸 픽셀이 배경과 같아져(숨김) 확인했다. (4) 2칸 패턴 복귀 중 팝업·Stop·재Play 뒤 칸 표시 없음(위 표).

### 실제 기본 검증 요약
- 빌드: Refresh 후 build 로그 81건 모두 Info(LIA 동적 참조 노이즈, 앞 회차와 같은 유형), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음.
- Play 5회(최초 통합 계측·수정 전 원인 실측 / 수정 후 통합 확인 / 9패턴·팝업·Stop 회귀 / Stop 뒤 재Play 기본값 2회). 모든 Play는 maker_stop으로 닫았고 시험값(AttackInterval 9999, 패턴 단일 행 교체, 그로기 연장 6~60초, 슬로우 8초, 예고 40초, 플레이어 HP 보충, 속성 "XYZ")은 Play 내부에만 두었다. 재Play에서 패턴 9행·AttackInterval 기준값·규칙값 정상.

### 프로브 오류와 제품 오류의 구분, 관찰
- 시험 스크립트 문제: (1) 이전 몬스터를 폴링하던 클라이언트 프로브가 DoSpawn(교체) 뒤에도 돌아 `LEA-2007 nil StateComponent`를 약 370건 냈다(14:38:38~52, 제품 오류 아님). (2) Stop 때 남은 클라이언트 프로브 타이머로 `LEA-3051 MemoryLeak(MakerScript)` 1건(14:42:06). (3) Stop과 같은 순간에 찍은 서버 로그 한 줄(T2)은 Play 정리가 시작돼 상태가 흔들려 읽혔다 — 같은 조작을 Stop 없이 다시 실행해 정상 값(그로기 켜짐 시 SpriteRUID hit)을 확인했다. 제품 runtime 오류·경고는 관측되지 않았다.
- 관찰(이번 범위 밖, 바꾸지 않음): 수정 전 기준선에서 IDLE의 몬스터가 사망하면(DEAD) 화면이 die가 아니라 stand 프레임으로 보였다(die 클립도 비반복이라 끝난 뒤 기본 표시 stand로 돌아가는 것으로 보이며, 스크린샷 차이 0·HP 0/100). 이번 변경 이후 그로기 중 사망은 die가 고정되어 표시가 다르다. 일반 사망의 die 유지 여부는 사용자 확인(V11) 또는 별도 결함 후보로 판단한다.
- 클라이언트 로컬 HIT: 그로기 중 피격 시 클라이언트가 STUN→HIT로 보이는 구조는 그대로다(서버 상태는 STUN). 화면은 hit 고정이라 문제 없다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 문구 없이 칸 위치·색만으로 방향·속성 구별과 노랑·적색·보라 칸 가독성, 그로기 hit 모션이 실제 눈에 어떻게 보이는지(여기서는 스크린샷 픽셀·프레임 대조), 별·접촉 파티클, 좌·우 UI 버튼 전체 면적(실기기·터치), 사람 손 0.20초 창 타이밍, Weight 체감. V12 외부 환경, V09 CSV 파일 변경 반영, 플레이어 사망·다른 맵 전환, 모바일 화면, 속성색의 색약 접근성은 미실시.
- 스크린샷 해상도(558×314)와 간격 한계: hit 프레임 유지는 연속 스크린샷 3~4장과 클라이언트 SpriteRUID·이벤트 시계열로 확인했다. 1.5초 전체를 연속 프레임으로 녹화한 것은 아니다. 짧은 자연 그로기(1.5초)의 육안 확인은 도구 왕복 시간 때문에 연장 그로기(시험값)로 대신했고, 자연 1.5초는 클라이언트 SpriteRUID 시계열로만 확인했다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F08 세 조건(피격 없음·그로기 중 실제 ↑ 공격·슬로우 겹침)에서 그로기 전체 구간 hit 표시, 종료 뒤 stand, 복귀 중 jump, 사망 시 die — 클라이언트 SpriteRUID 시계열(상태·ACE와 같은 시간축)과 스크린샷 두 방식을 함께 쓰고 기존 이벤트 근거만으로 PASS 하지 않는다. (2) F09 9패턴 칸 색·예고 문구 없음·결과 문구 유지·속성 미상 숨김·가드형 시험 데이터, 팝업 중 유지·사망·Stop 뒤 잔존 없음. (3) 회귀 V02·V03 대표, V06(복귀 중 jump 유지)·V07·V08(2칸 패턴 복귀 중 팝업·Stop 포함), V10 대표. 주의: maker_clear_logs를 호출하지 말고 시각·표지로 구분해 읽는다(로그가 매우 커서 파일로 저장된 분량을 걸러 읽는 것이 편하다). SetStunned 변경이 그로기 정리 경로(ClearOpponentExecution·OnMapLeave·OnEndPlay·사망)에서도 stand/die를 쓰므로 이 경로들(상대 교체·Stop·맵 이탈)의 표시 잔존 여부를 함께 본다. 육안·V11·V12는 사용자 몫이다.

### 2026-11-03 최종 제품 버전 묶음 (V11-F08·F09)
- 이전 묶음(b985aa4b…4dbf, 54경로)과 같은 경로 집합·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)이다. b89de46을 같은 방법으로 재계산해 b985aa4b…4dbf 일치를 확인한 뒤 작업트리를 계산했다. b89de46 대비 변경된 경로는 6개로, 이번 변경 3개(AttackAreaMarkComponent.mlua·MonsterStunComponent.mlua·CombatInputController.mlua)와 Maker 재저장 3개(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번에 수정하지 않음)다. 나머지 48개는 b89de46과 같다. .codeblock·.directory는 대상 외다.
- Bundle SHA-256: 377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363.
- 변경 경로 SHA-256: Combat/AttackAreaMarkComponent.mlua 09df43555df7528ef68043d44c4927183401c878f09aa63cedaf6695fa8b495f · Monster/MonsterStunComponent.mlua 165d8b5ec9bff3bbbb2b0feda73cfb42a53141f55657a5772b97efafac27cd34 · UI/CombatInputController.mlua 5e42865cdf8b15813aa2a5a8a47bd26b3587fa1387152735ae76a4e1a7bec21d · Models/Monsters/주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · @Assist/DataSet/AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 48경로 해시는 이전 묶음(V11-F06) 표와 같다.

## 2026-11-03 coder REV-F02·V11-F10·V11-F11 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §17의 CombatCore-REV-F02(모든 사망 경로 die 고정)·V11-F10(주황버섯 패턴 4행 재구성, CSV `AreaTarget` 열, RANDOM 대상 칸)·V11-F11(특수 가드 "가드 불가" 문구)뿐이다. §18(머쉬맘 전환)은 하지 않았다(이름·리소스·모델 무변경). 규칙·수치(0.20, ×0.40, ×2.2, 2.0초, ×0.5, 1.5초, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8), D01~D04, 입력 규칙, .ui·.map·몬스터 모델, 새 자원, 3단계, V11-F07은 바꾸지 않았다.
- 기준 버전: a921c76. 같은 방법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, F06 절 manifest 54경로)으로 a921c76 커밋 트리를 재계산해 리뷰가 기록한 38e7aa22…0ba53과 일치함을 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록; 구조 파일 무변경). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 파일로 저장해 시각·`[VRF9*]` 표지로 걸러 읽었다.
- 미커밋 Maker 재저장 3파일(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델)은 되돌리거나 건드리지 않았다. MonsterAttackPatternData.userdataset은 CSV 변경·Refresh·Play·Stop 뒤에도 Maker가 바꾸지 않았다(SHA-256 59bba898…e888 그대로, git status에도 안 뜸).

### 변경 파일 (6개, .codeblock·.directory·.userdataset·모델·맵·.ui 변경 없음)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | 9행을 4행으로 교체하고 마지막에 `AreaTarget` 열 추가(BOM·CRLF 유지). parry.left(LEFT·PARRY·2~3·Weight 2·FIXED), parry.right(RIGHT·PARRY·1~2·Weight 2·FIXED), parry.any(ANY·PARRY·0/0·Weight 2·NEAREST), special.random(ANY·SPECIAL·0/0·Weight 1·RANDOM). modelId castleenemy·AreaPaddingX 0.5·AreaHeight 1·AreaOffsetY 0.4·TelegraphLeadSec 0.5는 기존 값. normal.* 3행·special.left·special.right·special.any 제거 |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 필수 열에 AreaTarget 추가(열 누락은 기존 ReadRows 규칙으로 전체 거부). ValidateRows에 AreaTarget 검증: FIXED·NEAREST·RANDOM 외(빈 값·알 수 없는 값·누락) 거부, ANY↔FIXED·ANY가 아닌 유형↔NEAREST/RANDOM 불일치 거부. 방식과 맞지 않는 앵커는 기존 검사(ANY는 0/0만, 그 밖은 1~3 정수·From≤To)로 거부. 기존 SPECIAL+GUARD·Weight 양수·TelegraphLeadSec 검사 유지 |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 공통 층에 `SelectRandomCell(unit)`(0 이상 1 미만 → max(1,min(3,floor(unit×3)+1))) 추가. PrepareAttack의 ANY 분기가 `AreaTarget == "RANDOM"`이면 `SelectRandomCell(math.random())`으로, 아니면 기존 FindNearestCell로 고정 칸을 정한다. 고정 칸·영역·cells·유효 방향은 기존대로 실행 스냅샷에 한 번 고정(예고 중 재선택 없음). modelId 분기·주황버섯 전용 규칙 없음 |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | EvaluateDefense의 가드 분기에서 SPECIAL이면 `{ kind = "UNGUARDABLE", rate = 1, success = false }`를 반환(F11). 피해는 원래대로 |
| RootDesk/MyDesk/UI/CombatInputController.mlua | UNGUARDABLE의 HUD 문구 "가드 불가"(색 1, 0.43, 0.36, 기존 1초 규칙) 추가. 다른 문구·색·지속 무변경, .ui 무변경 |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | ApplyDamage 사망 확정 경로에서 기존 MonsterAttackMotion.SetVisualClip("die")를 재사용해 서버 표시 클립을 die로 고정(REV-F02). 공통 층이라 OrangeMushroomAttack에는 넣지 않았다. 사망 뒤 늦은 stand 쓰기 경로(공격 취소·점프 완료·슬로우 복원·그로기 종료)는 기존 가드(IsDead 조건·CancelPendingAttack·DEAD 잠금)로 막혀 있음을 소스와 시험으로 확인해 추가 차단은 하지 않았다 |
- RecordDefense의 EVADE 대체 규칙은 그대로다. 결과 종류를 읽는 곳(ResolveAttack의 JUST·PARRY 분기, Monster_Attack의 PARRY 분기, RecordDefense, HUD)을 grep으로 확인했고 UNGUARDABLE이 어느 분기에도 걸리지 않는다(슬로우·반격 권한·그로기 없음).

### 실제 기본 검증 (Play 1회, Maker MCP + 서버/클라이언트 프로브. 시험 설정은 Play 내부에만 두고 Stop으로 정리)
- 빌드: Refresh 뒤 build 로그 81건 전부 Info(LIA 동적 참조 노이즈), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음.
- 로드(V09): `[VRF] CombatCore catalog ready rules=1 patterns=4`, 4행 id·유형·속성·앵커·Weight 2·2·2·1·AreaTarget FIXED·FIXED·NEAREST·RANDOM이 Refresh 뒤 런타임에서 읽힘. normal.*·2칸 특수 행 없음.
- 검증(ValidateRows 프로브, 실제 DataSet 행을 복사해 한 항목씩 변경, 같은 입력 두 번 호출): baseline ok/ok. 빈 값·알 수 없는 값(BOGUS)·필드 누락(nil)·ANY+FIXED·LEFT+NEAREST·RIGHT+RANDOM·RANDOM 앵커 1/1·NEAREST 앵커 0/2·FIXED 앵커 0/0·FIXED 앵커 3/2·SPECIAL+GUARD·Weight 0·Weight abc가 전부 REJECT/REJECT이며 경고는 항목마다 정확히 1건(두 번째 호출은 경고 없음, 경고 13건 = 거부 13항목). 열 누락: 실제 DataSet에 없는 열 이름을 요구한 ReadRows가 nil(전체 거부). CSV 파일 자체를 시험용으로 바꾸는 열 누락 시험(Stop·Refresh·재Play)은 하지 않았다(NOT_RUN).
- 패턴 선택(합 7): 경계 난수 0→parry.left, 1.999/7→parry.left, 2/7→parry.right, 2.001/7→parry.right, 3.999/7→parry.right, 4.001/7→parry.any, 5.999/7→parry.any, 6/7→special.random, 6.001/7→special.random, 0.9999999999→special.random. 누적 구간 [0,2)·[2,4)·[4,6)·[6,7)와 CSV 행 순서, 4행 모두 선택 가능.
- RANDOM 칸: SelectRandomCell 단위 0·0.3·0.3333→1, 1/3·0.34·0.6666→2, 2/3·0.67·0.9999999999→3. PrepareAttack를 플레이어 Pos2(x=0.0)에서 90회 호출한 분포 Pos1 32·Pos2 31·Pos3 27(위치 무관). 난수 고정(math.random 임시 교체, 시험 뒤 복원) 0.1/0.5/0.9: 칸 1→영역 -2.0~-1.0·cells 100·방향 R, 칸 2→-0.5~0.5·010·LR, 칸 3→1.0~2.0·001·L, 예고 TelegraphAttribute SPECIAL·cells 동기. 제품 경로에서도 special.random이 target 3(방향 L)로 선택된 예고가 1건 관측됨. 예고 중 영역·칸은 스냅샷 고정(PrepareAttack 한 번뿐). NEAREST 회귀: 플레이어 x=0에서 칸 2, FindNearestCell -1.4→1, ±0.75·±0.7→2, 1.4→3(F06과 같음).
- F10 판정(special.random, 제품 ATTACK 경로, 난수 고정, 시험 설정은 Play 내부): (플레이어 Pos2) 칸 2 무가드 kind HIT·rate 1·nativeHit true·HP 12 감소=HitEvent 12·HUD HIT. 칸 1(범위 밖) 무가드 nativeHit nil·HP 0·HUD EVADE. (실제 DownArrow 홀드, 플레이어 GUARD 상태) 칸 2 가드 kind UNGUARDABLE·rate 1·nativeHit true·HP 12=HitEvent 12·HUD UNGUARDABLE, 칸 1 가드(범위 밖) kind UNGUARDABLE이나 nativeHit nil·HP 0·HUD EVADE. 시험 데이터 근거로 NORMAL 속성 test.normal 행(칸 2)·가드: kind GUARD·rate 0.4·HP 4=HitEvent 4(12×0.4=4.8→4)·HUD GUARD. 패링·저스트 방향 판정 규칙은 이번 변경이 건드리지 않았고(validDirs 로직 무변경) 이번 회차에 다시 시험하지 않았다(NOT_RUN: RANDOM 저스트·패링 불성공 키 입력).
- F11 HUD(클라이언트 defenseText 폴링): 가드 홀드 중 UNGUARDABLE 판정 때 defenseText.Text가 "가드 불가"(색 1.00, 0.43, 0.36)로 바뀌고 약 1.0초(264.56→265.55) 뒤 비워짐. 무가드 피격은 "피격", [VRF] defense kind=UNGUARDABLE·HUD feedback=UNGUARDABLE 로그로 구분. 가드·회피 문구는 기존대로(시험 행에서 feedback GUARD 확인).
- REV-F02(서버 SpriteRUID 시계열 + 소유 클라이언트 SpriteRUID·상태 시계열, 각 시나리오마다 새 몬스터 DoSpawn 뒤 ApplyDamage(999)로 사망): 사망 시점(+0.0)부터 +0.2·+1.2·+2.5초까지 서버 SpriteRUID=ActionSheet die, 상태 DEAD, IsDead true, HP 0. 소유 클라이언트도 상태 DEAD와 같은 시각에 SpriteRUID die. 경로: 그로기 중(S7, STUN·hit에서 die), 슬로우 PlayRate 0.5+ATTACK 점프 중(S6, 사망 때 PlayRate 1.0 복원, die 유지), HIT 상태(S5), ATTACK 복귀 구간(S4, 판정 직후 점프 중), ATTACK 점프 중간(S3), ATTACK 시작 직후(S2), IDLE(S1). 공중 사망은 몸이 y만 0.58까지 떨어지고 x는 고정, 사망 뒤 stand·jump·hit로 덮인 시점은 없음. S1은 사망 뒤 서버 일시정지(SetServerPaused) 시험을 했으나 컨트롤러가 약 1초 안에 paused를 false로 되돌려 팝업 정지 1초 이상 유지는 확인하지 못했고(paused-on 스냅샷 true 동안은 die 유지) 실제 UIPopup 열기·닫기 경로는 NOT_RUN. 스크린샷 1장(그로기 몬스터 사망 뒤)에서도 몬스터가 눌린 die 프레임으로 보임(육안 평가는 사용자 몫). Stop 뒤 재Play에서의 stand 시작은 이번에 재측정하지 않았다(NOT_RUN, 모델 무변경).
- H1(끝 칸 홀드 특수 피격, 참고 관찰): 실제 LeftArrow 홀드로 Pos1 유지(x=-1.50, 콜라이더 오프셋 0·폭 0.5), special.random 대상 Pos1(영역 -2.0~-1.0)을 난수 고정으로 두 번 연속 실행: 두 번 모두 홀드 유지 상태(MOVE)에서 nativeHit true·kind HIT·HP 12=HitEvent 12(규칙상 정상). 중간에 홀드를 떼 중앙으로 복귀하는 경우는 키 해제 타이밍이 두 번째 공격 이후라 관찰하지 못했다. RightArrow·Pos3 대칭, parry.any 끝 칸 대표는 하지 않았다. 나머지 H1은 tester 몫이다.
- 정리·로그: Play 안에서 만든 시험 스크립트 타이머(클라이언트 상태 폴링)가 Stop 때 `LEA-3051 MemoryLeak(MakerScript)` 1건을 냈다(시험 스크립트가 원인, 제품 오류 아님). 그 밖의 runtime 오류·경고는 없었다(경고는 ValidateRows 프로브가 일부러 만든 CombatRuleCatalog 13건뿐). 마지막 maker_stop 성공, 시험값(AttackInterval 9999, math.random·패턴 목록 임시 교체, 플레이어 HP 보충, 서버 일시정지)은 Play 내부에만 있었고 복원 로그를 확인했다.

### 최종 제품 버전 묶음 (REV-F02·V11-F10·V11-F11)
- F06 절 manifest의 54경로 그대로(경로 수 변경 없음), 같은 계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256). a921c76 커밋 트리를 먼저 재계산해 38e7aa22e05a0a71cc90ca6680278f4352315788cedbfabc7256e4d44dd0ba53 일치를 확인한 뒤 작업 트리를 계산했다.
- Bundle SHA-256(작업 트리): fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80. a921c76 대비 변경된 경로는 9개로, 이번 변경 6개와 Maker 재저장 3개(이번에 수정하지 않음)다.
- 변경 경로 SHA-256: MonsterAttackPatternData.csv 809d1bdfa2f1ba143cc702ee5a2aac93f3441260b37e950be5a57a7c95733f45 · Combat/CombatRuleCatalog.mlua a1a1cb32438843dfb24cbbd5dcc0a3f81782cad6ebe629c11151e8220b444e0b · Monster/MonsterAttackComponent.mlua b0053ff01366f971254ab034c0e3dd94275790363f955a0e049eefa0ab72c780 · Monster/MonsterHealthComponent.mlua e3d28e7321257aad7077acfc7559181d1e4b17f844be536fe2bf54f787f1c013 · Player/PlayerHealthComponent.mlua 2939d7f8144afbfea463b979da926be8e2ec8b722244f67e0a16928fb9560481 · UI/CombatInputController.mlua a062fed645e021e7b22fb967c9ec7b1ce1c6173123e4b7644274a233b728a10a · (Maker 재저장, 이번 변경 아님) 주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 45경로 해시는 이전 묶음(a921c76) 값과 같다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 보라 중심 구성과 특수 1칸 무작위의 난이도·구별, 범위 밖에서 시작한 저스트 인정 체감, "가드 불가" 문구의 눈에 보이는 느낌, HP 0 뒤 die 유지의 육안.
- NOT_RUN: 실제 UIPopup 열기·닫기 중 사망 뒤 die 유지(서버 일시정지는 1초 미만 유지), Stop 뒤 재Play에서 stand 시작 재측정, RANDOM 저스트·↓ 패링 불성공의 실제 키 입력과 반격 권한·슬로우, CSV 파일을 바꿔 열 누락을 일으키는 시험, 끝 칸 홀드를 떼 중앙으로 복귀하는 H1 경우·RightArrow/Pos3·parry.any 끝 칸(tester), V12 외부 환경, 사람 손 0.20초 타이밍, 실기기·터치, 플레이어 사망·실제 맵 전환.
- 판단 메모: 사망 경로의 die 고정은 서버 표시 클립 쓰기가 전부다. 사망 뒤 서버가 stand를 쓰는 경로는 소스상(IsCurrent·CancelMotion·DEAD 잠금·SetStunned 조건)과 시험(7개 경로)에서 확인되지 않았다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) REV-F02: 7경로 사망 뒤 서버·클라이언트 SpriteRUID가 die로 유지되는지(실제 표시는 스크린샷 픽셀도 병행, 실제 UIPopup 열고 닫기·Stop 뒤 재Play 포함). (2) F10: 4행 로드, 경계 난수의 누적 구간·칸, RANDOM 저스트(범위 안·밖 출발)·반격·슬로우와 고정 칸 쪽 방향·중앙 복귀·↓ 패링 불성공, 예고 뒤 이동에도 영역 불변, parry.any 회귀(Pos1·Pos2·Pos3), parry.left·right 2칸 중간 착지·F02 복귀 후 그로기·F08 그로기 hit, NORMAL·GUARD 유형은 시험 데이터 근거. (3) F11: 가드 홀드 중 special.random 범위 안 "가드 불가"·원래 피해, 범위 밖 "회피", 무가드 "피격", 일반 가드 "가드 · 피해 경감"·40%. (4) H1: 끝 칸 홀드 유지·해제(예고 중 서로 다른 두 시점 이상) 정밀 확인과 RightArrow·Pos3, parry.any 끝 칸. 주의: maker_clear_logs를 호출하지 말고 큰 로그는 파일로 저장한 뒤 시각·표지로 거를 것. 시험 스크립트가 만든 타이머는 Stop 때 LEA-3051을 낼 수 있으니 ClearTimer로 정리할 것.

## 2026-11-04 coder V11-F12·V11-F13 구현·기본 검증 인계 (회차 A)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §19 회차 A의 CombatCore-V11-F12(몬스터 die 1회 재생 뒤 마지막 프레임 정지)·V11-F13(JUST·PARRY 성공에 입력 시작 위치 Pos2 칸 ±0.75와 공격 영역의 Pos2 포함 조건 추가)뿐이다. 수치(JustWindowSec 0.20, GuardDamageRate 0.40, 반격 2.0초·×2.2, 슬로우 2.0초·×0.5, 그로기 1.5초, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8, 패턴 4행·Weight·영역·패딩·선행 시간, 이동·복귀 속도 6), CSV·DataSet, D01~D04, 입력 규칙, LEFT/RIGHT/ANY 영역·대상 칸 방식·ANY 탈출 검증, 몬스터 모델·.ui·.map, 새 RUID·자원, 회차 B(플레이어 기본 능력치·V11-F07), §18 머쉬맘 전환, fade·스테이지 전환(4단계), 3단계는 바꾸지 않았다.
- 기준 버전: 커밋 5c4eda3. 같은 방법(54경로 manifest, 경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)으로 5c4eda3 커밋 트리를 재계산해 리뷰 기록 9208e0aa…da79와 일치함을 확인했다. 시작 시 작업 트리는 5c4eda3 + Maker 재저장 미커밋 3파일(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번 변경 아님·되돌리지 않음)뿐이었고 그 밖의 예상 못한 제품 변경은 없었다.
- 실제 연결: 시작 시 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록, 구조 파일을 바꾸지 않아 다시 읽지 않았다). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 파일로 저장돼 시각·`[VRF…]` 표지로 걸러 읽었다.

### V11-F12 — 현재 재생 실측(수정 전, 5c4eda3 그대로)
- 방법: 서버 프로브(상태·SpriteRUID·PlayRate·Start/EndFrameIndex)와 소유 클라이언트 프로브(몬스터 엔티티의 SpriteAnimPlayerChangeFrameEvent 프레임 번호 + 같은 ServerElapsedSeconds 시계)를 같은 시간축에 기록했다. IDLE 몬스터에 ApplyDamage(999) 뒤 die 클립(ActionSheet die=65a2bf…, 프레임 3장, 지연 0.18·0.18·0.30초, 합 0.66초)이 프레임 0→1→2→0→1→2…로 약 0.66초 주기로 **끝없이 반복**됨을 확인했다(사망 뒤 약 47초 관측, 서버 SpriteRUID=die·상태 DEAD 유지). 사용자 보고와 일치한다. 서버가 쓴 SpriteRUID 값은 클라이언트에 같은 시각(시차 0.00초)에 반영되고 클라이언트 프레임 0이 곧바로 시작됐다.

### V11-F12 — 구현 방식과 이유
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | 공통 사망 표시 층. `SetVisualClip`이 (a) 사망 표시가 시작된 뒤(`_T.dieStarted`)에는 모든 키를 무시해 어떤 늦은 경로도 클립을 바꾸거나 die를 다시 시작하지 못하게 하고, (b) 키가 "die"이면 새 `PlayDieOnce()`로 간다. `PlayDieOnce()`는 die RUID의 AnimationClip을 `_ResourceService:LoadAnimationClipAndWait`로 읽어 프레임 수·지연 합·PlayRate로 "마지막 프레임 시작까지의 시간(=(합-마지막 지연)/재생 배율)"을 맵 전투 시계(CombatPauseComponent.GetCombatTime) 기준 기한으로 기록하고, StartFrameIndex=0·EndFrameIndex=2147483647로 정리한 뒤 SpriteRUID=die를 쓴다. `TickDie()`가 기한이 되면 StartFrameIndex=EndFrameIndex=마지막 프레임 번호로 쓴다(마지막 프레임 고정). 클립을 읽지 못하면(프레임 0) 종전처럼 die RUID만 쓴다(`[VRF] MonsterDie start without freeze`). |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | `OnUpdate`를 추가해 사망 후 `MonsterAttackMotion:TickDie()`만 호출(OrangeMushroomAttack.OnUpdate는 `__base`를 부르지 않아 거기에는 둘 수 없었다). 사망 확정 경로의 기존 `SetVisualClip("die")` 호출은 그대로(주석만 수정). |
- 고른 이유: 렌더러 PlayRate 0 방식은 슬로우 PlayRate 복원(`ClearCombatEffects`)과 순서가 엇갈리고 정지 프레임이 부정확하다. Start/EndFrameIndex 방식은 PlayRate와 무관하다. 기한은 서버 `_TimerService`가 아니라 **맵 전투 시계**로 재서 팝업 정지(클라이언트 SetClientTimeScale 0 + 서버 전투 시계 정지) 동안 남은 재생이 보존된다. "마지막 프레임 시작 시점"에 고정해 서버 쓰기가 클라이언트에 도착하기 전에 한 바퀴가 끝나 프레임 0으로 돌아가는 위험(여유 0.30초)을 없앴다. 새 Sync·RUID·모델·DataSet·자원 변경 없음(die 클립 반복 메타데이터도 그대로).
- 서버에서 쓴 렌더러 값이 클라이언트에 보이는지: 위 클라이언트 프레임 이벤트가 서버 쓰기 직후 frame 0(0.00초)·1(0.18~0.19초)·2(0.34~0.38초)를 순서대로 냈고 그 뒤 프레임 이벤트가 없었다. 클라이언트 렌더러 값 SpriteRUID=die·StartFrameIndex/EndFrameIndex=2/2를 시계열 끝에서 직접 읽어 확인했다(`SE=2/2`).

### V11-F12 — 수정 뒤 확인 (Play 1회 연속, 서버·클라이언트 동시 기록)
| 사망 경로(각 시나리오마다 DoSpawn으로 새 상대) | 서버 SpriteRUID/Start/End/상태 | 소유 클라이언트 die 프레임 이벤트(사망 시점 기준 초) |
| --- | --- | --- |
| S1 IDLE | 사망 +0.2 die 0/MAX → +0.6 이후 2/2 고정 → +4.0 2/2 | 0@0.00 1@0.19 2@0.38, 이후 이벤트 0건(정지) |
| S2 ATTACK 시작 직후 | 같음, pre=jump | 0@0.00 1@0.19 2@0.34, 이후 0건 |
| S3 ATTACK 점프 중 | 같음 | 0@0.00 1@0.18 2@0.36, 이후 0건 |
| S4 ATTACK 착지 대기(예고 3초) | 같음, pre=stand | 0@0.00 1@0.19 2@0.36, 이후 0건 |
| S5 ATTACK 복귀 중 | 같음 | 0@0.00 1@0.19 2@0.36, 이후 0건 |
| S6 HIT | 같음, pre=state HIT | 0@0.00 1@0.19 2@0.37, 이후 0건 |
| S7 슬로우 중(PlayRate 0.5) | pre rate=0.5 → 사망 때 1.0 복원 후 die 한 번 | 0@0.00 1@0.19 2@0.36, 이후 0건(frame 0 이벤트가 한 번 더 온 기록이 있으나 재생은 한 번) |
| S8 그로기(STUN) 중 | pre=stun hit RUID → die | 0@0.00 1@0.19 2@0.37, 이후 0건 |
- 서버 `[VRF] MonsterDie start frames=3 total=0.660 freezeAfter=0.360`, 이어 `MonsterDie freeze frame=2`(시계 차 0.36~0.37초). 모든 경로에서 상태 DEAD·HP 0·IsDead true, die 아닌 클립으로의 변경 0건(`nonDieAfter=0`), 정지 뒤 프레임 이벤트(1초 뒤) 0건.
- 팝업(실제 UIPopup 코드 경로, `_UIPopup:Open`/`OnClickCancel`): (1) die 재생 도중 열고 닫기 — 사망 후 약 0.07초에 서버 일시정지(전투 시계 127.994에서 정지), 1.8초 열어 둔 뒤 닫자 클라이언트 프레임이 1@2.15 2@2.32로 **이어서** 재생(처음부터 다시 시작 없음)되고 서버는 전투 시계 128.303(남은 0.31초 경과)에 고정. (2) 정지 뒤(고정 후) 열고 닫기 — 서버 paused true→false, 프레임 이벤트·SpriteRUID 변화 없음. 정지 중 서버 Start/End는 0/MAX로 유지돼 일시정지 동안 기한이 흐르지 않음.
- 화면: 정지 뒤 서로 다른 시점의 maker_screenshot(558×314) 몬스터 영역(320,165,420,225) 픽셀 차이 — 13:58:59·13:59:05 두 장(6초 간격)·13:59:59(팝업 닫은 뒤)·14:00:14(정지 뒤 팝업 열고 닫은 뒤, 다른 몬스터 개체)가 모두 평균 차이 0.000·최대 0(완전 동일). 같은 영역을 새 살아 있는 몬스터(stand) 화면(14:01:09)과 비교하면 평균 32.4·최대 255(다른 화면). 눌린 die 마지막 프레임이 정지해 있음을 화면에서 읽었다. 재생 중 화면은 팝업이 몬스터를 가려 캡처하지 못했고 재생 중은 클라이언트 프레임 이벤트(0→1→2)로 대신했다(육안 평가는 사용자 몫).
- 늦은 경로: 그로기 종료 `SetVisualClip("die")` 재호출·`SetStunned(false)`(사망 경로 S8)·슬로우 PlayRate 복원(S7)·공격 취소·점프 완료·복귀 완료(S2~S5의 `CancelPendingAttack`·`CancelMotion`)·HIT 복귀(S6)가 정지를 풀거나 재생을 다시 시작하지 않았다(`SetVisualClip` 가드 + 시계열 0건).
- 회귀: 살아 있는 몬스터의 stand·jump·그로기 hit 클립은 사망 전 값 그대로(pre 열: stand 96e955·jump 94bbe2·hit/stun aec950). Stop 뒤 재Play에서 첫 몬스터는 stand를 0↔1 프레임으로 정상 반복 재생하고 Start/End=0/2147483647(정지 설정 잔존 없음). DeadEvent 1회, HP 70=100−HitEvent 합 30(수동 공격 실제 ↑ 두 번, V02 대표), 사망 뒤 예고 칸 비어 있음, 추가 피해·공격 없음.

### V11-F13 — 구현
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua · PlayerGuardComponent.mlua | 서버 상태 진입(SetEvading(true)/SetGuarding(true))에서 시작 시각을 기록하는 같은 지점에 **그 순간 서버가 보는 플레이어 WorldPosition.x**를 `_T.evadeStartX`/`_T.guardStartX`로 함께 기록(`[VRF] PlayerEvade/PlayerGuard start x=… t=…`). `ClearStart()`(시각 −1·위치 nil)과 `GetStartX()`를 추가하고 OnMapLeave의 시각 삭제를 `ClearStart()`로 바꿨다. 클라이언트가 보낸 위치·성공 값은 쓰지 않는다. |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua · Player/PlayerHealthComponent.mlua | 팝업 닫기(RequestPopupPause 해제)와 플레이어 사망(HandleStateChangeEvent DEAD)의 시각 −1 삭제 두 곳씩을 `ClearStart()` 호출로 교체(위치 기록도 함께 폐기). |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | PrepareAttack이 실행 스냅샷에 `pos2Cell = { minX=(앵커1+앵커2)/2, maxX=(앵커2+앵커3)/2, areaIncludes = (앵커2 x ∈ [영역 minX, maxX]) }`를 한 번 고정(Pos2 칸 경계 = 앵커 중점, 지금 간격 1.5에서 ±0.75, 새 DataSet 열 없음). ResolveAttack이 이를 EvaluateDefense 6번째 인자로 넘긴다(호출자는 ResolveAttack 하나, grep 확인). 영역·유효 방향·ANY 탈출 검증은 그대로. |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | `IsStartInPos2Cell(startX, pos2Cell)`(기록 없음 → 불성립, 경계 포함 ±1e-6 허용)을 추가. EvaluateDefense는 JUST와 PARRY 성공에 기존 조건(창·방향·속성·가드 홀드)과 **그리고** (a) 시작 위치가 Pos2 칸 안, (b) 스냅샷 영역이 Pos2 앵커 포함을 요구한다. 불성립이면 성공만 빠지고 가드 경감(GUARD ×0.40)·가드 불가(UNGUARDABLE)·영역 밖 0(RecordDefense "회피")·영역 안 원래 피해(HIT)는 그대로. 판정 로그 `[VRF] PlayerHealth guard/evade eval x=… cellOk=… areaOk=…`. 새 결과 종류·문구·.ui 변경 없음(CombatInputController 무변경). |

### V11-F13 — 확인 (Play 내부, 서버 프로브 + 실제 키 입력)
- 방법: 패턴 단일 행 교체(Play 내부 `_CombatRuleCatalog.patterns`, 예고 3초/60초)와 math.random 임시 교체(RANDOM 칸), 시작 시각·위치·방향 강제("프로브 근거")로 제품 ATTACK 경로(PrepareAttack→ResolveAttack→EvaluateDefense→네이티브 AttackFast→CalcDamage)를 돌렸다. 판정 시각 직전 0.05초에 시작을 기록하고(창 0.20 안) 판정을 앞당겨 실행. 가드는 **실제 DownArrow 키 홀드**(서버 GUARD 상태·isGuarding true)에서 시작 위치·시각만 덮어썼다. 결과는 feedback 문자열(RecordDefense), HP 변화, 반격 권한, 슬로우, 패링 뒤 그로기 예약(`groggyAfterReturn`)으로 확인했다.
- E 단계(회피, 플레이어 Pos2 x=0, 17건, 전부 기대와 일치):
  - E01 parry.left·E02 parry.right·E03/E04 parry.any(Pos2 조준, 좌·우 양방향)·E05 special.random 칸 2(좌) → JUST·피해 0·반격 권한 true·슬로우 true.
  - E06 special.random 칸 1(영역 −2.0~−1.0, 유효 방향 R)·E07 칸 3(영역 1.0~2.0, 유효 방향 L)·E17 패링 속성 1칸 칸 1 → JUST 아님, 영역 밖이라 네이티브 피격 없음 → "EVADE" 피해 0·반격 없음·슬로우 없음(QA5 K3b·QA7 E1 계열 기대가 JUST에서 바뀜).
  - E08 x=+0.75·E09 x=−0.75(경계 포함) → JUST. E10 x=+0.76·E11 −0.76·E12 +0.80·E13 −0.80 → JUST 아님, 영역 안이라 HIT·피해 12. E14 틀린 방향 HIT 12(기존). E15 창보다 일찍 시작(0.6초 전) HIT 12(기존). E16 시작 위치 기록 없음 → HIT 12.
- G 단계(가드, 실제 DownArrow 홀드, 15건, 전부 일치): G01 parry.left·G02 parry.right·G03 parry.any·G05 패링 속성 1칸 칸 2 → PARRY·피해 0·그로기 예약 true·반격 true. G04 패링 속성 1칸 칸 1(영역이 Pos2 불포함) → PARRY 아님, 영역 밖이라 "EVADE"·그로기 없음. G06 x=+0.80·G07 −0.80·G09 +0.76 → GUARD, 피해 12×0.40=4.8→4(그로기·반격 없음). G08 x=+0.75 PARRY(경계 포함). G10 special.random 칸 2 → UNGUARDABLE·원래 피해 12. 시험 데이터 근거(GUARD 유형 3칸, Pos2 포함): G11 NORMAL → GUARD 4, G12 PARRY 속성 → PARRY, G13 같은 행 x=+0.80 → GUARD 4. G14 가드 시작 0.5초 전(창 밖) → GUARD 4(기존). G15 시작 위치 기록 없음 → GUARD 4.
- 실제 키 입력(K, 판정 시각 앞당김, 창 0.20은 시험값 30초로 넓힘 — 입력 시각을 못 맞춰서): K1 parry.left + LeftArrow 탭 → JUST·피해 0·반격·슬로우. K2 parry.right + RightArrow 탭 → JUST. K4 parry.left + LeftArrow(2번째) → JUST. K5 parry.right + RightArrow(2번째) → JUST. K3 special.random 칸 1(영역 Pos1) + LeftArrow 홀드(플레이어 Pos1에서 판정, 시작 때 x=0) → `areaOk=false`로 JUST 아님, 영역 안이라 HIT·피해 12("끝 칸 쪽 회피 → HIT"; H1 겹침 =HIT). DownArrow 홀드는 G 단계 전체가 실제 키.
- **위치 정확도(서버 시작 기록 x 대 클라이언트 segment.startX)**: LeftArrow/RightArrow 실제 키 입력 5건(K1·K2·K3·K4·K5) 모두 클라이언트 `MovementInput phase=OUTBOUND … x=0.0`, 서버 `PlayerEvade start x=0.000`으로 **차이 0.000**이다. 서버 기록 시각은 클라이언트 시작 시계보다 0.085~0.095초 늦었지만 그 시점 서버가 본 위치는 아직 0.000이어서 Pos2 칸(±0.75, 속도 6에서 약 0.125초) 안이었다. 정상 입력이 위치 때문에 거부된 사례 0건(DownArrow 실제 입력도 `PlayerGuard start x=0.000`). 한계: 입력 지연이 0.125초를 넘으면 서버 기록 위치가 칸을 벗어날 수 있으나 이번 시료에는 없었다(5건, 단일 접속 Maker 환경).
- 위치 기록 삭제: (1) 실제 UIPopup 열기→닫기 직전에 evade/guard 시작 x=0.5·시각을 심자 닫은 뒤 `evadeX=nil evadeT=-1.0 guardX=nil guardT=-1.0`. (2) 예고 중 팝업(예고 6초, 팝업 +1.0초부터 약 1.5초): 시작 기록 후 팝업 중 예고 남은 시간 5.71→4.50(정지 중 보존), 닫은 뒤 `evadeX=nil`, 이후 판정은 JUST가 아닌 HIT 12(이전 회피 시각 폐기 규칙 유지). (3) 플레이어 사망(서버 ChangeState DEAD): `evadeX=nil·guardX=nil`, 시각 −1. (4) Stop → 재Play: evade/guard x=nil·시각 −1.0·창 규칙 0.2/0.2(시험값 30초 복원)·패턴 4행·AttackInterval 기본.
- 회귀: 일반 가드 ×0.40(G11), 특수 가드 UNGUARDABLE 12(G10), 무가드 범위 안 HIT 12(E10~E16), 반격 소비·슬로우 대표(JUST 직후 실제 ↑ 한 번 → 반격 권한 소비, 10타 ×2.2 내림 2×10=20 vs 일반 10, 슬로우 true), HP=HitEvent 합 대표(위 30), 예고 중 팝업(위), Stop 뒤 다음 Play 기본값(위).

### 빌드·로그
- Refresh 뒤 build 로그 81건 전부 Info(LIA 1114/1115 동적 참조 노이즈, 앞 회차와 같은 유형), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음(git status에도 .codeblock·.directory·.userdataset 추가 변화 없음).
- Play 2회(통합 1회 약 6분 + Stop 뒤 재Play 1회). 마지막 Stop 정상. 두 Play 모든 로그가 Info 뿐이다(Warning·Error·LEA·LWA 0건). 시험 스크립트가 만든 반복 타이머는 Stop 전에 ClearTimer로 정리해 LEA-3051은 나오지 않았다.

### 프로브 오류와 제품 오류의 구분, 관찰
- 시험 문제: 팝업 감시 프로브의 첫 시도가 이전 사망 몬스터(IsDead)를 감지해 시나리오보다 먼저 팝업을 열었다(제품 오류 아님, 감시 대상을 새 몬스터로 바꿔 재시험). 그 첫 시도에서 우연히 "팝업 정지 중 사망·SpriteRUID 쓰기" 조합이 만들어졌는데 정지 중 서버 기한이 흐르지 않고 닫은 뒤 0.37초에 고정, 클라이언트 프레임은 1@0.00 2@0.19(첫 프레임 이벤트는 프로브 타이머가 정지돼 놓침) 순서로 한 번만 재생되고 고정됐다.
- 관찰(바꾸지 않음): (1) 새로 스폰한 직후 몬스터의 렌더러 Start/End가 0/0으로 읽힌 시점이 있었다(S1·S6 pre, 스폰 1초 이내, 다른 시나리오는 0/MAX). 사망 때 PlayDieOnce가 0/MAX로 정리하므로 영향 없고 stand 재생은 0↔1 정상이다. (2) 플레이어 HP가 시험 도중 큰 값(988)으로 읽혔다(기준 모델 값이 아니며 시험 스크립트가 MaxHp로 채움). (3) 슬로우(S7)에서 클라이언트 frame 0 이벤트가 두 번 온 기록이 있으나 재생은 한 번이다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 사망 뒤 die 1회 재생과 끝 모습 정지의 육안(그로기 중 처치·팝업 뒤 포함, 모바일), Pos2에서 가운데 칸 공격에서만 저스트·패링이 나는 체감과 끝 칸 1칸 공격(특수 무작위) 무보상 난이도. 사람 손의 0.20초 창 타이밍, 실기기·터치·모바일.
- 재생 중(0.36초) die 화면의 스크린샷 캡처(팝업이 가림, 프레임 이벤트로 대신), 파일 CSV 변경 반영, 실제 UIPopup 도중 플레이어 사망, 실제 다른 맵 전환, V12 외부 환경, 다중 접속 지연에서의 위치 기록 오차(시료 5건은 단일 접속).
- 시험값(창 30초, 패턴 단일 행 교체, 예고 3~60초, 판정 앞당김, 시작 시각·위치·방향 강제, math.random 임시 교체, 플레이어 HP 보충, 서버 직접 ChangeState)은 Play 내부에만 두었고 Stop·재Play로 기본값 복귀를 확인했다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인(Stop 직후 한 번 "play"로 보였다가 다음 조회에서 edit, 전환 중이던 값). Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F12: 사망 경로(IDLE·ATTACK 예고·점프·착지 대기·복귀·HIT·슬로우·그로기)별로 서버 SpriteRUID/Start/End와 소유 클라이언트 프레임 이벤트·SpriteRUID 시계열, 정지 뒤 5초 이상 변화 없음, 서로 다른 세 시점 이상의 스크린샷 몬스터 영역 동일(재생 중과 다름), 실제 UIPopup 재생 도중·정지 뒤 열고 닫기, 늦은 경로(그로기 종료 die 재호출·슬로우 복원·공격 취소), Stop 뒤 재Play stand. (2) F13: parry.left/right·parry.any·special.random 강제 칸 1/2/3, 가드형 시험 데이터, 실제 Left/Right/DownArrow, 시작 위치 ±0.75/±0.76/±0.80 프로브, 위치 기록 삭제(팝업 닫기·플레이어 사망·Stop), 서버 기록 x와 클라이언트 segment.startX 차이 기록(이번 5건 0.000). 주의: maker_clear_logs를 호출하지 말고 큰 로그는 파일로 저장된 것을 `[VRF`·`VRF12`·`VRF13` 표지와 시각으로 거른다. 시험 스크립트의 반복 타이머는 ClearTimer로 정리하고, 기존 QA5 K3b·QA7 E1 계열 기대(JUST)는 JUST 아님으로 바뀌었다.

### 2026-11-04 최종 제품 버전 묶음 (V11-F12·F13)
- 54경로 manifest 그대로(경로 수 변경 없음), 같은 계산법(경로 ASCII 정렬 `LC_ALL=C sort`, 경로 + TAB + sha256 + LF 연결의 SHA-256). 5c4eda3 커밋 트리를 먼저 재계산해 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79 일치를 확인한 뒤 작업 트리를 계산했다.
- Bundle SHA-256(작업 트리): b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f. 5c4eda3 대비 바뀐 manifest 경로는 10개로, 이번 변경 7개와 Maker 재저장 미커밋 3개(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번에 수정하지 않음, 직전 회차 작업 트리와 같은 값)다.
- 변경 경로 SHA-256: Combat/CombatPauseComponent.mlua 92e0b0800b9c71ecc377c720854599dbf406120ab51d8cdba29d3ce9e0c525dd · Monster/MonsterAttackComponent.mlua 5c6a7896bd04a1835de517522da49de187a3fb8e560b975f50a76877fd800fe0 · Monster/MonsterAttackMotion.mlua 349d3e8a699d58b2779c5a61adde812802135cbcbf8807bddab70c9351a24a0a · Monster/MonsterHealthComponent.mlua 38d5379fb523dda28cb60e4887ae30b2b88b6f6b8be99103e4ab52ab52936a00 · Player/PlayerEvadeComponent.mlua 679dc069fa8108d7839d61b8d748fbb037141b3e41a84e16b37cac1231753547 · Player/PlayerGuardComponent.mlua f8d0bd7052f8992630532b96ef30887a5227042978d62c3a5801bdb0102ace73 · Player/PlayerHealthComponent.mlua 9cf53db223aaaa130389c63e58b3a4854a8a1edeeb348e0abe570380e10883a2 · (Maker 재저장, 이번 변경 아님) 주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 45경로 해시는 이전 묶음(5c4eda3) 값과 같다.

## 2026-11-04 coder V11-F14·V11-F07 구현·기본 검증 인계 (회차 B)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §20 회차 B의 CombatCore-V11-F14(플레이어 최대 HP·이동 속도·복귀 속도 DataSet, 1000·6·6)와 CombatCore-V11-F07(몬스터 최대 HP·공격력·공격 간격 DataSet, 100·12·3.0)뿐이다. 수치·규칙·모델·맵·UI 파일·기존 CSV 5종·기존 .userdataset·.codeblock 직접 수정·몬스터 점프·Pos2 경계·앵커 간격·§18·3단계는 바꾸지 않았다. 작업 트리의 Plan·로드맵·run.md·이 WorkRecord의 기존 절은 건드리지 않았고 이 절만 덧붙였다.
- 기준 버전: 커밋 9eed765. 시작 시 git status는 메인·planner 문서 4개(run.md·로드맵·Plan·WorkRecord) 미커밋 변경뿐이었고 제품 파일 변경은 없었다. 같은 방법(54경로 manifest, 경로 ASCII 바이트 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)으로 9eed765 커밋 트리와 작업 트리를 계산해 둘 다 **b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f**(회차 A 작업 트리 값과 같음)를 확인했다.
- 실제 연결: 시작 시 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록, 맵을 바꾸지 않아 다시 읽지 않았다). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 저장된 JSON 파일에서 시각·`[VRF…]` 표지로 걸러 읽었다.

### 1단계 — 모델 Values 고정 수치 확인 (무수정, ModelBuilder.read)
- Global/DefaultPlayer 모델(컴포넌트 9개, Values 66개): 대상 컴포넌트 없는 속성 `maxHp`=1000(그 밖에 speed·jumpForce·카메라 등 기반 속성), `PlayerComponent.Hp`=0, `script.PlayerMoveComponent`는 `Enable`만. `PlayerComponent.MaxHp`에 해당하는 Values 항목은 없다. 따라서 이동·복귀 속도 6은 PlayerMoveComponent.mlua 속성 기본값이 이겼고, 최대 HP 1000은 모델 `maxHp` 1000과 엔진 PlayerComponent.MaxHp 기본 1000이 같아 둘을 구분할 수 없다(Play 실측 1000).
- Models/Monsters/주황버섯 모델(컴포넌트 14개, Values 45개): `script.MonsterHealthComponent.MaxHp`=100(모델 Values가 .mlua 기본값 위), MonsterHealthComponent IsDead false·Enable, `MonsterStateControl.attackTimer` 0·Enable, `MonsterAttackComponent`는 Enable만(AttackDamage 값 없음), MonsterStateControl에 AttackInterval 값 없음, MonsterDefenseComponent.isDefending false, MonsterStunComponent.isStunned false·stunDeadline -1·scheduledId 0·executionId 0, OrangeMushroomAttack.Home (0,0)·HomeCaptured false·JumpActive false·JumpStartX 0·JumpTargetX 0·JumpStartTime 0, MovementComponent.InputSpeed 1.5·JumpForce 6(이번 범위 아님). Plan §20 예상과 같다. 다른 수치 고정값은 없었다. 두 모델은 읽기만 했다(해시 불변).
- 현재 값 실측(수정 전, 9eed765 그대로, Play 1회): 서버 몬스터 MaxHp 100·Hp 100·AttackDamage 12·AttackInterval 3.0, 서버 PlayerComponent.MaxHp 1000(Hp는 자연 공격 몇 번 뒤 976), 클라이언트 MaxHp 1000·MoveSpeed 6.0·ReturnSpeed 6.0, 클라이언트 몬스터 MaxHp 100. 모델 `maxHp`가 PlayerComponent.MaxHp로 가는지는 두 값이 같아 구분하지 못했다(모델 값을 건드리지 않으므로 영향 없음).

### 구현 요지와 이유
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/PlayerBaseStatData.userdataset·.csv (새) | 열 id, MaxHp, MoveSpeed, ReturnSpeed. `default,1000,6,6`. serveronly false(UseService 0, 기존 AttackSkillData·MonsterData와 같은 형식). 래퍼는 기존 CombatRuleData와 같은 형식(CRLF, CoreVersion 26.10.0.0), CSV는 UTF-8 BOM + CRLF. EntryKey UUID는 node randomUUID |
| RootDesk/MyDesk/@Assist/DataSet/MonsterStatData.userdataset·.csv (새) | 열 id, MaxHp, AttackDamage, AttackInterval. `default,100,12,3.0` / `castleenemy,100,12,3.0`. serveronly true(UseService 1, CombatRuleData와 같음) |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 공용 검증 `ValidateStatRows(label, rows, columns)`와 `IsValidStat(value, kind)`(posint=유한한 양의 정수, pos=유한한 양수, nonneg=유한한 0 이상) 추가. id는 앞뒤 공백을 뺀 뒤 비어 있지 않고 중복 없음, `default` 행이 없거나 빈 칸·무효 값이면 표 전체 거부, default가 아닌 행의 빈 칸(빈 문자열·공백)은 default 값, 비어 있지 않은 무효 값은 default로 바꾸지 않고 표 전체 거부, 추가 열·`#` 열은 읽지 않으므로 무시. EnsureInitialized가 MonsterStatData를 같은 카탈로그에서 로드·검증하고(필수 열 누락·무효면 기존 규칙·패턴과 함께 전체 거부, 부분 캐시 없음) 로드 [VRF]에 표 행을 남긴다. `GetMonsterStats(modelKey)`(ServerOnly)가 행을 돌려주고 행이 없거나 예약 행 `default`이면 nil + 한 번 경고(default로 대신하지 않음). OnEndPlay에서 캐시를 지운다 |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | DoSpawn: modelKey(모델 id에서 `model://` 제거)를 스폰 전에 한 곳에서 정하고 `GetMonsterStats`가 nil이면 스폰하지 않는다(현재 상대 유지, `[VRF] MonsterManager spawn refused`). 스폰 뒤 서버가 MonsterHealthComponent.MaxHp·Hp(=MaxHp), MonsterAttackComponent.AttackDamage, MonsterStateControl.AttackInterval에 행 값을 쓴다(첫 공격 전, 필요한 컴포넌트가 없으면 몬스터를 파괴하고 경고). 기존 `attack._T.modelKey` 지정은 같은 modelKey를 쓴다. RefreshDuelPlayer: 플레이어 `PlayerHealthComponent:IsBaseStatsReady()`가 true일 때만 대결에 받는다 |
| RootDesk/MyDesk/Player/@Assist/Stat/PlayerBaseStatCatalog.mlua (새 @Logic, .codeblock·Stat.directory는 Maker 생성) | 서버와 클라이언트가 각자 호출하는 단일 로더·검증. `_CombatRuleCatalog:ReadRows`·`ValidateStatRows`를 공용으로 써 같은 표를 같은 기준(MaxHp posint, MoveSpeed·ReturnSpeed pos)으로 판단한다. `GetStats()`는 default 행을 돌려주며 호출한 쪽에서 한 번만 읽고 검증한다(실패도 캐시, 속성 기본값·모델 값으로 대신하지 않음). OnBeginPlay·OnEndPlay에서 캐시를 지운다 |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 서버 OnBeginPlay에서 표 default 행의 MaxHp를 `PlayerComponent.MaxHp`에 쓰고 Hp를 MaxHp로 맞춘다. 표가 무효면 쓰지 않고 `IsBaseStatsReady()`가 false. 새 ServerOnly 메서드 `IsBaseStatsReady()` |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | 클라이언트 OnBeginPlay에서 `ApplyBaseStats()`로 MoveSpeed·ReturnSpeed를 표에서 받는다. `CanStart`가 입력·상태 변경 전에 `ApplyBaseStats()`가 실패하면 false(`[VRF] MovementInput rejected reason=stats`, 경고는 카탈로그가 한 번). .mlua 속성 기본값 6·6은 그대로 두었으나 표 적용 뒤에는 쓰이지 않는다 |
- ExecSpace: 몬스터 값·플레이어 HP는 서버(ServerOnly), 이동·복귀 속도는 소유 클라이언트(ClientOnly), 플레이어 표 로더는 호출한 쪽에서 실행. 선언 없는 `self` 필드는 쓰지 않았고 `_T`만 썼다. 새 Sync·RUID·모델·맵·UI 변경 없음.
- 고른 이유: 몬스터 수치는 이미 서버 정적 데이터를 소유한 CombatRuleCatalog에 두면 전체 거부 정책이 한 곳에서 지켜진다. 플레이어 표는 클라이언트가 읽어야 해서 serveronly false이고, 서버 HP와 클라이언트 속도가 같은 표·같은 검증 함수를 쓰도록 `ValidateStatRows`를 공용으로 했다. 서버가 읽어 동기화하는 방식은 동기화 도착 전 기본값 구간이 생겨 택하지 않았다.
- 실패 시: 몬스터 표 무효·행 없음 → 공격 시작 거부(패턴 누락과 같은 경로)와 스폰 거부, 플레이어 표 무효 → 이동 시작 거부와 대결 제외. 대체 진행 없음, 경고는 서버·클라이언트가 원인마다 한 번(카탈로그 WarnOnce).

### 실제 기본 검증 (Maker MCP, Play 4회, 시험 설정은 Play 내부에만 두고 Stop·재Play로 정리)
- 빌드: Refresh 뒤 build 로그 89건 전부 Info(LIA 1114/1115 동적 참조 노이즈), 오류 0·경고 0. 새 .mlua의 .codeblock·Stat.directory는 Maker가 생성했다. Refresh가 범위 밖 파일을 다시 저장한 흔적 없음(git status에 의도하지 않은 변경 없음, 기존 CSV 5종·.userdataset·모델·맵·UI 파일 해시 불변).
- 값 동일성 PASS(Play 1, 서버/클라이언트 [VRF]): 로드 `MonsterStatData id=default/castleenemy MaxHp=100 AttackDamage=12 AttackInterval=3.0 source=DataSet`, `PlayerBaseStatData side=server/client default MaxHp=1000 MoveSpeed=6 ReturnSpeed=6 source=DataSet`. 서버 몬스터 MaxHp 100·Hp 100·AttackDamage 12·AttackInterval 3.0, 클라이언트 몬스터 MaxHp 100. 서버 `PlayerStat applied MaxHp=1000 Hp=1000`, 클라이언트 PlayerComponent.MaxHp 1000. `MovementInput boot speed=6.0 return=6.0 source=DataSet`. HP 바는 위 Hp·MaxHp 값으로 확인(스크린샷은 찍지 않음).
- 이동: 실제 LeftArrow 홀드 OUTBOUND 구간(1.5 거리) elapsed 0.238·0.241(약 1.5/6에서 마지막 프레임 맞춤 전), RETURNING 0.247·0.24. 홀드 해제 뒤 중앙 복귀, 복귀 완료 `state=IDLE`(1단계 중앙 복귀 잠금 그대로). 서버 PlayerEvade start x=0.000과 클라이언트 OUTBOUND startX=0.0의 차이 0.000(2건 이상).
- 공격 간격: 자연 공격 IDLE→ATTACK 전환의 전투 시계 간격 2.96~3.01초(타이머 표본 0.05초), 저스트 슬로우(×0.5, 2.0초) 직후에는 3.49~3.51초로 길어짐(기존 규칙: 슬로우 중 적 진행 시계 배율). 패링 그로기 뒤 2.98.
- 피해: 무대응 범위 안 12(964→952→940→928→916), 일반 가드(실제 DownArrow 홀드, 시험 단일 행 GUARD·NORMAL) 916→912 = 4 = floor(12×0.40), 이어진 가드 판정에서도 912→908. `[VRF] CombatCore defense` kind=GUARD rate=0.4.
- 몬스터 처치: 실제 UpArrow 두 번(250ms 탭) HitEvent 합 20, 몬스터 Hp 80 = 100−20, 이어 ApplyDamage(80)로 처치(받은 피해 합계 100: 실제 20 + 프로브 80), DEAD 1회·DeadEvent 1회. 사망 뒤 서버 SpriteRUID=die, StartFrameIndex/EndFrameIndex 0/MAX → 0.36초 뒤 `MonsterDie freeze frame=2` → 2/2 고정(+1.0초·+4.0초에도 2/2), 클라이언트도 2/2(회차 A F12 IDLE 사망 대표 1건 회귀 PASS). 그로기 중 사망 대표 1건(DoSpawn으로 새 상대, ApplyGroggy 뒤 0.5초에 ApplyDamage 999): die 후 2/2 고정 PASS. 새로 스폰한 상대도 `MonsterStat applied … MaxHp=100 Hp=100 AttackDamage=12 AttackInterval=3.0`로 같은 값.
- 회차 A F13 핵심 회귀 PASS(판정 창 JustWindowSec·ParryWindowSec를 Play 내부에서 30초로 넓힘, 패턴 단일 행 교체, 판정 앞당김 = 프로브 근거, 입력은 실제 키): (1) Pos2 시작 PARRY — 실제 DownArrow 홀드, parry.any(ANY·PARRY·NEAREST) → `PlayerHealth guard eval x=0.000 cellOk=true areaOk=true attr=PARRY`, defense kind=PARRY rate=0, 반격 권한·그로기 예약(`groggy applied`, 몬스터 STUN). 첫 시도는 가드 시작이 35초 전이라 창 30초 밖이어서 GUARD 4가 나온 프로브 타이밍 실수였고(제품 오류 아님) 다시 눌러 PARRY를 얻었다. (2) Pos2 시작 JUST — LeftArrow 탭, `evade eval x=0.000 cellOk=true areaOk=true dir=LEFT` → kind=JUST rate=0, 반격 권한·슬로우 적용. (3) 끝 칸 1칸 공격(special.random, math.random 임시 교체로 칸 1) + LeftArrow 홀드(플레이어 Pos1) → `areaOk=false`, kind=HIT rate=1 = JUST 아님·무보상. 이 시험 뒤 math.random·패턴·창 값을 복원했다(`restored: patterns=4 just=0.2 parry=0.2 mathRandomRestored=true`).
- 쓰기 가능성(중단 조건 1 확인): 서버가 PlayerComponent.MaxHp=777·Hp=777을 쓰자 서버·클라이언트 모두 777로 읽혔고 1000으로 되돌렸다. 클라이언트는 serveronly false 표를 읽었다(중단 조건 2 해당 없음): 클라이언트 [VRF] `PlayerBaseStatData side=client … source=DataSet`.
- Stop → 다음 Play 재로드(Play 2 부팅): 규칙·패턴 4행·몬스터 표 2행·플레이어 표가 다시 DataSet에서 로드되고 이전 Play의 시험 값(창 30초·단일 행 패턴·math.random 교체)이 남지 않음(`catalog ready rules=1 patterns=4 monsterStats=2`, 이후 telegraph 패턴이 CSV 4행 중 하나).
- 무효 데이터 프로브(Play 2, CSV 무변경, 시험 행을 검증 함수에 넣음 = 프로브 근거), 서버 `ValidateStatRows`(몬스터 열) 전부 기대와 PASS: 유효+빈 칸(빈 문자열·공백만 모두 default 값, MaxHp/AttackDamage/AttackInterval 각각 빈 칸 → fromDefault 표시), AttackDamage 0·0.5 허용, MaxHp 100.0 허용; default 행 없음·default 빈 칸(세 열 각각)·default 무효 → 표 거부; MaxHp 문자·0·−5·1.5·inf·nan·NaN 값·±무한대, AttackDamage 문자·−1·−0.1·NaN·무한대, AttackInterval 문자·0·−1·NaN·무한대 → 표 거부; default 아닌 행의 무효 값은 default로 대체하지 않고 거부; 중복 id·공백 포함 중복 id·빈 id·공백만 id 거부; 추가 열·`#memo` 키는 무시(수락); ReadRows 필수 열 누락 → nil(거부); 스폰 키 없음(`nosuchmodel`)·예약 `default` → GetMonsterStats nil + 경고 한 번(같은 키 두 번째 호출은 경고 없음), MonsterManager.DoSpawn은 `spawn refused`로 스폰하지 않고 현재 상대를 유지하며 default로 스폰하지 않음. 클라이언트 `PlayerBaseStatCatalog:Validate`도 같은 기준으로 유효·default 없음·빈 칸·MoveSpeed/ReturnSpeed(0·−1·문자·NaN·inf)·MaxHp(0·−1·1.5·문자·NaN·inf)·중복·빈 id를 거부하고 추가 열은 무시. 경고는 서로 다른 원인마다 한 번.
- 플레이어 표 실패(프로브): 서버·클라이언트를 실패한 첫 로드와 같은 상태(`_T.attempted=true`, Ready false, 무효 표 검증으로 경고 1회)로 만들면 서버 `PlayerStat rejected reason=table`, `IsBaseStatsReady()=false`, 대결 플레이어 없음(`CombatCore duel player=none`), 몬스터 ATTACK 진입 0회(19초 관찰), 클라이언트 `CanStart("LEFT")=false`, 실제 LeftArrow 두 번 모두 `MovementInput rejected reason=stats`로 이동하지 않음. 표를 다시 읽게 하자 서버 `PlayerStat applied … duel player` 복구, 클라이언트 `CanStart=true`, 속도 6.0/6.0. 모델 maxHp 1000·.mlua 6으로 대신 진행하지 않음. (로더 메서드를 임의 함수로 덮어쓰려는 첫 시도는 `An error occurred while assigning a value to variable <ReadRows>`로 막혀 시험 도구 오류 2건을 냈고 상태 기반 방식으로 바꿨다. 제품 오류 아님.)
- CSV 실제 변경 반영(Play 3 → 원복 → Play 4): 변경 전 바이트 해시를 기록(PlayerBaseStatData.csv 3202ac06…d094 53바이트, MonsterStatData.csv f9709bd8…1dc3 85바이트)한 뒤 PlayerBaseStatData `default,1000,9,6`(MoveSpeed 6→9)와 MonsterStatData `castleenemy,150,12,3.0`(MaxHp 100→150)로 바꾸고 Refresh → Play: 로드 [VRF] `MoveSpeed=9`·`castleenemy MaxHp=150`, 클라이언트 `boot speed=9.0 return=6.0`, 실제 LeftArrow OUTBOUND elapsed 0.158(약 1.5/9)·RETURNING 0.24, 서버·클라이언트 몬스터 MaxHp·Hp 150(모델 Values의 100보다 DataSet이 이김, 모델 값 제거 불필요). Stop → CSV를 백업 바이트로 복원, 두 CSV와 두 .userdataset 모두 변경 전과 byte 일치(sameAsBackup=true) → Refresh → Play: `MoveSpeed=6`·`MaxHp=100`·`boot speed=6.0`·OUTBOUND 0.239로 복귀. 이 시험 값은 커밋 대상이 아니고 현재 파일은 복원된 6·100이다.
- 로그 요약(첫 시험 Play 시작부터 마지막까지 전체): Info 587·Warning 40·Error 2. Warning 40건은 모두 무효 데이터 프로브가 의도적으로 낸 경고(CombatRuleCatalog WarnOnce)이고 Error 2건은 위 메서드 덮어쓰기 시험 도구 오류다. 정상 구간(Play 1·3·4와 Play 2의 정상 구간)에는 Warning·Error 0, LEA/LWA 0건(시험 반복 타이머는 모두 ClearTimer 후 Stop해 LEA-3051 없음).

### 실패/미확인/미실시 (PASS로 세지 않음)
- 중단 조건 (1)~(5) 해당 없음. 실패 없음. 수치를 조정해 맞춘 것 없음.
- 미실시: HP 바 스크린샷(값만 확인), 사람 손 0.20초 타이밍, 실제 HP 0 플레이어 사망과 부활 뒤 Hp 복원(tester (b)), 예고 없는 ↓ 홀드 `[VRF] PlayerGuard start` 관찰 재현(tester (a)), 방향키+UI 출처 합산·기본 공격 타수·범위 전수(대표 UpArrow 2회만), F06·F10의 2칸 중간 착지·점프 0.5초 판정 시각, F08 그로기 1.5초 hit 표시 전수, V07·V08 팝업 정지·재개 전수, 실기기·모바일, 다중 접속.
- 관찰(바꾸지 않음): 처음 UpArrow 100ms 탭 두 번은 manual cast 로그가 없었고 250ms 탭부터 cast가 났다(상태 영향인지 짧은 입력 문턱인지 미조사, 이번 변경과 무관해 보임). 시험 도중 플레이어 Hp 감소는 자연 공격 12씩이다.

### 최종 제품 버전 묶음 (V11-F14·V11-F07)
- 9eed765 대비 **기존 54경로 manifest**(경로·계산법 그대로) Bundle SHA-256: **a8c96297411224849adc9613f278d76f6f2eb94ab5cb8e1f785548a185fbcc5d**(작업 트리). 바뀐 manifest 경로는 4개(CombatRuleCatalog·MonsterManager·PlayerHealthComponent·PlayerMoveComponent)이고 나머지 50경로는 9eed765와 같다.
- 새 DataSet·로더가 제품 파일이므로 manifest에 5경로를 더한 **59경로 manifest** Bundle SHA-256: **9325c33ade8a2c32c058cb7e4050a82f8b44d9f22dcfe68c82874cd3e23bcd19**(경로 ASCII 바이트 정렬, 경로 + TAB + sha256 + LF). tester·reviewer는 이후 이 59경로(기존 54 + 아래 새 5)를 대상 버전으로 쓴다.
- 변경·추가 경로 SHA-256: RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua 0eec3975fe07da14b2a5fa8806a4c5221b692972c075a6c98fef1277ac727c8a · RootDesk/MyDesk/Managers/MonsterManager.mlua 7cc5ff3a478a2f3c1e3c5ff84f600a87b76c4c9dd11e5b9b0cee881ed616ae9e · RootDesk/MyDesk/Player/PlayerHealthComponent.mlua 276e1c50bd1ba3b3c979f89f018d768da18c6fe57c3ea45e24e8621f2ca40bb8 · RootDesk/MyDesk/Player/PlayerMoveComponent.mlua 7d9a9f41ab548770525a7970610461240bdee3d6d6cb505a09f8fcedacde068c · (새) RootDesk/MyDesk/Player/@Assist/Stat/PlayerBaseStatCatalog.mlua f20a1121f35c01dadf1e3274e1551c9592af9ef02acc2610c2d16554edfadeb3 · (새) RootDesk/MyDesk/@Assist/DataSet/PlayerBaseStatData.csv 3202ac06b9ebf31c13d73a2eb343ab788f5393e8b7f8255a36ad3efa815ed094 · (새) RootDesk/MyDesk/@Assist/DataSet/PlayerBaseStatData.userdataset f6d8da25e3b4a28cb5c0d5ce21c414a652e46e89741623d8bd8da6b8123a5d7f · (새) RootDesk/MyDesk/@Assist/DataSet/MonsterStatData.csv f9709bd83183f0c85f36d0d1037a6e7c85f4cb55111ad8d4bfe5536869471dc3 · (새) RootDesk/MyDesk/@Assist/DataSet/MonsterStatData.userdataset b5a226f21c2f636d3ee40ddc6f7a2f56df6f9d9d4ed457fd6fe402037b8fa2f0. 기존 54경로 중 위 4개를 뺀 50경로의 해시는 9eed765와 같다(기존 CSV 5종·.userdataset 5종·모델·맵·UI 파일 포함).
- 커밋 대상 파일(제품): 위 변경 4개 .mlua + 새 PlayerBaseStatCatalog.mlua + Maker 생성 PlayerBaseStatCatalog.codeblock·RootDesk/MyDesk/Player/@Assist/Stat.directory + 새 DataSet 4파일(PlayerBaseStatData·MonsterStatData 각 .csv·.userdataset). .codeblock·.directory는 Bundle 대상 밖이다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) 값 동일성(로드 [VRF] 두 표, 서버·클라이언트 MaxHp·속도·몬스터 값, 자연 공격 간격 3.0 전투 시계, 무대응 12·가드 4, 처치 합계 100)과 이동 구간 speed 6·복귀 6·1단계 홀드 합산·중앙 복귀 잠금, (2) Stop → 다음 Play 재로드와 시험 값 비잔존, (3) 무효 데이터·키·필수 열 프로브(몬스터 표는 서버 `_CombatRuleCatalog:ValidateStatRows`, 플레이어 표는 서버·클라이언트 `_PlayerBaseStatCatalog:Validate`)와 플레이어 표 실패 상태(`_PlayerBaseStatCatalog._T.attempted=true`·Ready false → CanStart false, `IsBaseStatsReady()` false, 대결 없음·몬스터 ATTACK 없음), (4) 파일 CSV 변경 반영(MoveSpeed 6→9, castleenemy MaxHp 100→150)과 원복·바이트 일치, (5) Plan §20 tester 추가 (a) 예고 없는 ↓ 홀드의 PlayerGuard start 로그 재현(클라이언트·서버 CurrentStateName, isGuarding, guardStartTime·시작 위치 기록 유무), (b) 실제 HP 0 플레이어 사망 뒤 시작 위치 기록 삭제와 MaxHp 적용·부활 뒤 Hp 복원, (6) 회차 A F12·F13·F06·F10·F08·V07·V08·V10 회귀 전수. 주의: maker_clear_logs를 호출하지 말고 큰 로그는 저장된 JSON 파일을 시각·표지로 거를 것. Logic 메서드를 임의 함수로 덮어쓰는 시험 방식은 막힌다. 반복 타이머는 ClearTimer로 정리하고 Stop할 것.

## 2026-11-05 coder 회차 C 구현·기본 검증 인계 (CombatCore-MM-01~06·V11-F15)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §21 전체(CombatCore-MM-01~06, V11-F15)뿐이다. §22(회차 D)는 건드리지 않았다. 수치·규칙(D01~D04, 판정 수치, 패턴 4행의 영역·비중·속성, JumpDuration 0.5·JumpHeight 0.8, Pos2 ±0.75·앵커 1.5, 몬스터→플레이어 판정, 머쉬맘 수치 100·12·3.0)과 map01·.ui·CombatRuleData·MonsterAttackComponent·MonsterManager·CombatRuleCatalog·스크립트 이름 OrangeMushroomAttack·`.codeblock`은 바꾸지 않았다. 기존 파일 이동·이름 변경은 하지 않았다(주황버섯 모델 파일 이름 `주황버섯.model` 유지).
- 시작 확인: HEAD e94b981. 작업 트리 변경은 PlayerBaseStatData.csv(사용자 값 `default,100,12,12`)와 run.md뿐이었다. 59경로 manifest(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래)를 e94b981 커밋 트리와 8f16a81 커밋 트리에서 계산해 둘 다 **9325c33ade8a2c32c058cb7e4050a82f8b44d9f22dcfe68c82874cd3e23bcd19**(회차 B 기록과 일치)임을 확인했다. 시작 작업 트리는 PlayerBaseStatData.csv 때문에 5702296c7c11ce70b911d5cede52999f33c13e4bbbc35ee473a304114fc28f6f였다. PlayerBaseStatData.csv는 수정하지 않았다(커밋은 메인이 포함).
- 실제 연결: 시작 시 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186(앞 회차 기록과 같음). 맵 TileMapMode=0(앞 회차 기록, 맵을 바꾸지 않았다). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 저장된 JSON 파일에서 시각·`[VRF…]` 표지로 걸러 읽었다.
- 1단계 모델 읽기 확인(무수정, ModelBuilder.read): 주황버섯 모델은 컴포넌트 14개·Values 45개이고 Plan 기록과 같다(ActionSheet stand 96e955c1…·move 6ad988b3…·jump 94bbe2a7…·hit aec9504d…·die 65a2bfb0…·stun aec9504d…, Scale (2,2,1), HitComponent BoxSize (0.63,0.58)·ColliderOffset (0.045,0.29), DamageSkinOffset (0,0.3), 스크립트 상태 값 17개). DefaultPlayer는 컴포넌트 9개·Values 66개이고 script.AttackRangeGizmo·script.AttackRangeTuner가 붙어 있으며 Values는 AttackRangeGizmo Enable 하나뿐이다(Tuner 값 없음). 표시용 모델은 컴포넌트 2개(Transform·LineRenderer)·Values 10개.

### 변경 파일 (제품)
| 파일 | 변경 | ID |
| --- | --- | --- |
| RootDesk/MyDesk/Models/Monsters/Mushmom.model (새) | ModelBuilder: 주황버섯 모델을 읽어 `renameModel("Mushmom","mushmom")`, ActionSheet 정확히 5키(stand 86015373…·move c745828d…·jump 5ecbcc40…·hit 90fee941…(hit1)·die ec90f0b6…(die1)), SpriteRUID=stand, Scale (1,1,1), HitComponent BoxSize (1.2,1.1)·ColliderOffset (0,0.55), DamageSkinOffset (0,1.1). 그 밖의 컴포넌트 14개·Values는 그대로 | MM-01 |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | `renameModel("주황버섯","orangemushroom")`, Scale (1,1,1), ActionSheet에서 stun 키 제거(5키). 클립·HitComponent 그대로. 파일 이름 변경은 이동 회차 | MM-05·MM-06 |
| Global/DefaultPlayer.model | script.AttackRangeGizmo·script.AttackRangeTuner 컴포넌트와 AttackRangeGizmo Enable 값 제거(컴포넌트 9→7, Values 66→65) | MM-04 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | `1,머쉬맘,model://mushmom` | MM-02 |
| MonsterAttackPatternData.csv | 4행 modelId castleenemy→mushmom(다른 열 무변경) | MM-02 |
| MonsterStatData.csv | 행 id castleenemy→mushmom(값 100·12·3.0 그대로) | MM-02 |
| AttackSkillData.csv | 열 AttackOffsetX·AttackOffsetY·AttackRangeWidth·AttackRangeHeight 삭제(남는 열 id·name·ruid·FrameCount·Direction·Damage·AttackCount, 값 무변경). .userdataset에 열 정보 없음 | MM-04 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | 동작 구간 `Segment`(none·approach·return, @HideFromInspector), `IsSegmentHittable(segment)`(기본 모두 true), `IsHittableNow()` | MM-03 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 속성 ApproachHittable=false·ReturnHittable=false, `IsSegmentHittable` 재정의. PerformAttackMotion·PerformReturnMotion이 성공하면 구간을 approach·return으로, CompleteMotion·CancelMotion이 none으로 되돌림(JumpActive와 일치) | MM-03 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | SetStunned의 `SetVisualClip("stun")` → `SetVisualClip("hit")` | MM-06 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | 속성 attackOffset·AttackRangeWidth·AttackRangeHeight·ShowAttackRangeGizmo와 LoadSkillData의 해당 읽기 제거. 규칙 목록 6개(currentOpponent·sameMap·notPaused·targetAlive·sameCast·targetHittableSegment, `GetHitRules`가 Play당 한 번 생성·재사용, 규칙 함수는 `RuleXxx` 메서드, `CheckHitRules`가 처음 실패한 규칙 이름 반환). ResolveScheduledHit은 예약 시각에 한 번 확인하고 실패하면 `[VRF] PlayerHitRule fail rule=<이름> hit=<번호>`, 통과하면 `[VRF] PlayerHitRule pass hit=<번호> checks=<누적>` 후 상대 몬스터 `WorldPosition + ColliderOffset×Scale`에 놓은 BoxShape(0.1×0.1)로 AttackFast. IsAttackTarget은 `resolvingHit` 안에서만 같은 CheckHitRules를 한 번 더 확인 | MM-03·MM-04 |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 필수 열 Damage·AttackCount·FrameCount 3열, 폭·높이 검사 제거(CRLF 유지) | MM-04 |
| 삭제 | AssistModel.csv·.userdataset, @Assist/RangeGizmo/AttackRangeGizmo.model, Player/@Assist/AttackRange/AttackRangeGizmo.mlua·AttackRangeTuner.mlua(.mlua만 지움) | MM-04 |
- Maker가 자동으로 지운 파일: AttackRangeGizmo.codeblock·AttackRangeTuner.codeblock(Refresh가 .mlua 삭제를 반영해 정리, 손대지 않았다). 남은 빈 폴더 메타데이터: `RootDesk/MyDesk/@Assist/RangeGizmo.directory`와 `RootDesk/MyDesk/Player/@Assist/AttackRange.directory`가 그대로 남았다(이동 회차 확인 대상, 손으로 고치지 않았다).
- 파일 바이트: CSV 4종은 UTF-8 BOM + CRLF 유지, 모델 두 개와 DefaultPlayer는 빌더가 LF·`1.0`→`1` 정수 표기로 쓴 뒤 원본과 같게 CRLF로 맞췄다(의미 차이는 숫자 표기뿐). .codeblock·.directory·.userdataset(AssistModel 제외)·map·.ui는 바꾸지 않았다. 범위 밖 파일을 Maker가 다시 저장한 흔적은 없다(git status에 의도하지 않은 변경 없음).

### 구현 이유 요약
- 규칙 충족형 피격은 사용자 결정 그대로 "공격 위치 조건은 규칙에 넣지 않고 입력 조건(IDLE = Pos2)에 맡김". 규칙 1~5는 기존 ResolveScheduledHit·IsAttackTarget의 검사를 옮겼다. 규칙 4는 `RefreshDuelPlayer`가 죽은 몬스터를 대결에서 먼저 빼므로 실제 흐름에서는 규칙 1(currentOpponent)에서 먼저 걸리고 예약 자체가 CancelAttack으로 취소된다(옛 코드와 같은 결과). 규칙 4는 직접 호출 프로브로 확인했다.
- 피해 전달은 엔진 흐름(AttackFast → IsAttackTarget → CalcDamage → HitEvent → 몬스터 HP)을 그대로 쓴다. 규칙 통과 모양만 상대 위치로 바뀌었고 몬스터 크기·HitComponent는 판정에 들어가지 않는다.
- 구간 선언은 하드코딩이 아니라 모션 컴포넌트 속성이다. 규칙 6은 상대의 모션 컴포넌트가 없으면 통과한다.

### 실제 기본 검증 (Maker MCP, Play 1회 + 서버/클라이언트 프로브, 시험 설정은 Play 내부에만 두고 Stop으로 정리)
빌드·등록 사이클: 삭제·수정 뒤 Refresh 1회, 모델·CSV 변경 뒤 Refresh 1회. build 로그 83건 전부 Info(LIA 1114/1115 동적 참조 노이즈), 오류 0·경고 0.

| 항목 | 결과 |
| --- | --- |
| 로드 | `[VRF] catalog ready rules=1 patterns=4 monsterStats=2`, MonsterStatData default 100·12·3.0과 mushmom 100·12·3.0, `PlayerBaseStatData side=server/client default MaxHp=100 MoveSpeed=12 ReturnSpeed=12`, 플레이어 `PlayerStat applied MaxHp=100 Hp=100`, `MovementInput boot speed=12.0 return=12.0`. 패턴 mushmom 4행 `parry.left:2,parry.right:2,parry.any:2,special.random:1`(Weight 2·2·2·1). AttackSkillData player.basic Damage 1·AttackCount 10·FrameCount 14·ruid 5308ef85… |
| 스폰 | 엔티티 이름 머쉬맘, Scale (1,1,1), ActionSheet 키 5개와 RUID 5개가 기대와 일치(stand 86015373…·move c745828d…·jump 5ecbcc40…·hit 90fee941…·die ec90f0b6…), 시작 SpriteRUID = stand, HitComponent BoxSize (1.2,1.1)·ColliderOffset (0,0.55), DamageSkinOffset (0,1.1). 몬스터 위치 (3.0,0.581). 엔티티의 모델 id 속성은 nil로 읽혀 `model://mushmom`은 스폰 성공(SpawnByModelId "mushmom")과 MonsterManager 스폰 로그로 확인 |
| 표시 시계열(서버 SpriteRUID/클라이언트 SpriteRUID, 전투 시계) | IDLE stand → ATTACK 접근 jump → 착지 순간 stand(판정 시각) → 복귀 jump → IDLE stand를 서버·클라이언트가 같이 기록(예: 서버 t=23.079 jump·approach, 23.562 판정, 23.596 jump·return, 24.081 stand·IDLE). 그로기 전체 hit(서버 hit·STUN t=305.941, 클라이언트 hit·STUN t=305.879, 그로기 중 피격에도 SpriteRUID는 hit 유지, 종료 t=307.425 stand·IDLE). STUN 진입 때 엔진이 낸 클립 요청은 `AnimationClipEvent name=stun`(ActionSheet에 stun 키 없음)이었고 SpriteRUID는 바뀌지 않음. 피격 반응은 `AnimationClipEvent name=hit`(엔진 HIT 상태가 hit 키를 요청, SpriteRUID 속성은 stand 그대로). 사망은 아래 |
| 사망 die 1회 뒤 정지(F12 회귀) | IDLE 사망: `MonsterDie start frames=6 total=1.100 freezeAfter=0.800`, 0.8초 뒤 `freeze frame=5`, 서버·클라이언트 SpriteRUID die, 5/5 고정이 6초 뒤에도 유지(state DEAD). 그로기 중 사망: ApplyGroggy(1.5) 뒤 0.5초에 ApplyDamage(999) → 같은 start/freeze 로그, 서버·클라이언트 die 5/5 고정, 6초 뒤에도 유지. **머쉬맘 die1 클립 실제 재생: 프레임 6개, 총 1.100초, 마지막 프레임(인덱스 5)은 0.800초 시점에 시작해 고정** |
| 피격 규칙 모두 통과 | IDLE 몬스터에 실제 입력 경로(PlayerStateControl.RequestChangeState("ATTACK"))로 기본 공격 → `PlayerHitRule pass` 10줄(hit 1~10), HitEvent 10회·합계 10·몬스터 HP 100→90(=HitEvent 합계 = 피해 숫자 1×10). 규칙 확인 횟수는 타격당 2회(예약 시각 1 + IsAttackTarget 1)로 10타 후 checks=20. 규칙 목록 생성은 Play 전체에서 builds=1(로그 `list built rules=6 builds=1`), Play 종료 시점 누적 checks=149 |
| 접근 점프 중 | 예고 시작(telegraph 0.5 남음)에 공격 → hit 1~10 모두 `fail rule=targetHittableSegment`, 피해 0 |
| 복귀 점프 중 | (무대응) 복귀 시작 직후 공격 → hit 1~10 모두 fail, 피해 0. (패링) 패링 성공 직후 공격(반격 보너스 ×2.2는 시전 시작에 소비, D03) → hit 1~6 fail, 복귀 끝(그로기 시작) 뒤 hit 7~10 pass. (저스트, 슬로우 ×0.5) 복귀가 전투 시계 1.0초(310.958→311.959)로 늘어남 → hit 1~10 모두 fail |
| 걸친 공격 | 복귀 시작 0.28초 뒤 공격 → hit 1~3 fail, hit 4~10 pass(HitEvent 7회, 몬스터 HP 90→83). 패링 사례도 hit 1~6 fail·7~10 pass |
| 착지·그로기 뒤 | 저스트 뒤 복귀 완료 IDLE에서 공격 → 10타 모두 pass(보너스는 앞 공격에서 소비돼 factor 1). 패링 그로기 중 두 번째 공격(몬스터 클라이언트 상태 HIT, 서버 STUN) → 10타 모두 pass, 그로기·hit 표시 유지 |
| 반격 창 기록 | 패링: counter granted until=307.401(성공 305.401 + 2.0), 복귀 0.5초(305.417→305.917), 그로기 1.5초(305.907→307.407) → 피격 가능 구간 약 1.5초. 저스트: 슬로우로 복귀 1.0초 → 반격 창 2.0초 중 피격 가능 약 1.0초 |
| 크기 무관 | HitComponent BoxSize를 (0.4,0.4)로 줄이고 공격 → pass 10, HitEvent 10·합계 10, HP 55→45. 모양은 항상 몬스터 `WorldPosition + (0,0.55)`(=(3.0,1.131))에 놓은 0.1×0.1 상자. 시험 뒤 BoxSize를 (1.2,1.1)로 되돌림 |
| 규칙별 실패(프로브 근거: 합성 시전 스냅샷으로 CheckHitRules/RuleXxx 직접 호출) | sameCast: 플레이어 IDLE에서 `'sameCast'`. currentOpponent: 대상=플레이어 `'currentOpponent'`. sameMap: 시전 맵=/maps `'sameMap'`. notPaused: 플레이어를 소유자로 하는 실제 `SetServerPaused(true)` 상태에서 `'notPaused'`. targetAlive: `RuleTargetAlive` 직접 호출 정상 true, IsDead true일 때 false, Hp 0일 때 false. 사망 몬스터로 CheckHitRules를 부르면 `'currentOpponent'`(위 구현 이유) |
| 스킬 표 검증(프로브 근거: 가짜 행을 표로 연결, 끝나고 원래 표 복원) | 3열(Damage·AttackCount·FrameCount)+ruid 정상 → 통과, 옛 범위 열이 쓰레기 값이어도 무시하고 통과. Damage 누락·−1·nan, AttackCount 0·1.5, FrameCount 0, ruid 빈 칸 → 거부. 복원 뒤 실제 player.basic 1/10/14 |
| 주황버섯 모델 | `SpawnByModelId("orangemushroom")` 성공: Scale (1,1,1), ActionSheet 5키, stun 키 없음. 주황버섯 스폰 거부(프로브): MonsterManager.data를 orangemushroom 행으로 바꿔 DoSpawn → `[VRF] MonsterManager spawn refused key=orangemushroom reason=stats`, 현재 상대 유지, GetMonsterStats nil, 경고 `monster stat row missing: orangemushroom` 1회 |
| 삭제 | `_DataService:GetTable("AssistModel")` 호출 성공·결과 nil. 삭제한 표시용 모델 id 27e5fe09… 스폰 → `[LEA-3028] MissingModel`(등록 없음). 플레이어 엔티티에 script.AttackRangeGizmo·script.AttackRangeTuner 컴포넌트 없음(서버·클라이언트) |
| grep | 제품 파일(RootDesk·Global·map·ui)에서 castleenemy·AttackRangeGizmo·AttackRangeTuner·AssistModel·ShowAttackRangeGizmo·AttackOffset·AttackRangeWidth·AttackRangeHeight·27e5fe09·attackOffset 일치 0 |
| 구간 선언 | OrangeMushroomAttack ApproachHittable=false·ReturnHittable=false, Segment 시험 끝 none |
| 로그 요약 | Info 1105·Warning 3·Error 2. Warning 3건은 의도한 프로브(주황버섯 수치 행 없음 1, 스킬 표 가짜 행 2). Error 2건도 의도한 프로브(`model://castleenemy` 문자열을 엔티티 이름으로 쓴 LEA-3021, 삭제한 표시용 모델 id 스폰의 LEA-3028). 정상 구간 Warning·Error·LEA/LWA 없음 |

- 프로브 한계: 첫 notPaused 프로브는 `pause.IsPaused = true`를 직접 써서 CombatPauseComponent.OnUpdate의 AbortCombat이 즉시 정지를 풀어 시험이 성립하지 않았다(제품 오류 아님). 실제 SetServerPaused 경로(소유자 지정)로 다시 했다. 패링/저스트 시험은 판정 창 JustWindowSec·ParryWindowSec를 Play 내부에서 30초로, mushmom 패턴을 parry.any 단일 행으로 바꿨고(프로브 근거) 시험 뒤 0.2·0.2와 4행으로 복원했다(`D restored just=0.2 parry=0.2 rows=4`). 이 때문에 이후 몇 번의 접근 JUST가 자동으로 났고 이는 시험 값 영향이다. 시험 중 플레이어는 무대응 12 피해로 사망·부활(대결 없음 5초)이 여러 번 있었다(시험 방식 영향).
- 반복 타이머(서버 기록 타이머, 클라이언트 기록 타이머)는 ClearTimer로 정리하고 Stop했다.

### 중단 조건 해당 여부
1. STUN 뒤 엔진의 hit 덮어쓰기: **해당 없음**(서버·클라이언트 SpriteRUID가 그로기 내내 hit, stun 키는 되살리지 않음).
2. 몬스터 위치 AttackFast가 HitEvent·피해 숫자·HP 감소를 못 맞춤: **해당 없음**(10타 HitEvent 10·합계 10·HP 감소 10, 박스 축소 시험도 동일).
3. renameModel 뒤 EntryKey 불일치 또는 Maker에 castleenemy 항목이 남음: **해당**. 파일의 EntryKey는 `model://mushmom`·`model://orangemushroom`으로 올바르고 제품 파일에 castleenemy 문자열은 없다. 그러나 Refresh 두 번 뒤 Play에서 `SpawnByModelId("castleenemy")`(대문자 `CastleEnemy` 포함)가 **여전히 성공**하고 **옛 내용**(Scale 2, SpriteRUID 96e955c1…, stun 키 포함 모델)의 엔티티를 만든다. `model://castleenemy` 항목이 Maker 작업 공간에 남은 것이다(같은 파일의 새 키 `orangemushroom`은 Scale 1로 정상 등록, 삭제한 표시용 모델·스크립트·AssistModel은 정상 제거). 대체 구현 없이 여기서 멈춘다. 제품 동작에는 영향이 없다(MonsterData는 mushmom만 쓰고 castleenemy를 참조하는 제품 파일이 없음). 선택지는 반환 보고에 적었다.
4. 스크립트 삭제 뒤 .codeblock·Maker 항목 잔존: **해당 없음**(.mlua 삭제만으로 Refresh가 .codeblock 2개를 지웠고 컴포넌트·모델 등록도 없음).
5. 크기·피벗 때문에 BattlePos 간격 등을 바꿔야 함: **해당 없음**(바꾸지 않음. 크기와 겹침은 사용자 V11 확인).
6. 범위 열 삭제가 다른 읽는 곳을 깨뜨림: **해당 없음**(grep 0, 로드·스킬 표 검증 정상).
7. Refresh가 범위 밖 파일을 다시 저장: **해당 없음**(없음).

### 최종 제품 버전 묶음 (회차 C)
- 같은 계산법·같은 확장자 집합의 manifest. 회차 B 마지막 값 9325c33a…(59경로)와 일치하는 e94b981 커밋 트리를 먼저 계산한 뒤 작업 트리를 계산했다. 삭제 5경로(AssistModel 2·표시용 모델 1·스크립트 2)와 새 1경로(Mushmom.model)로 **55경로**다.
- Bundle SHA-256(작업 트리, 55경로): **47bdb6a834a5b8a7daec27a3bea8fabbe22b8c74454912048d9f3c202bc0aa7d**. 시험 후 Stop 뒤에 계산했고 Play 전후 파일 변경은 없다.
- 변경·추가 11경로 SHA-256: Global/DefaultPlayer.model deedf553e96fd7144a56416e72619820dfca5862a68ae82effb52b3bab1dde52 · RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv 8218eb71930d38d97f58f7dda4d045bca5f14252559a249a5172c60ee0f83b5e · MonsterAttackPatternData.csv fb15494c6a3cbd8026507a4d43764385d9a10202150550348fecf891d736cee9 · MonsterData.csv ca5dc4d9fc4f7b9cdb4f3c461b1395af2a8b010d4a180549251457e0af4a4ba6 · MonsterStatData.csv a87dcb2f9865ca9dae634a740540fb86811c24c8f31201aec25d64e96a83344f · (새) RootDesk/MyDesk/Models/Monsters/Mushmom.model dfb422234ee66cf4228b86b27e577f49c997bde40cc78296eeb5aa9321bf9ecf · RootDesk/MyDesk/Models/Monsters/주황버섯.model f8737cba9b8be39be876f3a1ac9c721ee2b9b9032e093219d4f4467b23f9e6bf · Monster/MonsterAttackMotion.mlua a597f73ec51173e2286a2a3ba6cf41236b5548cbf9247ba3bfb01c1277c9ab81 · Monster/MonsterStunComponent.mlua b7fdc6721d6e91d32decf3a25840c2ae630601ceb45340c9eb168bd68e38def9 · Monster/OrangeMushroom/OrangeMushroomAttack.mlua b8ebb301c1dad809e9a48b1853ab7a7a01ea268431cbebfd17198d1d448f44b3 · Player/@Assist/Skill/PlayerSkillEffectTable.mlua 8558c89c715c235fee5d6974c68cf2158b76501f36f2ed062144afa4778a1822 · Player/PlayerCombatComponent.mlua b3b51e659c70073b2188105942d9aa3d63a969bed6562d1da72cf8edd35a1eea. PlayerBaseStatData.csv는 시작 작업 트리 값(사용자 변경)이고 이번에 수정하지 않았다. 나머지 43경로는 e94b981과 같다.
- 커밋 대상(제품): 위 변경·추가 파일 + 삭제 5경로 + Maker가 지운 .codeblock 2개 + PlayerBaseStatData.csv(사용자 값). 남은 AttackRange·RangeGizmo 폴더 .directory는 이동 회차에서 확인한다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 중단 조건 3(castleenemy 항목 잔존)이 열려 있다. 다른 실패는 없다.
- 미실시: 머쉬맘의 실제 화면 모습(크기, BattlePos 겹침, HP 게이지·별·피해 숫자 위치, 피벗)은 스크린샷을 찍지 않아 사용자 V11이다. HitComponent (1.2×1.1, 오프셋 0.55)와 DamageSkinOffset (0,1.1)은 계획 예시값을 따랐으며 스프라이트 피벗과 실제로 맞는지 확인하지 않았다. 사람 손 타이밍, 실기기·모바일, 다중 접속. hit1·move 클립의 실제 재생 시간(die1만 측정). 모든 규칙 실패를 실제 흐름에서 로그로 낸 것은 아니다(규칙 1·2·4·5는 프로브, 규칙 3은 팝업식 서버 정지 프로브, 규칙 6과 시전 취소는 실제 흐름). 규칙 4 실제 흐름 로그는 위 구현 이유 때문에 나오지 않는다.
- 관찰(바꾸지 않음): 그로기 중 피격 때 클라이언트의 몬스터 StateComponent 이름이 HIT로 보이고(서버는 STUN 유지, SpriteRUID는 hit 유지) 그로기 종료 시 stand·IDLE로 정리됐다. 이전 회차 동작과 비교는 하지 않았다. 엔진 HIT 상태의 hit 표시는 SpriteRUID 속성이 아니라 `AnimationClipEvent name=hit`로만 나타난다(앞 회차와 같은 구조).

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- 중단 조건 3의 처리는 사용자 선택이 필요하다(Maker 작업 공간 재로드 또는 Maker에서 castleenemy 항목 삭제). 처리 뒤 Play에서 `SpawnByModelId("castleenemy")`가 nil인지 확인하면 된다. 주의: 옛 항목이 같은 파일 경로를 가리킬 수 있어 재로드·저장 뒤 `주황버섯.model`이 옛 내용(Scale 2·stun 키·키 castleenemy)으로 되돌아가지 않았는지 git diff로 확인해야 한다.
- tester가 확인할 것: 위 표 전부를 같은 방법으로 독립 재현(특히 규칙 6 접근·복귀·걸친 공격, 패링/저스트 복귀 중 공격, 박스 축소, 주황버섯 스폰 거부, 스킬 표 검증), 회차 A F12·F13, 회차 B DataSet 로드·실패 동작, V07·V08 팝업 정지(구간 선언 유지)와 Stop 뒤 다음 Play 구간 none, 몬스터→플레이어 판정 회귀. 주의: maker_clear_logs를 호출하지 말고 로그는 저장된 JSON 파일을 시각·`[VRF…]` 표지로 거를 것. `pause.IsPaused`를 직접 쓰는 시험은 쓰지 말고 소유자를 지정한 SetServerPaused를 쓸 것.

### 2026-11-05 독립 QA 10회차 — 회차 C(CombatCore-MM-01~06·V11-F15)
- 상태: **실행 완료.** 실행 기준 PASS, FAIL·NEEDS_DECISION·새 결함 없음. coder 중단 조건 3(옛 키 castleenemy 항목 잔존)은 사용자의 월드 재열기 뒤 **해소 확인**. 독립 reviewer 대기. NOT_RUN과 사용자 직접 확인은 아래 절.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품 코드·모델·맵·UI·DataSet·CSV 수정 없음, commit·push 없음, **maker_clear_logs 호출 없음**(Maker 로그는 저장 파일을 `[T10`·`[VRF` 표지와 시각으로 걸러 읽음). coder 개발절의 PASS는 이번 실행으로 세지 않았고 아래 표는 모두 이번 Play의 서버·클라이언트 프로브와 실제 키 입력 근거다.
- 대상 버전: HEAD **b4adbdd**(= coder `[code]` 커밋 5a605ba + 그 위 `[ops]` Maker 재저장). 55경로 manifest(경로 `LC_ALL=C sort`, 경로 + TAB + sha256 + LF 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래) **Bundle SHA-256 `222e7a041b619cc26bb3bd51492a352cd95a41c42259fc8f6f06e9c5e03b476d`**. 같은 계산법으로 5a605ba 커밋 트리는 `47bdb6a834a5b8a7daec27a3bea8fabbe22b8c74454912048d9f3c202bc0aa7d`(coder 기록과 일치)였다. **5a605ba→b4adbdd의 manifest 차이 경로는 2개뿐**이다: `RootDesk/MyDesk/Models/Monsters/Mushmom.model` dfb42223…→c1570deb6067…, `RootDesk/MyDesk/Models/Monsters/주황버섯.model` f8737cba…→87686d37a01e…. 다른 53경로 해시는 같고, manifest 밖 변경은 `.directory` 6개(CoreVersion)다(`git diff --stat 5a605ba b4adbdd`: 8파일). 모델 두 파일의 변경이 숫자 표기뿐이라는 의미 비교는 메인의 JSON 비교를 따랐고(모델 파일은 셸 읽기가 금지돼 내가 diff를 보지 않았다), 대신 Play에서 스폰한 모델의 Scale·ActionSheet·HitComponent·DamageSkinOffset 값을 직접 읽어 확인했다(아래 첫 단계). 작업 트리는 시작 때 run.md만 변경이었고 시험 뒤에도 run.md만 변경, 작업 트리 55경로 해시 목록이 b4adbdd와 **완전히 일치**(Play 전후 제품 파일 무변경).
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186(앞 회차 기록과 같음). TileMapMode는 앞 기록(0 MapleTile)을 따랐고 다시 읽지 않았다. build 로그 83건 모두 Info(LIA 1114/1115 동적 참조), 오류 0·경고 0, 시험 전·후 동일(같은 시각 20:39:19 항목). Play 2회(Play 1 20:43~20:55 본 시험, Play 2 20:56 Stop 뒤 기본 상태 확인), 마지막 Stop 뒤 map01 / edit 확인. 런타임 로그 요약: Error 2건(내가 의도한 `SpawnByModelId("castleenemy"/"CastleEnemy")` LEA-3028), Warning 21건(모두 내 무효 데이터 프로브가 의도적으로 낸 것), 정상 구간 LEA/LWA 없음.
- 방법 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client). (B) 실제 키 입력 = maker_keyboard_input. 서버 `player.StateComponent:ChangeState("ATTACK"/"GUARD")`는 **논리 경로**(UpArrow/DownArrow 실제 키와 구분해 아래에 표기). 시험값(Play 내부): 몬스터 AttackInterval 9999(자연 공격 억제), 판정 창 JustWindowSec·ParryWindowSec 30초, 패턴 표 단일 행 교체, 몬스터 Hp·플레이어 Hp 설정, 몬스터 HitComponent BoxSize 0.4×0.4, 모션 Segment 직접 값, 소유자를 지정한 `SetServerPaused`. 모두 시험 끝에서 복원을 로그로 확인했고(`windows restored just=0.2 parry=0.2`, `restored patterns=4`, `box restored=(1.200, 1.100)`) Stop으로 폐기됐으며, 새 Play 2 시작에서 기본값을 다시 확인했다(아래 V08).

#### 첫 단계 — 옛 키·모델 등록 확인 (coder 중단 조건 3)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| `SpawnByModelId("castleenemy")`·`"CastleEnemy"` | A | 둘 다 nil, `[LEA-3028] MissingModel : Model 'castleenemy'/'CastleEnemy'가 없습니다.` 각 1건(의도한 프로브 오류). 옛 내용(Scale 2·stun 키)으로 스폰되지 않음 | PASS (조건 3 해소) |
| `model://mushmom` 등록·내용 | A(스폰해 읽고 즉시 Destroy) | Scale (1,1,1), SpriteRUID = stand 86015373…, ActionSheet **정확히 5키**: die ec90f0b6…·hit 90fee941…·jump 5ecbcc40…·move c745828d…·stand 86015373…(Plan 표와 일치), stun 키 없음, HitComponent BoxSize (1.2,1.1)·ColliderOffset (0,0.55), DamageSkinOffset (0,1.1) | PASS |
| `model://orangemushroom` 등록·내용 | A | Scale (1,1,1), ActionSheet 5키(die 65a2bfb0…·hit aec9504d…·jump 94bbe2a7…·move 6ad988b3…·stand 96e955c1…), **stun 키 없음**, BoxSize (0.63,0.58)·Offset (0.045,0.29)·DamageSkinOffset (0,0.3) | PASS |
| MonsterManager 스폰 | A | 부팅 스폰 엔티티 이름 `머쉬맘`, Scale 1.0, 시작 SpriteRUID 86015373…(stand), MonsterData `머쉬맘 / model://mushmom` | PASS |

#### 자동 검사 — 전환·삭제 (Plan §21 확인 기준)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 로드 [VRF] | A | `catalog ready rules=1 patterns=4 monsterStats=2`, `MonsterStatData id=default/mushmom 100·12·3.0`, `PlayerBaseStatData side=server`·`side=client default MaxHp=100 MoveSpeed=12 ReturnSpeed=12`, `PlayerStat applied MaxHp=100 Hp=100`, `MovementInput boot speed=12.0 return=12.0`. 패턴 `GetPatterns("mushmom")` 4행 parry.left·parry.right·parry.any·special.random = Weight 2·2·2·1(modelId mushmom). `GetPatterns("castleenemy")` nil(경고 1회), orangemushroom 패턴·수치 행 없음. AttackSkillData player.basic Damage 1·AttackCount 10·FrameCount 14·ruid 5308ef85…, **열 7개 id·name·ruid·FrameCount·Direction·Damage·AttackCount**(범위 4열 없음) | PASS |
| 표시 시계열 — 서버·클라이언트 SpriteRUID | A(30ms 폴링 변경 기록) | 접근 jump(5ecbcc) → **착지 stand(860153, x=0.75, 시작 +0.504초)** → 복귀 jump → IDLE stand(x=3.0). 서버·클라이언트 같은 순서(예고 1.0초 사례: 서버 612.745 jump·approach → 613.249 stand x=0.75 → 613.772 jump·return → 614.261 stand·IDLE). 그로기 전체 hit(90fee9)(서버 STUN·hit, 클라이언트 STUN·hit), 그로기 종료 stand(860153)·IDLE. 피격 반응은 SpriteRUID가 stand 유지(엔진 HIT 상태, 앞 회차와 같은 구조). **STUN 진입 뒤 hit를 다른 값으로 바꾸는 갱신 없음**(서버·클라이언트 모두 그로기 내내 90fee9, 그로기 중 피격 10타에도 유지). 사망 die는 아래 F12 | PASS |
| 빌드·등록 | A+B | 빌드 로그 오류 0(위). `_DataService:GetTable("AssistModel")` nil. 플레이어 엔티티의 `script.AttackRangeGizmo`·`script.AttackRangeTuner` GetComponent nil. `model://orangemushroom`·`model://mushmom` 등록, `model://castleenemy` 없음 | PASS |
| grep | git grep / Grep 도구 | 제품 파일(Global·RootDesk·map·ui)에서 castleenemy·AttackRangeGizmo·AttackRangeTuner·AssistModel·ShowAttackRangeGizmo·AttackOffset·AttackRangeWidth·AttackRangeHeight·27e5fe09·attackOffset(대소문자 무시) **일치 0**. 남은 것: 빈 폴더 메타데이터 `@Assist/RangeGizmo.directory`·`Player/@Assist/AttackRange.directory`(coder 기록과 같음, 이동 회차 확인 대상) | PASS |
| 주황버섯 스폰 거부 | A(프로브 근거: MonsterManager.data를 orangemushroom 한 행으로 바꿔 DoSpawn 2회, 끝나고 원래 표 복원) | `[VRF] MonsterManager spawn refused key=orangemushroom reason=stats` 2회, **경고 `monster stat row missing: orangemushroom` 1회만**, 현재 상대 그대로(`sameMonster=true`), default로 스폰하지 않음 | PASS |
| 스킬 표 검증 | A(프로브 근거: 가짜 표 연결, 끝나고 원래 표·캐시·경고 복원) | 3열 정상(옛 범위 열에 쓰레기 값을 넣어도 무시) → 수락 D=1 A=10 F=14. Damage 누락·−1·nan, AttackCount 0·1.5, FrameCount 0, ruid 빈 칸 → **모두 거부**(각 경고). 복원 뒤 실제 player.basic 1/10/14 | PASS |

#### 자동 검사 — 피격 규칙 (MM-03)
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 모두 통과 | 논리(서버 ChangeState ATTACK) + **실제 UpArrow 100ms 탭 1회** | IDLE 몬스터에 10타: `PlayerHitRule pass hit=1~10`, HitEvent 10회·합계 10, 몬스터 Hp 100→90(= HitEvent 합계 = 피해 숫자 1×10). 논리 사례와 실제 키 사례가 같은 결과. 규칙 확인 횟수 타격당 2회(예약 시각 1 + IsAttackTarget 1)로 10타에 +20, 규칙 목록 생성 **Play 전체 builds=1**(`list built rules=6 builds=1` 1줄, 누적 checks 223 후에도 1) | PASS |
| 접근 점프 중 | A(몬스터 ATTACK 시작 0.05초 뒤 시전, parry.left 강제) | hit 1~10 모두 `fail rule=targetHittableSegment`, HitEvent 0, 몬스터 Hp 변화 없음, 규칙 확인 +10(타격당 1회) | PASS |
| 복귀 점프 중 — 무대응 | A(몬스터 시작 +0.55초 시전) | hit 1~10 모두 fail, 피해 0 | PASS |
| 복귀 점프 중 — 패링 | A(서버 GUARD 논리 + 복귀 중 시전) | PARRY 판정 217.773, 시전 factor 2.2(보너스 시전 시작에 소비): hit 1~9 fail, **복귀 끝·그로기 진입 순간 hit 10 pass**(HitEvent 1·합계 2 = floor(2.2)) | PASS |
| 복귀 점프 중 — 저스트(슬로우 ×0.5) | **실제 LeftArrow 탭** + 복귀 중 시전 | JUST 판정 445.179, 슬로우 2.0초 ×0.5, 복귀가 전투 시계 약 1.0초(445.18→446.2), 복귀 중 시전(factor 2.2): HitEvent 0·피해 0(전부 fail). 보너스 소비됨 | PASS |
| 착지 뒤 | A | 무대응 복귀 뒤 IDLE 시전 10타 모두 pass(Hp 100→90) | PASS |
| 걸친 공격 | A(몬스터 시작 +0.85초 시전) | **hit 1~4 fail, hit 5~10 pass**(복귀 완료 IDLE 직후), HitEvent 6·Hp 100→94 | PASS |
| 그로기 중 | A(패링 → STUN 진입 직후 시전) | 반격 남은 1.491초, 10타 모두 pass, factor 2.2: HitEvent 10·합계 **20**(2/타), 몬스터 Hp 100→80. 그로기 중 보너스 없이 시전(factor 1): 10타 pass·합계 10 | PASS |
| 반격 창 기록 | A + **실제 DownArrow 홀드(PARRY)·실제 LeftArrow 탭(JUST)** | **패링**: 판정 500.819, 반격 until 502.819(+2.0), STUN 진입 501.335, 그로기 종료 502.839(그로기 1.5초) → 피격 가능 구간 약 1.48~1.5초. **저스트**: 판정 473.973, until 475.973, 복귀 완료 IDLE 474.981(복귀 1.008초), 그때 `counterRemaining=0.992` → 피격 가능 약 1.0초. 복귀 완료 IDLE 직후 시전: factor 2.2, HitEvent 10·합계 20 | PASS |
| 크기 무관 | A(HitComponent BoxSize (0.4,0.4)로 줄인 뒤 시전, 끝나고 (1.2,1.1) 복원) | pass 10, HitEvent 10·합계 10, Hp 100→90. 모양은 몬스터 WorldPosition + ColliderOffset×Scale = **(3.000, 1.131)**에 놓은 0.1×0.1 상자(콜라이더 크기와 무관) | PASS |
| 확인 시점·재사용 | 위 로그 집계 | 규칙 확인은 타격 예정 시각에만(타격당 [VRF] 1줄: pass 또는 fail), 규칙 목록 생성은 Play당 1회(builds=1). 시전 0.12초 뒤 취소 시 이후 예약 타격 해제(HitEvent 4·규칙 확인 +8 뒤 더 늘지 않음) | PASS |
| 규칙별 실패 이름 | A(프로브 근거: 합성 시전 스냅샷 `CheckHitRules`/`RuleTargetAlive` 직접 호출) | 플레이어 IDLE → `sameCast`; 방어자=플레이어 → `currentOpponent`; 시전 맵=/maps → `sameMap`; **소유자를 지정한 `SetServerPaused(true)` 뒤 0.15초에 `notPaused`**, 재개 뒤 다시 `sameCast`; 대상 생존 true / IsDead true→false / Hp 0→false(추가 스폰한 머쉬맘, 끝나고 Destroy); 상대 아닌 몬스터 → `currentOpponent`. 구간 선언: Segment none→hittable true, approach·return→false, ApproachHittable=ReturnHittable=false | PASS (규칙 1·2·4·5는 프로브 근거, 규칙 3 일부와 규칙 6·취소는 실제 흐름) |

#### 회귀 표 (플레이어 100·12·12 기준)
| 기존 근거 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 회차 A F12 — IDLE 피격 사망 | A(Hp 5, 실제 10타 피격 경로) | HIT→DEAD, `MonsterDie start frames=6 total=1.100 freezeAfter=0.800`, 서버·클라이언트 SpriteRUID die(ec90f0), 0.8초 뒤 `freeze frame=5`(fr 5-5), +3.3초에도 5-5 유지(머쉬맘 die1: 프레임 6개, 총 1.100초) | PASS |
| 회차 A F12 — 그로기 중 사망 | A(ApplyGroggy 1.5 뒤 0.5초 ApplyDamage 999) | STUN·hit → DEAD·die, 같은 start/freeze 로그, 클라이언트 STUN\|die(1틱)→DEAD, +4.3초에도 5-5 | PASS |
| 회차 A F13 — Pos2 시작 PARRY | **실제 DownArrow 홀드**(판정 창 30초 시험값) | `PlayerGuard start x=0.000`, `guard eval x=0.000 cellOk=true areaOk=true attr=PARRY`, `defense kind=PARRY rate=0`, 플레이어 Hp 100 유지, 반격·그로기 | PASS(시험값) |
| 회차 A F13 — Pos2 시작 JUST | **실제 LeftArrow 탭 2건**(판정 창 30초 시험값) | `PlayerEvade start x=0.000`, `evade eval x=0.000 cellOk=true areaOk=true dir=LEFT`, `defense kind=JUST rate=0`, 슬로우 2.0×0.5, 반격 | PASS(시험값) |
| 회차 A F13 — 끝 칸 1칸 공격 무보상 | **실제 LeftArrow 홀드**(RIGHT·PARRY·앵커 1~1, 판정 창 30초) | 플레이어 x=−1.5 홀드, `evade eval x=0.000 cellOk=true areaOk=false dir=LEFT`, `defense kind=HIT rate=1 nativeHit=true`, Hp 100→88(−12), 반격·슬로우 없음 | PASS(시험값) |
| 서버 기록 x 대 클라이언트 segment.startX (속도 12) | 실제 키 4건(JUST 2·끝 칸 홀드 1·UI 합산 1 포함) | 서버 `PlayerEvade start x=0.000` / 클라이언트 `MovementInput phase=OUTBOUND x=0.0` 차이 **0.000**(로컬 Maker에서는 지연이 없어 허용 여유 절반 문제는 재현되지 않음). 서버 `PlayerGuard start x=0.000`(실제 DownArrow). 실기기 지연은 NOT_RUN | PASS(로컬) / NOT_RUN(실기기) |
| F06·F10 — 패턴 4행·선택, 2칸 중간 착지·점프 0.5초·판정 시각 | A | 4행 Weight 2·2·2·1(위). 자연 공격에서 parry.right(min −2.0 max 0.5)·parry.left(−0.5~2.0)·parry.any(−0.5~0.5, target 2)·special.random(1.0~2.0, target 3) 모두 선택·판정(Play 1 부팅 직후 10회, Play 2 8회). parry.left 강제 사례: 몬스터 x 3.0→**0.75 중간 착지**, 점프 +0.504초, 판정 시각 = 시작 + 예고(0.5·1.0 사례 모두 일치) | PASS |
| F08·F02 — 패링 → 복귀 뒤 그로기 1.5초, 그로기 중 hit | A + 실제 DownArrow | 복귀 0.5초 뒤 STUN(hit 90fee9), 그로기 1.5초 뒤 IDLE(stand): `groggy applied deadline=502.835`, 종료 관측 502.839 | PASS |
| V07 — 예고(접근) 중 정지·재개 | A(소유자 지정 `SetServerPaused`, 서버 경로) | 접근 +0.2초에 정지: 전투 시계 612.936 고정(1.5초), x 2.064 고정, Segment=approach 유지, 피격 가능 false, JumpActive true, 정지 중 시전 시도는 `active=false`·HitEvent 0·규칙 확인 0. 재개 뒤 판정 613.737(시작 612.728 + 예고 1.0, 정지 구간 제외), 복귀 | PASS(서버 정지 경로) |
| V07/V08 — 복귀 점프 중 정지, 구간 선언 유지 | A | 복귀 +0.15초에 정지 1.2초: 시계 613.896 고정, x 1.465 고정, **Segment=return 유지**, 피격 가능 false, 시전 거부(HitEvent 0·checks 0). 재개 뒤 IDLE·Segment none·x=3.0·IsPaused false | PASS |
| V08 — Stop 뒤 다음 Play 기본 상태 | A | 복귀 점프 중 정지한 채(`Segment=return` 유지, 패턴 1행, AttackInterval 9999) **Stop → 새 Play 2**: `IsPaused=false owner=nil seg=none jumpActive=false mstate=IDLE patterns=4 windows=0.2/0.2 AttackInterval=3.0 monHp=100.0 monName=머쉬맘 scale=1.0 hitBox=(1.200, 1.100)`, `ruleBuilds/ruleChecks=nil`(새 Play에서 새로 시작). 시험값 비잔존(플레이어 Hp 52/100은 그 사이 자연 공격 4회 12씩) | PASS |
| V10 — 이동·방향키·UI 출처·반환 잠금·타수 | B + A(클라이언트 `RequestChangeState` 논리 호출) | 이동 OUTBOUND 1.5 거리 `elapsed` 0.121~0.139초(1.5/12 = 0.125), 복귀 RETURNING 0.122~0.158초(중간에서 복귀 시작한 부분 거리는 0.087초). UI 출처 `RequestChangeState("LEFT","ui.left")` 수락·`MOVE\|HOLD`, 홀드 중 `RIGHT` 거부, 해제 직후 반환 중 `RIGHT` **거부(잠금)**, 복귀 완료 뒤 수락. **실제 LeftArrow 홀드 + UI 출처 합산**: 합산 수락(`sources=true/true`), 실제 키를 놓아도 UI 출처가 남아 `MOVE\|HOLD x=−1.5` 유지(+0.5초 뒤에도), UI 해제 뒤에만 RETURNING→IDLE. 기본 공격 타수 10(위) | PASS (키 출처 실제, UI 출처 논리 호출) |
| 회차 B — DataSet 로드·검증·실패 동작 | A(프로브 근거: 검증 함수 직접 호출) | 몬스터 수치 표: default만·빈 칸 default 대체 → 수락; default 행 없음·default 빈 칸·MaxHp 0/1.5/abc·AttackInterval 0·중복 id·빈 id → 거부(원인별 경고). 플레이어 표: 100/12/12 수락; MoveSpeed 0·ReturnSpeed −1·MaxHp 1e999·default 빈 칸 → 거부. (CSV 파일 실제 변경은 이번 범위가 아니라 하지 않음) | PASS |
| 회차 B — 플레이어 MaxHp 100·시작 Hp 100, 몬스터 피해 | A | `PlayerStat applied MaxHp=100 Hp=100`, 서버 PlayerComponent MaxHp 100. 무대응 자연 공격 12씩(100→88→…→52, 4회). 일반 가드(GUARD·NORMAL, 서버 GUARD 논리 상태): `defense kind=GUARD rate=0.4`, Hp 100→**96(−4)**; 같은 패턴 무방어: kind HIT, 100→88(−12). HP 바 육안은 NOT_RUN | PASS(값) |
| 몬스터→플레이어 칸 규칙·콜라이더·EvaluateDefense | A + 실제 키 | 위 JUST·PARRY·끝 칸 HIT·GUARD·무대응 결과가 회차 B 값과 같음(MonsterAttackComponent 무변경) | PASS |

#### coder 관찰 1건 확인 — 그로기 중 피격 때 클라이언트 StateComponent HIT / 서버 STUN
- 이번 Play 재현: 그로기 중 플레이어 10타(논리·factor 1 및 2.2) 동안 서버 상태 `STUN`·SpriteRUID hit(90fee9) 유지, 클라이언트는 첫 타격 직후 `STUN→HIT`(SpriteRUID 90fee9 유지)로 보이다가 그로기 종료 때 `IDLE`·stand로 정리됨. 서버는 `GroggyRemaining`이 줄어 조기 해제 없음.
- 이전부터 같은 구조였는지: **같았다고 판단**한다. 이 WorkRecord의 이전 QA·개발 기록에 같은 현상이 있다 — QA4(2026-11-02) F04와 "클라이언트 HIT 신호" 항목("복귀 중·그로기 중 피격에서 서버 상태는 ATTACK/STUN을 유지하지만 클라이언트 로컬 상태가 HIT가 되고 clip=hit가 발생한다"), coder V11-F08·F09 절 관측 3("그로기 중 플레이어 ↑ 공격에서 서버 상태는 STUN을 유지하지만 클라이언트 로컬 상태가 STUN→HIT로 바뀌고 … 서버 그로기 종료까지 HIT로 남았다"), 리뷰 기록("이번 변경 이전부터 있는 클라이언트 표시 구조"). 회차 B(1b4f4ee) 기준 동작을 따로 다시 측정하지는 않았다. 다만 서버 상태 판정(그로기 중 HIT 미진입)은 Monster_Stun·MonsterHealthComponent에 있고 이번 회차가 그 경로를 바꾸지 않았으며(변경 파일 목록), 결과가 앞 기록과 같다. 달라진 점은 이전에는 `stun` 키 클립 이벤트였고 이번에는 코드가 hit 클립을 직접 지정한다는 것뿐이다. **관찰로 남김, 결함 아님.**

#### 기타 관찰 (결함 아님)
1. `DoSpawn`으로 다시 스폰한 몬스터는 서버 SpriteRendererComponent 프레임 범위가 `0-0`으로 보이고(클라이언트 `0-2147483647`), 부팅 첫 스폰은 서버도 `0-2147483647`이었다. stand·jump·hit는 모두 1프레임 클립이라 화면 영향은 없고 die는 명시 설정으로 정상 재생·고정했다. 6프레임 move 클립은 이번 범위에서 쓰지 않아 영향은 확인하지 못함.
2. 몬스터 HIT(피격 반응) 중 서버 SpriteRUID 속성은 stand 그대로이고 상태 이름만 HIT다(엔진 클립 이벤트 구조, 앞 회차와 같음).
3. 첫 Play의 부팅 직후 자연 공격 3회가 내 프로브 실행 전에 플레이어 Hp를 깎았다(프로브가 Hp를 100으로 되돌리고 몬스터 AttackInterval을 9999로 올림). 시험 방식 영향.

#### 시험 오류 (제품 오류 아님)
- 첫 `notPaused` 프로브는 소유자 지정 없이 `SetServerPaused(true)`를 불러 같은 틱에 CombatPauseComponent가 소유자 없는 정지를 `AbortCombat`으로 풀어(`[VRF] CombatPause abort notify=false`) 결과가 `sameCast`였다. 제품 규칙 오류가 아니다. 소유자를 지정하고 0.15초 정지를 유지한 재시험에서 `notPaused`가 나왔다. 앞 coder 인계 주의와 같은 원인.
- `maker_logs(kind=build)`를 시작과 끝에 그대로 읽어 큰 출력이 들어왔다(결과 영향 없음). 런타임 로그는 첫 몇 번만 직접 읽고 이후는 저장 파일을 필터했다.

#### NOT_RUN (PASS로 세지 않음)
1. 머쉬맘 실제 화면(크기, 피벗, BattlePos1~3 겹침, HP 게이지·그로기 별·피해 숫자 위치, die1 마지막 모습) — 스크린샷을 찍지 않았다(사용자 V11).
2. move·hit1 클립의 실제 재생 시간(die1 6프레임 1.100초만 측정됨), HP 바 숫자 육안.
3. 사람 손 기본 0.20초 타이밍(실제 키 사례는 판정 창 30초 시험값), 실기기·모바일·터치, 다중 접속, PC·실기기 지연 때문에 속도 12에서 Pos2 저스트·패링이 빠지는지.
4. 실제 UIPopup 열기·마우스 클릭(V07은 소유자 지정 서버 정지 경로, 클라이언트 시간 배율 0 경로는 실행하지 않음).
5. 규칙 6 "모션 컴포넌트가 없는 몬스터는 통과" 분기(코드 읽기만), 규칙 4를 실제 흐름에서 로그로 낸 것(사망 몬스터는 규칙 1에서 먼저 걸림, 직접 호출만).
6. F06 `parry.right` 대칭 착지 강제 측정(자연 공격 선택·판정만 확인), 4패턴 출현 빈도 통계, 실제 다른 맵 전환.

#### 사용자 V11 직접 확인 항목 (Plan §21, AI 결과로 대신하지 않음)
- 머쉬맘 모습: 대기·점프 공격·그로기(hit1)·피격·사망(die1 끝 모습) 연결이 자연스러운지, 크기와 BattlePos1~3 겹침, HP 게이지·그로기 별·피해 숫자 위치.
- 점프 중 안 맞음: 예고 중·복귀 중 공격이 막히는 체감, 반격 창이 패링 약 1.5초·저스트 약 1.0초로 줄어든 난이도(측정값: 패링 약 1.48~1.5초, 저스트 약 0.99~1.0초), 복귀 중 공격 때 보너스가 사라지는 점.
- 이동 속도 12·복귀 12와 플레이어 HP 100의 체감(무대응 12 피해로 9번 맞으면 사망), PC·실기기에서 Pos2 저스트·패링이 지연 때문에 빠지지 않는지.
- 주황버섯 모델 키 이름(orangemushroom)이 괜찮은지(이번에는 화면에 나오지 않음).
- 기존 V11 미확인(모바일·터치·음향·CF-F07)은 그대로 남는다.

#### reviewer가 알아야 할 근거의 한계
- 플레이어 공격 시작은 서버 `ChangeState("ATTACK")` 논리 경로가 대부분이고 실제 키 입력은 UpArrow 1건·PARRY(DownArrow 홀드) 1건·JUST(LeftArrow 탭) 2건·끝 칸(LeftArrow 홀드) 1건·V10 홀드 몇 건이다. 판정 창을 30초로 넓힌 시험값 근거가 F13 계열 전부다.
- 규칙 실패 이름 중 일부는 합성 시전 스냅샷 직접 호출(프로브 근거)이다.
- 모델 두 파일의 b4adbdd 재저장 의미 차이 0은 메인의 JSON 비교를 따랐고 나는 Play에서 값만 확인했다(모델 파일 셸 읽기 금지).
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시작·끝 55/55 동일 Bundle(`222e7a04…476d`), 제품 파일 무수정, commit·push 하지 않음. Maker 사용 종료.

## 2026-11-06 coder 회차 C2 구현·기본 검증 인계 (CombatCore-MM-12)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §23 CombatCore-MM-12뿐이다. 맵·Body·스크립트·규칙·수치·MonsterData·MonsterStatData·MonsterAttackPatternData(주황버섯 행 추가 없음, 6단계)는 바꾸지 않았다. `OrangeMushroomAttack.mlua`의 이름·폴더·한국어 주석(52행)은 범위 밖이라 그대로다.
- 기준 커밋 105e585(= 회차 C 종료 b93e2ac 이후 제품 파일 동일). 시작 Maker: maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186(앞 회차 기록과 같음). TileMapMode 0(Plan §23 기록, 맵을 바꾸지 않아 다시 읽지 않았다). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 저장 JSON 파일을 `[VRF`·`[VRF C2]` 표지와 시각으로 걸러 읽었다.
- 파일 이름 변경은 **사용자가 Maker 작업 공간에서 직접** 했다(Plan §23.2 순서 2). 메인 git 확인: 작업 트리 제품 변경은 옛 경로 삭제 + 새 경로 추가 1쌍뿐.

### 순서 4 확인 — 쓰기 없음
- ModelBuilder.read로 두 판을 비교했다: 기준 커밋 판(`git show`로 임시 파일에 꺼낸 b93e2ac·105e585 두 판)과 작업 트리 `RootDesk/MyDesk/Models/Monsters/OrangeMushroom.model`. 두 판 모두 컴포넌트 14개·Values 45개·자식 0개이고 snapshot 전체(components·properties·values·base_model_id·version) 재귀 비교의 의미 차이는 **name `주황버섯` → `OrangeMushroom` 1곳뿐**이다. 새 파일 model_id `orangemushroom`.
- Maker가 Name까지 바꿨으므로 `renameModel`은 **호출하지 않았고 모델을 다시 쓰지 않았다**(Plan §23.2 순서 4 단서). 새 파일은 Maker가 직접 저장한 그대로다.

### 변경 파일
| 파일 | 변경 | ID |
| --- | --- | --- |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model → OrangeMushroom.model | 파일 이름 변경(사용자 Maker 작업) + Name `OrangeMushroom`(Maker가 함께 변경). 키 `orangemushroom` 유지. 쓰기는 coder가 하지 않음 | MM-12 |
| .maplestory-skill-maker-ledger.md | 23행 "실효 대상별 사전 표"의 모델 경로를 새 경로로만 갱신(제품 파일 아님, 1줄) | MM-12 |
- 원장 갱신 범위: 스킬(`execution-core.md`)의 원장 규칙은 "단계마다 갱신"만 말하고 낡은 내용 정리 범위를 정하지 않는다. Plan §23.2 순서 5의 "규칙에 없으면 경로만" 단서에 따라 경로만 고쳤다. 같은 행 괄호 `(castleenemy)`와 원장의 MHP-01~04.castleenemy·"현재 MonsterData는 castleenemy 1행" 표현은 회차 C 이전 내용이라 **낡았다. 바꾸지 않았고 메인에 보고한다**(주황버섯 키는 orangemushroom, MonsterData는 mushmom 1행).
- 이 외 Maker 재저장 흔적: 없음(refresh 전후 git status·55경로 manifest 동일, `.directory` 변경도 git status에 없음).

### 버전·바이트 지문
- 같은 계산법·같은 확장자 집합 manifest(경로 바이트순 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래). 계산 도구는 이번에 새로 쓴 스크립트이며 b4adbdd 커밋 트리에서 **222e7a041b619cc26bb3bd51492a352cd95a41c42259fc8f6f06e9c5e03b476d(55경로)** 를 재현해 방법이 앞 회차와 같음을 확인했다. 기준 105e585도 같은 값이다.
- **작업 트리 Bundle SHA-256(55경로): 8ef9c6f1c60d73b7b74f5febd09932abfe6ba5866bfc577cb226c82d5ed2e080.** refresh 전·Play 뒤 Stop 뒤 세 번 계산해 모두 같다(Play가 제품 파일을 바꾸지 않음).
- 기준 105e585 대비 manifest 차이는 **1경로**: 옛 `RootDesk/MyDesk/Models/Monsters/주황버섯.model` 87686d37a01e7c6464b650257e19fd34c455bebeca78f88b532ebb881eb0c1d4 → 새 `RootDesk/MyDesk/Models/Monsters/OrangeMushroom.model` **28048d8f0be5822f8f9838fd4ff966bcea35ab07c829a472c1a7dfd7eced9ffb**. 나머지 54경로 해시는 같다.
- **회차 C에서 쓴 Bundle 경로 목록에서 주황버섯 모델 경로가 `…/Models/Monsters/주황버섯.model`에서 `…/Models/Monsters/OrangeMushroom.model`로 바뀐다**(경로 수 55 그대로, 정렬 위치만 달라짐). 이후 tester·reviewer의 55경로 재계산은 새 경로를 쓴다. 로컬 커밋 해시는 메인이 [code] 커밋을 만든 뒤 적는다.

### 실제 기본 검증 (Maker MCP, refresh 1회 + Play 1회, 시험 설정은 Play 내부에서만)
| Plan §23.3 | 결과 |
| --- | --- |
| 1 Glob `RootDesk/MyDesk/**/*.model` | `AttackAreaMark.model`·`Mushmom.model`·`OrangeMushroom.model` 3개, `주황버섯.model`은 어디에도 없음, Mushmom 그대로 PASS |
| 2 ModelBuilder.read | 위 "순서 4 확인" 그대로. EntryKey/Id 상당 model_id `orangemushroom`, Name `OrangeMushroom`, 기준 판과 의미 차이 Name 1곳 PASS. (파일 형식 차이는 기록 대상으로 보되 snapshot 비교에서 나타나지 않음) |
| 3 refresh 뒤 build 로그 | refresh status ok, build 로그 83건 전부 Info(LIA 1114/1115 동적 참조 노이즈, 앞 회차와 같은 건수), 오류 0·경고 0 PASS. 옛 이름 항목 징후(경고·파일 이동·내용 되돌림) 없음: refresh 전후 git status·manifest 동일 |
| 4 Play 회귀 | 부팅 `[VRF] CombatCore catalog ready rules=1 patterns=4 monsterStats=2`, `MonsterStatData id=mushmom MaxHp=100 AttackDamage=12 AttackInterval=3.0 source=DataSet`, `MonsterStat applied key=mushmom MaxHp=100.0 Hp=100.0 … source=DataSet`, `MonsterManager spawned parent=map01 x=3.0`, 맵 자식에 엔티티 이름 `머쉬맘` 1개, Scale (1,1,1), ActionSheet 키 `die,hit,jump,move,stand`(5개). 자연 예고 패턴이 부팅 뒤 `parry.right`·`parry.left`·`parry.any`×2·`parry.right`(예고 id 1~5)로 이어지고 `defense kind=HIT rate=1`이 기록됐다(시험 중 플레이어는 대응하지 않음). 피격 규칙: 몬스터가 ATTACK 상태일 때 서버 요청 직후 실제 입력 경로 `PlayerStateControl:RequestChangeState("ATTACK")`(클라이언트, ok=true)으로 기본 공격 → `PlayerHitRule list built rules=6 builds=1`, hit 1 `fail rule=targetHittableSegment`, hit 2~10 `pass`(checks 2→18, 타격당 2회), 몬스터 HP 100→**91**(통과 9타×1). 회차 C 기록의 "걸친 공격"(앞 타 fail·이후 pass) 사례와 같은 동작. 이후 몬스터 상태 IDLE |
| 5 직접 스폰 | `_SpawnService:SpawnByModelId("orangemushroom", …)` 성공: Scale (1.000,1.000,1.000), ActionSheet 키 `die,hit,jump,move,stand`(n=5), `ActionSheet["stun"]` nil, SpriteRUID 96e955c1bf27415e84f96deea200a8f1(stand), HitComponent BoxSize (0.630,0.580)·ColliderOffset (0.045,0.290)(앞 회차 기록과 같음). MonsterManager.CurrentMonster가 아님(`isManagerMonster=false`)과 부팅 스폰이 머쉬맘 1개뿐인 것으로 MonsterManager 경로에서는 주황버섯이 나오지 않음을 확인(MonsterData 1행 mushmom, 앞 회차 설계 그대로). 확인 뒤 `Destroy`, 이름 `C2Probe*` 잔존 0(`final leftovers=0`). 대조: `SpawnByModelId("castleenemy")`·`SpawnByModelId("주황버섯")`은 `[LEA-3028] MissingModel`로 nil(옛 이름 항목 없음). 대소문자 다른 `"OrangeMushroom"`은 성공(모델 id 비교가 대소문자 무시, 시험 객체 즉시 Destroy) |
| 6 Grep | 제품 파일(RootDesk·Global·map·ui) 전체에서 `주황버섯` 일치 1건뿐: `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua:52` 한국어 주석(범위 밖, 그대로) |
| 7 git | 제품 변경은 모델 1개(옛 경로 삭제 + 새 경로 추가)뿐. 원장 1줄 변경. 다른 재저장 파일 없음 |
- 로그 요약(이번 Play, 14:53 시작분): Error 3건 모두 내 프로브 때문이다. (a) 첫 스폰 프로브의 `#e.Components` 길이 조회 `[LEA-2002]`(제품 오류 아님, 그 때문에 첫 프로브가 Destroy 전에 멈춰 두 번째 프로브에서 같은 시험 개체를 읽고 지움), (b)(c) 의도한 `MissingModel`(castleenemy, 주황버섯). 정상 구간 LEA/LWA 없음. 앞 회차 13:53 Play의 로그는 사용자 로그라 지우지 않았다.
- 프로브 한계: 첫 스폰 프로브 실패로 같은 시험 개체를 두 번째 프로브에서 읽었다. 구성 값은 동일하다. 피격 규칙 시험은 서버 상태를 맞추지 않고 몬스터가 ATTACK일 때 한 번만 실행해 접근 점프 구간·IDLE 전체 통과·패링/저스트 사례는 다시 하지 않았다(회차 C 근거 그대로, tester 범위).

### 실패/미확인/미실시 (PASS로 세지 않음)
- 실패 없음.
- 미실시: 사용자 V11(Plan §23.4) — Maker 작업 공간 창에서 주황버섯이 `OrangeMushroom` 하나로만 보이는지(AI는 작업 공간 창을 볼 수 없음), 플레이 화면(머쉬맘)이 회차 C와 같은지. 규칙 6 접근·복귀 구간, 패링/저스트 복귀, 사망 die 정지 같은 회차 C 전수 회귀는 실행하지 않았다(범위 밖, 모델 이름 변경만 했고 이번 회차는 스크립트·Body 무변경). 사람 손 타이밍, 실기기·모바일, 다중 접속.
- 원장의 낡은 `castleenemy` 내용은 정리하지 않고 보고만 한다(위).

### 사용 종료·다음 담당
- 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것(Plan §23.3 같은 버전 독립 재확인): Glob 1, ModelBuilder.read 2(기준 판은 `git show 105e585:`로 임시 파일에 꺼내 비교), refresh 뒤 build 로그 3, 부팅 머쉬맘 스폰·피격 규칙 4(회차 C QA10의 규칙 6 접근/복귀/걸친 공격 회귀를 이번 버전으로 포함할지는 메인 판단), 직접 스폰 5(시험 개체 반드시 Destroy), Grep 6, git 7. 55경로 Bundle은 새 경로 기준으로 재계산해 위 `8ef9c6f1…e080`과 대조. maker_clear_logs는 호출하지 말 것.

## 2026-11-08 coder 회차 D 구현·기본 검증 인계 (CombatCore-MM-07~11) — 22.10 중단 (구현 전)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §22 CombatCore-MM-07~11이다. **제품 파일은 하나도 바꾸지 않았다**(수정 전 중단).
- 기준: HEAD c595e0f(= 제품 파일은 회차 종료 커밋 7a796aa와 같음, 직전 커밋은 문서만 변경). 같은 계산법·같은 확장자 집합 manifest로 작업 트리 55경로 Bundle SHA-256 **8ef9c6f1c60d73b7b74f5febd09932abfe6ba5866bfc577cb226c82d5ed2e080**(회차 C2 값과 같음). 시작 전·중단 뒤 두 번 계산해 모두 같다(Play가 제품 파일을 바꾸지 않음).
- 시작 Maker: maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. TileMapMode 0. maker_clear_logs는 호출하지 않았다.

### Plan 22.9 순서 2 — 클립 길이·피벗 상승량 측정 (Maker Play 1회, server_main 프로브, 읽기만)
| 클립 | 프레임 | 프레임 Delay(초) | Delay 합 | 클립 PlayRate | 피벗 y(px, 프레임 0→끝) |
| --- | --- | --- | --- | --- | --- |
| attack1 90c5456e… | 5 | 0.80 / 0.20 / 0.05 / 0.05 / 0.75 | **1.85** | 1.0 | 0 / -88 / -70 / -8 / 0 |
| skill1 b9345875… | 5 | 0.80 / 0.20 / 0.05 / 0.05 / 0.75 | **1.85** | 1.0 | 0 / -88 / -70 / -8 / 0 (attack1과 같은 값) |
| jump 5ecbcc40…(참고) | 1 | 0.12 | 0.12 | 1.0 | 0 |
| stand 86015373…(참고) | 1 | 0.12 | 0.12 | 1.0 | 0 |
| 이펙트 05113e9d… | 15 | 0.1×6, 0.2, 0.3, 0.1×5, 0.2, 0.05 | **1.85** | 1.0 | 프레임별 -21~+1(px), 크기 w 32~254·h 1~79(px), ppu 100 |
- 렌더러 PlayRate 기본 1.0, 접근 점프 JumpDuration 0.5. 클립 길이(Delay 합 ÷ PlayRate)는 attack1·skill1 모두 **1.85초**다.
- 피벗 상승량: 프레임 1에서 최대 0.88 단위(Plan 22.10의 "최대 약 0.88"과 일치). 판단은 하지 않고 수치만 적는다(JumpHeight 0.8과 합치면 최대 1.68이 될 수 있음, 사용자 V11).
- 이펙트: 충격파 프레임(f8~f13)은 모션 시작 뒤 Delay 누적 **1.1초**에 시작해 1.8초에 끝난다. 판정(접근 점프 끝, 모션 시작 뒤 TelegraphLeadSec 0.5초)과 충격파 시작은 **약 0.6초** 어긋난다(충격파가 판정보다 늦음). 충격파 폭 최대 254px = 2.54 단위, 3칸 범위 약 4.5 단위. 서버 PlayEffect의 화면 표시 확인은 구현 전이라 못 했다.

### 22.15 수정 전 기준선 (구현 전, 같은 Play)
- 부팅 첫 스폰 개체(서버): StartFrameIndex-EndFrameIndex = **0-2147483647**, SpriteRUID = stand(86015373…).
- `MonsterManager:DoSpawn()` 재스폰 개체(서버): 직후 **0-0**, 1초 뒤에도 **0-0** — QA10 관찰이 재현됐다.
- 같은 재스폰 개체의 클라이언트: 0-2147483647(둘 다 이상 없음).
- 다음 단계(범위 지정 + 같은 RUID 재지정 재시작 시험)는 구현 뒤 측정 항목이라 하지 못했다.

### 중단 사유 (Plan 22.10 첫 항목)
- 클립 길이 **1.85초 ≥ 1.0초**: "1.0초 이상(절반 넘게 잘림)" 조건에 해당한다. 접근 점프 0.5초 동안 attack1·skill1은 첫 프레임(Delay 0.8초, 정지 자세, 피벗 0)에서 끝나고 나머지 4프레임(기 모으기·도약·착지)은 보이지 않는다. 대안 구현은 하지 않고 멈췄다.
- 이 중단 뒤 한 일: Stop → map01 편집 모드 확인. 코드·모델·CSV·.userdataset 변경 0, Refresh 0, commit·push 없음.
- 메인에 돌려준 선택지는 반환 보고에 적었다.

### 2026-11-08 coder 회차 D 재개 (사용자 D-Q2 "재생 2.2배로 판정에 맞춤") — 구현·기본 검증, 22.10 정렬 기준 일부 초과로 판단 대기

#### 범위·기준
- 기준 HEAD c595e0f(제품 파일은 7a796aa와 같음). 재개 때 55경로 Bundle `8ef9c6f1…e080` 재확인(변경 없음). maker_clear_logs는 호출하지 않았다.
- D-Q1(MonsterSoundData 수동 작성)과 §22.15 처리 원칙(서버 클립 지정 때 프레임 범위 전체로 맞춘 뒤 SpriteRUID) 그대로 구현했다. 2단계 측정은 다시 하지 않았다.

#### 변경 파일
| 파일 | 변경 |
| --- | --- |
| Models/Monsters/Mushmom.model | ActionSheet에 attack1(90c5456e…)·skill1(b9345875…) 추가(ModelBuilder). 다른 값은 snapshot 비교로 변화 0. 빌더가 줄바꿈을 LF·숫자를 `6`처럼 다시 써서 git diff가 파일 전체로 보인다(`--ignore-cr-at-eol` 기준 의미 변경은 ActionSheet 2키) |
| @Assist/DataSet/MonsterAttackPatternData.csv | Weight 4/4/5/3/4, 열 MotionClip·AttackSound·EffectClip·MotionPlayRate, parry.guard 행(2.2/2.2/1/1/2.2) |
| DataSet/MonsterSoundData.userdataset·.csv (새, 수동 작성) + DataSet.directory(Maker 생성) | mushmom 행. Refresh 뒤 인식 확인: 로드 [VRF] `monsterSounds=1`, `MonsterSoundData id=mushmom damaged=c611ae50 hitplayer=7c8e5f1e die=d48ec1cc` |
| Combat/CombatRuleCatalog.mlua | 새 열 검증(MotionClip 소문자 키·die 금지, RUID 32자 소문자 16진수, MotionPlayRate 양의 유한수·빈 값 1), `FormatWeights`·`ParseOptionalRuid`·`ValidateSoundRows`, 사운드 표 로드·거부, `GetMonsterSounds`, `PlayMonsterSound`, 로드 [VRF](행별 Weight·비율%, 행별 clip/rate/sound/effect, 사운드 행) |
| Managers/MonsterManager.mlua | 스폰 전 사운드 행 확인, 스폰 뒤 모든 MotionClip 키가 ActionSheet에 있는지 확인(없으면 파괴·거부·경고 1회) |
| Monster/MonsterAttackMotion.mlua | `SetMotionClip(key, rate)`(범위 0~끝으로 맞춘 뒤 SpriteRUID, 배율 기록, `ApplyClipRate`), `SetVisualClip`은 배율 1로 위임, `ApplyClipRate`(PlayRate = 클립 배율 × ActionRate, 사망 표시 뒤에는 쓰지 않음), `ResetClipRate`, `PlayAttackEffect`, `PlayDieOnce`가 PlayRate 1 명시, `PerformAttackMotion` 시그니처에 클립·배율·착지 x 추가 |
| Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 접근은 패턴 클립·배율, 복귀는 jump·배율 1, 착지 x는 서버가 넘긴 값, `CancelMotion`이 배율 1로 되돌림. 이름·폴더·기존 주석 줄 유지 |
| Monster/MonsterAttackComponent.mlua | 스냅샷에 `area.landingX`(1·2칸 = 영역 중앙 그대로, 앵커 1~3 전부 = Pos2 앵커 x), 공격음(PrepareAttack 성공 직후), 플레이어 피격음(nativeHit이고 HIT·GUARD·UNGUARDABLE) |
| Monster/@StateControl/Monster_Attack.mlua | 패턴 클립·배율·착지 x 전달, 모션 시작과 함께 PlayAttackEffect |
| Monster/MonsterHealthComponent.mlua | 피격음(공격자 PlayerCombatComponent의 `_T.attackId`가 바뀐 첫 HitEvent에서 한 번), 사망음(ApplyDamage에서 사망 확정 때 한 번, 대상은 MonsterManager.CurrentPlayer) |
| Monster/@StateControl/MonsterStateControl.mlua (22.7 조건부) | **고쳤다.** 이유: 슬로우가 시작할 때 렌더러 PlayRate를 `_T.savedPlayRate`에 저장하고 끝날 때 복원하는 방식은 접근 배율 2.2를 저장값에 섞어 종료 뒤 다른 클립(die·stand)에 남기거나 접근 도중 1로 되돌린다. 저장·복원 3곳(ApplySlow·ClearCombatEffects·OnUpdate 만료)을 `_T.slowPlayRateOn` 플래그 + `ApplyMotionClipRate()`(모션 쪽 `ApplyClipRate` 호출)로 바꿨다. 슬로우 시간·배율·ActionRate·액션 시계·공격 대기 규칙·수치는 그대로 |
- 재생 배율 구현 방식: 렌더러 PlayRate는 항상 `그 클립 배율(_T.clipRate) × 현재 ActionRate`로 계산한다. 클립을 지정할 때(`SetMotionClip`), 슬로우 시작·종료 때, 접근 취소 때 같은 함수를 부른다.

#### 버전·바이트 지문
- 작업 트리 Bundle SHA-256: 기존 55경로 manifest 방식에 새 DataSet 2파일을 더한 **57경로 `a7bc3d7395d636863c92ef5e6af853a12003ba4cd34a925eb9c534c36b32539d`**(refresh 직후·Play 뒤 Stop 뒤 같음). 기준 55경로 값은 `8ef9c6f1…e080`.
- 변경 경로 SHA-256: Catalog 4866f69d…0aaf · MonsterManager 73882929…75f3 · Mushmom.model 5704ffa3…11ad · MonsterStateControl 4db78beb…c146 · Monster_Attack b7c6ec30…7169 · MonsterAttackComponent 4ca00fd6…60e6e0 · MonsterAttackMotion f6cb5af8…2cce · MonsterHealth 284f6d45…b3ce · OrangeMushroomAttack af21c7ef…b738 · PatternData.csv d1692795…d655 · (새) MonsterSoundData.csv 89883a3f…347f · (새) .userdataset 22a4e314…2412.

#### 기본 검증 (Maker Play 1회 + 저장 로그, 시험값은 Play 안에서만)
- 빌드: Refresh 뒤 build 로그 90건 전부 Info(LIA 노이즈), 오류 0·경고 0. 새 .mlua 없음(.codeblock 새로 생기지 않음).
- 로드 [VRF]: 패턴 5행 `total=20 parry.left=4(20.0%) parry.right=4(20.0%) parry.any=5(25.0%) special.random=3(15.0%) parry.guard=4(20.0%)`, 행별 `clip/rate/sound/effect`, `MonsterSoundData` 1행. PASS.
- 패턴별 결정적 실행(패턴 목록을 한 행으로 교체): attack1(parry.left·right)·skill1(parry.guard)·jump(parry.any·special.random) 클립 PASS. 착지 x: parry.left 0.750(= 영역 중앙, 회차 C와 같은 식)·parry.right -0.750·parry.guard **0.000 = Pos2**·parry.any 0.000·special.random -1.500. 공격음 [VRF]: 2칸 f135fc39·3칸 5da7bb48·1칸 없음. 이펙트 호출은 parry.guard만(x=0.000 y=0.581 playRate=2.2). PASS.
- 판정(parry.guard, 실제 DownArrow·LeftArrow 홀드): 판정 창 안 가드(홀드가 이른 가드) → GUARD rate 0.4(hitplayer 음 1줄), 패링 창을 30초로 넓힌 시험 → PARRY rate 0·그로기·hitplayer 0줄, LeftArrow(Pos2 시작 회피) + 저스트 창 30초 시험 → JUST·슬로우·hitplayer 0줄, 입력 없음/이동 → HIT rate 1(hitplayer 1줄). 시험 창 값은 모두 원래 0.2로 되돌렸다. PASS(프로브·창 조정 근거).
- 사운드: 플레이어 UpArrow 1회(10타)에 `sfx kind=damaged` 1줄, 사망 때 `kind=die` 1줄, 자연 공격 HIT에서 `kind=hitplayer`. PASS.
- 22.15 재스폰: 부팅 첫 스폰 서버 0-2147483647, `DoSpawn` 재스폰 서버 직후 **0-0**(기준선 재현). 재스폰 개체에서 attack1·skill1 접근 실행: 서버 범위 0-2147483647로 맞춰지고 클라이언트 프레임 이벤트가 f0→f1→f2→f3 진행(f4는 stand 쓰기와 겹쳐 있기도 없기도 함, 착지 시점 f4 시작). 첫 스폰 개체도 같음. 같은 RUID 재지정 때 재시작 여부는 **미실시**(로그 버퍼 가득, 아래).
- 재생 배율·정렬(22.8 자동 9번): 슬로우 없음 attack1·skill1: 서버 PlayRate 2.2, 클라이언트 f0→f4 시작 **0.497~0.500초**, 판정 0.517~0.534초(샘플 0.017초 간격) → 차이 0.02~0.04초 PASS. 이펙트 충격파(f8)는 PlayRate 2.2로 계산상 1.1÷2.2 = 0.5초(클라이언트 측정 불가). 1칸 parry.any는 PlayRate 1. 착지 뒤 stand PlayRate 1. 슬로우 계속(접근 전 ApplySlow 3초×0.5): 접근 PlayRate 1.1, f3 0.973·계산 f4 1.0초, 판정 1.022초 → 차이 0.02초 PASS. 슬로우 종료 뒤 stand PlayRate 1 PASS. die는 슬로우 중 치명타에서도 PlayRate 1이고 마지막 프레임(5)에 정지하며 슬로우 만료 뒤에도 유지(F12 회귀 PASS).
- **22.10 정렬 기준 초과(슬로우 변화가 접근 도중에 생기는 경우)**: 렌더러 PlayRate를 클립 도중 바꾸면 클라이언트 애니메이션이 프레임 0부터 다시 시작한다(PlayRate 변화 때 `idx=0` 이벤트가 다시 옴, 슬로우 시험 S1·S2). S1(슬로우 0.3초 뒤 종료): PlayRate 1.1→2.2, 재시작 0.291초, 판정 0.660초, 재시작 기준 f4 시작은 약 0.77초로 판정보다 약 0.11초 늦음. S2(접근 0.2초에 슬로우 시작, 1.5초): 재시작 0.221초, 판정 0.816초, f1에 도달하지 못한 채 착지(f4 시작 계산 약 1.22초, 판정보다 약 0.4초 늦음). 두 경우 모두 슬로우 종료 뒤 렌더러 PlayRate는 "클립 배율 × ActionRate"로 정확히 돌아왔다(접근 중 2.2, 복귀·stand 0.5→1). 이펙트는 재생 시작 때 PlayRate 고정이라 접근 중 슬로우 변화는 따라가지 않는다(22.6 기존 부채).
  - 자연 흐름 참고: 슬로우 시작은 판정 순간(저스트 성공)이므로 접근 도중에 시작하지 않는다. 지금 SlowDurationSec 2.0·AttackInterval 3.0(액션 시계)에서는 슬로우가 다음 접근 전에 끝난다. 접근 중에 시작·종료가 생기는 것은 값을 크게 바꾸거나 시험 프로브로 만들 때만이다.
- 실패 동작(프로브): 패턴 표 RUID 형식 오류·대문자 RUID·짧은 RUID → 카탈로그 거부 + 경고 1회, MotionClip 빈 값·`die`·대문자 → 거부 + 경고 1회, MotionPlayRate 0·-1·abc·1e999 → 거부 + 경고 1회, Weight 0·-2·abc → 거부 + 경고, Weight 1/1/1/1/1 → 비율 20%씩, 빈 MotionPlayRate는 1, 사운드 표 형식 오류·열 누락 → 표 거부. 스폰: 모델 ActionSheet에 없는 MotionClip → 스폰 거부 + 엔티티 파괴 + 경고 1회, 사운드 행 없음·사운드 표 무효 → 스폰 거부 + 경고 1회(같은 원인 반복은 경고 없음), 모두 현재 상대 유지. PASS.
- 서버 PlayEffect 화면 표시: 같은 이펙트를 서버에서 반복 재생하고 스크린샷으로 확인했다(스케일 3, 클라이언트에서 옅은 노란색 별 모양이 보임). 서버 호출이 클라이언트에 보인다 → @Sync 대체 경로 불필요. 이펙트가 옅고 얇다.

#### 미실시·미확인 (PASS로 세지 않음)
- **로그 버퍼 가득**: Maker 로그가 764건(사용자 16:51 세션 94건 포함, 357k자)에서 더 늘지 않아 17:29:10 이후 로그가 기록되지 않았다. 그 뒤 계획한 아래는 못 했다: 통계 프로브(SelectPattern 2만 회 비율 ±1%p)와 누적 경계 단위 프로브(스크립트는 실행됐으나 결과 로그 없음, 코드 `SelectPattern`은 이번에 바꾸지 않음), 같은 RUID 재지정 시 재시작 여부, 이펙트 크기·높이 두 배 판단(수치만: 피벗 상승 최대 0.88, 이펙트 충격파 폭 최대 2.54).
- 사람 손 타이밍, 모바일, 사용자 V11(22.8) 전부.

#### 사용 종료
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. commit·push 없음.


### 2026-11-09 coder 회차 D 재작업 (Plan §22.16, 사용자 D-Q3~D-Q7) — 구현·기본 검증

#### 시작 기준·로그 정리
- 기준: coder 로컬 커밋 e5f7249(57경로 Bundle `a7bc3d7395d636863c92ef5e6af853a12003ba4cd34a925eb9c534c36b32539d`). 시작 HEAD f82c549(e5f7249 뒤 [ops] 문서 커밋). 작업 트리에는 Maker가 자동 저장한 `RootDesk/MyDesk/DataSet.directory`(StudioVersion "" → "0.1.0.0") 변경이 있었고 내 변경이 아니라 그대로 두었다(이번에도 git status에 남아 있음, Bundle 대상 밖). 시작 시 같은 계산법으로 Bundle을 다시 계산해 위 값과 일치함을 확인했다.
- 시작 Maker: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit.
- D-Q7 로그 정리: 세션 시작 때 `maker_logs(normal)`은 **0건**이었다(이전 세션 로그는 Maker 쪽에서 이미 비어 있었음). 그래서 처음에는 clear를 부르지 않았다. 검증 중 내 시험 로그(프레임 이벤트 포함)로 버퍼가 약 333k자·741건(17:30:43~17:37:11, 전부 이번 세션 시험 로그)에서 더 늘지 않아(새 로그 미기록) 허용된 `maker_clear_logs`를 **1회** 호출했다(clearedCount 741). 그 밖에는 지우지 않았다.

#### 변경 파일 (22.7 + 22.16.6 안, 새 파일 없음)
| 파일 | 변경 |
| --- | --- |
| @Assist/DataSet/MonsterAttackPatternData.csv | 열 `JumpStartFrame` 추가(1/1/빈/빈/1). parry.left·parry.right·parry.guard 행 TelegraphLeadSec 0.5→1.1, MotionPlayRate 2.2→1. 1칸 행은 0.5·1 그대로 |
| Combat/CombatRuleCatalog.mlua | JumpStartFrame 검증(빈 값=0, 0 이상 정수가 아니면 카탈로그 전체 거부 + 경고 1회), ReadRows 필수 열에 추가, 로드 [VRF]에 행별 jumpFrame·lead |
| Managers/MonsterManager.mlua | 스폰 확인: JumpStartFrame>0 행은 프레임이 클립 안인지, 제자리 시간 W < TelegraphLeadSec인지(아니면 파괴·스폰 거부·경고 1회) |
| Monster/MonsterAttackMotion.mlua | 구간 `windup` 이름·주석, 클립 타임라인 캐시 `GetClipTimeline`·`GetWindupSeconds`, 서버 프레임 구동 `StartDrivenClip`·`TickClip`·`StopDrive`(D-Q6 후보 1), 이펙트 2단계 분할 `PlayWindupEffect`·`PlayDustEffect`·`PlayEffectRange`(옵션 StartFrameIndex·EndFrameIndex), [VRF]용 `ClockText`, `PerformAttackMotion` 시그니처에 leadSec·jumpStartFrame 추가. 이펙트 프레임 경계는 속성 `EffectWindupLastFrame`=6·`EffectDustFirstFrame`=8(이 이펙트 자원의 구조, modelId 분기 아님) |
| Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 2·3칸: 공격 시작~W 제자리(windup) → W에 실제 점프(approach, 시간 J = TelegraphLeadSec − W, 높이 속성 `LeapJumpHeight` 기본 0) → 착지 = 판정. 속성 `WindupHittable` 기본 true. 1칸·복귀는 JumpDuration·JumpHeight 그대로(`JumpToLocalX`). `OnUpdate`에서 TickClip. 이름·폴더 그대로 |
| Monster/@StateControl/Monster_Attack.mlua | 패턴의 TelegraphLeadSec·JumpStartFrame 전달, 공격 시작 때 이펙트 1단계(눈빛, 머쉬맘 현재 위치), 착지(판정) 때 2단계(먼지, 착지 x). 판정 전 취소되면 OnAttackComplete에 오지 못해 2단계 없음 |
- **MonsterStateControl.mlua는 이번에 고치지 않았다**(e5f7249의 `ApplyMotionClipRate` 알림 그대로 사용). 22.7 밖 파일 수정 없음.
- 구현 방식 근거(D-Q6): 후보 1(서버가 액션 시계로 프레임 경계마다 `Start=End=k`)로 완료 기준을 지켰다. 후보 2는 시험하지 않았다. 측정으로 확인한 엔진 동작: (a) 클립(SpriteRUID)을 바꾸면 프레임 범위가 전체로 돌아가므로 RUID를 먼저 쓰고 그 뒤에 `Start=End=0`을 쓴다(처음엔 반대 순서라 클라이언트가 `0-max`로 자연 재생했고, 순서를 바꾸자 클라이언트가 `0-0`을 본다). (b) 같은 RUID에서 `Start=End=k`를 쓰면 클라이언트가 즉시 그 프레임으로 가고 프레임 이벤트가 나온다(`idx=3` +0.014초). (c) 같은 RUID를 다시 지정해도 재시작 이벤트가 없다. (d) 한 프레임 고정 중 PlayRate를 바꾸면 같은 프레임 이벤트만 한 번 다시 온다(되돌림 아님).

#### 버전·바이트 지문
- 작업 트리 57경로 Bundle SHA-256: **`8dccccf58c6138d16e5b84277fa275c6a982c8d397e487d85e1f55e33e6ab738`**(Refresh 뒤·Play 뒤 Stop 뒤 같음). 바뀐 경로 6개: PatternData.csv f1ebd85e…58e4 · CombatRuleCatalog a326f630…cbef · MonsterManager 41aac3d2…36d0 · Monster_Attack 3cbdfcc3…b4f1 · MonsterAttackMotion 6cde25aa…e77a · OrangeMushroomAttack b4922c96…589e. 나머지 51경로는 e5f7249와 같다.

#### 기본 검증 (Maker Play 2회, 시험 설정은 Play 안에서만)
- 빌드: Refresh 뒤 build 로그 93건 전부 Info(LIA 노이즈), 오류 0.
- 로드 [VRF]: 패턴 5행 비율 20/20/25/15/20%, 행별 `rate=1 jumpFrame=1 lead=1.1`(left·right·guard)·`jumpFrame=0 lead=0.5`(any·special), 사운드 1행.
- **10 제자리·도약 분리**(서버 샘플 0.01초, 클라이언트 프레임 이벤트·프로퍼티 폴링):
  - 슬로우 없음 parry.left: 제자리 x 변화 3.000..3.000, JumpActive false·구간 windup, W 시점에 구간 approach·JumpActive true(서버 `leap start` 전투 시계 W = 0.807초 후), 실제 점프 0.3초, 착지 x 0.750(영역 중앙, 회차 C와 같음), 착지 y 0.581(변화 0). 클라이언트 f1 이벤트 f0 대비 +0.803~0.810초(W와 ±0.01), f2 +1.01, f3 +1.06, **f4는 서버가 같은 틱에 stand로 바꿔 클라이언트에 그려지지 않음**(착지 때 stand 계약). f4 시작 시각은 서버 `frame set frame=4` 전투 시계 elapsed 1.102~1.114와 판정 `defense` clock이 0.001초 안으로 같다. parry.guard: 착지 x 0.000(= Pos2), W 0.806~0.814, f4 elapsed 1.102~1.116 = 판정 같은 시계.
  - 접근 전체 슬로우(rate 0.5, parry.guard): W 실제 1.605초(클라이언트 f1 +1.603), 착지 = 판정 = f4 2.210초(resolved 2.228 샘플), 렌더러 PlayRate 0.5, 이펙트 PlayRate 0.5.
- **11 이펙트 분할**(parry.guard): 1단계 호출 시각 = 공격 시작(`clip driven`과 같은 전투 시계), 위치 머쉬맘 현재 x 3.000·지면 y 0.581, 프레임 0-6, PlayRate = 1 × ActionRate. 2단계 호출 시각 = 판정(`defense` clock과 같은 값), 위치 x 0.000(Pos2)·y 0.581, 프레임 8-끝. 판정 전 취소(공격 시작 0.6초 뒤 `CancelPendingAttack` + IDLE): 2단계 호출 없음, 렌더러 범위 0-2147483647·PlayRate 1로 복구. 화면 확인: 같은 이펙트를 `StartFrameIndex=0`·`EndFrameIndex=6` 옵션으로 반복 재생해 스크린샷으로 옅은 별 모양을 확인(구간 옵션이 동작함). 먼지 구간(8~끝)과 스케일 1 눈빛은 얇고 옅어 스크린샷으로 구분하지 못했다. 방향(FlipX·SyncFlip) 확인은 못 했다(스케일 1 이펙트가 방향 판별이 안 되게 옅음).
- **12 제자리 피격**: windup 중 플레이어 UpArrow 10타가 규칙을 모두 통과해(`PlayerHitRule pass hit=1..10`) 몬스터 HP 100→90, 피격음 1줄. 샘플러의 구간별 피격 선언 값: windup true, approach false, return false, none true. approach·return 실제 타격 차단은 규칙 코드를 바꾸지 않았고(회차 C) 선언 값만 확인했다(실입력 시험은 미실시).
- **13 높이**: 2·3칸 접근 y 0.581..0.581(변화 0). 1칸 parry.any·special.random 접근 y 0.581..1.380(+0.8), 시작과 동시에 점프, 판정 0.52~0.53초, 착지 x 0.000·1.500(회차 C와 같음).
- **15 검증 실패**: JumpStartFrame -1·1.5·abc → 카탈로그 거부 + 경고 1회("invalid jump start frame", 경고 키 하나), 빈 값·0 허용(0), 4 허용(스폰 단계가 거름). 스폰: JumpStartFrame 5(≥ 프레임 수 5) → 거부 + 경고 1회 + 엔티티 파괴, TelegraphLeadSec 0.7(W 0.8 ≥ 0.7) → 거부 + 경고 1회, 두 경우 모두 현재 상대 유지, 정상 값은 다시 스폰 성공.
- **16 접근 클립 이어 재생(D-Q6)**: 클라이언트 프레임 번호가 되돌아간 적이 없다(모든 경우 0→1→2→3, 같은 프레임 이벤트 반복은 PlayRate 변경 때뿐).
  - S1(parry.left, windup 0.4초에 슬로우 시작·2.0초, 착지 뒤 종료): f1 클라이언트 +1.193초, 서버 W(전투 시계) +1.199초 → 0.006초. 착지·f4 +1.806초 = 판정.
  - S2(슬로우 0.6초 뒤 windup 도중 종료): f1 +1.100, 서버 W +1.103 → 0.003초. 착지 +1.413 = 판정.
  - S3(parry.guard, 도약 0.9~1.1초 사이에 슬로우 시작·종료): f1 +0.808, W +0.813 → 0.005초. f2 서버 1.107, 클라이언트 +1.102, f4 1.213 = 판정.
  - S4(ApplySlow 0.95초 = windup 안에서 종료)·S5(ApplySlow 1.9초 = 도약 안에서 종료): f1 W와 ±0.01초, 클라이언트 프레임 단조 증가. S5 f1 클라이언트 +1.621초·서버 W +1.617.
  - 슬로우 종료 뒤 렌더러 PlayRate는 "클립 배율 × ActionRate"(접근 중 1.0·0.5, 판정 뒤 stand·jump는 배율 1 × ActionRate).
- **14 1칸 회귀·F12·사운드**: 1칸 PlayRate 1·클립 jump·착지 후 stand. 슬로우 중 치명타에서도 die PlayRate 1, 마지막 프레임(5)에 정지(F12 회귀 PASS). 공격음(2칸 f135fc39·3칸 5da7bb48·1칸 없음), 피격음 1줄/공격 1회, 사망음 1줄, HIT·GUARD에서 hitplayer, PARRY에서 hitplayer 0줄. 판정 규칙(parry.guard): 이른 가드 GUARD 0.4, 창을 넓힌 가드 PARRY·그로기(hit 클립 PlayRate 1), 무대응 HIT. 모두 e5f7249와 같은 결과.
- **22.8 4번 통계·경계**: 누적 경계 프로브(제품 `SelectPattern` 직접 호출) PASS: u=0·0.1999999→parry.left, 0.2·0.3999999→parry.right, 0.4·0.6499999→parry.any, 0.65·0.7999999→special.random, 0.8·0.9999999→parry.guard. 제품 함수와 같은 알고리즘의 시험용 복사본을 150개 난수로 비교해 불일치 0. 20,000회 분포 프로브는 **미실시**: 제품 함수 호출은 한 번에 약 8ms(200회 1.6초)라 한 스크립트로 2만 회가 끝나지 않고, 같은 알고리즘의 시험용 복사본으로 돌려도 Maker 시험 스크립트가 초당 약 170회 수준이라(6,000회 34.7초) 2만 회 스크립트는 로그를 남기기 전에 끝나지 않았다(스크립트는 컨텍스트마다 한 번에 하나만 돌고 새 스크립트를 보내면 앞 것이 멈춘다). 분포 ±1.0%p는 근거 없음(NOT_RUN).
- **같은 RUID 재지정 재시작**: PASS(위 구현 근거 (c)): 같은 RUID를 다시 쓰면 프레임 이벤트·범위 변화가 없다(재시작 없음).

#### 미실시·미확인 (PASS로 세지 않음)
- f4(착지 시점)는 서버 쓰기 기준으로만 판정과 일치를 확인했다(클라이언트에는 그려지지 않음, 계약).
- 이펙트 눈빛·먼지의 화면 위치·방향(FlipX) 육안 확인, approach·return 중 실제 플레이어 타격 차단 실입력, 사람 손 타이밍, 모바일, 사용자 V11.
- 시험용 [VRF D] 프로브·`cf/cp` 로그는 제품 코드가 아니다.
- 시험 중 `LEA-3051 MemoryLeak`(내 클라이언트 프로브의 반복 타이머가 Play 종료 때 남음) 1건은 제품 오류가 아니다.

#### 사용 종료
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. commit·push 없음.


### 2026-11-10 REV-D-O1 수정 (reviewer 관찰, 사용자 "먼저 고침") — 부동소수 경계·조용한 취소 제거

> 제목 날짜 정정(planner, 2026-11-16): 원래 제목은 "2026-11-09"였다(사용자 지시와 회차 시작은 run "2026-11-09 REV-D-O1 수정 회차"). 제품 커밋 8428a05가 2026-11-10 20:16이라 완료일로 고쳤다. 본문은 그대로다.

#### 시작 기준
- 시작 HEAD 9918e3d(제품 = a5efe69), 57경로 Bundle `8dccccf58c6138d16e5b84277fa275c6a982c8d397e487d85e1f55e33e6ab738`로 재계산해 일치. 작업 트리는 메인 run.md만 수정된 상태(제품 변경 없음, 앞 작업이 API 한도로 끊겼으나 쓰다 만 제품·WorkRecord 변경은 남아 있지 않았음). 시작 Maker map01 / edit.
- 로그(D-Q7): 시작 때 clear 호출 결과 clearedCount 0(Maker 쪽에서 이미 비어 있음). 이번에는 시험 로그가 적어 추가 clear는 하지 않았다.

#### 원인과 수정
- 원인: `OrangeMushroomAttack.BeginWindup`이 `windupSec + (leadSec − windupSec)`를 돌려줬다. W가 TelegraphLeadSec의 절반보다 작으면 이 합이 부동소수로 1 ulp 커질 수 있고, `Monster_Attack.OnEnter`의 `TelegraphLeadSec < duration` 검사에 걸려 그 패턴 공격이 경고 없이 IDLE로 취소됐다(TelegraphLeadSec 0.9 + MotionPlayRate 2.5 등).
- 수정(근본): `BeginWindup(…, windupSec, leadSec)`가 `jumpSec = leadSec − windupSec`를 안에서 쓰되 **접근 전체 시간으로 leadSec를 그대로 돌려준다**(다시 더하지 않음). 그래서 호출 쪽 비교가 오차로 뒤집힐 수 없다. `PerformAttackMotion`은 `BeginWindup`에 `leadSec`를 넘긴다.
- 같은 종류 점검: 
  - `windup >= leadSec`(PerformAttackMotion·스폰 검증 `windup >= TelegraphLeadSec`): 두 곳이 **같은 `GetWindupSeconds` 결과를 같은 leadSec와 비교**하고 합을 만들지 않아 오차로 갈리지 않는다. 그대로 둔다(경계 W == lead면 J = 0이라 진짜 불가 조합).
  - 1칸 `JumpToLocalX`는 `JumpDuration`을 그대로 돌려주고 `lead < JumpDuration`은 두 입력 값의 직접 비교라 재계산이 없다. 그대로 둔다.
  - 착지 판정 순서(`attackDue = 시작 + lead`, 점프 끝 `시작 + W + J`)는 두 경로가 같은 곳으로 수렴해(CompleteMotion은 한 번만 실행) 1 ulp 차이가 동작을 바꾸지 않는다. `TickClip`의 f4 경계도 같은 이유로 ulp 차이는 표시 한 틱 차이일 뿐이다. 그대로 둔다.
- 진짜 시간이 맞지 않아 취소해야 하는 경우의 **경고 추가**(규칙·수치·CSV는 바꾸지 않음, 22.7 안 파일만):
  - `Monster_Attack.OnEnter`: 접근 시간이 TelegraphLeadSec보다 길어 취소하면 경고 1회("attack cancelled: approach … exceeds telegraph … (id)"). 정지·기준 위치 같은 일시 상태로 -1이 오는 경우는 경고하지 않는다.
  - `OrangeMushroomAttack.PerformAttackMotion`: 제자리 시간 W가 TelegraphLeadSec 이상이면 경고 1회("attack cancelled: windup … is not shorter than telegraph …").
  - `OrangeMushroomAttack.IsMotionReady`: `JumpDuration`이 0 이하·숫자 아님이면 경고 1회, 기준 위치 미확보(`HomeCaptured`)는 일시 상태라 경고 없이 false를 그대로 돌려준다.

#### 변경 파일
- `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua`
- `RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua`
- 그 밖 변경 없음(CSV·카탈로그·매니저·모션 베이스 그대로).

#### 검증 (Maker Play 1회, 시험 행 값은 Play 안 메모리에서만 바꾸고 복원)
- 방법: 시험 행의 TelegraphLeadSec·MotionPlayRate를 바꿔 한 행으로 강제 실행하고, 제품 [VRF] 전투 시계로 시작(`clip driven`)·W(`leap start`)·f4(`frame set frame=4`)·먼지(`effect dust`)·판정(`defense`)을 대조했다. 기대값 W = 0.8 ÷ MotionPlayRate, 판정 = TelegraphLeadSec.
- 재현 조합과 정렬식 조합(MotionPlayRate = 1.1 ÷ lead): 모두 공격이 취소되지 않고(상태 IDLE로 정상 종료, telegraph·판정 도달) W·판정이 ±0.02초 안.

| 조합(행) | lead | rate | W 측정(기대) | f4 | 판정 측정(기대) |
| --- | --- | --- | --- | --- | --- |
| 재현 (parry.left) | 0.9 | 2.5 | 0.335(0.320) | 0.453 | 0.901(0.900) |
| 정렬 (parry.guard) | 0.6 | 1.833 | 0.451(0.436) | 0.605 | 0.607(0.600) |
| 정렬 (parry.left) | 0.8 | 1.375 | 0.589(0.582) | 0.803 | 0.803(0.800) |
| 정렬 (parry.right) | 1.0 | 1.1 | 0.731(0.727) | 1.007 | 1.008(1.000) |
| 정렬 (parry.guard) | 1.3 | 0.846 | 0.953(0.945) | 1.315 | 1.316(1.300) |
| 정렬 (parry.left) | 1.5 | 0.733 | 1.093(1.091) | 1.511 | 1.513(1.500) |
| 이탈 (parry.left) | 1.1 | 2.0 | 0.414(0.400) | 0.554 | 1.105(1.100) |
| 이탈 (parry.guard) | 1.5 | 3.0 | 0.276(0.267) | 0.379 | 1.503(1.500), 먼지 1.502 |
| 이탈 (parry.right) | 0.7 | 1.7 | 0.475(0.471) | 0.648 | 0.715(0.700) |
- 정렬식에서 벗어난 조합은 취소되지 않고 W·판정(실제 점프 시작·착지)은 맞으며, 클립 f4 자세만 판정과 어긋난다(Plan 22.16.3 안내대로).
- 진짜 불가능 조합: parry.left lead 0.7 + rate 0.5(W 1.6 ≥ 0.7) → 공격 취소 + 경고 1회 "attack cancelled: windup 1.600 is not shorter than telegraph 0.700 (clip attack1, JumpStartFrame 1)". parry.any lead 0.4(JumpDuration 0.5 > 0.4) → 취소 + 경고 1회 "attack cancelled: approach 0.500 exceeds telegraph 0.400 (parry.any)". 두 경우 모두 이전에는 경고 없이 취소됐다.
- 회귀(현재 CSV 값, 제품 전투 시계): parry.left W 0.807·판정 1.100, parry.guard W 0.811·f4 1.105·먼지 1.106·판정 1.106, parry.any(1칸) 시작과 동시에 점프·판정 0.505(시험 러너 샘플 0.522). 모두 취소 없음. 사운드: 공격음 2칸 f135fc39·3칸 5da7bb48, 플레이어 UpArrow 1회(10타)에 피격음 1줄, 사망음 1줄. die: 슬로우 중 치명타에서도 PlayRate 1, 마지막 프레임 5에 정지(F12 PASS).
- 이번 시험은 시험용 [VRF D] 러너로 한 번의 Play에서 했고, 시험 행 값은 Play 끝에 메모리에서 원래 값으로 되돌렸다(CSV 파일은 바꾸지 않음). 로그 용량은 시험 로그를 줄여 가득 차지 않았다.

#### 버전·바이트 지문
- 작업 트리 57경로 Bundle: **`8d5b6d1c029d1eefad8e6ac2a878ec55facf069aab23d77c96a6fa3465f04eed`**(Refresh 뒤·Play 뒤 Stop 뒤 같음). 바뀐 경로 2개: Monster_Attack 225ee465…4656 · OrangeMushroomAttack dcc35351…147d. 나머지 55경로는 a5efe69와 같다.

#### 사용 종료
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. commit·push 없음.


### 2026-11-10 회차 D2 — MM-13~15 (Plan §22.17, 사용자 D-Q8~D-Q10) coder

#### 시작 기준
- 기준: 원격 HEAD 7cbf14e(제품 = 8428a05). 시작 때 57경로 Bundle을 커밋 트리(8428a05)와 작업 트리에서 같은 계산법(경로 바이트순, 경로 TAB sha256 LF, 확장자 9종, Global·RootDesk·map·ui)으로 계산해 둘 다 `8d5b6d1c029d1eefad8e6ac2a878ec55facf069aab23d77c96a6fa3465f04eed` 일치. 작업 트리의 미커밋 변경은 메인·planner 문서(run.md, Plan, AssetList)뿐이었다.
- 시작 Maker: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit.
- 로그: `maker_clear_logs` **호출 0회**(D-Q7 허용은 이미 사용됨). 시작 때 기존 normal 로그 **1181건, 2026-11-10 20:18:09~20:49:33**(앞 tester 세션 로그)이었고 지우지 않았다. `[VRF]`·시험 태그를 저장된 JSON에서 걸러 읽었다. 끝났을 때 2029건·약 1.23M자였고 새 로그 기록이 끊기지 않았다(포화로 멈춘 적 없음).

#### 변경 파일 (제품 1개, 22.17.5 안)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | MM-13: parry.left·parry.right·parry.guard TelegraphLeadSec 1.1 → **1.571429**, MotionPlayRate 1 → **0.7**. MM-15: parry.any·special.random AttackSound (빈 값) → **35ee15e50b17410093e768c33f7f76d6**. 그 밖의 열·행·순서·줄 끝(CRLF)은 그대로 |
- 코드(.mlua)·모델·카탈로그·매니저 변경 없음. MM-14는 계약 안 수정이 필요하다고 확정되지 않아 구현하지 않았다(아래).

#### 버전·바이트 지문
- 작업 트리 57경로 Bundle SHA-256: **`1bd2447a48103cf163eb058b9348291e78f5400fddde70bee27734fe0d1efd00`**(Refresh 뒤·Play 뒤 Stop 뒤 같음). 8428a05 manifest와의 차이는 1경로뿐: `RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv` f1ebd85e…58e4 → **f71c57a5…142e**. 나머지 56경로는 8428a05와 같다(manifest 줄 diff 확인).

#### 로드 확인 (Refresh 뒤 Play)
- build 로그 93건 전부 Info(LIA 노이즈), 오류 0(앞 회차와 같은 건수).
- 로드 [VRF]: 패턴 비율 20/20/25/15/20%, 행별 `parry.left/right/guard rate=0.7 jumpFrame=1 lead=1.57143`, `parry.any/special.random rate=1 jumpFrame=0 lead=0.5 sound=35ee15e5`, MonsterSoundData 1행, MonsterStatData default·mushmom. 스폰 성공·경고 0.

#### MM-14 — 접근 버벅임 기준선 측정 (코드 변경 전, 22.17.2 CSV만 적용한 상태, Maker 로컬 Play)
- 방법: 서버 `server_main` 프로브가 `_CombatRuleCatalog.patterns["mushmom"]`을 한 행 복제본으로 바꾸고 몬스터 AttackInterval 9999, 플레이어 HP 보충 뒤 `StateComponent:ChangeState("ATTACK")`로 강제 실행(시작 위치는 Home x=3.0 확인). 서버는 20ms 타이머로 위치·구간·JumpActive·프레임 범위·PlayRate를 기록하고, 클라이언트 프로브가 `SpriteAnimPlayerChangeFrameEvent`와 클라이언트 `WorldPosition`·렌더러 Start/End/PlayRate를 매 프레임(약 17ms) 기록했다. 두 쪽이 같은 `ServerElapsedSeconds` 시계를 쓴다. 시험 값(패턴 한 행 교체, AttackInterval, HP)은 Play 안에서만 두고 Stop으로 정리했다.
- 규모: 슬로우 없음 parry.left 3회·parry.right 3회·parry.guard 3회(첫 Play 2회씩 + 새 Play 1회씩), 접근 전체 슬로우(rate 0.5) 3칸·2칸 각 1회 이상, 1칸 비교 parry.any 2회·special.random 1회.
- 결과(슬로우 없음 9회, 클라이언트 기준, 첫 f0 이벤트 = 0):

| 지표 | 측정 | 기준 | 판정 |
| --- | --- | --- | --- |
| B1 프레임 순서 | 0→1→2→3→(착지 stand) 순서, 건너뜀 0, 되돌림 0 | 0→1→2→3, 건너뜀 0 | 순서·건너뜀·되돌림은 통과. 아래 **관찰 1** 참고 |
| B2 프레임 시각 | f1 시작 1.136~1.160초(기대 1.143, 차 −0.007~+0.017), f2 시작 차 −0.001~+0.024(기대 1.429), f3 시작 차 +0.001~+0.021(기대 1.500). f1 표시 0.273~0.297초, f2 표시 0.068~0.088초, f3 표시 0.068~0.089초 | ±0.05초, f2·f3 0.035초 이상 | PASS |
| B3 위치 연속성 | approach 구간(클라이언트 J 0.430~0.449초) 역행 0, 같은 x에 멈춘 가장 긴 구간 0.018~0.035초, 두 샘플 사이 최대 이동 0.0945~0.2975(한도 = 거리 × 0.05 ÷ J = 0.2506~0.4360) | 정지 0.05초 이하, 최대 이동 ≤ 한도 | PASS |
| B4 착지 튐·높이 | 클라이언트 y 0.5810 ~ 0.5810(변화 0). 착지 x에 도달한 뒤 되돌아오는 움직임 없음(착지 뒤 위치는 같은 틱에 시작한 복귀 점프의 이동뿐) | y ±0.01, 벗어났다 돌아오기 0 | PASS |
| B5 제자리 | windup 구간 클라이언트 x 3.0000 고정, 렌더러 Start-End 0-0(f0만) | x ±0.01, f0만 | PASS |
| (다) Start≠End 따로 도착 | 클라이언트 프레임 단위 샘플에서 approach 전 구간 Start≠End 행 0, k−1 프레임 이벤트 0 | 0 | 관찰되지 않음 |

- 서버 [VRF] 대조(parry.left): `clip driven` 시계 22.104 → `frame set 1` elapsed 1.146 = `leap start`(같은 틱) → f2 1.443 → f3 1.512 → f4 1.582(= stand 지정 = 판정 틱) → `clip set jump`(복귀) 같은 틱 +0.001. parry.guard는 같은 틱에 `effect dust x=0.000 playRate=0.7`.
- 서버 위치도 같은 직선이다(서버 샘플 0.0595/34ms, 클라이언트 0.0297/17ms). Maker 로컬 Play는 서버–클라이언트 사이 네트워크 지연이 없어, 위 지표는 지연이 있는 실제 접속의 위치 동기화 단차를 대변하지 못한다(아래 한계).
- 접근 전체 슬로우 2칸·3칸: 프레임 0,1,2,3,0 순서 유지, 렌더러 PlayRate 0.70 → 0.35(슬로우 중) → stand 0.5, B3 역행 0·최대 이동이 한도 이하(0.0919/0.1299, 0.1225/0.1767).
- 1칸 비교(parry.any 2회·special.random 1회): 0.5초, 클라이언트 y 최대 1.380(+0.8), x 3.0 → 0.0 / −1.5, 두 샘플 최대 이동 0.204 / 0.315(1칸이 초당 이동거리가 더 크다: 6~9 단위/초, 2칸 우 8.6·좌 5.2). 판정 기준에 쓰지 않는 기록이다.

**관찰 1 — 같은 프레임 이벤트가 같은 시각에 2회 도착 (B1 "재수신 0"을 이벤트 수까지 엄밀히 읽으면 어긋남)**
- 클라이언트 프레임 이벤트가 구동 프레임마다 같은 프레임 번호로 같은 시각(ms 단위 같음)에 2번 온다(f0는 클립 지정 때 3번). 예: `f1@1.147 f1@1.147 f2@1.444 f2@1.445 f3@1.513 f3@1.513`.
- 분리 시험(Play 안, 몬스터가 IDLE일 때 렌더러를 직접 구동): (A) End=k → Start=k 순서(제품 순서), (B) Start=k → End=k 순서 모두 프레임마다 이벤트가 2번 온다. (C) End만 올리면(Start 0 유지) 프레임이 안 바뀐다. (D) 구동 없이 자연 재생(Start 0·End 최대)하면 프레임마다 이벤트가 1번이다(f0@0, f1 +0.810, f2 +0.205, f3 +0.051, f4 +0.034, f0 +0.753).
- 해석: Start·End 두 @Sync 속성 쓰기가 각각 프레임 변경 이벤트를 낸다. 같은 프레임·같은 시각이고 k−1 프레임 이벤트는 없어 눈에 보이는 되돌림·깜박임·건너뜀은 측정되지 않았다. 쓰기 순서를 바꿔도 사라지지 않는다. 없애려면 구동 방식을 바꿔야 하고(자연 재생 + 경계 재고정 등) D-Q6(22.16.12) 완료 기준을 다시 증명해야 한다. 눈에 보이는 문제로 확인되지 않아 이번에 고치지 않았다. 판정은 메인·planner 몫이다.
- 한계: 첫 Play의 첫 측정(1회)에서는 이벤트가 1번씩만 왔다(원인 미확인). 이후 측정(같은 Play 안, 새 Play)은 모두 2번이다. 새 Play에서 핸들러 하나만 연결해도 같다.

**원인 확정 결과: 계약 22.17.3 3번(측정으로 잡히는 끊김 없음, (라))**
- B2~B5는 모두 통과, B1은 눈에 보이는 순서가 통과(위 관찰 1은 비가시 이중 도착)이므로 원인 (가)·(나)·(다)로 확정할 지표가 없다. 22.17.3 3번에 따라 **코드를 고치지 않았다**. 분리 시험은 B1 이중 도착 확인 목적으로만 했고 제품 파일에는 남기지 않았다.
- 어색해 보일 수 있는 지점(측정으로 "끊김"은 아니지만 사용자에게 물어볼 후보. 클립 피벗은 Plan 22.16.1 측정값 인용):
  1. 클립 자체 도약이 4개 자세로만 그려진다. 피벗 y가 f0 0 → f1 −88px(약 +0.88 단위) → f2 −70px → f3 −8px → stand 0이고, f1이 0.273~0.297초 머무는 동안 x는 2.25~3.75 단위를 직선으로 미끄러진다. 높이는 W 순간 0.88 단위로 한 번에 오르고 f2·f3 0.07초씩 사이에 거의 내려온다(자세 사이에 보간이 없음).
  2. 도약 시작 순간: 제자리 f0 1.143초 정지 직후 f1로 튀어 오르며 같은 순간 수평 이동이 시작된다(이동 속도 2칸 좌 5.2·우 8.6 단위/초, 클라이언트 한 프레임 0.09~0.14 단위).
  3. 착지 순간 정지 시간 0: 판정 틱에 stand 지정과 복귀 jump 클립 지정이 같은 틱(약 0.001초 차)이라 착지 자세(f4·stand)가 화면에 보이지 않고 곧바로 복귀 점프(높이 0.8, 0.5초)가 시작된다. 이 구조(착지 = 판정 → 복귀)는 Plan 22.16.2가 정한 것이고 이번 계약에서 바꾸지 않는다.
- 실제 접속(서버–클라이언트 지연)의 위치 단차(후보 (나))는 Maker 로컬 Play에서 측정할 수 없었다. 사용자의 V11도 Maker 로컬 Play이면 같은 조건에서 위 지표가 통과한 것이다.
- 선택지(메인이 사용자에게 어느 순간이 버벅이는지 물은 뒤 정한다): (a) 사용자가 순간을 지목하면 그 순간만 대상으로 planner가 계약을 정하고 coder가 고친다. (b) 관찰 1의 이중 도착을 눈에 보이지 않아도 고치려면 구동 방식 변경(D-Q6 재증명 필요)이 든다. (c) 착지 자세 정지·보간 도약은 규칙·수치(1칸·복귀 경로, 높이 0)를 바꾸므로 사용자 결정이다.

#### 기본 검증 결과 (22.17.7 항목, Maker Play 2회, 시험 값은 Play 안에서만)
| 항목 | 결과 |
| --- | --- |
| 1 로드 [VRF]·build | PASS(위 "로드 확인") |
| 2 MM-13 시각(parry.left·right·guard, 슬로우 없음) | PASS. 서버 시계: W = `frame set 1`·`leap start` elapsed 1.144~1.152(기대 1.1429), f4 쓰기 = 판정 = 먼지 호출 elapsed 1.574~1.588(기대 1.5714, ±0.05 이내), 클라이언트 f1 W+0.001~0.017. 렌더러 PlayRate 0.7(`clip driven playRate=0.7`), 3칸 `effect windup`(공격 시작 틱, 머쉬맘 현재 x=3.000, frames 0-6, playRate 0.7)·`effect dust`(판정 틱, x=0.000 = Pos2, frames 8-end, playRate 0.7). 착지 x: 2칸 좌 0.750·우 −0.750(영역 중앙), 3칸 0.000 |
| 2 접근 전체 슬로우 | PASS. 3칸·2칸: 렌더러 PlayRate 0.35, 이펙트 PlayRate 0.35, 시각 2배(예: 슬로우 0.4초 시작 때 f1 1.887초, 착지 2.749초, 기대 1.886·2.743) |
| 3 MM-13 스폰 | PASS. 현재 CSV로 스폰 성공·경고 0. 시험 행(Play 안 메모리) TelegraphLeadSec 1.1 + MotionPlayRate 0.7(W 1.142857 ≥ 1.1) → `spawn refused reason=windup not shorter than telegraph row=parry.left windup=1.143` + 경고 1회, 현재 몬스터 유지. 복원 뒤 정상 스폰 성공 |
| 4 MM-14 B1~B5 | 위 기준선 측정(고치지 않아 개선 비교 없음) |
| 5 D-Q6 S1~S3(0.7배) | PASS. 프레임 되돌림 0(0→1→2→3, 같은 프레임 반복은 PlayRate 변경 시점에만 추가). S1(2칸, 0.4초에 시작한 6초 슬로우): f1 W 정확(서버 action 1.147), 판정 2.749초. S2(3칸, 슬로우 1.0초가 windup 안에서 종료): f1 1.652초(기대 1.0 + 0.644), 판정 2.082초(기대 2.071). S3(2칸, 접근 중 1.2초에 시작한 0.3초 슬로우): f1 W 정확, 판정 1.734초(기대 1.721), 클라이언트 f1 이벤트가 PlayRate 변경 시점(1.224·1.517초)에 반복, f2 1.585·f3 1.653. S3b(3칸, 접근 중 시작 6초): 판정 1.948초(기대 1.942). 렌더러 PlayRate는 "0.7 × ActionRate", 끝 뒤 stand 1 × ActionRate |
| 6 MM-15 공격음 | PASS. parry.any·special.random 강제 실행마다 `[VRF] sfx kind=attack ruid=35ee15e5 user=있음` 1줄, 공격 시작(telegraph)과 같은 틱·`clip set jump`(점프 시작)와 0.001초 이내. 2칸 f135fc39·3칸 5da7bb48 공격음 회귀 없음. 후보 64c83d144b5d46ffa6d460ca61a66f1d·09df85566b984d72b97c7aa9860c4b18은 `ParseOptionalRuid`를 통과(원문 그대로 반환), 8자 줄임·비16진수는 nil. 소리 자체는 미청취 |
| 7 회귀 | 1칸 parry.any·special.random: stand 지정(착지)이 시작 +0.500초, 복귀 jump → stand +0.516초, y 최대 +0.8, 착지 x 0.000 / −1.500. windup 피격 통과: 늘린 시험 행(lead 24, rate 0.05, W 16)에서 windup 중 실제 UpArrow 1회(10타) → `PlayerHitRule pass hit=1..10`, 몬스터 HP 100 → 90, 피격음 1줄. 사운드 hitplayer 1줄/HIT. 서버 로그 Warning은 의도한 스폰 거부 1건뿐, Error는 내 프로브 오타 1건(`mon.Parent.TransformComponent` nil, 제품 오류 아님) |

#### 미실시·미확인 (PASS로 세지 않음)
- approach·return 구간 실제 UpArrow 차단(입력 도구 호출이 지연돼 approach 안에 들어가지 못함, 선언 값 ApproachHittable false·ReturnHittable false는 코드 그대로), die F12 정지, 판정 결과 GUARD 40%·PARRY·HIT 재확인, 판정 전 취소 때 먼지 없음, 이펙트 눈빛·먼지의 화면·방향 육안, 사람 손 타이밍, 청취, 사용자 V11. 이 항목들의 코드 경로는 8428a05와 같다(제품 변경은 CSV 1파일, .mlua 변경 0).
- 실제 접속(지연 있는 환경)의 위치 동기화는 측정하지 못했다.
- 첫 Play 첫 측정의 이벤트 단일 도착 원인 미확인.

#### 사용 종료
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. commit·push 없음. 시험용 프로브는 제품 파일에 남기지 않았다.

### 2026-11-16 회차 D2 MM-14 2차 — 도약 조절 항목 (Plan §22.17.10, 사용자 D-Q11·D-Q12) coder (계약 2026-11-10)

> 제목 날짜 정정(planner, 2026-11-16): 원래 제목은 "2026-11-10 … (실제 작업일 2026-11-16)"였다. 실제 작업일(제품 커밋 e710907, 2026-11-16 09:20)을 앞에 두고 계약일을 괄호로 옮겼다. 본문은 그대로다.

#### 시작 기준
- 기준: 로컬 HEAD 1b41f29(push 전). 시작 때 57경로 Bundle을 같은 계산법(경로 바이트순, 경로 TAB sha256 LF, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui)으로 작업 트리에서 계산해 `1bd2447a48103cf163eb058b9348291e78f5400fddde70bee27734fe0d1efd00` 일치(22.17.10.7-1). 작업 트리의 미커밋 변경은 메인·planner 문서(run.md, Plan)와 범위 밖 skills-lock.json(건드리지 않음)뿐이었다.
- 시작 Maker: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. `maker_clear_logs` 호출 0회(로그 포화 없음: 마지막 읽기 2498건·약 1.56M자까지 기록이 끊기지 않았다. 도구가 큰 로그를 파일로 저장해 [VRF]·[PRB] 줄만 걸러 읽었다).

#### 변경 파일 (제품 1개, 22.17.10.4 안)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 속성 `EqualizeLeapFrames`·`EaseLeapMove`(boolean, 기본 true, LeapJumpHeight 옆, 한국어 주석). `BeginWindup`에 인자 `jumpStartFrame`을 더해(같은 파일 안 호출만) StartDrivenClip 성공 직후 곡선 선택을 `_T.easeActive`에 고정하고 새 메서드 `EqualizeLeapBounds`로 이 공격의 구동 경계표 `_T.drive.bounds`만 고친다(f_j 시작 W ~ 마지막 프레임 시작 L을 n등분, W·L·앞뒤 경계·클립 Delay 캐시·GetWindupSeconds·스폰 검증은 그대로). OnUpdate x를 `easeActive`면 smoothstep(3t²−2t³), 아니면 t로 계산(y는 시간 t 포물선 그대로). `JumpToLocalX`에 플래그 초기화 한 줄 `self._T.easeActive = false`(1칸 접근·복귀는 속성과 무관하게 직선). [VRF] `leap start`에 `equalize=true|false|skip ease=true|false`, `leap bounds key=… f1=… f2=… f3=… f4=…`(구동 시작 기준 초, 소수 6자리) 1줄 |
- MonsterAttackMotion·Monster_Attack·MonsterStateControl·CSV·모델·맵·UI·.codeblock는 바꾸지 않았다(git status: 제품 변경은 위 .mlua 1개, 모델 파일 변경 0). git diff: PerformReturnMotion 변경 0, JumpToLocalX 추가 1줄.

#### 버전·바이트 지문
- 작업 트리 57경로 Bundle SHA-256: **`1e468c15dc603e46efe778637a3377e15779554c8bcb55e54f379d14d2f21bc4`**(Refresh 뒤·Play 중·최종 Stop 뒤 모두 같음).
- 1b41f29 manifest와의 차이는 1경로뿐: `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua` dcc35351…147d → **28a53a2b…d99a**. 나머지 56경로는 1b41f29와 같다(manifest 줄 diff 확인).
- 계산 도구는 scratchpad의 스크립트이며 앞 회차와 같은 방법임을 기준값 1bd2447a…fd00 재현으로 확인했다.

#### 기본 검증 방법 (Maker Play, 시험 값은 Play 안 메모리에서만)
- Refresh → build 로그 93건 전부 Info(LIA 노이즈, 앞 회차와 같은 건수), 오류 0. 실행 뒤 normal 로그에 제품 Warning·Error 0(Error 3건은 아래 관찰 2).
- 서버(server_main) 프로브: `_CombatRuleCatalog.patterns["mushmom"]`을 한 행으로 바꾸고 몬스터 AttackInterval 9999, 플레이어 HP 보충, `StateComponent:ChangeState("ATTACK")`로 강제 실행. 조합은 `OrangeMushroomAttack`의 `EqualizeLeapFrames`·`EaseLeapMove`·`LeapJumpHeight`를 Play 안에서 바꿔 실행. 서버 20ms 타이머가 액션 시계 기준 위치·구간·프레임 범위·PlayRate를 기록하고, 위치 곡선은 시간 지연(0~0.08초, 1ms 간격) 최적 맞춤으로 판정했다(샘플 시각이 OnUpdate 시각과 달라 지연 0 그대로는 0.04~0.065 어긋나고, 최적 지연은 0.013~0.018초로 서버 틱 이내). 클라이언트(client) 프로브: 몬스터 `SpriteAnimPlayerChangeFrameEvent`와 클라이언트 WorldPosition을 매 프레임(약 16ms) 기록하고 ATTACK 관찰 시각(서버 시작 +0.03~0.05초 뒤)을 0으로 계산. 두 쪽 모두 `ServerElapsedSeconds` 시계.
- 측정 횟수(슬로우 없음): (켬,켬) 서버 6회(2칸 좌2·우2·3칸2) + 높이 시험 4회 + 자연 공격 다수, (켬,끔) 좌1·3칸1, (끔,켬) 좌1·3칸1, (끔,끔) 좌1·3칸1 + 보정 2차 좌·우·3칸 각 1회(조합마다), 1칸 3회(+자연 1칸 다수), 슬로우 5회(S1·S2·S3a·S3 f2 안·S3b).
- Play는 2회 열었다: 첫 Play(조합 22회 + 보정 14회)에서 T7 클라이언트 높이 계산의 기준 샘플 오류를 발견해, 같은 제품으로 Stop → Play를 다시 해 T7 4회만 재측정했다(제품 파일 변경 없음).

#### 조합별 결과 (표기 (균등화, 곡선))
서버 `frame set` elapsed(액션 시계, 구동 시작 기준). `leap bounds` 로그와 서버 값이 일치한다.

| 조합 | leap bounds f1/f2/f3/f4 (로그) | 서버 frame set 1/2/3/4 | f4 쓰기 − 판정 | 비고 |
| --- | --- | --- | --- | --- |
| (켬,켬) 6회 | 1.142857 / 1.285714 / 1.428571 / 1.571429 | 1.147~1.157 / 1.287~1.295 / 1.433~1.443 / 1.572~1.588 | −0.002~0 | `leap start … equalize=true ease=true` |
| (켬,끔) 2회 | 위와 같음 | 1.147·1.151 / 1.301·1.288 / 1.442·1.444 / 1.580·1.582 | 0 | `equalize=true ease=false` |
| (끔,켬) 2회 | 1.142857 / 1.428571 / 1.500000 / 1.571429 | 1.152·1.156 / 1.429·1.431 / 1.516·1.501 / 1.586·1.587 | −0.001~0 | `equalize=false ease=true` |
| (끔,끔) 2회 | 위와 같음 | 1.151·1.159 / 1.441·1.435 / 1.513·1.504 / 1.583·1.575 | −0.001~0 | `equalize=false ease=false` |

3칸 먼지 호출 − 판정 = −0.001~0초(전 조합). 렌더러 PlayRate 0.7(슬로우 없음).

클라이언트(시각은 ATTACK 관찰 시각 기준 상대):

| 조합 | 표시 시간 f1/f2/f3 | 최대 이동 비(한도 k) | 정지(처음·끝 제외) | 되돌림·순서 | 착지 방향 전환 |
| --- | --- | --- | --- | --- | --- |
| (켬,켬) 자연 포함 8회 | 0.117~0.171 각 | 0.51~1.01 (k 1.5) | 0.000~0.018 | 되돌림 0, 순서 0→1→2→3 | 접근→복귀 1회, 전환 x는 목표 ±0.003 |
| (켬,끔) 2회 | 0.139~0.140 각 | 0.70·0.68 (k 1) | 0.000~0.017 | 0 | 1회 |
| (끔,켬) 2회 | 0.277~0.293 / 0.069~0.089 / 0.069~0.071 | 0.87·0.54 (k 1.5) | 0.000~0.017 | 0 | 1회 |
| (끔,끔) 2회 | 0.290~0.294 / 0.069~0.072 / 0.069~0.070 | 0.72·0.73 (k 1) | 0.000~0.018 | 0 | 1회 |

- 서버 위치 곡선 맞춤: 곡선 켬 최대 편차 0.0035~0.0056, 끔 0.0023(기준 ±0.01). 서버 위치 역행 0. 2·3칸 y 변화 0(yMax 0.000).
- 착지 x: 마지막 접근 샘플 다음 첫 샘플이 같은 틱에 시작한 복귀 점프의 이동분이라, 복귀 점프 식(y=4·0.8·t(1−t), x는 목표→홈 직선)으로 역산한 목표가 2칸 좌 0.750·우 −0.750·3칸 0.000으로 22회 모두 일치한다(코드의 JumpTargetX와도 같음). 착지 y는 CompleteMotion이 Home.y로 맞추며 y=0.000 직접 관찰도 다수.
- B4 착지 튐: 접근 종료 뒤 0.3초 구간에서 x 방향 전환은 1회뿐(착지 → 복귀)이고 전환 지점이 목표와 같다(최대 어긋남 +0.023, (켬,끔)·높이 0.5 좌, 기준 0.05). 초기 지표 `ovs`(첫 stand 프레임 이벤트 이후 진행 방향 이동량)는 곡선 끔에서 0.04~0.10까지 나오지만 프레임 이벤트가 마지막 이동 샘플보다 한두 프레임 먼저 오는 효과이며, 위 전환 x 측정이 실제 초과 여부의 근거다.
- B5: windup 클라이언트 x 3.000 고정, 접근 전 프레임은 f0뿐(preNon0=0).

#### T1~T11 판정 (coder 기본 검증, tester가 같은 조합으로 다시 본다)
| # | 결과 | 근거 |
| --- | --- | --- |
| T1 시각 불변 | PASS (4조합) | W(`frame set 1`/`leap start`) 1.145~1.159, f4 쓰기 = 판정 = 먼지 1.572~1.588(기대 1.5714 ±0.05), 착지 x 22회 일치, y = Home.y |
| T2 프레임 경계 | PASS (4조합) | 서버 f2·f3: 켬 1.287~1.301·1.433~1.446, 끔 1.429~1.441·1.501~1.516. `leap bounds` 켬 1.285714·1.428571, 끔 1.428571·1.500000(6자리 일치). 클라이언트 표시 시간: 켬 f1~f3 모두 0.117 이상(≥0.071), 끔 0.277~0.294/0.069~0.089/0.069~0.072(B2 그대로, 기대의 절반 이상) |
| T3 프레임 순서 | PASS (4조합) | order=true, 되돌림 0, 건너뜀 0. 같은 프레임 이중 도착은 구동 프레임마다 4건(0.01초 안, 22.17.10.5 중복 묶음). 접근 안 재도착 0(슬로우 시험만 PlayRate 변경 시점에 재도착, 허용) |
| T4 위치 역행 | PASS (4조합) | 서버 rev=0, 클라이언트 rev=0 |
| T5 곡선 모양 | PASS (4조합) | 위 맞춤. 곡선 켬 smoothstep, 끔 직선, 편차 ≤0.0056. 단 시간 지연 맞춤 방식(서버 틱 이내 지연 허용) |
| T6 클라이언트 연속성 | PASS (4조합) | 위 표. 정지 ≤0.018초, 최대 이동 비 ≤1.01(켬 k 1.5 이하, 끔 ≤0.73 ≤1), B4 방향 전환 1회, B5 제자리·f0 |
| T7 높이 관계 | PASS | LeapJumpHeight 0.5, 2칸 (켬,켬) 좌·우, (켬,끔) 좌·우 각 1회. 서버 yMax 0.497·0.498, 서버 y 편차 0.0042·0.0043(기대 4·0.5·t(1−t)). 클라이언트 y 꼭대기 +0.4999·+0.4996((켬,켬))·+0.4999·+0.5000((켬,끔)), 꼭대기 시각이 W+J/2에서 +0.008·+0.019·−0.009·−0.013초, 착지 y는 Home.y. x는 T5와 같은 곡선(서버 맞춤 0.0059·0.0023) |
| T8 D-Q6 유지 | PASS | (켬,켬) 5회. S1(windup 0.4초에 시작, 6초): 클라이언트 0→1→2→3, f1 상대 1.867초(늘어난 W 1.886초), 착지 2.737초(기대 2.743), 서버 PlayRate 0.7→0.35→착지 뒤 stand 0.5. S2(공격 직전 시작한 1초 슬로우가 windup 중 종료): f1 1.618초(기대 1.643), 클라이언트 착지 2.083초는 기대 2.071보다 약 0.047초 늦음(서버 f4 쓰기↔판정은 0.000초), PlayRate 0.35→0.7→1.0. S3a(접근 중 1.2초에 시작 0.3초): f2 1.375·f3 1.563·착지 1.715(기대 1.371·1.579·1.721). S3 f2 안(1.3초 시작 0.2초, 시작·끝 모두 균등화된 f2 구간 안): f2 1.268 → PlayRate 변경 재도착 1.493 → f3 1.510. S3b(3칸)도 비슷. 프레임 되돌림 전부 0, 서버 f4 쓰기↔판정 −0.017~0초, 서버 렌더러 PlayRate = 0.7 × ActionRate |
| T9 1칸·복귀 불변 | PASS | (켬,켬) parry.any·special.random, (끔,끔) parry.any: 접근 0.503·0.513·0.504초, 복귀 0.516·0.500·0.501초, y 최대 +0.799, 착지 x 0.000 / −1.500, `easeUsed=false`라 진행률 직선(편차 0.004·0.008 ≤0.01). 소스: JumpToLocalX 추가 1줄, PerformReturnMotion 변경 0. 공격음 `[VRF] sfx kind=attack ruid=35ee15e5` 1줄씩 |
| T10 기본값·로드 | PASS | 속성 기본값 true/true(프로브 읽기), `leap start … equalize=true ease=true`, 모델 파일 변경 0, 빌드 오류 0 |
| T11 (끔,끔) = 지금 | PASS | 서버 W 1.151·1.159(기준선 1.144~1.152 + 틱 오차), f4 1.583·1.575(기준선 1.574~1.588), 클라이언트 표시 0.290/0.072/0.070·0.294/0.069/0.069(기준선 0.273~0.297/0.068~0.088/0.068~0.089), 정지 0·0.018초(기준선 최대 0.035), 최대 이동 0.184·0.245(기준선 0.0945~0.2975), 착지 x 같음 |

#### 관찰·미실시 (PASS로 세지 않음)
1. 시작 직후(자연 공격 중) `CombatCore duel player=none`이 한 번 나온 뒤 1칸 공격이 중단되어 머쉬맘이 착지 지점(x 0.0)에 남았다. 제품 변경과 무관한 기존 동작으로 보이며 이번에 고치지 않았다. 프로브가 머쉬맘을 홈으로 되돌리고 시작했다(Play 안 메모리).
2. 프로브 반복 타이머 때문에 Play 정지 때 `[LEA-3051] MemoryLeak … 'MakerScript'` Error 3건이 나왔다(내 MakerScript 타이머, 제품 코드 아님). 제품 오류·경고 0.
3. T8 S2에서 클라이언트 착지 이벤트가 기대보다 약 0.047초 늦게 관찰됐다(기준 ±0.05초 안 경계). 서버 f4 쓰기↔판정은 0.000초이고 f1↔W는 0.010초라 계약 문구(f1 시작↔W, 서버 f4 쓰기↔판정)는 통과로 본다. tester가 같은 경우를 볼 때 클라이언트 이벤트 지연 변동(약 1~2프레임)을 감안할 것.
4. 곡선 끔(직선) 조합의 클라이언트 `ovs` 지표(위 B4)는 정의상 프레임 이벤트와 마지막 이동 샘플의 어긋남이 섞인다. tester는 방향 전환 횟수와 전환 x를 쓰는 편이 정확하다.
5. NOT_RUN: 화면 체감("뚝 끊기는 느낌"이 줄었는지)은 사용자 V11. 실접속(서버–클라이언트 지연) 위치 동기화, approach·return 실입력 차단, die F12, 판정 결과 GUARD·PARRY·HIT 재확인, 판정 전 취소 먼지 없음, 이펙트 눈빛·먼지 육안, 효과음 청취, 사람 손 타이밍, MM-13·MM-15의 나머지 22.17.7 항목(1b41f29 coder 기본 검증으로 확인했고 이번에 다시 하지 않음). T8은 (켬,켬) 5회뿐이고 (끔,끔) 슬로우는 보지 않았다.

#### 사용 종료
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. commit·push 없음. 시험용 프로브는 제품 파일에 남기지 않았다. 다음 담당: tester(같은 버전, 22.17.7 + 22.17.10.6 T1~T11).

### 2026-11-16 회차 D V11 선택값 — 1칸 점프음 (D-Q13, 사용자 "1칸 점프음을 player가 사용하는 점프음으로") coder

#### 변경
- 제품 1파일: `RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv`의 `parry.any`·`special.random` 두 행 AttackSound를 `35ee15e50b17410093e768c33f7f76d6` → **`a49c4b3963e148f09b2eb9de98d42ef4`**. 다른 행·열·순서는 그대로, BOM(EF BB BF)과 줄 끝 CRLF를 유지했다(바이트 치환 2건, git diff는 두 행뿐).
- 근거: 엔진 `MaplePreferencesLogic.JumpSound` 기본값(`Environment/NativeScripts/Logic/MaplePreferencesLogic.d.mlua` 14행). 프로젝트의 .mlua·.csv·.config·.userdataset에서 `JumpSound`를 덮어쓴 곳은 없다(Grep 결과 위 d.mlua 1건뿐). Play 중 런타임 값도 서버(server_main)·클라이언트 모두 `a49c4b3963e148f09b2eb9de98d42ef4`로 같았다.
- 코드(.mlua)·모델·맵·UI 변경 0. 후보 3개(35ee15e5·64c83d14·09df8556)는 채택하지 않았다.

#### 시작 기준·버전 지문
- 시작: 원격과 같은 HEAD f78bab5, 작업 트리 변경은 메인의 run.md뿐. 57경로 Bundle을 같은 계산법(경로 UTF-8 바이트순, 경로 TAB sha256 LF, 확장자 9종, Global·RootDesk·map·ui)으로 계산해 `1e468c15dc603e46efe778637a3377e15779554c8bcb55e54f379d14d2f21bc4` 일치(57/57).
- 변경 뒤(Stop 뒤) 57경로 Bundle SHA-256: **`28f833db19afaef1c69364bc2d88aad9615aeb7734d94cb054c91f067cbe012a`**. 시작 manifest와의 차이는 1경로뿐: `RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv` f71c57a5…142e → **4d0525b2…6ebe**. 나머지 56경로는 같다(manifest 줄 diff 확인). 시험 중 Maker가 다른 제품 파일을 다시 저장하지 않았다(Stop 뒤 git status는 CSV와 run.md뿐).

#### 기본 검증 (Maker MCP, Refresh 1회 + Play 1회, 서버 프로브는 Play 안 메모리에서만)
- map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인 후 시작. `maker_clear_logs` 호출 0회.
- Refresh 뒤 build 로그 93건 전부 Info(LIA 노이즈, 앞 회차와 같은 건수), 오류 0. (Play 뒤 build 로그는 다시 읽지 않았다.)
- 로드 [VRF]: `pattern row id=parry.any … sound=a49c4b39`, `id=special.random … sound=a49c4b39`(1칸 두 행), parry.left·right `sound=f135fc39`, parry.guard `sound=5da7bb48`. 카탈로그 ready patterns=5, 스폰 성공.
- server_main 프로브(패턴 목록을 한 행으로 바꾸고 AttackInterval 9999, 플레이어 HP 보충, `ChangeState("ATTACK")`, 4초 간격): parry.any 2회·special.random 2회 모두 **`[VRF] sfx kind=attack ruid=a49c4b39 user=있음` 1줄씩**(공격 시작 틱, `clip set key=jump`와 같은 틱). parry.left·right 각 1회 `ruid=f135fc39`, parry.guard 1회 `ruid=5da7bb48`(`effect windup`·`effect dust` 정상). 프로브가 끝나며 패턴 목록·AttackInterval 원복(`restored=true`), 이후 자연 공격에서도 2칸 f135fc39·3칸 5da7bb48 확인. 이 Play에서 자연 1칸도 a49c4b39로 나왔다.
- `_MaplePreferencesLogic.JumpSound`: 서버 프로브 `a49c4b3963e148f09b2eb9de98d42ef4`, 클라이언트 프로브 같은 값.
- 로그 전체: normal 로그 526건 모두 Info, 제품 Warning·Error 0.

#### 미실시·미확인 (PASS로 세지 않음)
- 소리 자체의 청취(a49c4b39가 실제로 점프음으로 들리는지, 0.13초 길이)는 사용자 V11. 로그는 재생 요청 RUID만 보여 준다.
- 이번 변경은 CSV 값 1종이라 2·3칸 시각·도약 조절·판정 등 나머지는 e710907 QA14 결과를 이어 쓰며 다시 하지 않았다. 실접속·모바일은 NOT_RUN.

#### 사용 종료
- 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. 프로브는 제품 파일에 남기지 않았다. commit·push 없음. 다음 담당: tester(같은 버전, CSV 1경로 변경 확인) 또는 메인 판단.

## 2026-11-16 coder 회차 E 구현·기본 검증 인계 (CombatCore-UX-01·UX-02)

### 범위·기준
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §24(UX-01 버튼 테마, UX-02 가드 모션·이펙트·소리, E-Q1 새 표 PlayerActionFxData)뿐이다. 판정 규칙·수치·입력 계약·회차 D 동작은 바꾸지 않았다. 기준 원격 HEAD de6e6aa(제품 파일은 회차 D·D2 최종 커밋 5ce65d6과 같음).
- 시작 Maker: maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. **maker_clear_logs는 호출하지 않았다.** 로그는 저장 파일을 시각·`[VRF` 표지로 걸러 읽었다.
- **map/map01.map**: 사용자 "그대로 둠" 변경(attackareamark 위치)이 작업 트리에 있다. 건드리지 않았다. 시작 전 SHA-256 `3e60c21d6bd2328e1119f9566beb55901b13da64a99400c3d3ce68a0be5c2094`, Refresh 1회·Play 1회·Stop 뒤 `3e60c21d6bd2328e1119f9566beb55901b13da64a99400c3d3ce68a0be5c2094`(**전후 동일, Maker 저장·Play가 이 파일을 다시 쓰지 않았다**). 커밋에 섞지 않을 것.

### 변경 파일
| 파일 | 변경 | ID |
| --- | --- | --- |
| RootDesk/MyDesk/DataSet/PlayerActionFxData.userdataset (새) | MonsterSoundData.userdataset과 같은 형식. EntryKey·`id` `userdataset://ecb9c840-2af3-42cb-aff3-758b01590b99`(node randomUUID), name `PlayerActionFxData`, serveronly true, UseService 1, CoreVersion 26.10.0.0. CRLF·끝 줄바꿈 없음(원본 형식 그대로) | UX-02 |
| RootDesk/MyDesk/DataSet/PlayerActionFxData.csv (새) | UTF-8 BOM·CRLF. `id,EffectClip,EffectSound` / `guard,318a46627eca4ae5b9c5d1fb16244e3c,605da1fc42f34ef4a1468387004a6223` | UX-02 |
| Combat/CombatRuleCatalog.mlua | 속성 `playerActionFx`·`fxReady`, `ValidatePlayerFxRows`(표 전체 검증, 빈 칸 = 그 연출만 없음), `EnsurePlayerActionFx`(별도 1회 시도 플래그 `_T.fxAttempted`, 로드 [VRF]), `GetPlayerActionFx(id)`(표 무효면 nil, 행 없으면 경고 1회 + nil), OnBeginPlay에서 EnsureInitialized 뒤 1회 시도, OnEndPlay에서 캐시·플래그 정리. EnsureInitialized·Ready·패턴·능력치·MonsterSoundData 코드는 한 줄도 바꾸지 않음(+53줄) | UX-02 |
| Player/PlayerGuardComponent.mlua | SetGuarding 시작 분기(기존 시작 시각·위치 기록 뒤)에 `GetPlayerActionFx("guard")` → EffectClip이 비어 있지 않으면 서버 `_EffectService:PlayEffect` 1회, `[VRF] guard fx effect=앞8자\|-`(표 없음·행 없음은 `[VRF] guard fx off`), `PlayMonsterSound("guard", EffectSound, self.Entity)` 1회(+14줄) | UX-02 |
| Player/@StateControl/PlayerStateControl.mlua | 16행 `SetActionSheet("GUARD", "sit")` → `"alert"` 한 단어 | UX-02 |
| ui/CombatScreen.ui | UIBuilder(load → patchComponent/sprite/patch → write, ui_lint clean): 버튼 4개 SpriteGUIRenderer ImageRUID `e314c09b9b39486bb1c68d018b2abded`·Type 1·Color (1,1,1,1)만 패치(PreserveSprite 1·RaycastTarget 켬·ButtonComponent·크기·위치 그대로). 자식 `{버튼}/Icon` 4개 추가(middle-center·(0,0)·60×60·sprite_type 0·`#FFFFFF`·raycast 끔·PreserveSprite 1), display_order Icon 0·Highlight 1. 엔티티 새로 만들지 않음, bind·injectBindings 미사용 | UX-01 |

- C-1(이펙트 방향): 기본 공격 선례와 같게 위치 = 플레이어 WorldPosition, 크기 `Vector3(-LookDirectionX, 1, 1)`, 반복 없음. LookDirectionX가 0이면 1. 클라이언트 화면에서 이펙트가 플레이어 오른쪽 위로 보였다(아래 확인). 방향·위치 어울림은 V11.
- C-2: 계획대로 `sprite_type: 0` + PreserveSprite 1(비율 유지) 방식이 lint·validate를 통과해 기록 비율 상자 대안은 쓰지 않았다.
- .ui 파일 diff가 큰 것(+3995/-3415줄)은 UIBuilder가 파일을 다시 직렬화한 형식 차이이며, 내용 변경은 위 표와 UIBuilder 읽기 비교(엔티티 19→23, 기존 버튼·Highlight UUID 7개 전후 동일)로 확인했다. 셸로 .ui를 읽는 것은 가드로 막혀 줄 단위 diff는 보지 않았다.

### 버전·바이트 지문
- 계산 방식은 앞 절과 같다(경로 `LC_ALL=C` 바이트순, `경로 TAB sha256 LF` 연결의 SHA-256, 확장자 .mlua·.model·.stateset·.userdataset·.csv·.map·.ui·.config·.collisiongroupset, Global·RootDesk·map·ui 아래). 새 스크립트로 계산했고 5ce65d6 커밋 트리에서 앞 절의 **28f833db19afaef1c69364bc2d88aad9615aeb7734d94cb054c91f067cbe012a(57경로)** 를 재현했다.
- 시작 전 작업 트리 57경로: `82185c159b7960e49e9fd5fb80a4966ca194e50829d913aa64545f50b7fb9102`(= 5ce65d6 + 사용자 map01 변경 1경로).
- **끝(Stop 뒤) 작업 트리 59경로 Bundle SHA-256: `7f6a703b237f07837ea642bf548c3bc749ac012785fbd76721af88e69a308940`**(새 2경로 포함, map01 사용자 변경 포함).
- **map01.map을 뺀 58경로 Bundle(커밋 대상 제품 묶음): `1d70bc71a65ddd70d8f29c377065b4058e7e60d71f0690ffcab48618e23975dd`**(같은 방식으로 뺀 5ce65d6 56경로 값은 `12a6ca64a2ba8d194bb05fcc3702a3c05e441490b41dd9bb6ff8efa19babfd48`).
- 5ce65d6 대비 manifest 차이(map01 제외): 변경 4경로 — `RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua` a326f630…→4ac9bdeaf3ec4af38a36e53eb50afee81109ef31e61ae22dd3c919411a095a5b · `RootDesk/MyDesk/Player/PlayerGuardComponent.mlua` f8d0bd70…→92c85a450b5df5246454395acff1a240fb2a011ce795fbd095f4311f23867936 · `RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua` 1bf98ade…→95ad9015ce80ad9935930ee1c78988d0677f82d81765da767fb7af3f64db40b9 · `ui/CombatScreen.ui` f0b37dd5…→b420738c6d875e20b0b5bdc008df8b116ae95d2a6fd24fe2f72bfbe63e1c143e. 새 2경로 — `RootDesk/MyDesk/DataSet/PlayerActionFxData.csv` 75b8e8f0d7383ff313514ffe4114ea479b81a238261a5900872efa6722e8dc9b · `RootDesk/MyDesk/DataSet/PlayerActionFxData.userdataset` f1be99ad3327d47d3419b3bbea7bac3123800f58ce5b643d26b884e5df4d432a. 나머지 52경로는 같다. map01.map은 사용자 변경(5ce65d6 커밋 값 02e41f3c… → 작업 트리 3e60c21d…)이라 이 차이에서 뺀다.
- Maker Refresh·Play가 만든 다른 변경: 없음(git status는 위 변경 6경로 + 사용자 map01 + 메인·planner 문서뿐, .codeblock·.directory 변경 없음).

### 실제 기본 검증 (Refresh 1회 + Play 1회, 시험 설정은 Play 내부에서만)
- 빌드: refresh status ok, build 로그 93건 모두 Info(LIA 1114/1115 동적 참조 노이즈), 오류 0·경고 0. 런타임 normal 로그는 Info 외에 내가 의도한 Warning 4건뿐(아래 3번), 오류 0.
- 방법 구분: (A) 서버·클라이언트 프로브 = maker_execute_script, (B) 실제 키 입력 = maker_keyboard_input, (C) 실제 마우스 = maker_mouse_input.

| Plan §24.7 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 1 UI 정적(UX-01) | UIBuilder.load 스크립트(36개 검사) | 버튼 4 UUID·Highlight 3 UUID가 §24.1 표와 같음. 배경 ImageRUID e314c09b…·Type 1·Color 흰색·PreserveSprite 1·Raycast 켬. `{버튼}/Icon` 버튼마다 정확히 1개, RUID ↑3119d280…·↓a714a1ea…·←002ca90c…·→740aba24…, Color 흰색·Type 0·Raycast 꺼짐·PreserveSprite 1, 앵커 (0.5,0.5)·위치 (0,0)·60×60. Icon display_order 0 < Highlight 1(←·↓·→), ButtonComponent Transition 1·PressedColor 0.784·상태 스프라이트 4개 null, 크기 140×140·위치 (0,270)/(-170,110)/(0,110)/(170,110). write lint 오류 0(`ui_lint: clean`) | PASS |
| 2 데이터 로드 | A(Play 시작 로그) | `[VRF] PlayerActionFxData id=guard effect=318a4662 sound=605da1fc` 1회. 같은 Play의 `catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`, 패턴 5행(parry.left·right·any·special.random·guard) Weight 4/4/5/3/4·모션·`jumpFrame`·`lead`·`sound`(f135fc39·a49c4b39·5da7bb48)·`effect=05113e9d`, MonsterSoundData mushmom 3개, MonsterStatData 100/12/3.0, 머쉬맘 스폰 `x=3.0`이 de6e6aa와 같은 값. Ready true. (de6e6aa 기준 패턴은 이미 5행이라 §24.7의 "4행" 표현은 낡았다) | PASS |
| 3 오류 동작 | A(가짜 행으로 `ValidatePlayerFxRows` 직접 호출, `playerActionFx`·`fxReady`를 Play 안에서 바꿔 `SetGuarding(true/false)` 호출, 끝에 `_T.fxAttempted` 해제 + `EnsurePlayerActionFx`로 복원) | 빈 EffectClip: `guard fx effect=-` + `sfx kind=guard` 1, 경고 0. 빈 EffectSound: `guard fx effect=318a4662`, sfx 0. 형식 오류(대문자·31자·공백 끼움·16진 아님·소리 칸 오류) 5건 모두 REJECT, 경고 `PlayerActionFxData invalid ruid` **1회**(원인당 1회 중복 제거). 중복 id(공백 제거 뒤) REJECT·`duplicate id` 1회, 빈 id REJECT·`invalid id` 1회. 정상·빈 칸 둘·행 0개는 ACCEPT. 필수 열 누락 모사(`ReadRows`에 MonsterSoundData를 넘김) → nil(표 무효 경로, EnsurePlayerActionFx가 `missing or required columns missing` 경고를 내는 줄은 직접 실행하지 않음). 표 무효 상태에서 가드 시작: `guard fx off`·sfx 0. guard 행 없음: `[CombatRuleCatalog] player action fx row missing: guard` 경고 **1회**, 두 번째 가드 시작은 경고 없이 `guard fx off`. 모든 경우 `Ready=true`·`GetMonsterStats("mushmom")` 정상. 복원 뒤 로드 [VRF] 다시 1줄, 가드 시작 정상 연출 | PASS(표 파일 자체는 건드리지 않음) |
| 4 입력 회귀(UX-01) | B·C + A | **실제 LeftArrow·RightArrow 탭**: `MovementInput phase=OUTBOUND`(±1.5, 0.12초)→`RETURNING`→`complete state=IDLE`, `PlayerEvade start`. **실제 UpArrow 탭 1회·실제 마우스 클릭(BtnAttack 위치 960,340) 1회**: 각각 IDLE→ATTACK·`CombatCore manual cast count=10`·HitRule pass 10(버튼 클릭 경로도 동작). **마우스 홀드(가드 버튼 960,180) 1.5초**: `IDLE→GUARD`·`PlayerGuard start`·가드 연출 1회, 떼면 `GUARD→IDLE`. 실제 DownArrow 홀드·탭도 같음. 가드 Highlight는 홀드 중 `Enable=true`로 확인(←·→ Highlight 토글은 따로 읽지 않음). `[VRF] sfx` 집계(방식 B·C 구간): ←·→ 입력에서 sfx **0건**, ↑ 입력에서 `kind=damaged` 1건씩(몬스터 피격음, 버튼 누름 소리 아님), ↓ 입력(마우스·키보드 모두)에서 `kind=guard` 정확히 1건씩. 버튼 누름 자체의 소리 없음 | PASS(출처 합산·반환 잠금은 이번 범위 밖이라 다시 시험하지 않음, 입력 코드·UUID 무변경) |
| 4 화면 존재 | 스크린샷(입력 좌표 확인용) | 800×450 스크린샷에서 버튼 4개가 원형 배경 + 흰 아이콘(칼·왼쪽 화살표·아래 화살표·오른쪽 화살표)으로 보이고 아이콘이 배경 가운데에 있다. 존재 확인만, 어울림 판정은 V11 | PASS(존재) |
| 5 가드 모션 | A(서버 시트 읽기 + 클라이언트 이벤트 리스너) | 서버 `StateToAvatarBodyActionSheet` GUARD=`alert`·ATTACK=`attack`·MOVE=`walk`·IDLE=`stand`. 실제 ↓ 입력: 클라이언트 `StateChange IDLE→GUARD`, `BodyActionStateChangeEvent Alert`, `ActionStateChangedEvent core=alert parts=alert`. 떼면 `GUARD→IDLE`·`Stand`·`stand1`. 패링 성공 찌르기 모션 호출 없음(코드에 없음) | PASS |
| 6 이펙트·소리 | B·C + A + 스크린샷 | 가드 시작마다 `[VRF] guard fx effect=318a4662` 정확히 1줄 + `[VRF] sfx kind=guard ruid=605da1fc user=있음` 정확히 1줄. 홀드 유지 중 추가 없음(1.5초·6초 홀드), 떼었다가 다시 누르면 다시 1회, 실제 입력 가드 시작 6번(키 5·마우스 1) 모두 1:1. 클라이언트에서 실제로 보이는지: 클라이언트 시간 배율을 0.1로 늦춘 프로브에서 ↓ 입력 직후 스크린샷에 **금색 방패 이펙트가 플레이어 오른쪽 위에 표시됨**(배율은 프로브가 1로 복원). 서버 PlayEffect가 클라이언트에 보이므로 @Sync 대체 경로는 쓰지 않음. 같은 홀드에 출처가 합쳐질 때(터치+키 동시)의 추가 재생 없음은 코드 경로(같은 홀드 출처 합산은 서버 GUARD 진입을 다시 만들지 않음)로 판단했고 동시 입력 시험은 NOT_RUN | PASS(출처 합산 동시 입력만 NOT_RUN) |
| 7 다른 회귀 | A + B | 가드 판정: 가드를 든 채 자연 공격(`interval 1.5`) 3회 → `defense kind=GUARD rate=0.4`(40%)·`sfx kind=hitplayer ruid=7c8e5f1e`·`HUD feedback=GUARD`. 가드 없이 맞은 경우 `kind=HIT rate=1`(parry.right 1회도 HIT). 1칸 점프음 `sfx kind=attack ruid=a49c4b39`(parry.any 자연 공격), 2칸 f135fc39, 3칸 5da7bb48. die F12: 몬스터 Hp 5에서 ↑ 공격 → `MonsterDie start frames=6 total=1.100 freezeAfter=0.800` 1회·`freeze frame=5` 1회, `sfx kind=die ruid=d48ec1cc`. 빌드 오류 0, 제품 경고·오류 0(오류 시험의 의도한 경고 4건 제외) | PASS(아래 NOT_RUN 제외) |

### 시험 오류·한계 (제품 오류 아님)
- 첫 확인 스크립트가 늦어 몬스터의 자연 공격 2회가 먼저 들어와 플레이어 Hp가 76까지 내려갔다. 이후 프로브가 몬스터 `AttackInterval`을 9999로 올리고 Hp를 100으로 되돌렸다.
- 이펙트 엔티티 탐색 프로브(클라이언트에서 맵 하위·World 루트 4단계를 30~50ms 간격으로 스캔)는 이펙트 새 엔티티를 찾지 못했다. 이펙트는 엔티티 트리 밖의 엔진 렌더로 보이며, 존재 증거는 스크린샷이다. `PlayEffect` 반환 serial은 기록하지 않았다.
- 스크린샷은 3장 찍었다: 입력 좌표 확인(1), 가드 홀드 중 확인(1), 시간 배율 0.1 프로브의 이펙트 확인(1). 계획의 허용은 입력 좌표용 1장이었으므로 나머지 2장은 이펙트 표시 확인 목적이다(가드 홀드 중 장면에는 이펙트가 이미 끝나 보이지 않았다).
- 가드 판정 시험은 자연 공격이라 패턴이 무작위였다(parry.guard·parry.any·parry.right). Pos2 패링·저스트는 이번에 시험하지 않았다(코드 무변경).

### 실패/미확인/미실시 (PASS로 세지 않음)
- **버튼·아이콘·이펙트의 어울림, alert 모습, 소리 청취, 이펙트 크기·위치·방향(좌우 반전)은 AI가 판정하지 않는다(Plan §24.8, 사용자 V11).** 이펙트는 플레이어보다 오른쪽 위에 보였다.
- 관찰: 무기 없는 계정이라 ATTACK(`attack`)도 `core=alert`로 재생돼 공격과 가드의 모습이 같다(Plan §24.5 위험으로 이미 기록). V11에서 확인할 것.
- Pos2 패링·저스트 시험, 기존 패링 성공 스파크(SparkRadialExplosion)·그로기 별 육안, 팝업 정지·재개 중 가드(홀드 풀림·연출 미발생), 터치+키 동시 출처 합산에서 추가 재생 없음, 필수 열 누락의 `EnsurePlayerActionFx` 경고 줄 직접 실행, 실기기·모바일·다중 접속은 실행하지 않았다.
- 제품 코드·모델·맵·CSV는 시험 때문에 바꾸지 않았다(시험 값은 Play 내부 캐시·속성뿐, Stop으로 폐기).

### 사용 종료·다음 담당
- 마지막 maker_stop 성공(play_to_edit) 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: Plan §24.7 1~7을 같은 방식으로 독립 재현(특히 3의 오류 시험은 CSV를 고치지 말고 Play 프로브로, 4의 sfx 집계는 몬스터 공격 구간과 분리, 6의 이펙트 표시 1회 확인, 5의 alert 전환·복귀, 7의 Pos2 패링·저스트·그로기 별·팝업 정지). maker_clear_logs는 호출하지 말고 로그는 저장 파일을 시각·`[VRF` 표지로 거를 것. map01.map은 사용자 변경이라 커밋 대상이 아니며 Bundle은 map01 제외 58경로 `1d70bc71…75dd`를 우선 쓸 것.
