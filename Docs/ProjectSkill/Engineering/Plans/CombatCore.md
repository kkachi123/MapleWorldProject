# CombatCore — 2단계 후속 확인 계획

## 목표·상태

2026-11-19 사용자 결정 "모바일연결이나 멀티환경 테스트는 하지는 않음. 그래도 2단계 완료는 해도 될것 같음."으로 2단계를 완료했다. 현재 결과는 [2단계 Feature](../Features/2_CombatCore.md)다.

**현재 상태(2026-11-20): 후속 회차 2 종료(READY, 사용자 V11 수락). 3단계 시작 지시 대기.** 2026-11-19 사용자 지시("FU-04~22먼저 하고, 이후 3단계 진행하자")의 후속 처리는 회차 1(FU-24·03·23·26)과 회차 2(FU-17·19·12)로 모두 끝났다([후속 회차 1에서 닫은 항목](#후속-회차-1에서-닫은-항목2026-11-20), [후속 회차 2에서 닫은 항목](#후속-회차-2에서-닫은-항목2026-11-20)). 아래 표에 남은 (B)·(C)·(D) 행은 이 처리의 대상이 아니며, 각 행의 다시 볼 조건이 오면 사용자 승인으로 새 회차를 정한다. 3단계는 사용자 시작 지시로 시작한다.

이 계획은 2단계에서 끝나지 않은 것만 추적한다:

- 미실시 확인;
- 부채·남은 과제;
- 사용자 결정 대기 항목.

경계:

- **구현 승인이 아니다.** 각 항목은 표의 시점이 오고 사용자가 지시하거나 승인할 때 시작한다.
- 이 계획은 규칙·수치·입력 계약을 바꾸지 않는다.
- 항목의 원문·당시 근거는 [2단계 Plan](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)과 [CombatCore WorkRecord](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md)에 있다. 두 문서와 run(20261020-combat-core)은 2026-11-19 사용자 결정("링크 정리 후 삭제")으로 삭제했으며, 위 링크와 이 표의 원문 링크는 기준 커밋 5efe005를 가리킨다.

상태: **NOT_RUN** = 하지 않음(통과 아님) / **대기** = 조건·사용자 결정 대기.

## 미실시 확인 (NOT_RUN, PASS로 세지 않음)

| ID | 상태 | 실행 시점·확인 기준 |
| --- | --- | --- |
| CombatCore-V11(모바일·실기기 부분) | NOT_RUN(2026-11-19 사용자가 하지 않기로 함) | **시점**: 모바일 실기기 연결 때. 늦어도 7단계 헤네시스 기준 PC·모바일 검증. **기준**: [Plan §7](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) V11의 남은 부분. 예고 방향·속성 구별, 0.20초 타이밍·반격 체감, 실제 터치와 키·터치 혼합 조작, 버튼 크기·화면 잘림, HP·피해 숫자 가독성, 피격·die 연출, 음향. PC(Maker) 부분은 회차별로 수락됐다. CombatFoundation-F07의 모바일 연출도 이 행에서만 추적하며 F07은 다시 열지 않는다 |
| CombatCore-V12(실제 외부 환경 부분) | NOT_RUN(2026-11-19 사용자가 하지 않기로 함) | **시점**: 비전투 몬스터나 다른 플레이어가 같은 맵에 있는 환경이 생길 때. 4단계 Run 격리 또는 다중 접속 확인 회차. **기준**: 현재 상대 외 개체에 공격·슬로우·그로기·UI가 퍼지지 않는다. 단일 참조·교체·사망 뒤 무효 부분은 AI PASS(QA1). 검증을 위해 다중 전투 체계를 새로 만들지 않는다 |
| CombatCore-FU-01 | NOT_RUN | **시점**: 지연 있는 실접속·모바일 확인 회차. **기준**: 실접속 지연에서 Pos2 경계(±0.75, 이동 속도 12에서 약 0.0625초에 지남)의 저스트·패링 판정 위치가 화면과 맞다. 출처는 [Plan §21](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) 위험과 §22.14 NOT_RUN |
| CombatCore-FU-02 | NOT_RUN | **시점**: 맵이 늘어나는 단계(4단계). **기준**: 맵 이동 뒤 복귀·재접속 때 플레이어 최대 HP가 PlayerBaseStatData 값과 같다. 출처는 회차 B NOT_RUN([Plan §20](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)) |

CombatCore-FU-03은 2026-11-19 후속 회차 1에서 실행해 닫았다(아래 [후속 회차 1에서 닫은 항목](#후속-회차-1에서-닫은-항목2026-11-20)).

CombatFoundation-F07은 2026-11-19 사용자 "기존 수락으로 닫기"로 완료해 이 표에서 뺐다(PC Maker 기준). 상태와 근거는 [CombatFoundation](CombatFoundation.md)에서만 관리하고, 모바일·실기기 연출은 위 CombatCore-V11 행이 맡는다.

**후속 회차 2 남은 미실시(2026-11-20, eaeb032 기준, PASS로 세지 않음)**

새 ID를 붙이지 않는다. 기존 행이 맡는 것은 그 행을 따르고, 나머지는 이 표의 다시 볼 조건을 따른다. 원문은 2026-11-20 reviewer 회차 2 O-1 재리뷰 "planner 마감 때 옮길 항목" 5다.

| 항목 | 상태·근거 | 추적·다시 볼 조건 |
| --- | --- | --- |
| O-1 수정의 효과(PlayRate≠1 이펙트 클립, tester O1-T7) | NOT_RUN. 지금 이펙트 클립(`05113e9d`)은 PlayRate 1.0이라 Play로 볼 수 없어 소스 대조만 했다. `PlayEffect` 옵션 `PlayRate`가 엔진에서 클립 PlayRate와 곱해진다는 전제(`MonsterAttackMotion` 전체의 가정)도 검증하지 않았다 | `EffectClip`을 PlayRate≠1 클립으로 바꾸거나 이펙트를 새로 더할 때, 또는 `MonsterAttackMotion` 이펙트 코드를 고칠 때 |
| 자연 플레이에서 슬로우와 몬스터 이펙트가 겹치는 경우(R-2) | 경로 없음. 이펙트가 있는 패턴은 `parry.guard`(3칸 가드형)뿐이고 가드형은 JUST(슬로우의 유일한 원인)를 만들지 않는다. 다른 공격의 JUST 슬로우(2.0초 ×0.5)는 다음 공격과 겹치지 않는다. 화면은 사용자 프로브 시연으로만 수락했다 | JUST가 나는 공격에 `EffectClip`을 넣을 때, `AttackInterval`·`SlowDurationSec`를 크게 바꿀 때, 6단계에서 몬스터가 늘 때 |
| 실제 팝업(`_UIPopup:Open`) 경로의 이펙트 정지와, 서버 정지·클라이언트 정지를 실제 지연을 두고 함께 거는 조합 | NOT_RUN. 시연은 Play 메모리 프로브(`SetServerPaused`·`SetPresentationPaused`)였다 | FU-27(팝업을 실제로 여는 경로가 생기는 회차 V11), 지연 조합은 FU-01 |
| 정지 중 플레이어 공격·가드 이펙트의 화면 | NOT_RUN(일부). 시연 대상은 눈빛·먼지였다. 공격 이펙트는 coder 측정, 가드 이펙트는 같은 클라이언트 시간 배율 경로라는 판단뿐이다 | FU-27 회차 V11에서 함께 본다 |
| 시연 n=7(먼지 중 정지의 해제)·n=8(먼지 중 슬로우 2회차) | 하지 않음. 사용자 "필요 없음"(2026-11-20). 먼지 정지·먼지 슬로우는 n=3·n=4로 한 번씩 봤다 | 다시 보지 않는다 |
| 맵 이탈 단독 정리(TR11) | NOT_RUN. `OnMapLeave`가 Stop과 같은 `ClearCombatEffects`를 지나는 것은 소스로 확인했다 | 실제 맵 전환 회차([CombatFoundation-F03](CombatFoundation.md)·[CombatPause-F01](CombatPause.md)) |
| 연출 표 무효 상태의 가드 Play(TR14) | NOT_RUN. Plan이 소스 대조를 허용했고 `SetGuarding` 순서만 바뀌었다 | `SetGuarding`의 연출 경로를 다시 고칠 때 |
| 실제 키 패링 | tester는 입력 수락 지점 호출로 확인했다. 사용자 자연 플레이 V11(패링·반격 체감 동일, "모두 괜찮음")으로 수락했다 | 추적 불필요 |
| 첫 공격의 이펙트 클립 로드 시각(R-1) | 측정하지 않음(필수 아님) | 아래 부채 표 "동작 관찰"의 CombatCore-FU-30 |
| 지연 있는 실접속·모바일 | NOT_RUN | 위 CombatCore-V11(모바일)·V12·FU-01 행 |

## 부채·남은 과제 (구현 승인 아님)

원문은 [Plan §21 부채](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)·§22.13·§24.12다. 다시 볼 조건이 오면 사용자 승인으로 새 회차 범위를 정한다.

**스크립트·데이터 구조**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-04 | OrangeMushroomAttack 스크립트와 `Monster/OrangeMushroom` 폴더 이름 정리 | 6단계 몬스터 동작 일반화. 2026-11-19 (C) 유지 |
| CombatCore-FU-05 | 피격 가능 구간 선언을 패턴 데이터로 옮길지 | 6단계. 2026-11-19 (C) 유지 |
| CombatCore-FU-06 | 주황버섯(일반 몬스터)의 공격 패턴·스폰·MonsterData·MonsterStatData 행 | 6단계. 사용자가 planner 질문 절차로 정한다(2026-11-06 "6단계로 미루기"). 2026-11-19 (C) 유지 |
| CombatCore-FU-07 | 스킬별 타격 간격·프레임 지연 열 | 스킬 교체 시스템 단계. 2026-11-19 (C) 유지 |
| CombatCore-FU-08 | 묶음(1·2·3칸) 단위 비율 표 | 사용자 요청 때. 지금은 행별 Weight로 조정한다. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-29 | 2·3칸 도약 균등화 항목 정리. FU-26 방안 1-A 뒤 도약 구간(W 이후)에는 attack1·skill1 프레임이 보이지 않아, `OrangeMushroomAttack`의 `EqualizeLeapFrames` 속성·`EqualizeLeapBounds`·`CompleteMotion`의 `TickClip()` 호출·`[VRF] leap bounds`의 `equalize=` 출력·관련 주석이 화면·시각 효과 없이 남았다(2026-11-20 reviewer 판단 5). W·판정 시각에는 영향이 없다. `StartDrivenClip`·`TickClip` 자체는 windup 구동에 계속 쓰여 대상이 아니다 | 2026-11-20 (C) 추적 등록. **작업 승인 아님.** 정리하려면 사용자 승인이 필요하다(사용자가 요구하고 기본값을 수락한 조절 항목을 지우는 일이고, GameDesign §4.2 조절 항목 문구도 함께 고친다). 시점 후보: 같은 파일을 고치는 회차, 늦어도 6단계 몬스터 동작 일반화(FU-04와 함께). 후속 회차 2의 바꿀 파일에는 `OrangeMushroomAttack`이 없어 거기에 묶으려면 범위 추가 승인이 필요하다 |

**연출·소리 조절**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-09 | 효과음 음량 열 | 사용자가 음량 조정을 원할 때. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-10 | 이펙트 배율·위치 열 | 사용자가 조정을 원할 때. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-11 | 클립·이펙트 재생 배율 분리 열(예: EffectPlayRate) | 사용자가 둘을 따로 조정하길 원할 때. 지금은 MotionPlayRate 하나가 둘에 같이 쓰인다. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-13 | 접근 클립 마무리 프레임(f4) 표시와 착지 순간 정지 0. **관찰 O-2(2026-11-20 tester, a18b251)**: 착지 순간 클라이언트에 stand가 1프레임 끼었다가 복귀 jump로 이어지는 경우가 2·3칸 10회 중 1회 있었다. `CompleteMotion`의 `SetVisualClip("stand")` 뒤 같은 서버 틱에 `PerformReturnMotion`의 `SetMotionClip("jump")`가 이어지는 기존 코드다(1-A 전에도 attack1 → stand → jump 순서). 사용자 V11(2026-11-20 "모두 괜찮음")에서 **보이지 않았다**. 결함이 아니며 관찰로만 둔다. 1-A 뒤 2·3칸은 f4 대신 jump 자세로 착지한다 | 사용자가 f4가 잘리거나 착지가 어색하다고 할 때, 또는 착지 순간 stand가 끼어 보인다고 할 때(그때 O-2를 결함으로 올리고, 수정안(예: 복귀가 바로 이어질 때 stand 쓰기 생략)은 사용자 승인 대상). 착지 정지는 판정 뒤 시각을 바꾸는 사용자 결정이다. 2026-11-19 FQ-4 (가): 바꾸지 않음, 추적 유지 |
| CombatCore-FU-20 | 연출 표(PlayerActionFxData) 경고에 칸·값 넣기 | 사용자가 요청할 때만(새 요구). 2026-11-19 FQ-6 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-21 | 위 공격 버튼 아이콘을 선택한 액티브 스킬 아이콘으로 연결. 지금은 칼 아이콘 | 액티브 스킬 선택이 생기는 단계(5단계). 2026-11-19 (C) 유지 |

**동작 관찰**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-14 | 관찰 O-1(2단계 QA14). 간헐적으로 클라이언트 접근이 멈춘다. QA14 재현 0/28. **→ 2026-11-20 FU-16에 합침(planner 판단).** FU-26 진단에서 이 "가끔 멈춤"은 FU-16의 정지 1프레임(정지 뒤 다음 프레임 약 2배 이동)과 같은 현상일 가능성이 높다고 봤다. QA14가 0/28이었던 것은 당시 기준이 "정지 0.05초 이하 PASS"여서 약 0.017초 정지를 잡지 못했기 때문이다. 원인 확정은 아니다 | 따로 추적하지 않고 FU-16 행의 다시 볼 조건을 따른다. 다시 볼 조건·수정안(이동 방식)이 같아 두 행으로 둘 이유가 없다. FU-16을 처리할 때 "가끔 멈춤"이 함께 사라졌는지 확인하고, 사라지지 않으면 이 ID를 다시 연다 |
| CombatCore-FU-15 | 관찰 O-3(2단계). 구동 프레임 이벤트가 같은 ms에 2건 도착한다. 2026-11-19~20 FU-26 진단: 2·3칸 18회 모두 f1·f2·f3 이벤트가 2건씩 왔지만 화면 되돌림·Start≠End 표본은 0이었다. **FU-26의 원인으로 지지되지 않는다.** 1-A 뒤 2·3칸 도약 구간에는 서버 프레임 구동이 없다(windup f0만 구동) | 유지. 프레임 이벤트에 기대는 새 기능을 만들 때, 또는 화면 문제로 확인될 때. 2026-11-19 (C). 구동 방식 변경은 사용자 승인 대상이다 |
| CombatCore-FU-16 | 접근·복귀 이동을 서버 `OnUpdate`에서 매 틱 `SetPosition`으로 처리한다. FU-14를 합쳤다. **측정(2026-11-19~20 FU-26 진단, Maker 26.11 로컬 Play)**: 클라이언트에서 "정지 1프레임 + 다음 프레임 약 2배 이동"이 접근 0.43초 안에 2·3칸 18회 중 13회(72%), 1칸 6회 중 4회(67%) 나왔다. 2·3칸은 정지 뒤 한 프레임 이동이 최대 0.44단위다. 같은 시험에서 엔진 물리 이동(`Rigidbody.MoveVelocity`)은 0회, 틱 위치 쓰기는 `SetPosition`·`SetWorldPosition`·`MovementComponent:SetPosition` 모두 같은 정지가 났다. 2026-11-16 기록에도 같은 값이 있어 Maker 26.10/26.11과 무관하다. 속도 기반 이동은 `WalkSpeed`·`InputSpeed`를 스크립트에서 올리면 필요한 속도(2·3칸 평균 5.2~8.7단위/초)에 닿고 고속에서도 정지 0이었지만, 가속에 약 0.15초가 들고 착지 x(±0.01)·판정 시각(±0.05초) 정밀도는 시험하지 않았다(수정안 A). **1-A로 다루지 않은 사유**: 진단에서 사용자 체감("도중이 뚝 끊기는 느낌")의 주원인은 클립 공중 높이 계단으로 보고 이 정지 프레임은 부원인("가끔")으로 봤다. 사용자는 이동 방식 변경안(A~D)을 고르지 않고 클립 쪽 1-A를 골랐다. 이동 방식 변경은 Plan의 사용자 승인 대상이고, 1-A는 수평 이동·위치 쓰기를 바꾸지 않았으므로 이 정지 프레임은 그대로 남아 있다(1-A 뒤 클라이언트 표본 4회 0건은 표본이 적어 개선 근거로 쓰지 않음) | (C) 유지. 다시 볼 조건: (1) 1-A 뒤에도 사용자가 "가끔 툭 건너뜀/멈춤"을 보고할 때(2026-11-20 V11에서는 "모두 괜찮음"으로 보고 없음), (2) 지연 있는 실접속·모바일 회차(늦어도 7단계), (3) 6단계 몬스터 동작 일반화로 이동 구조를 다시 정할 때. 앞당기려면 (B)로 바꿔 사용자가 이동 방식을 정한다. 수정안·위험은 [WorkRecord FU-26 진단 7절](../WorkRecords/CombatCoreWorkRecord.md)이 원문이다 |
| CombatCore-FU-28 | 전투 중단·공격 취소 뒤 몬스터 표시·위치 정리. **관찰 O-1(2026-11-20 tester, a18b251)**: 접근(jump)·windup 중 공격이 취소되면 클립을 stand로 되돌리는 경로가 없어 jump(또는 attack1·skill1) 클립이 남고, 몬스터는 집으로 돌아가지 않고 그 자리에 선다. `CancelMotion`은 HIT·DEAD 위에 stand를 쓰지 않으려는 의도로 클립을 건드리지 않는 기존 구조다(c6422cd에서도 attack1이 남음, 1-A로 바뀐 것은 남는 그림뿐). 실제 플레이에서는 플레이어 사망·정지 중단(`AbortCombat`)·맵 이탈 때만 생긴다. **관찰 O-3(같은 시험, 원인 미확정)**: 플레이어 HP를 보충하지 않은 자연 공격 중 1칸 공격이 0.52초에 ATTACK → IDLE로 끝나며 x 0.000에 남았고 5초 뒤 x 3.000·IDLE·플레이어 HP 100/100으로 돌아와 있었다. 플레이어 사망 → `AbortCombat` → `CancelPendingAttack` → `CancelMotion` 경로(O-1과 같은 구조)로 보이나 로그로 확정하지 못했다. 결함 아님(reviewer 판단 3). **관찰(2026-11-20 회차 2 tester O-3, d8c61db)**: 공격이 취소돼도 이미 재생을 시작한 눈빛·먼지 이펙트는 화면에서 끝까지 나온다. `ClearEffects`는 추적만 끊는다. FQ-3 (가) "기존 이펙트 유지"와 같은 기존 동작이며 결함이 아니다(회차 2 reviewer 판단 4) | 2026-11-20 (C) 추적 등록. **작업 승인 아님.** 다시 볼 조건: 사용자가 플레이어 사망·정지 중단 뒤 몬스터 모습·위치가 어색하다고 보고할 때, 또는 3단계 이후 전투 종료·재시작 흐름을 만들 때(3단계 Plan 작성 때 후보 검토). O-3 재현 조건(tester): 자연 공격 중 플레이어 HP를 보충하지 않고, 플레이어 사망·부활 시각, 몬스터 상태·구간·x, `[VRF] CombatPause abort`를 같은 시계로 기록한다 |
| CombatCore-FU-30 | 이펙트 클립 첫 동기 로드(2026-11-20 reviewer 회차 2 관찰 R-1, 결함 아님·낮음). 몬스터 엔티티별 첫 눈빛 때 `MonsterAttackMotion`의 `TrackEffect` → `GetRuidTimeline` → `LoadAnimationClipAndWait`가 서버에서 동기로 돈다. 접근 클립은 스폰 때 `MonsterManager`(138행)가 미리 읽지만 이펙트 클립은 미리 읽지 않아 `GetClipTimeline` 주석("진행 중에는 읽지 않는다")과 다르다. `Monster_Attack` 58·59행 순서상 로드 시간만큼 `attackDue`(판정)와 추적 시작이 늦어질 수 있다. 측정된 눈빛→먼지 1.576·1.588초(예고 1.571초)는 ±0.05 안이지만 그 표본이 첫 공격인지는 확인하지 않았다. 고치려면 회차 2 범위 밖인 `MonsterManager`(이펙트 클립 미리 읽기)를 바꿔야 한다 | 2026-11-20 (C) 추적 등록. **작업 승인 아님.** 다시 볼 조건: (1) Play 시작 뒤 첫 3칸 공격의 눈빛→먼지 전투 시계 차가 예고 1.571초보다 눈에 띄게 길 때, (2) 사용자가 첫 공격 지연을 보고할 때, (3) 늦어도 6단계 몬스터 동작 일반화(FU-04·FU-29와 함께, 리뷰 제안). 확인 방법: Play 시작 뒤 첫 3칸 공격의 눈빛·먼지 `clock` 차를 기록한다 |

**문서·운영**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-18 | 화면 표시 확인이 완료 기준에 있으면, 그 확인용 스크린샷의 허용 범위(목적·대략 장수)를 완료 기준에 함께 적는다 | 다음 Plan 작성 때(planner, 3단계 Plan 포함). 2026-11-19 (D), 후속 처리 계획 회차별 완료 기준에 먼저 적용 |
| CombatCore-FU-22 | 범위 밖 관찰. 플레이어 쪽 피해에 남은 HP 상한이 없고, 사망 직후 플레이어 HP 문자가 음수로 보일 수 있다(화면 미관찰) | 3단계 Plan 작성 때 후보로 검토(플레이어 HP 0 종료·승패). 2026-11-19 (D) |
| CombatCore-FU-27 | 팝업·토스트를 게임 안에서 여는 경로가 없다. RootDesk `.mlua`에서 `_UIPopup:Open`·`_UIToast:ShowMessage`를 부르는 곳이 0이다(2026-11-19 planner Grep). 그래서 사용자가 모양·실제 버튼 닫기를 볼 수 없고, 회차 1 V11 4번은 NOT_RUN이다. [CombatPause-F02](CombatPause.md)의 팝업·토스트 화면 확인도 같은 이유로 지금은 할 수 없다. AI 근거는 프로브 호출(Enable·정지·재개)뿐이다. 새 기능은 만들지 않는다. **2026-11-20 후속 회차 2(FU-12)**: 팝업 정지 중 이펙트 모습도 같은 이유로 게임 안에서 볼 수 없어, 사용자가 고른 Play 메모리 프로브 시연(`SetServerPaused`·`SetPresentationPaused`)으로만 보고 수락했다("모두 괜찮음"). 실제 `_UIPopup:Open` 경로의 이펙트 정지 화면은 이 행에 남는다 | 3단계 Plan 작성 때 후보로 검토. 결과·정산 등에서 팝업·토스트를 실제로 여는 경로가 생기면, 그 회차 V11에 모양·버튼 닫기 확인과 **팝업 정지 중 이펙트(눈빛·먼지·플레이어 공격·가드) 정지 모습**을 넣는다. 그 전에는 V11 목록에 넣지 않는다. 2026-11-19 (D) |

## 사용자 결정 대기

| 항목 | 내용 | 원문 |
| --- | --- | --- |
| 3단계 시작 | 2단계 완료 뒤 다음 로드맵 단계. 2026-11-19 사용자 지시로 아래 후속 처리를 먼저 끝낸 뒤 진행한다. 후속 처리는 2026-11-20 회차 2 종료로 끝났다. **사용자 시작 지시 대기** | [로드맵](../DevelopmentRoadmap.md) |
| CombatCore-FU-25 머쉬맘 수치 | 머쉬맘 수치 조절. 사용자가 CSV에서 직접 조절하며 AI 작업이 아니다 | [Plan §21 부채](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) |
| 부채 처리 시점 | 위 FU-04~FU-22를 언제 다룰지. → 2026-11-19 사용자 결정: 3단계 전에 먼저 처리. 항목별 분류·회차는 [후속 처리 계획](#후속-처리-계획2026-11-19). **후속 회차 2 종료(2026-11-20, reviewer READY, 사용자 V11 수락). 이 run의 후속 처리는 모두 끝났고, 3단계 시작 지시 대기다.** 회차 1(FU-24·03·23·26)과 회차 2(FU-17·19·12)에서 (A)와 결정된 항목을 처리했다. 나머지 (B)·(C)·(D) 행은 이 문서의 표에서 계속 추적하며, 앞당기려면 사용자가 항목과 회차를 정한다 | 이 문서 |

FU-23(원장 문구)·FU-24(기존 파일 이동)는 후속 회차 1에서 처리해 이 표에서 뺐다(아래 [후속 회차 1에서 닫은 항목](#후속-회차-1에서-닫은-항목2026-11-20)).

에셋 목록의 최종 위치(8단계 전 결정)는 [로드맵 8단계 시작 전 결정 사항](../DevelopmentRoadmap.md#8-콘텐츠-데이터-제작)에서 관리한다.

## 후속 회차 1에서 닫은 항목(2026-11-20)

근거 흐름: coder → 메인 `[code]` 로컬 커밋 → 같은 버전 tester → reviewer → 사용자 V11. 상세는 [WorkRecord](../WorkRecords/CombatCoreWorkRecord.md), 현재 결과는 [2단계 Feature](../Features/2_CombatCore.md)다. 대상 버전 c6422cd(FU-24·03·23)·a18b251(FU-26), 둘 다 회차 종료 커밋 `[CombatCore][review]` b071b5c와 함께 2026-11-20 push했다.

| ID | 결과 | 남은 것·추적 |
| --- | --- | --- |
| CombatCore-FU-24 | 완료. 22파일(DataSet 6쌍 → `DataSet/`, 로더 3쌍 → `Catalog/`, UIPopup·UIToast → `UI/`)을 바이트 그대로 옮겼다(git R100). 빈 `@Assist`·`Player/@Assist` 폴더는 사용자가 Maker에서 지웠다(`.directory` 7개 삭제, `Catalog.directory`는 Maker 생성). reviewer 충족, 사용자 V11 1(작업 공간 창) 수락 | 없음. 커밋 구성 예외 2건은 회차 1 위험 4·완료 기준 8에 적었다 |
| CombatCore-FU-03 | 완료. 임시 헤더(`EffectSoundX`)에서 경고 정확히 1회·`guard fx off`·가드와 전투 계속, 원 바이트 복원(SHA-256 일치)·다음 Play 정상 로드(coder 실행, tester 로그·해시 대조). reviewer 충족 | tester 독립 재현은 Plan 설계대로 NOT_RUN(제품 임시 변경 금지) |
| CombatCore-FU-23 | 완료. 원장 주석 1줄과 23·24행 현재 상태 문구, 30행 DATA-02 경로(`Catalog/CombatRuleCatalog`)를 고쳤다(+5/−3). ID·과거 기록 절·OPEN 상태는 그대로. reviewer 충족 | 없음 |
| CombatCore-FU-26 | 완료. 사용자 승인 방안 1-A(2·3칸 도약 시작 W에서 jump 클립으로 한 번 전환, 높이 0.8 포물선)로 클립 공중 높이 계단을 없앴다. tester FAIL 0, reviewer AI 1~7 충족·결함 0, 사용자 V11 "모두 괜찮음"(2026-11-20) | 부원인 정지 프레임은 FU-16(FU-14 합침)으로 남는다. 관찰 O-1·O-3은 FU-28, O-2는 FU-13, 균등화 잔존은 FU-29. [FU-26 절](#후속-회차-1-추가--combatcore-fu-26-머쉬맘-23칸-점프-초반-공중-끊김-2026-11-19) |

사용자 V11(2026-11-19) 4번 팝업·토스트 모양은 게임 안 호출 경로가 없어 NOT_RUN이며 FU-27로 추적한다.

## 후속 회차 2에서 닫은 항목(2026-11-20)

근거 흐름: coder → 메인 `[code]` d8c61db → 같은 버전 tester(FAIL 0) → reviewer WAITING(AI 1~5 충족, 새 코드 잠재 결함 O-1 지적) → 사용자 결정(O-1 이번에 고침, FU-12 화면은 "시연 보고 확인") → coder O-1 수정 → 메인 `[code]` eaeb032 → 같은 버전 tester O-1 회귀(FAIL 0)·사용자 시연 → reviewer READY → 사용자 V11 수락. 상세는 [WorkRecord](../WorkRecords/CombatCoreWorkRecord.md), 현재 결과는 [2단계 Feature](../Features/2_CombatCore.md)다.

- 대상 버전: d8c61db(트리 `3940b24f378ecf9e1fdcd9bb99e9463ef46edd17`, 제품 `.mlua` 4개) + O-1 수정 eaeb032(`eaeb03230019fe929fb5423cb8cbc8b3dc857bbd`, 트리 `fe15c8744a1c91931a89d272b1f3bfa895825a75`, `MonsterAttackMotion.mlua` blob `8d22ddda9183c257053c1fce14bcc740f3a0a4d9`). 둘 다 회차 종료 `[CombatCore][review]` 커밋과 함께 push한다. 커밋 제외: `map/map01.map`(SHA-256 `22b6acbf…987e`, 범위 밖 사용자 변경).
- 사용자 V11(2026-11-20): 자연 플레이(기본 공격 10타 피해 숫자와 HP 감소, 가드 시작 이펙트·소리 1회, 패링·반격 체감 동일) "모두 괜찮음". FU-12 화면은 Play 메모리 프로브 시연 6회(정지 n=1·3·5, 슬로우 n=2·4·6, 눈빛·먼지 × 정지·슬로우 각 1회 이상) "모두 괜찮음"(끊김·처음부터 재시작·겹침 없음). n=7·8 재시연은 "필요 없음". 시연 중 Play 종료는 사용자 Stop이었다("내가 Stop함", 제품 결함 아님).

| ID | 결과 | 남은 것·추적 |
| --- | --- | --- |
| CombatCore-FU-17 | 완료. `PlayerCombatComponent`의 쓰기 전용 `self._T.resolveIndex = index` 1줄을 지웠다(Grep `resolveIndex` 0곳). 동작은 같다(V02 회귀: HitEvent 합 = HP 감소, ×2.2 반격 1회, 화면 피해 숫자는 사용자 V11). reviewer 충족 | 없음 |
| CombatCore-FU-19 | 완료. `SetGuarding`이 기록 전 값으로 시작을 판단하고 `isGuarding` 기록을 연출 호출 앞에 둔다. 정상 경로 결과는 같다(실제 ↓ 키 시작·연출·효과음 각 1회, 잔여 40%, 패링 2회). 블록 안 오류 때도 상태가 기록되도록 나아졌다. reviewer 충족 | 표 무효 가드 Play(TR14)는 소스 대조로 판단(위 "후속 회차 2 남은 미실시") |
| CombatCore-FU-12 | 완료((가) 기존 이펙트 유지). **정지**: 클라이언트 시간 배율 0(`SetClientTimeScale(0)`)이 이미 이펙트를 멈춘 프레임으로 두고 재개 때 이어 재생함을 측정해, 정지 코드를 더하지 않았다(`CombatPauseComponent` 변경 0). **슬로우**: `MonsterAttackMotion`이 재생 중 몬스터 이펙트(눈빛·먼지)를 추적하고 배율이 바뀌면 지금 프레임부터 새 배율로 다시 낸다. 프레임 계산에는 클립 PlayRate를 포함한다(O-1, eaeb032). 끝난 이펙트는 다시 내지 않고, 사망·대결 종료·맵 이탈·Stop 때 추적을 정리한다. 슬로우는 몬스터만 받으므로 플레이어 공격·가드 이펙트는 정지만 대상이다(GameDesign §4.2). 한계: 이어 재생은 프레임 단위라 배율이 바뀔 때마다 끝이 최대 한 프레임 늦어질 수 있다. tester FAIL 0, reviewer READY, 사용자 프로브 시연 수락 | 지금 데이터에는 자연 발생 경로가 없다(R-2). 남은 미실시·다시 볼 조건은 위 "후속 회차 2 남은 미실시". 첫 로드 관찰 R-1은 FU-30, 취소 뒤 이펙트 끝까지 재생(O-3)은 FU-28 관찰 |

관찰 분류(회차 2 tester·reviewer): O-1(클립 PlayRate 미반영)은 이번 회차에서 고쳤다. O-2(끝난 항목이 다음 재생까지 목록에 남음, 최대 1~2개)는 설계이며 추적하지 않는다. O-3은 FU-28 관찰, O-4(Hp=0인데 `IsDead()` false)는 기존 FU-22, R-1은 FU-30, R-2는 아래 회차 2 절 "사용자 V11"과 위 미실시 표다.

## 연결된 외부 추적 ID

이 계획에서 상태를 바꾸지 않는다. 2단계 완료나 V11 회차 수락만으로 완료 처리하지 않는다. 사용자가 명시적으로 결정한 항목만 원 계획에서 상태를 바꾼다.

- [CombatFoundation](CombatFoundation.md): F01 재시작 경고, F02 배포 개발 도구 차단, F03 실제 맵 전환, F04 PC·모바일 UI, F05 성능 실측. F07 피해·표시 일치는 2026-11-19 사용자 결정 "기존 수락으로 닫기"로 완료(PC Maker 기준, 모바일은 위 CombatCore-V11).
- [CombatPause](CombatPause.md): F01 실제 맵 전환, F02 PC·모바일 화면·음향.

## 후속 처리 계획(2026-11-19)

### 근거·상태

- 사용자 지시(2026-11-19, 원문): "castleenemy 문구 정리(FU-23), DataSet 6종 이관(FU-24), 부채 처리(FU-04~22먼저 하고, 이후 3단계 진행하자".
- 이 지시는 **순서 승인**이다. 2단계 후속 항목을 3단계보다 먼저 처리한다. 3단계 Plan은 이 처리가 끝난 뒤 사용자 시작 지시로 쓴다.
- 사용자 답(2026-11-19, 원문): FQ-1 "파일 너가 이동시키고 내가 maker에 동기화 할게", FQ-2 "회차 1에 함께", FQ-3 "기존 이펙트 유지 방식", FQ-4~7 "모두 추천안대로". 반영은 [4. 사용자 질문과 답](#4-사용자-질문과-답)에 있다.
- **구현 승인 상태(2026-11-19 확정)**
  - 후속 회차 1: **구현 승인.** 근거는 위 순서 지시("먼저 하고")와 FQ-1·FQ-2·FQ-7 답이다. 범위는 아래 회차 1 절이 전부다.
    - 2026-11-19 범위 확장: 사용자 V11 중 보고한 결함 FU-26(머쉬맘 2·3칸 점프 초반 공중 끊김)을 사용자 결정 "회차 1에서 처리"로 더했다. 처음에는 진단만 승인했고, 2026-11-20 사용자가 진단 결과를 보고 방안 1-A를 승인했다([FU-26 절](#후속-회차-1-추가--combatcore-fu-26-머쉬맘-23칸-점프-초반-공중-끊김-2026-11-19)).
    - **2026-11-20 완료.** FU-24·FU-03·FU-23·FU-26 모두 reviewer 충족(결함 0)과 사용자 V11 수락으로 닫았다([후속 회차 1에서 닫은 항목](#후속-회차-1에서-닫은-항목2026-11-20)). 회차 종료 커밋 `[CombatCore][review]` b071b5c는 2026-11-20 push됐다.
  - 후속 회차 2: 범위 확정(FQ-3 (가)). **구현 승인(2026-11-20 사용자 "회차 2 시작").** 시작 조건 1~4는 모두 충족했고 planner 범위 확인 결과는 READY_FOR_CODE다(기준 a593e2b). 상세는 [회차 2 절](#후속-회차-2--플레이어-공격가드-코드-정리--fu-12-이펙트-정지슬로우-추종가-방식)의 "시작 조건"과 "범위 확인(2026-11-20 planner)"이다.
    - 2026-11-20 범위 안 추가: reviewer가 지적한 새 코드 잠재 결함 O-1(`GetEffectFrame` 클립 PlayRate 미반영)을 사용자 결정 "이번에 고침"으로 같은 승인 범위에서 고쳤다(eaeb032).
    - **2026-11-20 완료.** FU-17·FU-19·FU-12 모두 tester FAIL 0, reviewer READY, 사용자 V11 수락(자연 플레이 + FU-12 프로브 시연)으로 닫았다([후속 회차 2에서 닫은 항목](#후속-회차-2에서-닫은-항목2026-11-20)). 이로써 이 후속 처리의 회차는 모두 끝났다.
  - 후속 회차 3: 회차 1에 합쳤다(FQ-2).
  - 후속 회차 4: 열지 않는다(FQ-4·FQ-5·FQ-6 모두 (가)).
- run: `.pipeline/20261119-combatcore-followup/run.md`. 기준 버전 16d70b3(회차 1), a593e2b(회차 2).
- WorkRecord: [CombatCoreWorkRecord](../WorkRecords/CombatCoreWorkRecord.md). 후속 처리 회차 기록이며 2단계 원본(기준 커밋 5efe005)과 다른 새 기록이다.
- 대상 맵은 map01이고 `TileMapMode` 0(MapleTile)이다(근거: [2단계 Feature](../Features/2_CombatCore.md), 2단계 WorkRecord의 MapBuilder 조회). 이 처리는 맵·Body·규칙·수치·입력 계약을 바꾸지 않는다.
- 작업 트리의 `map/map01.map` 변경은 범위 밖이다. 사용자가 "그대로 둠"으로 정했고, 어느 회차 커밋에도 섞지 않는다.
  - 해시 기준: 회차 시작 `3e60c21d…c2094`. 2026-11-19 2차 동기화 때 Maker 26.11이 CoreVersion 1줄을 다시 저장해 바뀌었고, 사용자 결정으로 새 기준은 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`다(run 2026-11-19 기록). 이후 회차 1의 모든 단계(FU-26 포함)는 이 값을 기준으로 본다.

분류:

- **(A)** 지금 처리 가능: 새 규칙·수치 결정 없이 범위와 완료 기준을 정할 수 있다.
- **(B)** 사용자 결정 필요: 값·열 설계·보이는 결과를 바꾸는 선택이 있다. 질문으로만 남긴다.
- **(C)** 지금은 불가 또는 비효율: 뒤 단계 시스템이 없거나 재현 조건이 없다.
- **(D)** 3단계 Plan 작성 때 처리한다.

### 1. 분류

| ID | 분류 | 이유 | 처리 위치·남길 시점 |
| --- | --- | --- | --- |
| FU-03 | (A) | 기존 경고 줄을 실제로 실행해 보는 확인이다. 규칙 변경이 없다 | 후속 회차 1(이동 회귀와 함께). 2026-11-20 완료 |
| FU-04 | (C) | 새 이름·폴더는 6단계 동작 유형 일반화(FileStructure §3 `Monster/Motions/{TypeName}/`)에서 정해진다. 지금 바꾸면 모델의 script 구성요소까지 두 번 바꾼다 | 6단계 몬스터 동작 일반화 |
| FU-05 | (C) | 새 열 설계가 필요하고, 6단계 동작 일반화와 같은 결정이다 | 6단계 |
| FU-06 | (C) | 사용자가 2026-11-06 "6단계로 미루기"로 정했다. 몬스터 공격 구성 질문 절차가 필요하다 | 6단계 |
| FU-07 | (C) | 두 번째 스킬이 없어 열의 쓰임을 검증할 수 없다 | 스킬 교체 시스템(5단계 액티브 스킬) |
| FU-08 | (B) | 새 표 설계다. 지금은 행별 Weight와 로드 로그 %로 조정한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-09 | (B) | 새 열과 빈 값 기본값을 정해야 한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-10 | (B) | 새 열과 빈 값 기본값을 정해야 한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-11 | (B) | 새 열을 정해야 하고, 지금의 MotionPlayRate 하나의 뜻이 바뀐다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-12 | (B) → 결정됨 | 정지·슬로우 추종 자체는 기존 규칙(GameDesign §4.3 "전투 연출을 모두 정지", §4.2 "행동·모션 진행 ×0.5")과 맞다. 엔진 `_EffectService`에는 재생 중 이펙트를 멈추거나 배율을 바꾸는 API가 없다(`PlayEffect`·`PlayEffectAttached`·`RemoveEffect`만 있음). 사용자가 FQ-3에서 (가) 기존 이펙트 유지 방식을 골랐다 | 후속 회차 2. 2026-11-20 완료 |
| FU-13 | (B) | 착지 정지는 판정 뒤 시각을 바꾼다(2단계 Plan §22.13 "사용자 결정"). f4 잘림은 V11에서 수락됐다. 2026-11-20 관찰 O-2(착지 stand 1프레임)를 이 행에 붙였다(사용자에게 보이지 않음) | FQ-4 (가): 바꾸지 않음, 추적 유지 |
| FU-14 | (C) → FU-16에 합침 | 재현 0/28이고 재현 조건이 없었다. 2026-11-20 FU-26 진단에서 FU-16 정지 1프레임과 같은 현상일 가능성이 높다고 봐 합쳤다(원인 확정 아님) | FU-16을 따른다 |
| FU-15 | (C) | 보이는 문제가 측정되지 않았다. 없애려면 구동 방식을 바꾸고 D-Q6을 다시 증명해야 한다. 2026-11-20 FU-26 진단에서도 원인으로 지지되지 않았다 | 프레임 이벤트에 기대는 새 기능을 만들 때(6단계 동작 일반화 후보) |
| FU-16 | (C) | 속도 기반 이동은 시각·착지 x·D-Q6 재증명이 필요한 새 결정이다. 6단계 일반화가 이동 구조를 다시 정하므로 그때 한 번에 보는 것이 효율적이다. 2026-11-20 FU-26 진단으로 정지 1프레임을 측정 확정했지만 사용자는 1-A(클립 쪽)를 골랐다 | 6단계 몬스터 동작 일반화, 또는 사용자 "가끔 툭 건너뜀" 보고·실접속·모바일 회차. 앞당기려면 (B)로 바꿔 사용자가 정한다 |
| FU-17 | (A) | 기록만 하고 읽지 않는 필드 1줄 제거다(`PlayerCombatComponent` 268행, 읽는 곳 0 Grep 확인). 동작이 같아야 한다 | 후속 회차 2. 2026-11-20 완료 |
| FU-18 | (D) | 다음 Plan 작성 원칙이다. **이 절의 회차별 완료 기준에 먼저 적용했다**(각 회차 "스크린샷" 줄) | 3단계 Plan 작성 때도 적용 |
| FU-19 | (A) | `SetGuarding`의 상태 기록을 연출 호출 앞으로 옮기는 순서 정리다. 가드 판정·연출 1회 결과가 같아야 한다 | 후속 회차 2. 2026-11-20 완료 |
| FU-20 | (B) | 경고 문구에 칸·값을 넣는 것은 새 요구다(2단계 Plan §24.12) | FQ-6 (가): 하지 않음, 추적 유지 |
| FU-21 | (C) | 액티브 스킬 선택 시스템이 아직 없다 | 5단계 |
| FU-22 | (D) | 플레이어 HP 0 종료·승패는 3단계 범위다(GameDesign §4.2 끝) | 3단계 Plan 작성 때 후보로 검토 |
| FU-23 | (A) | 문서 문구 정리다. 원장 규칙(maplestory-skill-maker execution-core "Required progress ledger")에 낡은 내용 정리 조항이 없어 범위를 이 계획이 정한다. 사용자가 FQ-7에서 기본안을 골랐다 | 후속 회차 1. 2026-11-20 완료 |
| FU-24 | (A) | DataSet 6종과 그 밖의 기존 파일(로더 3개·UI 2개) 이동, `@Assist` 계열 정리다. 대상·위치는 사용자가 승인한 [FileStructure §5](../FileStructure.md)이고, 참조는 경로가 아니라 이름·키다(아래 조사). 이동은 AI, Maker 동기화는 사용자다(FQ-1). 그 밖의 이동도 회차 1에 넣는다(FQ-2) | 후속 회차 1. 2026-11-20 완료 |
| FU-26 | 결함(2026-11-19 사용자 보고) | 머쉬맘 2·3칸 점프 초반 공중 끊김. 진단 → 사용자 승인(1-A) → 수정 | 후속 회차 1(사용자 "회차 1에서 처리"). 2026-11-20 완료 |
| FU-27 | (D) | 팝업·토스트를 게임 안에서 여는 경로가 없어 사용자가 모양을 볼 수 없다. 새 기능은 만들지 않는다 | 3단계 Plan 작성 때 후보 검토 |
| FU-28 | (C) | 2026-11-20 tester 관찰 O-1·O-3(a18b251), 회차 2 tester 관찰 O-3(취소 뒤 이펙트 끝까지 재생, 기존 동작) 추가. 기존 취소 구조의 표시 공백이고 실제 플레이에서는 플레이어 사망·정지 중단·맵 이탈 때만 생긴다. 전투 종료·재시작 흐름이 없어 지금 고칠 기준이 없다 | 사용자 보고 또는 3단계 이후 전투 종료·재시작 흐름(3단계 Plan 작성 때 후보 검토) |
| FU-29 | (C) | 2026-11-20 reviewer 판단 5. 1-A 뒤 화면 효과가 없는 조절 항목 잔존 코드다. 지우는 것은 사용자가 수락한 조절 항목을 없애는 일이라 사용자 승인 대상이다 | 같은 파일을 고치는 회차 또는 6단계 몬스터 동작 일반화(FU-04와 함께). 작업 승인 아님 |
| FU-30 | (C) | 2026-11-20 reviewer 회차 2 관찰 R-1(이펙트 클립 첫 동기 로드). 측정된 판정 시각은 허용 범위 안이고, 고치려면 회차 2 범위 밖 `MonsterManager`를 바꿔야 한다. 6단계에서 몬스터 클립 미리 읽기를 일반화할 때 함께 보는 것이 덜 고친다 | 첫 공격 지연 측정·보고 때, 늦어도 6단계 몬스터 동작 일반화(FU-04·FU-29와 함께). 작업 승인 아님 |

이 처리 범위 밖: FU-01·FU-02·V11·V12(조건 그대로)와 FU-25(사용자가 CSV에서 직접 조절, AI 작업 아님).

### 2. FU-24 영향 조사 (2026-11-19 planner, 소스 읽기)

**DataSet 로더·이름**

- 표를 읽는 곳은 `_DataService:GetTable("{이름}")` 8곳뿐이고, 경로 문자열은 없다.
  - MonsterManager → MonsterData.
  - Player/@Assist/Skill/PlayerSkillEffectTable → AttackSkillData.
  - Player/@Assist/Stat/PlayerBaseStatCatalog → PlayerBaseStatData.
  - Combat/CombatRuleCatalog → CombatRuleData·MonsterAttackPatternData·MonsterStatData·MonsterSoundData·PlayerActionFxData.
- 그래서 이동해도 `.mlua`·`.codeblock`은 고치지 않는다.
- 6종 모두 파일 이름 = `ContentProto.Json.name` = 조회 이름이다.

**DataSet 래퍼 현재 값(회차 B 형식)**

- 6종 모두 같은 래퍼 형식이고 `CoreVersion` 26.10.0.0이다.
- serveronly:
  - true(UseService 1): CombatRuleData·MonsterAttackPatternData·MonsterStatData.
  - false(UseService 0): AttackSkillData·MonsterData·PlayerBaseStatData. PlayerBaseStatData는 서버·클라이언트 양쪽에서 읽는다.
- CSV는 6종 모두 UTF-8(BOM 있음)이다.
- 이동은 바이트를 그대로 옮긴다. id·EntryKey·name·serveronly·UseService·CoreVersion을 고치지 않는다(FileStructure §2: 이미 만든 파일의 CoreVersion은 고치지 않음).

**D-Q1(AI 수동 작성)과의 관계**

- D-Q1은 새 표를 만드는 절차다. 이 회차는 새 래퍼를 만들지 않는다.
- 이동 뒤 인식에 실패해도 다시 만들지 않고 멈춘다. 새로 만들면 새 id가 생겨 Maker의 옛 항목과 같은 이름 표가 둘이 될 수 있다.

**스크립트 짝 5개(2026-11-19 FQ-2 뒤 추가 조사)**

- 대상: CombatRuleCatalog·PlayerSkillEffectTable·PlayerBaseStatCatalog·UIPopup·UIToast. 5개 모두 `@Logic`(`script {이름} extends Logic`)이다.
- 다른 스크립트는 `_{이름}`으로 부른다(예: `_CombatRuleCatalog`). 스크립트 이름 기준이라 위치와 무관하다. PlayerBaseStatCatalog가 `_CombatRuleCatalog:ReadRows`를 부르는 것도 이름 호출이다.
- 모델·맵·UI 참조: `.model`·`.map`·`.ui`·`.gamelogic`·`.config`·`.stateset`에서 5개 이름과 `.codeblock` Id가 나오는 곳은 0이다(Grep). 어느 모델의 script 구성요소로도 붙어 있지 않다. 그래서 모델·맵·UI는 고치지 않는다.
- `.codeblock`에는 경로 칸이 없다. EntryKey `codeblock://{Id}`와 `ContentProto.Json`의 Id·Name만 있다. 현재 Id 앞 8자리: UIToast 63fe07f0, UIPopup 15873444, CombatRuleCatalog 044094c4, PlayerSkillEffectTable fb69477d, PlayerBaseStatCatalog 3f5e02b6.
- UIToast·UIPopup이 쓰는 UI 엔티티 참조(UUID 기본값)는 `.mlua` 안에 있어 이동해도 같다.
- 소스로 판단할 수 없는 위험: Maker가 옮긴 `.codeblock`을 같은 항목으로 보는지다. 다른 위치에 새 `.codeblock`(새 Id)을 만들거나 옛 위치 항목을 남기면 같은 이름 스크립트가 둘이 된다. 그래서 1차 동기화로 시험하고 중단 조건에 넣는다.

**폴더 메타데이터(git 추적 파일 기준)**

- `.directory`에는 `entry_id`·`name`만 있고 부모 경로 칸이 없다. 폴더 소속은 실제 디스크 위치로 정해진다.
- 있음:
  - `MyDesk/@Assist.directory`;
  - `@Assist/` 안의 `DataSet.directory`·`RangeGizmo.directory`;
  - `Player/@Assist.directory`;
  - `Player/@Assist/` 안의 `Skill.directory`·`Stat.directory`·`AttackRange.directory`;
  - `DataSet.directory`·`UI.directory`(이동 대상 폴더).
- 없음: `Catalog.directory`. 새 폴더 `Catalog/`는 coder가 만들고, 메타데이터는 사용자 동기화가 만든다.
- `@Assist`·`Player/@Assist` 폴더 안에는 `.directory`가 있다. 그래서 실제 폴더를 AI가 지우면 `.directory`를 손으로 지우는 것이 된다(FileStructure §2·§7 금지). 이 두 폴더는 사용자가 Maker 작업 공간에서 지운다(아래 2차 동기화).

**위험**

1. **Maker 재인식.** Maker가 이동을 같은 항목으로 보지 않으면 옛 항목이 남거나 같은 이름 표·스크립트가 둘이 될 수 있다. 그러면 GetTable 결과가 nil이거나 모호하고, 스크립트는 build 오류가 날 수 있다. 선례는 회차 C 중단 조건 3이다: 키를 바꾸며 같은 경로에 다시 쓴 뒤 옛 항목이 남았고, 사용자 월드 재로드로 풀렸다.
2. **Maker 재저장.** Maker가 이동한 래퍼나 `.codeblock`을 다시 저장할 수 있다(예: CoreVersion 26.11.0.0). 의미 차이가 없으면 기록만 한다. id·EntryKey·name·serveronly, `.codeblock` Id·Name이 바뀌면 멈춘다.
3. **빈 폴더 `.directory` 잔존.** 사용자가 Maker에서 폴더를 지운 결과를 기록한다. 지우지 않으면 남은 일로 추적한다.
4. **범위 밖 재저장.** 동기화가 다른 파일을 다시 저장하면 기록하고 이 회차 커밋에 섞지 않는다(FileStructure §7).
   - **예외(2026-11-19 사용자 결정, 리뷰 선택지 (가)):** `[code]` c6422cd에 들어간 `RootDesk/MyDesk.directory`·`RootDesk/MyDesk/Player.directory`(Maker 26.11 재저장, `CoreVersion 26.10.0.0→26.11.0.0` 1줄씩)는 사용자 답 "하나의 커밋으로"에 따라 커밋을 나누지 않고 그대로 둔다. 이력 재작성은 하지 않는다. 이 두 파일 말고 같은 성격의 재저장(`Global/common.gamelogic`·`ui` 4개)은 [ops] bb3ec01로 분리됐고, `map/map01.map`은 계속 커밋에서 뺀다.
   - **예외 2(2026-11-20 사용자 결정 "회차 커밋에 포함", 리뷰 선택지 (나)):** FU-26 진단 Play 중(2026-11-19 23:03:04) Maker 26.11이 다시 저장한 `RootDesk/MyDesk/DataSet/PlayerActionFxData.userdataset`(`CoreVersion 26.10.0.0→26.11.0.0` 1줄, AI가 직접 쓰지 않음)은 따로 [ops]로 나누지 않고 메인이 회차 종료 `[CombatCore][review]` 커밋에 넣는다. 그때까지 c6422cd·a18b251 어느 쪽에도 들어 있지 않다(작업 트리 미커밋, SHA-256 `c4a19587…fd62`). 예외 1과 같이 다음 회차의 선례로 쓰지 않는다.

### 3. 회차 계획

순서: **후속 회차 1 → 2**. 회차 3은 회차 1에 합쳤고(FQ-2), 회차 4는 열지 않는다(FQ-4~6). 회차마다 coder → 같은 버전 tester → reviewer → 사용자 V11로 돈다. 커밋 단위는 CLAUDE.md 기준을 따른다(`[CombatCore][code]` → `[CombatCore][review]`).

순서 이유:

- 회차 1은 사용자가 먼저 이름 붙인 항목이고, 코드 내용 변경이 없다(위치만 바뀜).
- 회차 2는 코드 정리다. 고칠 파일(PlayerCombatComponent·PlayerGuardComponent·MonsterAttackMotion 등)은 회차 1의 이동 대상이 아니다.

#### 후속 회차 1 — 기존 파일 이동·원장 문구·열 누락 경고 실행

**요구 ID**: CombatCore-FU-24(DataSet 6종·로더 3개·UI 2개 이동, `@Assist` 계열 정리), FU-03, FU-23. 2026-11-19 추가: FU-26(결함, 진단 → 사용자 승인 → 수정, 아래 별도 절).

**승인**: 2026-11-19 사용자 순서 지시와 FQ-1·FQ-2·FQ-7 답(위 "근거·상태"). FU-26은 사용자 결정 "회차 1에서 처리"이며 진단만 승인이다.

**진행 상태(2026-11-20): 완료.** FU-24·FU-03·FU-23은 coder → `[code]` c6422cd → tester(FAIL 0) → reviewer WAITING(세 요구 충족, 결함 0) → 사용자 V11(1·2·3·5·6 수락, 4 NOT_RUN)로 끝났다. FU-26은 진단 → 사용자 1-A 승인 → coder → `[code]` a18b251 → tester(FAIL 0) → reviewer WAITING(AI 1~7 충족, 결함 0) → 사용자 V11 "모두 괜찮음"으로 끝났다. 남은 것은 메인의 회차 종료 커밋·push다([회차 1 흐름](#회차-1-흐름2026-11-20-완료)).

**이동 목록**: 11쌍 22파일. 바이트와 파일 이름은 그대로다. 경로는 `RootDesk/MyDesk/` 기준이다.

| 차수 | 원래 위치 | 새 위치 | 종류 |
| --- | --- | --- | --- |
| 1차(시험) | `@Assist/DataSet/PlayerBaseStatData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 1차(시험) | `UIToast.mlua`·`.codeblock` | `UI/` | 스크립트 |
| 2차 | `@Assist/DataSet/AttackSkillData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 2차 | `@Assist/DataSet/CombatRuleData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 2차 | `@Assist/DataSet/MonsterAttackPatternData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 2차 | `@Assist/DataSet/MonsterData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 2차 | `@Assist/DataSet/MonsterStatData.userdataset`·`.csv` | `DataSet/` | DataSet |
| 2차 | `Combat/CombatRuleCatalog.mlua`·`.codeblock` | `Catalog/`(새 폴더) | 스크립트 |
| 2차 | `Player/@Assist/Skill/PlayerSkillEffectTable.mlua`·`.codeblock` | `Catalog/` | 스크립트 |
| 2차 | `Player/@Assist/Stat/PlayerBaseStatCatalog.mlua`·`.codeblock` | `Catalog/` | 스크립트 |
| 2차 | `UIPopup.mlua`·`.codeblock` | `UI/` | 스크립트 |

폴더:

- coder는 2차 이동 때 실제 폴더 `RootDesk/MyDesk/Catalog/`를 만든다. `Catalog.directory`는 사용자 동기화가 만든다.
- 비게 되는 `@Assist`(안에 `DataSet`·`RangeGizmo`)와 `Player/@Assist`(안에 `Skill`·`Stat`·`AttackRange`)는 AI가 지우지 않는다. 안에 `.directory`가 있기 때문이다.
- 2차 동기화 뒤 Maker 작업 공간에 두 폴더가 남아 있으면 사용자가 Maker에서 지운다(2차 요청에 포함). 사용자가 지우지 않으면 남겨 두고 FU-24의 남은 일로 이 계획에 적는다.

이동 방법:

- 파일 단위로 옮긴다: `node -e "require('fs').renameSync(원래, 새)"`(FileStructure §2). 복사 후 삭제나 다시 쓰기는 하지 않는다.
- 이동 뒤 사용자 동기화 완료 알림 전까지 AI는 `maker_refresh_workspace`를 부르지 않는다. 이동 인식은 사용자 단계다.
- FU-03의 CSV 헤더 임시 변경·복원은 이동이 아니라 내용 편집이다. 2차 확인 뒤 coder가 기존 방식대로 `maker_refresh_workspace`로 반영한다.

**바꾸지 않을 파일**

- 22파일의 내용. 모든 `.mlua`·`.codeblock` 내용과 스크립트 이름.
- `.model`·`.map`·`.ui` 전부. 특히 `map/map01.map`은 작업 트리 변경 그대로 두고, 회차 시작 해시를 유지하며 커밋하지 않는다.
- `DataSet/MonsterSoundData`·`DataSet/PlayerActionFxData`. FU-03의 임시 변경은 원 바이트로 되돌린다.
- `Monster/OrangeMushroom/OrangeMushroomAttack`(FU-04, 6단계), `Models/Effects`(유지), 그 밖의 폴더.
- 모든 `.directory`. 손으로 만들거나 고치거나 지우지 않는다. Maker가 만들거나 지운 것만 기록한다.
- `Global/`·`Environment/`, 루트·Docs 문서 이동(FileStructure §6).
- 원장은 아래 "FU-23·원장 갱신"의 줄만 고친다.

**사용자 Maker 동기화 횟수(FQ-1 뒤 planner 결정)**: 2차로 나눈다.

| 방식 | 사용자 왕복 | 실패 때 영향 |
| --- | --- | --- |
| 한 번에(11쌍) | 1회 | 22파일과 두 종류(DataSet·스크립트)가 한꺼번에 미확인 상태가 된다. 원인 구분이 어렵다. 되돌리려면 22파일을 옮기고 다시 동기화해야 하고, 같은 이름 항목이 여러 개 남으면 월드 재로드가 필요할 수 있다 |
| 1쌍씩 엄격 시험 | 3회 | DataSet과 스크립트는 인식 방식이 달라 1쌍은 한 종류만 증명한다. 둘 다 시험하려면 시험 2회 + 나머지 1회다 |
| **2차(채택)** | 2회 | 1차에 종류별 1쌍만 옮긴다. 실패는 2쌍에서 멈춘다. 2차에 나머지 9쌍과 빈 폴더 정리를 한다 |

채택 이유:

- 왕복 1회를 더 쓰는 대신 두 종류를 각각 1쌍으로 먼저 증명한다.
- UIToast는 FileStructure §7이 정한 시험 대상이고, 실패해도 토스트만 영향받는다.
- PlayerBaseStatData는 서버·클라이언트 [VRF]가 함께 나와 양쪽 인식을 한 번에 본다.
- 사용자가 1회로 줄이길 원하면 메인이 1차 요청 때 묻는다. 그때도 중단 조건은 같고 실패 범위만 커진다.

**절차**

1. **메인**: run 상태와 git 작업 트리를 확인한다. 제품 변경은 `map/map01.map`뿐이어야 한다(문서·run 변경은 허용).
2. **coder 사전 확인**
   - `maker_get_current_map`: 이 월드·map01·편집 모드.
   - `map/map01.map` 해시, 22파일과 `DataSet/PlayerActionFxData.csv`의 SHA-256을 WorkRecord 개발 절에 적는다.
   - 이동 전 기준 값은 [2단계 Feature](../Features/2_CombatCore.md)와 아래 "확인 [VRF]·프로브"다. 이동 전 Play는 하지 않아도 된다.
3. **coder 1차 이동**: 시험 2쌍을 옮긴다. Glob 결과를 적고 `WAITING_USER`(1차 동기화 요청)로 메인에 돌려준다.
4. **메인 → 사용자**: run을 `WAITING_USER`로 바꾸고 1차 동기화를 요청한다. 요청에는 옮긴 4파일과 "동기화 뒤 완료를 알려 달라"를 적는다.
5. **사용자**: Maker 동기화 → 완료 알림.
6. **coder 1차 확인**
   - Glob: 옛 위치에 파일이 다시 생기지 않았다. `UIToast.mlua`·`UIToast.codeblock`이 작업 공간 전체에 1개씩이고, `.codeblock` 바이트가 이동 전과 같다(Id 63fe07f0…).
   - `maker_build_logs` 오류 0.
   - Play → server_main·client 프로브 각 1회:
     - `GetTable("PlayerBaseStatData")`가 비어 있지 않다.
     - `[VRF] PlayerBaseStatData side=server`·`side=client`가 100·12·12다.
     - 클라이언트 `_UIToast`가 있고 `message`·`toastGroup`이 유효하다. `ShowMessage` 1회 뒤 `toastGroup.Enable`이 true다.
   - Stop. 하나라도 실패하면 중단 조건.
7. **coder 2차 이동**
   - `Catalog/` 폴더를 만들고 나머지 9쌍을 옮긴다.
   - `@Assist`·`Player/@Assist` 아래에 `.directory` 말고 다른 파일이 없는지 Glob으로 확인한다.
   - `WAITING_USER`(2차 동기화 요청)로 메인에 돌려준다.
8. **메인 → 사용자**: 2차 동기화를 요청한다. 함께 요청한다: 동기화 뒤 작업 공간에 `@Assist`·`Player/@Assist` 폴더가 남아 있으면 Maker에서 지워 달라.
9. **사용자**: 동기화(와 빈 폴더 삭제) → 완료 알림.
10. **coder 2차 확인**
    - Glob(완료 기준 1), SHA-256(기준 2).
    - `.directory` 결과를 기록한다: `Catalog.directory`가 생겼는지, `@Assist` 계열 `.directory`가 지워졌는지.
    - `maker_build_logs` 오류 0. Play는 13단계와 합친다.
11. **coder FU-03**: 아래 "FU-03 실행".
12. **coder FU-23·원장**: 아래 "FU-23·원장 갱신". 원장은 Maker가 읽지 않는 루트 문서라 동기화가 필요 없다.
13. **coder 통합 확인**: FU-03 복원을 반영한 뒤 Play 1회로 완료 기준 4~6과 7의 "복원 뒤 정상 로드"를 모은다 → Stop → 편집 모드로 인계한다. WorkRecord 개발 절에 근거를 적는다.
14. **메인**: `[CombatCore][code]` 로컬 커밋 → 같은 버전 tester → reviewer → 사용자 V11 → planner 문서 정리 → `[CombatCore][review]` 커밋·push.

**FU-03 실행**(coder만)

- `DataSet/PlayerActionFxData.csv` 원본을 스크래치에 복사하고 SHA-256을 적는다.
- 헤더의 필수 열 `EffectSound`를 임시 이름(예: `EffectSoundX`)으로 바꾼다. 다른 바이트는 그대로다.
- `maker_refresh_workspace` → `maker_build_logs` → Play → 가드 1회(↓ 홀드) → 로그 → Stop.
- 원본 바이트로 되돌린다(SHA-256 일치) → `maker_refresh_workspace`. 정상 로드 확인은 13단계 통합 Play에서 한다.
- 이 표를 쓰는 이유: 실패해도 가드 연출만 꺼지고 전투는 계속된다(2단계 Plan §24.10 오류 동작). 출처도 §24.9 NOT_RUN이다.
- tester는 제품을 고치지 않으므로 임시 변경을 하지 않는다. 복원 일치·정상 로드·coder 로그 근거를 독립 확인하고, 자신의 경고 재실행은 NOT_RUN으로 적는다. 메인이 tester의 임시 변경을 따로 허락하면 다시 실행한다.

**FU-23·원장 갱신**(FQ-7 (가), FileStructure §7 경로 규칙. 줄 번호는 편집 전 기준)

- 주석: 20행 제목 "## 실효 대상별 사전 표" 바로 다음, 표 앞에 주석 1줄과 빈 줄 1줄(표 표시용)을 더한다. 문구: "(2026-11-19 주석) MHP-xx.castleenemy ID와 날짜가 붙은 기록 절은 2026-10-25 당시 키(castleenemy) 기준이다. 현재 실효 상대는 Mushmom.model(`mushmom`)이다."
- 23행: `(castleenemy)` → `(키 orangemushroom, 패턴·스폰 없음(6단계))`.
- 24행: "현재 MonsterData는 castleenemy 1행" → "현재 MonsterData는 머쉬맘(`model://mushmom`) 1행".
- 30행(DATA-02): `Combat/CombatRuleCatalog` → `Catalog/CombatRuleCatalog`. 원장이 옮긴 파일의 경로를 가리키면 갱신한다는 FileStructure §7 규칙이다. 이름만 쓴 줄(11·32행 등)은 고치지 않는다.
- 고치지 않는다: ID 이름, 날짜가 붙은 과거 기록 절(50행 이후), OPEN 상태. Mushmom 행 추가와 원장 재작성도 하지 않는다.

**확인 [VRF]·프로브**(새 코드·새 [VRF] 없음. 기존 로그와 프로브만 쓴다)

- 서버 로드:
  - `[VRF] CombatCore catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`;
  - Weight 비율 [VRF](mushmom), pattern row [VRF] 5줄;
  - `[VRF] MonsterSoundData id=...`, `[VRF] MonsterStatData id=default`·`id=mushmom ... source=DataSet`;
  - `[VRF] PlayerActionFxData id=... effect=... sound=...`;
  - MonsterStat applied mushmom 100·12·3.0, 머쉬맘 스폰 1회.
- 서버·클라이언트: `[VRF] PlayerBaseStatData side=server`·`side=client` MaxHp=100 MoveSpeed=12 ReturnSpeed=12 source=DataSet.
- Logic 존재(프로브): 서버 `_CombatRuleCatalog`·`_PlayerSkillEffectTable`·`_PlayerBaseStatCatalog`, 클라이언트 `_UIPopup`·`_UIToast`·`_PlayerBaseStatCatalog`가 nil이 아니다. 서버에서 `player.basic` 스킬 조회 결과가 nil이 아니다(조회 방법은 coder가 소스에서 정한다).
- 팝업: 기존 팝업 정지 경로 1회 → 정지·재개, `[VRF] CombatPause popup closed` 1회.
- 토스트: `ShowMessage` 1회 뒤 `toastGroup.Enable` true(프로브).
- FU-03 임시 상태: `[CombatRuleCatalog] PlayerActionFxData missing or required columns missing` 1회, `[VRF] guard fx off`.

**완료 기준 — AI**(coder 기본 검증, 같은 버전 tester 독립 재확인)

1. Glob:
   - `DataSet/`에 8쌍 16파일이 있다.
   - `Catalog/`에 로더 3쌍 6파일, `UI/`에 4쌍 8파일(CombatHpBarController·CombatInputController·UIPopup·UIToast)이 있다.
   - 22파일의 옛 위치에 파일이 없다. 5개 스크립트의 `.mlua`·`.codeblock`은 작업 공간 전체에 1개씩이다.
   - `@Assist`·`Player/@Assist`: 사용자가 지웠으면 실제 폴더와 그 `.directory`가 없다. 남았으면 남은 파일 목록을 기록한다(결함 아님, 사용자 V11에서 판단).
2. 22파일의 SHA-256이 이동 전과 같다. Maker가 다시 저장했다면 차이를 기록한다. DataSet의 id·EntryKey·name·serveronly와 `.codeblock`의 EntryKey·Id·Name이 같으면 결함이 아니다.
3. 1차·2차 동기화 뒤와 FU-03 Refresh 뒤 build 로그 오류가 0이다.
4. Play 서버(server_main 프로브 1회):
   - 8개 이름의 GetTable이 모두 비어 있지 않다.
   - 행 수가 이동 전과 같다(CombatRuleData 1·AttackSkillData 1·MonsterData 1·MonsterStatData 2·MonsterAttackPatternData 5·PlayerBaseStatData 1·MonsterSoundData 1·PlayerActionFxData 1).
   - PlayerBaseStatData는 클라이언트에서도 비어 있지 않다.
   - 위 Logic 5개가 존재한다.
5. 로드 [VRF]가 위 "확인 [VRF]·프로브"의 서버 로드·서버·클라이언트 항목과 같다.
6. 짧은 회귀 1회(FileStructure §7 회귀 포함):
   - ↑ 기본 공격 10타에서 HP 감소 = 피해 숫자;
   - 가드 시작 연출 [VRF] 1회, 몬스터 공격 1회 판정;
   - die 1회 정지, Pos2 JUST·PARRY 각 1회;
   - 팝업 정지 1회·토스트 1회;
   - 머쉬맘 스폰 1회·피격 규칙.
   - 회차 A·C 전수 회귀는 하지 않는다. 코드 내용 변경이 없기 때문이며, 그 사실을 NOT_RUN으로 적는다.
7. FU-03:
   - 임시 상태에서 위 경고가 정확히 1회 나온다.
   - 가드 시작 때 연출이 없고(`guard fx off`), 가드·전투는 계속된다.
   - 복원 뒤 SHA-256이 일치하고, 다음 Play에서 정상 로드 [VRF]가 나온다.
8. git:
   - 제품 변경은 22파일 경로 변경(이름 변경 100%), Maker가 만들거나 지운 `.directory`(`Catalog.directory` 추가, `@Assist` 계열 삭제), 원장 1파일뿐이다.
     - 예외(2026-11-19 사용자 결정, 위험 4): c6422cd의 `RootDesk/MyDesk.directory`·`RootDesk/MyDesk/Player.directory` CoreVersion 1줄씩은 그대로 둔다. 기준 위반으로 세지 않는다.
     - 예외 2(2026-11-20 사용자 결정 "회차 커밋에 포함", 위험 4): Maker 재저장 `DataSet/PlayerActionFxData.userdataset` CoreVersion 1줄은 회차 종료 `[review]` 커밋에 들어간다. 기준 위반으로 세지 않는다.
   - `map/map01.map`은 커밋에 섞지 않는다. 해시 기준은 2026-11-19 사용자 결정으로 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`다(회차 시작 `3e60c21d…c2094` → 2차 동기화 때 Maker 26.11 CoreVersion 재저장, run 기록). FU-26 단계도 이 값이 그대로여야 한다.
   - 다른 재저장은 분리해 기록한다(`common.gamelogic`·`ui` 4개는 [ops] bb3ec01).
   - FU-26 수정 커밋은 사용자가 승인한 파일만 담는다(FU-26 절 완료 기준 7).
9. 원장: Grep으로 편집 전 23·24행에 해당하는 줄에 `castleenemy`가 없고, 주석 1줄이 있으며, DATA-02 줄이 `Catalog/CombatRuleCatalog`를 가리킨다. 그 밖의 줄은 바뀌지 않았다(diff).

**완료 기준 — 사용자**

- 진행 조건: 1차·2차 Maker 동기화를 하고 완료를 알린다. 2차 때 빈 `@Assist`·`Player/@Assist` 폴더가 남았으면 Maker에서 지운다.
- V11 작업 공간: DataSet 폴더에 표 8개, Catalog 폴더에 스크립트 3개, UI 폴더에 스크립트 4개가 하나씩만 보인다. 옛 위치(`@Assist`, `Player/@Assist`, MyDesk 바로 아래 UIPopup·UIToast, Combat의 CombatRuleCatalog)에 항목이 없다. AI는 작업 공간 창을 볼 수 없다.
- V11 플레이: 전투·팝업·토스트 화면이 이전과 같다.
- **결과(2026-11-19, 사용자 원문 "모두 문제없음")**: 리뷰가 정리한 V11 6항목 기준이다.
  - 수락: 1 Maker 작업 공간 창, 2 피해 숫자와 HP, 3 die 마지막 프레임, 5 실제 키 JUST·PARRY와 반격, 6 전투 화면 전반.
  - **NOT_RUN**: 4 팝업·토스트 모양(실제 버튼으로 팝업 닫기 포함). 게임 안에서 `_UIPopup:Open`·`_UIToast:ShowMessage`를 부르는 경로가 없어 사용자가 볼 수 없다(planner Grep: RootDesk `.mlua`에서 두 Logic을 부르는 곳은 `CombatPauseComponent`의 응답·중단 처리와 `PlayerStateControl`의 `_UIPopup.isOpen` 읽기뿐). 메인이 V11 목록에 잘못 넣은 항목이며 PASS로 세지 않는다. AI 근거(Enable·정지·재개 프로브, coder·tester 각 1회)는 그대로다. 추적은 FU-27.
  - 같은 V11 중 새 결함 FU-26을 보고했다(아래 절).

**스크린샷(FU-18)**: 0장. 화면이 바뀌지 않는 회차이고, 입력은 키 입력·프로브로 하므로 좌표가 필요 없다. 팝업·토스트 표시는 [VRF]와 Enable 프로브로 본다. 다른 목적의 스크린샷이 필요하면 찍기 전에 멈추고 메인에 묻는다.

**중단 조건**(대안 구현이나 자동 되돌리기 없이 그 상태에서 멈추고 메인에 돌려줌)

1. 1차 확인 실패: PlayerBaseStatData의 GetTable이 nil이거나 한쪽이라도 [VRF]가 없다. 또는 `_UIToast`가 nil이다.
2. 같은 이름 항목이 둘인 징후: build 경고, 옛 위치 파일이 다시 생김, 다른 위치에 새 `.codeblock`(새 Id)이 생김.
3. 래퍼의 id·EntryKey·name·serveronly, 또는 `.codeblock`의 EntryKey·Id·Name이 바뀌었다.
4. 동기화 뒤 build 오류(스크립트 미등록, Symbol not found 등)가 난다.
5. 표를 다시 만들거나 `.mlua`·`.codeblock`·`.directory`·`.model`·`.map`·`.ui`를 고쳐야 한다.
6. FU-03 복원 뒤 SHA-256이 다르다.
7. `map/map01.map` 내용이 회차 중에 바뀌었다. (2026-11-19 이 조건으로 한 번 멈췄고, 사용자가 새 기준 `22b6acbf…987e`를 정해 해소했다. 이후는 새 기준과 다르면 멈춘다.)
8. 2차 요청 전 `@Assist` 계열 폴더에 `.directory` 말고 다른 파일이 남아 있다.
9. 사용자 동기화 완료 알림 없이 확인을 진행해야 한다. Maker 연결 실패·다른 월드·도구 거절은 EnvGuides대로 `WAITING_ENV`다.

실패하면 메인이 사용자에게 다음 중 무엇으로 할지 묻는다:

- 사용자 월드 재로드;
- 옮긴 파일을 원래 위치로 되돌리고 다시 동기화;
- 사용자가 Maker 작업 공간에서 직접 이동(FQ-1 질문의 (나), 회차 C2 선례).

**coder 인계 범위**(이 회차 절 전체가 원본이다)

- 순서: 사전 확인 → 1차 이동 → `WAITING_USER` → 1차 확인 → 2차 이동 → `WAITING_USER` → 2차 확인 → FU-03 → 원장 → 통합 Play → 편집 모드 인계.
- 경로: 위 "이동 목록" 11쌍과 새 폴더 `Catalog/`. 바꾸지 않을 파일: 위 목록.
- 사용자 동기화 요청 시점: 절차 3 끝(1차)과 7 끝(2차). 이동 후 완료 알림 전에는 `maker_refresh_workspace`를 부르지 않는다.
- FU-03: 헤더 임시 변경 → 확인 → 원 바이트 복원(SHA-256 일치).
- 확인: 위 "확인 [VRF]·프로브". 새 코드·새 [VRF]는 넣지 않는다.
- 중단 조건: 위 1~9.
- 기록: WorkRecord 개발 절에 해시, 동기화 결과, `.directory` 결과, 로그 근거.

#### 후속 회차 1 추가 — CombatCore-FU-26 머쉬맘 2·3칸 점프 초반 공중 끊김 (2026-11-19)

**근거·승인**

- 사용자 보고(2026-11-19 회차 1 V11, 원문): "머쉬맘이 2칸,3칸 점프할때 점프 초반 즘 공중에서 자연스럽게 이어지지 않음.(1칸 공격은 ㄱㅊ음)"
- 사용자 결정: "회차 1에서 처리".
- 승인 순서: 2026-11-19에는 **진단만** 승인했다. 수정은 coder 진단 보고 → 메인이 사용자에게 원인·수정안을 보임 → 사용자 승인 뒤에만 했다.
- **수정 승인(2026-11-20, 사용자 원문)**: "일단 1-A로 진행하고 결과 보여줘. 결과 확인하고 2-b할지 판단할게". a18b251 화면 확인 뒤 "1-A 유지"(2-b 제자리 점프 불채택). 진단 보고의 다른 안(A 속도 기반 이동·B 클라이언트 보간·C 현상 유지·D 도약 클립 교체, 1-B·1-C·2-a·2-b)은 고르지 않았다.
- **방안 1-A(승인 내용)**
  - 2·3칸 도약 시작(W)에서 클립을 기존 ActionSheet 키 `jump`로 한 번 바꾼다(`SetMotionClip("jump", 1)`: 전체 범위 자연 재생, 배율 1 × ActionRate). 이때 서버 프레임 구동(`TickClip`)이 끝나며, 구동은 제자리(windup, f0) 구간에서만 한다.
  - 높이: `LeapJumpHeight` 0 → 0.8(1칸 `JumpHeight`와 같은 값). 엔티티 y가 시간 포물선으로 Home.y + 0.8까지 올랐다 내려온다.
  - 그대로인 것: 수평 이동(매 틱 `SetPosition`·smoothstep), W·판정 시각, 착지 x·y, 판정 영역, 피격 구간, 복귀, 1칸 경로, 패턴 표·모델·이펙트·효과음.
  - 바뀐 파일: `Monster/OrangeMushroom/OrangeMushroomAttack.mlua` 1개(+10/−7, a18b251). 모델·CSV·`.codeblock` 변경 0.
  - 애니메이션 규칙: 새 클립이 아니라 머쉬맘 ActionSheet의 기존 키 `jump`(5ecbcc40…, 1칸 공격과 같은 클립)다. ActionSheet 7개 키·RUID 목록은 WorkRecord 진단 1절에 있다.
- 관찰 버전·환경: c6422cd(이 회차는 위치만 바뀜), Maker 26.11.
- 변경 이력(planner git log 확인):
  - 머쉬맘 공격 스크립트(`RootDesk/MyDesk/Monster/` 아래)와 `Models/` 아래 모델은 e710907(회차 D2 MM-14 2차, 2026-11-16 V11 수락 기준) 뒤 커밋 변경이 없다.
  - 패턴 표 변경은 5ce65d6(1칸 두 행 AttackSound)과 c6422cd(위치 이동 R100)뿐이다.
  - 그 사이 바뀐 환경은 Maker 26.10 → 26.11이다(d0d095b NativeScripts·CoreVersion, bb3ec01).
- 이전 이력: 회차 D2 MM-14의 "접근 버벅임"(D-Q9)·"점프 중 뚝 끊기는 느낌"(D-Q11)은 원인을 측정으로 확정하지 못했다. 조절 항목(EqualizeLeapFrames·EaseLeapMove 켬, LeapJumpHeight 0)을 V11에서 수락해 닫았다([2단계 Plan §22.17.3·§22.17.10](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)). FU-26은 같은 구간에서 다시 보고된 결함이다. 관련 추적 행은 FU-14(O-1 클라이언트 접근 멈춤, 2026-11-20 FU-16에 합침)·FU-15(O-3 프레임 이벤트 이중 도착)·FU-16(접근 이동 매 틱 `SetPosition`)이다. 이 FU-14·FU-15의 O-1·O-3은 2단계 QA14 관찰 번호이고, 2026-11-20 FU-26 tester 관찰 O-1·O-2·O-3과 다르다.

**증상**

- 2칸(parry.left·parry.right, attack1)·3칸(parry.guard, skill1)에서 점프 초반, 공중 동작이 자연스럽게 이어지지 않는다.
- 1칸(parry.any·special.random, jump)은 괜찮다(사용자).
- FQ-8 답(2026-11-19): 가끔 보임, (나) 뜬 직후 공중, 시기는 "최근 아니다 계속 봄"(11-16 수락 이전부터). 2026-11-20 체감: "보간된 포물선 느낌이 아닌 도중이 뚝 끊기는 느낌".

**진단 결과(2026-11-19~20 coder, 제품 변경 0)** — 원문은 [WorkRecord FU-26 진단](../WorkRecords/CombatCoreWorkRecord.md) 1~10절.

- **주원인(항상, 체감 "뚝 끊김")**: attack1·skill1 클립 공중 부분의 계단식 높이. 그림 높이가 0 → +0.88 → +0.70 → +0.08 → 0이고 프레임 사이 보간이 없다. W에 +0.88을 한 번에 올리고 W+0.286초에 −0.62를 한 번에 내린다. 클립 안 수평 이동은 없고, 수평은 스크립트 smoothstep이라 "높이는 계단, 수평은 곡선"이 겹쳐 보였다. 1칸은 jump 정지 자세 + 스크립트 포물선이라 높이가 연속이다.
- **부원인(가끔)**: FU-16 정지 1프레임(서버 매 틱 `SetPosition`이 클라이언트에서 정지 1프레임 + 다음 프레임 약 2배 이동으로 도착). 2·3칸 18회 중 13회, 1칸 6회 중 4회. 결과는 [FU-16 행](#부채남은-과제-구현-승인-아님).
- FU-15(프레임 이벤트 이중 도착)는 원인으로 지지되지 않았다. Maker 26.11 변경과 무관하다(2026-11-16 기준값과 같은 범위).

**기준 기획 문구**([GameDesign §4.2](../GameDesign.md). 2026-11-20 1-A 승인 범위의 문구만 갱신, 시각·판정 규칙은 그대로)

- 2·3칸: 제자리에서 기를 모은 뒤(약 1.143초) 짧게 도약해(약 0.429초) 착지 = 판정이다. 반응 시간 약 1.571초다. 제자리 모션과 이펙트는 원작의 0.7배이고, 도약 구간은 1-A로 jump 자세(배율 1)와 높이 0.8 포물선이다.
- 1칸: 예고 시작과 동시에 0.5초 점프하고 착지 = 판정이다.
- 2·3칸 차이: 2칸은 두 칸의 중간에 착지, 3칸은 Pos2에 착지한다. 3칸 눈빛은 머쉬맘 위치에서 예고 시작 때, 먼지는 착지 지점에서 판정 때다.
- 도약 모습 조절 항목: 2026-11-16 기본값(도약 프레임 균등화 켬, 수평 이동 곡선 켬, 도약 높이 0)에서 1-A로 도약 높이만 0.8이 됐다. 균등화는 도약 구간에 attack1·skill1 프레임이 보이지 않아 화면 효과가 없다(정리는 FU-29). "이 값들은 반응 시간·판정 시각을 바꾸지 않는다."
- 피격: 실제 점프(출발)·복귀 중에는 맞지 않고, 2·3칸 제자리 기 모으기 동안은 맞는다.

**2·3칸과 1칸의 차이**(진단 당시 c6422cd와 1-A 뒤 a18b251)

| 항목 | 1칸(괜찮음, 변경 없음) | 2·3칸 진단 당시(c6422cd) | 2·3칸 1-A 뒤(a18b251) |
| --- | --- | --- | --- |
| 경로 | `JumpToLocalX` | `BeginWindup` → approach | 같음 |
| 제자리(windup) 클립 | — | attack1·skill1 f0, 서버 구동, 배율 0.7 | 같음 |
| 도약(approach) 클립 | jump, 전체 범위 자연 재생, 배율 1 | attack1·skill1 f1~f3, 서버가 프레임 경계마다 Start=End=k로 구동(D-Q6), 배율 0.7 | W에서 jump로 한 번 전환, 전체 범위 자연 재생, 배율 1 × ActionRate. 구동 없음 |
| 점프 시작 | 공격 시작과 동시 | f0 제자리 약 1.143초 뒤(W) | 같음 |
| 높이 | 스크립트 포물선 JumpHeight 0.8 | 엔티티 0. 클립 그림 계단(+0.88 → +0.70 → +0.08) | 스크립트 포물선 LeapJumpHeight 0.8(정점 Home.y + 0.8) |
| 수평 이동 | 직선 | smoothstep(EaseLeapMove) | 같음 |
| 위치 쓰기 | 서버 매 틱 `SetPosition`(공통) | 같음. 약 0.429초에 2.25~3.75단위 | 같음(FU-16 정지 프레임 그대로) |

**coder 절차**(2026-11-19~20 실행 완료. 아래 절차·승인 대상·편집 범위는 실행 당시 지시로 남긴다)

1. **진단(제품 파일 수정 없음)**
   - 사전 확인: Maker map01·편집 모드, HEAD·작업 트리(제품 변경은 `map/map01.map`뿐, 해시 `22b6acbf…987e`).
   - 값 확인: 머쉬맘 모델의 OrangeMushroomAttack 값(EqualizeLeapFrames·EaseLeapMove·LeapJumpHeight·JumpDuration·JumpHeight·WindupHittable)을 ModelBuilder 읽기로 보고 스크립트 기본값과 같은지 적는다. 패턴 표 2·3칸 세 행(TelegraphLeadSec 1.571429·MotionPlayRate 0.7·JumpStartFrame 1)과 ActionSheet·MotionClip 값도 적는다.
   - 패턴 데이터: 2·3칸과 1칸 행의 차이를 확인한다.
   - 점프 처리 스크립트: OrangeMushroomAttack(windup·approach·`JumpToLocalX`·OnUpdate 위치 계산), MonsterAttackMotion(구동 클립·경계·PlayRate).
   - 애니메이션·상태 전환: windup → approach 전환 순간의 클립 지정(RUID·Start/End·PlayRate), 상태·구간 이름, 같은 틱의 쓰기 순서.
   - 측정(Play, 슬로우 없음): 2칸 좌·우·3칸 각 2회 이상과 1칸 1회 비교. MM-14 측정 방법을 다시 쓴다(서버 20ms + 클라이언트 매 프레임, 같은 `ServerElapsedSeconds` 시계). 지표는 2단계 Plan §22.17.3 B1~B5·§22.17.10.6 T1~T6이다. 특히 W ~ W+0.3초(점프 초반)의 클라이언트 프레임 번호·Start/End·PlayRate·x·y와 서버 쓰기 시각을 본다.
   - 비교: 2026-11-16 기준값([기준 커밋 5efe005 WorkRecord](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md)의 회차 D2 coder·QA14 측정)과 Maker 26.11에서 달라진 지표가 있는지 본다.
   - 분리 시험: Play 메모리·프로브에서만 후보 하나씩 바꾼다. 예: 조절 항목 4조합, 구동 없이 자연 재생, LeapJumpHeight > 0, 위치 쓰기 방식. 제품 파일·모델·CSV에는 남기지 않는다.
   - 로그: `maker_clear_logs`는 쓰지 않는다. 누적 로그의 22:11:32 `[LEA-3022]` 5건은 tester 시험 흔적이므로 제외한다.
   - 스크린샷: 0장. 화면 확인이 꼭 필요하면 찍기 전에 멈추고 메인에 묻는다.
   - Stop → 편집 모드로 인계.
2. **메인 보고**(WorkRecord 개발 절에도 적음)
   - 측정표, 1칸과의 차이, 2026-11-16 값과의 차이.
   - 확정한 원인 또는 "확정 못함"과 그 근거.
   - 수정안 선택지. 선택지마다 바꾸는 파일, 바꾸는 수치·규칙·애니메이션, 1칸 영향, 아래 "유지할 기존 규칙" 영향, 위험을 적는다.
   - 아래 "사용자 승인 대상" 중 해당 항목.
3. **사용자 승인**(메인이 묻는다). 승인 전에는 수정하지 않는다.
4. **수정**: 승인된 수정안의 파일·범위만 → Refresh → 한 실행 주기로 아래 완료 기준 — AI → Stop → 편집 모드 인계.

**사용자 승인 대상**(메인이 수정 전에 묻는다)

- 수정안 자체(파일·방식).
- 애니메이션: 새 클립 연결, 클립 교체, ActionSheet 키·패턴 표 MotionClip 변경. 이때는 **기존 세팅 목록(머쉬맘 ActionSheet 키와 RUID, 패턴 표 MotionClip 값)을 보여 주고 무엇을 쓸지 묻는다**(사용자 상시 규칙).
- 수치·규칙: TelegraphLeadSec, MotionPlayRate, JumpStartFrame, 제자리 W, 점프 J, JumpDuration, JumpHeight, LeapJumpHeight, 조절 항목 기본값, 착지 x, 판정 시각·창, 피격 구간, 이펙트 시각·위치.
- 이동·구동 방식: 매 틱 `SetPosition` → 속도 기반 이동(FU-16), 서버 프레임 구동 방식 변경(D-Q6 계약, FU-15).
- 1칸·복귀 경로 변경, 모델 값·컴포넌트 변경, CSV 변경, 새 파일.

**편집 허용 범위**

- 진단: 제품 파일 편집 없음. 시험 코드·값은 Play 메모리·프로브에만 둔다.
- 수정(승인 뒤): 승인된 수정안이 이름 붙인 파일만이다.
  - 후보 파일: `Monster/OrangeMushroom/OrangeMushroomAttack.mlua`, `Monster/MonsterAttackMotion.mlua`, `Monster/@StateControl/Monster_Attack.mlua`, `Monster/@StateControl/MonsterStateControl.mlua`(슬로우 배율 알림 부분만).
  - 승인된 경우만: `DataSet/MonsterAttackPatternData.csv`, 머쉬맘 모델(ModelBuilder).
  - 새 [VRF]는 승인안에 들어 있을 때만 넣는다.
- 바꾸지 않음:
  - 회차 1에서 옮긴 22파일과 그 위치, 원장;
  - `map/map01.map`(`22b6acbf…`, 커밋 제외);
  - `.ui`·`Global/`·`Environment/`, `.codeblock`·`.directory`;
  - Player 계열 스크립트;
  - CombatRuleCatalog·MonsterManager(승인안이 요구할 때만 예외);
  - GameDesign 규칙.

**유지할 기존 승인 규칙**(1-A가 바꾼 항목 말고는 그대로다)

- 시각: 2·3칸 W 1.142857초, 착지 = 판정(`CompleteMotion`) = 3칸 먼지 호출 1.571429초. 1칸 0.5초. 1-A 뒤에는 approach 동안 서버 프레임 구동이 없어 "서버 f4 쓰기"는 없다(판정 시각 기준은 `CompleteMotion`).
- 위치: 착지 x 2칸 좌 0.750·우 −0.750·3칸 0.000, 착지 y = Home.y. 2·3칸 접근 높이는 1-A 승인으로 0 → 포물선 0.8(정점 Home.y + 0.8)이다.
- 피격: windup 맞음, approach·return 막음.
- 판정·피해: GUARD(잔여 40%)·PARRY·JUST·HIT, 반격 2.0초 ×2.2.
- 슬로우·일시정지: D-Q6(접근 도중 슬로우 변화 때 프레임 되돌림 없음, ±0.05초), 일시정지 중 몬스터 정지.
- 3칸 이펙트 1·2단계 시각·위치, die 1회 정지와 die 가드.
- 1칸 접근·복귀 점프(0.5초, 높이 0.8, 직선).

**완료 기준 — AI**(coder 기본 검증, 같은 버전 tester 독립 재확인, 기본 조합)

1. 결함 지표: 진단에서 원인으로 정한 지표가 수정 뒤 기준을 통과한다. 전·후 값을 나란히 적는다. 원인을 확정하지 못한 채 사용자가 수정안을 승인했다면, 그 승인안이 정한 관찰 지표로 본다.
2. 시각·위치: W 1.142857 ±0.05초, 착지 = 판정(`CompleteMotion`) = 먼지 호출 1.571429 ±0.05초, 착지 x ±0.01, 착지 y = Home.y ±0.01. approach 중 y는 1-A 승인 높이(포물선 0.8, 정점 Home.y + 0.8 ±0.01)를 따른다.
3. 클립(1-A로 바꾼 기준, 2026-11-20): approach 동안 클립 전환 attack1·skill1 → jump 1회, attack1·skill1 프레임≥1 이벤트 0, 되돌림 0. 옛 기준 "클라이언트 0→1→2→3 순서"는 1-A가 도약 구간에 attack1·skill1 프레임을 쓰지 않으므로 대신했다(reviewer 판단: 대체 타당).
4. D-Q6: windup·approach 도중 슬로우 시작·종료(S1~S3) 때 되돌림 0, W·판정 시각 ±0.05초. windup 서버 렌더러 PlayRate = 0.7 × ActionRate, approach jump 클립 PlayRate = 1 × ActionRate.
5. 1칸 회귀: parry.any·special.random 접근 0.5초, 높이 최대 +0.8, 착지 x, 복귀 0.5초·0.8. 승인안이 1칸·복귀 경로를 바꾸지 않았다면 그 경로 소스 diff 0.
6. 회귀: windup 피격 통과·approach·return 차단, 판정 결과 각 1회, 3칸 이펙트 1·2단계 시각·위치, die 1회 정지, 일시정지 중 몬스터 정지.
7. build 로그 오류 0. git 변경은 승인 파일뿐이다. `map/map01.map` 해시 `22b6acbf…987e` 그대로, 커밋 제외.
- NOT_RUN은 PASS로 세지 않는다. AI 측정은 시각·순서·연속성만 증명하고, 화면 체감은 사용자 V11이다.
- **스크린샷(FU-18)**: 0장. 필요하면 찍기 전에 멈추고 메인에 묻는다(사용자 요청 없이 찍지 않음).

**완료 기준 — 사용자(V11 점프)**

- 2칸 좌·우·3칸 점프 초반 공중 동작이 자연스럽게 이어진다.
- 1칸 공격이 지금처럼 괜찮다(회귀 없음).
- 반응 시간·속도·맞는 구간 체감이 이전과 같다(승인으로 바꾼 것 제외).

**중단 조건**(대안 구현 없이 그 상태에서 멈추고 메인에 돌려줌)

1. 진단에서 원인을 확정하지 못했다. 측정값·관찰을 보고하고 수정하지 않는다. 메인은 FQ-8로 순간을 다시 묻거나, 확정 없이 고를 수정안이 있는지 사용자에게 묻는다.
2. 사용자 승인 없이 수정해야 하는 상황이 된다(위 "사용자 승인 대상" 전부).
3. 수정 뒤 완료 기준 2~6 중 하나가 깨진다(승인으로 바꾼 항목 제외).
4. 승인 파일 밖 수정이 필요하다.
5. 원인이 Maker 26.11 엔진 동작 변경이고, 프로젝트 코드로 피할 방법이 승인 범위에 없다. 측정 근거와 함께 멈추고, 다음은 사용자 결정(수락·우회안·보류)이다.
6. `maker_clear_logs`가 필요하거나 로그 포화로 측정이 막힌다.
7. `map/map01.map` 해시가 `22b6acbf…987e`와 다르다. Maker 연결 실패·다른 월드·도구 거절은 EnvGuides대로 `WAITING_ENV`다.

**FU-26 결과(2026-11-20)**

- 버전 a18b251(`[CombatCore][code]` FU-26 방안 1-A, 로컬). 제품 diff는 c6422cd 뒤 `OrangeMushroomAttack.mlua` 1개뿐이다.
- tester: FAIL 0. 클립 전환 1회·attack1/skill1 프레임≥1 이벤트 0, 정점 Home.y + 0.8, W·판정·착지 x·y·3칸 이펙트·피격 구간·1칸 회귀 기준 안.
- reviewer: WAITING(AI 1~7 충족, 결함 0, AI 3 대체 타당).
- 사용자 V11(2026-11-20): "모두 괜찮음". 1-A 유지, 2-b(제자리 점프) 불채택.
- 남은 관찰: FU-16 정지 프레임(그대로, 사용자 V11에서 눈에 띄지 않음), O-1·O-3 → FU-28, O-2 → FU-13 행, 화면 효과가 없어진 균등화 코드 → FU-29.

#### 회차 1 흐름(2026-11-20 완료)

1. 완료: FU-24·FU-03·FU-23 coder → `[code]` c6422cd → tester → reviewer WAITING(충족·결함 0) → 사용자 V11(1·2·3·5·6 수락, 4 NOT_RUN) → 커밋 구성 (가) 결정.
2. 완료: coder FU-26 진단 → 메인 보고.
3. 완료: 메인 → 사용자 원인·수정안·승인 대상 항목(애니메이션 기존 세팅 목록 포함).
4. 완료: 사용자 1-A 승인(2026-11-20).
5. 완료: coder FU-26 수정·기본 검증 → 메인 `[CombatCore][code]` a18b251.
6. 완료: 같은 버전 tester(FAIL 0).
7. 완료: reviewer(FU-26 충족·결함 0, c6422cd 뒤 제품 diff는 승인 파일 1개뿐).
8. 완료: 사용자 V11(점프) "모두 괜찮음".
9. 완료: planner 회차 종료 문서 정리(2026-11-20). 남은 것은 메인 `[CombatCore][review]` 커밋·push다.

**회차 종료 때 문서 정리(planner)**

- FileStructure §4(회차 기록), §5(완료 표시), §7(빈 폴더 결과);
- [2단계 Feature](../Features/2_CombatCore.md) 데이터 계약 "위치" 열(`DataSet/`);
- 현재 문서의 경로·링크:
  - Features/0_CombatPause.md(UIPopup·UIToast 링크);
  - Plans/MonsterCombat.md(MonsterData.csv 링크);
  - AssetList.md(패턴 표 경로);
- 이 계획의 FU-03·FU-23·FU-24 행.
- 2026-11-19 추가:
  - FU-26 결과를 2단계 Feature에 짧게 반영하고 이 계획의 FU-26을 정리한다. FU-14·FU-15·FU-16 행은 진단 결과에 맞춰 정리한다.
  - 회차 1 V11 결과(1·2·3·5·6 수락, 4 NOT_RUN)를 Feature에 반영한다.
  - 승인으로 수치·규칙이 바뀌었으면 사용자 승인 범위 안에서 GameDesign §4.2를 고친다. 바뀌지 않았으면 GameDesign은 고치지 않는다.
  - 사용자 승인 후보 처리(2026-11-20):
    - 가드 문구 통일: 사용자 승인 2026-11-20, 반영 완료. GameDesign §4.2·2단계 Feature·이 계획 회차 2 완료 기준 3의 가드 문구를 "잔여 피해 40%(60% 경감)"으로 맞췄다. 규칙·수치는 그대로다(reviewer 발견 5, tester 측정 rate=0.4·12→4).
    - Bundle 개선 후보: 사용자 승인 2026-11-20, [ops]로 반영 예정. → 2026-11-20 [ops] a593e2b로 반영(Bundle 폐지, git 트리·blob id 방식).
- 위 정리는 2026-11-20 끝났다(결과는 [후속 회차 1에서 닫은 항목](#후속-회차-1에서-닫은-항목2026-11-20)).
- 지난 기록(WorkRecord 이전 절·run)은 고쳐 쓰지 않는다.

#### 후속 회차 2 — 플레이어 공격·가드 코드 정리 + FU-12 이펙트 정지·슬로우 추종((가) 방식)

**요구 ID**: CombatCore-FU-17, FU-19, FU-12(FQ-3 (가) "기존 이펙트 유지 방식").

**시작 조건**: 회차 1이 끝난 뒤(reviewer 판정, 회차 종료 커밋, 사용자 V11). FU-12가 같은 파일(PlayerCombatComponent·PlayerGuardComponent)을 고치므로 세 항목을 한 회차에서 한 번에 고친다.

- 2026-11-20 상태: 아래 조건 1~4를 모두 충족했다(planner 확인).
  1. 충족. 메인 `[CombatCore][review]` 회차 종료 커밋 b071b5c를 `origin main`에 push했다(run 2026-11-20 기록, 비밀값 검사 통과).
  2. 충족. 버전 확인 방식 변경은 `[ops]` a593e2b로 반영됐다. CLAUDE.md "버전 고정"(2026-11-20 사용자 결정)에 따라 회차 2부터 Bundle(확장자별 파일 묶음 지문)은 쓰지 않고 git으로만 확인한다:
     - 커밋 해시와 트리 id(`git rev-parse <커밋>^{tree}`);
     - 바뀐 제품 파일은 `git diff --stat <부모> <커밋>`과 `git ls-tree -r <커밋> -- <경로>`의 blob id;
     - 작업 트리 미커밋 변경은 `git status --porcelain`, 커밋에서 뺀 범위 밖 파일(`map/map01.map`)은 SHA-256.
  3. 충족. 회차 2 기준 버전 = a593e2b(`origin/main`과 같음), 트리 id `d7ab128dc93ff5b8120882a8fcfd72a905a15f08`. `git status --porcelain` 결과 제품 변경은 ` M map/map01.map`(SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`, 커밋 제외)뿐이고, 나머지는 메인이 관리하는 ` M .pipeline/20261119-combatcore-followup/run.md`다. `RootDesk/` 미커밋 변경 0.
  4. 충족. planner는 범위 확인만 했다. 새 사용자 결정은 없다(FQ-3 (가)·원래 순서로 확정). 구현 승인은 사용자 "회차 2 시작"(2026-11-20)이다.
- **진행 상태(2026-11-20): 완료.** coder → `[code]` d8c61db(트리 `3940b24f…`) → tester FAIL 0 → reviewer WAITING(AI 1~5 충족, O-1 지적, 사용자 판단 4건) → 사용자 결정 → coder O-1 수정 → `[code]` eaeb032(트리 `fe15c874…`, `MonsterAttackMotion.mlua` blob `8d22ddd…`) → tester O-1 회귀 FAIL 0·사용자 프로브 시연 → reviewer READY → 사용자 V11 수락. 결과는 [후속 회차 2에서 닫은 항목](#후속-회차-2에서-닫은-항목2026-11-20). 남은 것은 메인의 회차 종료 `[CombatCore][review]` 커밋·push와 planner 마감 B(아래 "회차 종료 때 문서 정리")다.
- 구현 상태(2026-11-20 coder, d8c61db로 커밋됨): FU-17·FU-19·FU-12 (가) 구현·기본 검증 완료. 변경은 `PlayerCombatComponent`·`PlayerGuardComponent`·`MonsterAttackMotion`·`MonsterStateControl` 4개이고 `CombatPauseComponent`는 바꾸지 않았다(정지·재개는 클라이언트 시간 배율 0이 이미 이펙트를 멈춘 프레임으로 두고 이어 재생함을 측정으로 확인, 슬로우 추종만 몬스터 이펙트에 구현). 근거·미실시는 WorkRecord 개발 절 "후속 회차 2". 이후 QA·리뷰·사용자 V11 전까지 이전 판정은 이 변경에 적용되지 않는다.
- O-1 수정(2026-11-20 coder, eaeb032로 커밋됨): `GetEffectFrame`의 경과 시간에 클립 PlayRate(`fx.timeline.rate`)를 곱했다(+1/−1). 같은 파일의 `GetWindupSeconds`·`StartDrivenClip`·`PlayDieOnce`와 같은 관계다. 지금 클립은 PlayRate 1.0이라 결과 값은 같고(회귀 프레임 일치), 효과 자체는 소스 대조만 했다(O1-T7 NOT_RUN).
- FU-29(도약 균등화 코드 정리)는 `OrangeMushroomAttack.mlua`라 회차 2 범위가 아니다. 사용자가 따로 승인해야만 들어간다.

**범위 확인(2026-11-20 planner, 기준 a593e2b, Read·Grep·git 읽기만)**

- 대상 파일 7개의 a593e2b blob id(coder 시작 전 대조용):

  | 파일 | blob id |
  | --- | --- |
  | `RootDesk/MyDesk/Player/PlayerCombatComponent.mlua` | `598794553e22af79a08182f8dbe3a3a5a37bff81` |
  | `RootDesk/MyDesk/Player/PlayerGuardComponent.mlua` | `d6f9621c7bb7d73041cb8e705d6e98d2a92804d6` |
  | `RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua` | `ee41483064115a24de76a1e8dc935475ff9d5e2b` |
  | `RootDesk/MyDesk/Combat/CombatPauseComponent.mlua` | `1658387d80672ca210b7cdd050055d04f0e60926` |
  | `RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua` | `3bbc84c3143682f7dc10d946193391d796c909fd` |
  | (바꾸지 않음, 대조만) `RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua` | `af264b032d20dd76f444686bcc511816eadaa7ea` |
  | (바꾸지 않음, 대조만) `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua` | `62dcb6853dc12171a246faf3e20f7a5ce9cb437e` |

- 회차 1과의 겹침: `git diff --stat 16d70b3 a593e2b -- RootDesk/`에서 위 바꿀 파일 5개는 바뀌지 않았다. 회차 1의 이동(DataSet/·Catalog/·UI/)은 이 5개의 경로를 바꾸지 않았다(`CombatPauseComponent`는 그대로 `Combat/`에 있고, 같은 폴더에서 옮겨진 것은 `CombatRuleCatalog`뿐이다). FU-26 1-A는 `OrangeMushroomAttack.mlua` 1개만 바꿨고 이 회차의 바꿀 파일이 아니다.
- FU-17: `self._T.resolveIndex = index`가 `PlayerCombatComponent.mlua` 268행(`ResolveScheduledHit` 안)에 그대로 있다. RootDesk 전체 Grep `resolveIndex`는 이 1곳뿐이라 읽는 곳 0이다. 바로 위 267행 `self._T.resolveId = id`는 247행 `RuleSameCast` 규칙이 읽으므로 지우지 않는다. 기획 수치·규칙 변경 없음.
- FU-19: `PlayerGuardComponent.mlua` `SetGuarding`(10~35행)은 12행에서 `self.isGuarding`(기록 전 값)으로 시작을 판단하고, 연출(26행 `PlayEffect`, 28행 [VRF], 29행 효과음) 뒤 34행에서 `self.isGuarding = isHeld`를 기록한다. 함수 안 연출·효과음 경로는 `isGuarding`을 읽지 않는다(`isGuarding`을 읽는 곳은 `PlayerHealthComponent` 49행 피해 판정뿐이고 같은 서버 호출 안에서 끼어들지 않는다). 그래서 순서만 바꿔도 결과는 같아야 한다. 호출처 4곳(`Player_Guard` 10·18행, `CombatPauseComponent` 98행, `PlayerHealthComponent` 102행)은 바꾸지 않는다. 기획 수치·규칙 변경 없음.
- FU-12: 이펙트 재생 지점은 RootDesk 전체에서 3곳이다.
  - `MonsterAttackMotion.mlua` 177행 `PlayEffectRange`(ServerOnly) — 눈빛(186행 `PlayWindupEffect`)·먼지(194행 `PlayDustEffect`). serial을 이미 받고 `PlayRate`·`StartFrameIndex`·`EndFrameIndex` 옵션을 쓴다. 호출은 `Monster_Attack.mlua` 58·91행이다.
  - `PlayerCombatComponent.mlua` 166행(`DoAttack`, ServerOnly) — 옵션·serial 없음.
  - `PlayerGuardComponent.mlua` 26행(`SetGuarding`, ServerOnly) — 옵션·serial 없음.
  - 엔진 `_EffectService`는 `PlayEffect`·`PlayEffectAttached`·`RemoveEffect`만 있다(`Environment/NativeScripts/Service/EffectService.d.mlua` 8·12·16행). Plan 분류의 전제와 같다.
  - 정지·재개 신호: 서버 `CombatPauseComponent.SetServerPaused`(52~72행, `IsPaused` @Sync·전투 시계 정지). 클라이언트 `SetPresentationPaused`(114~126행, ClientOnly)는 `_UtilLogic:SetClientTimeScale(0)`으로 클라이언트 연출 시간을 멈춘다. 그래서 **팝업 정지 중 재생 중 이펙트가 이미 클라이언트에서 멈추는지**가 소스로는 정해지지 않는다. coder가 먼저 측정한다(아래 "coder가 정할 것" 첫 줄).
  - 슬로우 신호: `MonsterStateControl` `ApplySlow`(47~66행), 만료(102~106행), `ClearCombatEffects`(69~82행)가 모두 `ApplyMotionClipRate`(85~90행) → `MonsterAttackMotion.ApplyClipRate`(147~157행)를 부른다. 슬로우는 몬스터만 받는다(GameDesign §4.2 "플레이어·팝업/토스트·오디오는 늦추지 않는다"). 그래서 슬로우 추종 대상은 몬스터 이펙트(눈빛·먼지)뿐이고, 플레이어 공격·가드 이펙트는 정지만 대상이다.
  - 규칙 근거: GameDesign §4.3 "전투 연출을 모두 정지", §4.2 "행동·모션 진행 ×0.5". 기획 수치·규칙 변경 없음.
- 편집 허용 파일(이 5개 밖은 범위 밖, 중단 조건): `Player/PlayerCombatComponent.mlua`, `Player/PlayerGuardComponent.mlua`, `Monster/MonsterAttackMotion.mlua`, `Combat/CombatPauseComponent.mlua`, `Monster/@StateControl/MonsterStateControl.mlua`. Maker가 만드는 이 5개의 `.codeblock` 갱신은 함께 커밋할 수 있다. `Monster_Attack.mlua`(이펙트 호출처)·`UI/UIPopup.mlua`(클라이언트 정지 호출처)·`OrangeMushroomAttack.mlua`(FU-29)는 바꿀 파일 목록에 없으므로 고쳐야 하면 멈추고 메인에 반환한다.
- 판단: **READY_FOR_CODE.** 구현 승인(사용자 "회차 2 시작")이 있고, 결과를 바꾸는 미결정이 없다.

**바꿀 파일**

- `Player/PlayerCombatComponent.mlua`: `self._T.resolveIndex = index` 한 줄(a593e2b 기준 268행)을 지운다.
- `Player/PlayerGuardComponent.mlua` `SetGuarding`:
  - 시작 여부는 기록 전 값으로 판단한다.
  - `self.isGuarding` 기록을 연출 호출보다 앞에 둔다.
  - 시작 시각·시작 x·연출 1회는 그대로다.
- FU-12((가)):
  - `Monster/MonsterAttackMotion.mlua`(눈빛·먼지);
  - 위 두 파일의 이펙트 호출;
  - 정지·재개와 슬로우 시작·끝을 알리는 곳(`Combat/CombatPauseComponent`, `Monster/@StateControl/MonsterStateControl`). 실제로 고칠 파일은 coder가 정하고 개발 절에 적는다.
  - 새 `.model`은 만들지 않는다((가)).

**바꾸지 않을 파일**: 규칙·수치·DataSet·`.ui`·`.map`·`.model`, Player_Attack·Player_Guard·MonsterAttackComponent, 판정·피해 경로, 회차 1에서 옮긴 파일의 위치. 2026-11-20 범위 확인에서 명시: `Monster_Attack.mlua`(이펙트 호출처), `UI/UIPopup.mlua`(클라이언트 정지 호출처), `OrangeMushroomAttack.mlua`(FU-29)도 바꾸지 않는다. 편집 허용은 위 "바꿀 파일"의 5개 `.mlua`(와 Maker가 만드는 그 `.codeblock`)뿐이다.

**coder가 정할 것**(FU-12, 승인 범위 안)

- 먼저 측정: 지금 코드 그대로 팝업 정지(클라이언트 `SetClientTimeScale(0)`) 중 재생 중 이펙트(눈빛·먼지·플레이어 공격·가드)가 화면에서 멈추는지, 재개 뒤 남은 프레임부터 이어지는지. 이미 멈추고 이어지면 정지 쪽은 측정 근거만 적고 같은 일을 하는 코드를 더하지 않는다. 슬로우 추종(몬스터 이펙트)은 이와 따로 판단한다;
- 정지·재개·배율 변경을 받을 위치;
- 재생 중 이펙트 serial과 진행 프레임을 추적하는 방법;
- 남은 프레임부터 다시 재생할 때의 프레임 계산(기존 `PlayEffectRange` 옵션 재사용);
- "멈춘 프레임 표시"가 되는지 측정하고, 안 되면 정지 동안 숨김으로 떨어뜨리는 것;
- [VRF] 문구.

**사용자가 정할 것**: 없음(FQ-3 (가) 확정). 보이는 결과는 사용자 V11에서 판단한다.

**완료 기준 — AI**

1. Grep: `resolveIndex` 0곳.
2. V02 회귀 1회: ↑ 기본 공격 10타에서 HP 감소 = HitEvent 합 = 피해 숫자. 반격 보너스 ×2.2 1회 포함.
3. 가드:
   - ↓ 홀드 시작 때 시작 [VRF]·연출 [VRF]·효과음 [VRF]가 각 1회다.
   - 홀드 유지·추가 입력 출처에서는 더 나오지 않는다.
   - 패링 1회 성공(Pos2), 일반 가드 잔여 피해 40%(60% 경감) 1회.
   - 연출 표가 무효인 상태는 회차 1의 FU-03 결과로 대신하지 않는다. `SetGuarding` 순서만 바뀌므로 소스 대조로 판단하고, 그렇다고 적는다.
4. FU-12:
   - 팝업 정지 중 눈빛·먼지·플레이어 공격·가드 이펙트의 재생 상태 [VRF];
   - 재개 뒤 남은 구간만 재생되고 끝 시각이 정지 시간만큼 밀리는지;
   - 슬로우 시작·끝 때 재생 중 눈빛의 배율이 ×0.5·×1로 바뀌는지;
   - 재생이 끝난 이펙트를 다시 내지 않는지;
   - 사망·Stop 때 추적이 정리되는지.
5. build 로그 오류 0, git 변경이 범위 파일뿐이다. 확인 방법(2026-11-20 CLAUDE.md "버전 고정", Bundle 쓰지 않음): `[code]` 커밋 해시·트리 id, `git diff --stat a593e2b <커밋>`이 편집 허용 5개 `.mlua`(+ 그 `.codeblock`)와 Plan·WorkRecord 문서뿐이고, 바뀐 파일은 `git ls-tree -r <커밋> -- <경로>` blob id로 대조한다. `git status --porcelain`에는 `map/map01.map`(SHA-256 `22b6acbf…987e` 그대로)과 메인의 run.md 말고 남은 제품 변경이 없다.

**스크린샷(FU-18)**: 목적은 "팝업 정지 중 이펙트가 멈춤/숨김/계속 재생 중 무엇으로 보이는지 확인" 하나다. 이펙트 종류마다 정지 직전·정지 중·재개 직후 3장 안팎, 회차 전체 12장 이하. 그 밖의 용도는 쓰지 않는다.

**사용자 V11**: 팝업 정지 중 이펙트 모습과 슬로우 중 눈빛 속도가 어색하지 않은지 본다.

- **2026-11-20 정리(reviewer R-2): 자연 경로 없음 → 사용자 선택 프로브 시연으로 수락.** 위 두 항목은 지금 게임 안에서 볼 경로가 없다. 팝업을 여는 호출이 0곳이고(FU-27), 이펙트가 있는 패턴(`parry.guard`)은 JUST를 만들지 않으며 다른 공격의 슬로우는 다음 눈빛과 겹치지 않는다. 그래서 이 V11은 FU-27의 "경로가 생기기 전에는 V11에 넣지 않는다"와 어긋난 채 쓰였다.
  - 실제 처리: 사용자가 "시연 보고 확인"을 골랐다. tester가 Play 메모리 프로브(서버 `SetServerPaused`, 클라이언트 `SetPresentationPaused`, `ApplySlow(2.0, 0.5)`)로 정지·슬로우를 걸고, 사용자가 Maker 화면에서 눈빛·먼지를 봤다. 판정 "모두 괜찮음"(2026-11-20). 제품 변경 0, AI 스크린샷 0.
  - 이 수락은 **프로브 시연 수락**이며 실제 `_UIPopup:Open` 경로도, 자연 플레이의 슬로우·이펙트 겹침도 아니다. 실제 팝업 경로 확인은 FU-27(그 경로가 생기는 회차 V11)에 남긴다.
  - 다시 볼 조건(자연 슬로우·이펙트 겹침): JUST가 나는 공격에 `EffectClip`을 넣을 때, `AttackInterval`·`SlowDurationSec`를 크게 바꿀 때, 6단계에서 몬스터가 늘 때. 위 "후속 회차 2 남은 미실시" 표에도 적었다.
  - Plan 작성 메모(규칙 아님): 다음 Plan부터 V11에는 자연 경로가 없는 항목을 넣지 않거나, 넣을 때는 "프로브 시연"이라고 적고 방법을 함께 적는다. 이를 Plan 작성 원칙이나 FU-18 같은 (D) 운영 항목으로 만들지는 사용자 승인 사항이라 이번에는 만들지 않았다.

**회차 종료 때 문서 정리(planner)**

- 마감 A(2026-11-20, 완료): 이 계획의 목표·상태·미실시 표·부채 표(FU-12·17·19를 닫은 항목으로 옮김, FU-28에 회차 2 O-3, FU-30 등록, FU-27에 회차 2 내용)·사용자 결정 대기·분류 표, 이 절의 진행 상태·V11 정리, [2단계 Feature](../Features/2_CombatCore.md), [로드맵](../DevelopmentRoadmap.md) 재개 지점, [WorkRecords README](../WorkRecords/README.md) 상태 문구. GameDesign은 규칙·수치 변경이 없어 고치지 않았다.
- 마감 B(메인 `[CombatCore][review]` 커밋·push 뒤): 사용자 결정 "링크 정리 후 삭제"(2026-11-20)에 따라 WorkRecord·run을 가리키는 링크를 그 커밋의 GitHub 고정 링크로 바꾸고 `WorkRecords/CombatCoreWorkRecord.md`와 `.pipeline/20261119-combatcore-followup/`을 지운다(2026-11-19 5efe005 선례). 끝나면 메인이 `[CombatCore][plan]` 커밋·push.

**중단 조건**

- 판정·피해·가드 결과가 바뀐다.
- 범위 밖 파일을 고쳐야 한다.
- (가) 방식으로 정지·재개를 표현할 수 없다(측정 근거와 함께 메인에 반환).
- 새 모델이 필요해진다.
- 시작 때 대상 파일 blob id가 위 "범위 확인" 표와 다르거나, `map/map01.map` SHA-256이 `22b6acbf…987e`가 아니거나, `maker_get_current_map`이 map01이 아니다.

**coder 절차(2026-11-20 planner 인계)**

1. 사전 확인: `git rev-parse HEAD`(a593e2b 또는 그 뒤 메인 커밋), `git status --porcelain`, 대상 파일 blob id, `map/map01.map` SHA-256, `maker_get_current_map`(map01·편집 모드).
2. FU-17: 268행 1줄 삭제. Grep `resolveIndex` 0곳.
3. FU-19: `SetGuarding`에서 기록 전 값을 지역 변수로 잡아 시작 판단에 쓰고, `self.isGuarding = isHeld`를 연출 호출 앞으로 옮긴다. 시작 시각·시작 x·[VRF]·연출·효과음 1회는 그대로.
4. FU-12 측정(위 "coder가 정할 것" 첫 줄) → 필요한 만큼만 구현((가), 새 `.model` 없음, 편집 허용 5개 파일 안). [VRF]는 재생 시작·정지 처리·재개 재생(남은 프레임 범위·배율)·배율 변경·끝난 이펙트 건너뜀·정리(사망·Stop·맵 이탈)에 둔다.
5. `maker_refresh_workspace` → build 로그 → Play 한 사이클로 완료 기준 AI 1~5 근거 수집(스크린샷은 FU-18 범위 안).
6. Maker 편집 모드 인계, WorkRecord 개발 절에 회차 2 기록(대상 버전은 메인 `[code]` 커밋 해시·트리 id·blob id로 메인이 적는다). commit·push는 하지 않는다.

#### 후속 회차 3 — 회차 1에 합침(2026-11-19)

FQ-2 답 "회차 1에 함께"로 이 회차의 이동(로더 3개 → `Catalog/`, UIPopup·UIToast → `UI/`, `Player/@Assist` 정리, 원장 경로 갱신)을 후속 회차 1에 합쳤다. 이 회차는 열지 않는다. FileStructure §7의 "위험이 낮은 1건 먼저" 원칙은 회차 1의 1차 동기화(UIToast)로 지킨다.

#### 후속 회차 4 — 열지 않음(2026-11-19)

FQ-4·FQ-5·FQ-6이 모두 (가)여서 FU-08~11·FU-13·FU-20은 하지 않고 위 부채 표에서 추적한다. 사용자가 나중에 하나라도 고르면, planner가 회차 시작 전에 계약(열 이름, 빈 값 기본값, 검증·오류 동작, 대상 파일, 스크린샷 범위)을 먼저 적고 사용자 확인을 받는다.

### 4. 사용자 질문과 답

**사용자 답(2026-11-19)**

| 번호 | 사용자 답(원문) | 반영 |
| --- | --- | --- |
| FQ-1 | "파일 너가 이동시키고 내가 maker에 동기화 할게" | AI(coder)가 파일을 옮기고 Maker 동기화는 사용자가 한다. 질문의 (가)·(나)를 나눈 방식이다. 동기화 횟수는 planner가 2차로 정했다(회차 1 절) |
| FQ-2 | "회차 1에 함께" | (다). 회차 3을 회차 1에 합쳤다. 루트·Docs 문서 이동(FileStructure §6)은 넣지 않는다 |
| FQ-3 | "기존 이펙트 유지 방식" | (가). FU-12를 후속 회차 2에 넣는다 |
| FQ-4 | "모두 추천안대로" | (가). FU-13은 바꾸지 않고 추적한다 |
| FQ-5 | "모두 추천안대로" | (가). FU-08~11은 만들지 않고 추적한다 |
| FQ-6 | "모두 추천안대로" | (가). FU-20은 하지 않고 추적한다 |
| FQ-7 | "모두 추천안대로" | (가). 원장은 23·24행 현재 상태 문구와 주석 1줄만 고친다 |

**회차 1 리뷰·V11 뒤 사용자 결정(2026-11-19, run 기록)**

| 항목 | 사용자 답(원문) | 반영 |
| --- | --- | --- |
| 리뷰 발견 1: c6422cd의 `MyDesk.directory`·`Player.directory` | "하나의 커밋으로" | 리뷰 선택지 (가). 커밋을 나누지 않는다. 회차 1 위험 4·완료 기준 8, FileStructure §7에 예외로 적었다 |
| V11 1·2·3·5·6 | "모두 문제없음" | 수락. 4(팝업·토스트 모양)는 게임 안 호출 경로가 없어 NOT_RUN, FU-27로 추적 |
| `map/map01.map` 해시 기준 | 새 기준 `22b6acbf…987e` | 완료 기준 8·중단 조건 7과 FU-26에 반영 |
| 새 결함(머쉬맘 2·3칸 점프 초반) | "회차 1에서 처리" | FU-26. 진단만 승인, 수정은 진단 보고 뒤 사용자 승인 |

**FU-26 보조 질문(메인이 필요할 때 사용자에게 묻는다. 답이 없어도 진단은 시작한다)**

| 번호 | 질문 | 선택지 |
| --- | --- | --- |
| FQ-8 | 머쉬맘 2칸·3칸 점프 초반의 끊김이 매번 보이나요, 가끔 보이나요? 가장 잘 보이는 순간은 언제인가요? 2026-11-16 수락 때도 있었는지, 최근(Maker 26.11 이후) 처음 본 것인지도 알려 주세요 | 빈도: 매번 / 가끔. 순간: (가) 눈빛이 끝나고 몸이 뜨는 순간 (나) 뜬 직후 공중 (다) 공중 가운데 이후 (라) 잘 모르겠음. 시기: 전에도 있었음 / 최근 처음 / 모르겠음 |

**질문 원문(2026-11-19 planner)**

| 번호 | 질문 | 선택지 | 추천 |
| --- | --- | --- | --- |
| FQ-1 | DataSet 6종을 어떻게 옮길까? | (가) coder가 파일을 옮기고 Refresh한다. 시험 1쌍을 먼저 하고, 실패하면 멈춘다. FileStructure §7 승인 절차다. (나) 사용자가 Maker 작업 공간에서 6개 표를 `DataSet` 폴더로 옮기고, AI는 결과만 확인한다. 회차 C2 모델 이름 변경 선례다 | (가). AI가 바이트·로드를 단계마다 확인할 수 있고, 실패하면 1쌍에서 멈춘다. 실패 때는 (나)나 월드 재로드로 돌린다 |
| FQ-2 | FU-24의 "그 밖의 기존 파일 이동"(로더 3개 → Catalog/, UIPopup·UIToast → UI/, Player/@Assist 정리)도 이번에 할까? | (가) 이번 후속 처리에서 회차 3으로 따로 한다. (나) 하지 않고 계속 추적한다(3단계 이후). (다) 회차 1에 함께 넣는다 | (가). 승인된 목표 구조라 지금 정리하면 3단계의 새 로더가 Catalog/ 한 곳에 모인다. 스크립트 짝 이동은 재인식 위험이 커서 DataSet 회차와 나눈다. 루트·Docs 문서 이동(FileStructure §6)은 어느 쪽이든 포함하지 않는다 |
| FQ-3 | FU-12(팝업 정지 중 이펙트 정지, 슬로우 중 이펙트 속도 추종)를 어떻게 할까? | (가) 지금 쓰는 엔진 이펙트를 유지한다. 정지 중에는 멈춘 프레임을 보이게 하고, 안 되면 숨긴다. 재개·배율 변경 때 남은 프레임부터 새 배율로 다시 재생한다. 새 모델이 없고, 이어 붙는 순간이 한 번 끊겨 보일 수 있다. (나) 이펙트를 전용 엔티티(새 `.model`)로 재생하고 렌더러 배율로 정확히 멈추고 늦춘다. 범위가 크다(스폰·정리·모델). (다) 지금 하지 않는다. 1회성 짧은 이펙트이고 V11에서 수락됐으며, 7단계 연출 점검 때 다시 본다 | (가). 기존 규칙(GameDesign §4.3)에 가장 가깝게 맞추면서 새 구조를 만들지 않는다. 보이는 결과는 V11에서 판단한다 |
| FQ-4 | FU-13: 착지 순간이 보이지 않는 것(f4 잘림, 착지 정지 0)을 바꿀까? | (가) 바꾸지 않는다(V11 수락 유지, 추적 계속). (나) 판정 뒤 복귀 점프 시작을 늦춰 착지 자세를 보인다. 늦출 시간(초)은 사용자가 정한다. 판정 시각은 그대로이고 공격 한 주기가 그만큼 길어진다 | (가). V11에서 f4 잘림까지 수락했고, (나)는 판정 뒤 시각을 바꾸는 규칙 변경이다 |
| FQ-5 | FU-08~FU-11(묶음 비율 표·효과음 음량 열·이펙트 배율·위치 열·이펙트 재생 배율 분리 열) 중 지금 만들 것이 있나? | (가) 지금 만들지 않는다. 조정하고 싶은 것이 생기면 그때 고른다. (나) 번호를 골라 만든다. planner가 열 설계안을 회차 4 전에 제안한다 | (가). 지금 조정 요구가 없어 열의 쓰임을 확인할 수 없다. 5·6단계에서 표 구조를 확정할 때 함께 보는 것이 덜 고친다 |
| FQ-6 | FU-20: 표 오류 경고에 칸·값을 넣을까? | (가) 지금 하지 않는다. (나) 연출 표 2개(MonsterSoundData·PlayerActionFxData) 경고에 행 id·열 이름을 넣는다. (다) CombatRuleCatalog의 모든 표 경고에 넣는다(경고 키가 바뀌어 "원인당 1회" 단위가 행·열 단위로 바뀜) | (가). 지금 표를 고친 결과는 로드 [VRF]로 바로 보인다. 사용자가 CSV를 직접 고치다 원인을 찾기 어려우면 그때 (다)를 권한다 |
| FQ-7 | FU-23 원장 정리 범위를 기본안으로 할까? | (가) 기본안: 현재 상태 문구(23·24행)만 고치고 주석 1줄을 더한다. ID·과거 기록 절은 그대로다. (나) 원장의 모든 `castleenemy`를 바꾼다(ID 포함, 과거 근거와 어긋남). (다) 원장 전체를 현재 상태로 다시 쓴다(OPEN 상태 정리 포함, 범위 큼) | (가) |

(C)로 둔 항목 가운데 FU-04·FU-16을 앞당기고 싶으면 그 항목은 (B)가 된다. FU-04는 새 이름·폴더, FU-16은 이동 방식 결정을 사용자가 정하고 별도 회차를 만든다.

### 5. 기록·종료

- **WorkRecord**: 2026-11-19 후속 회차 1을 시작하며 planner가 만들었다: [CombatCoreWorkRecord](../WorkRecords/CombatCoreWorkRecord.md).
  - 2단계 원본 WorkRecord는 기준 커밋 5efe005에만 있다. 그래서 첫 줄에서 "2단계 후속 처리(FU) 회차 기록"이라고 구분한다.
  - 회차마다 개발·QA·리뷰 절을 순서대로 둔다.
- **회차 종료**: 결과를 [2단계 Feature](../Features/2_CombatCore.md)에 짧게 반영하고 위 부채 표의 행을 정리한다(아래 "진행·종료").
- **(B)·(C)·(D) 행**: 이 계획에 남긴다. 3단계 Plan이 FU-18·FU-22·FU-27을 맡으면 그 Plan으로 ID를 옮긴다.
- **3단계 시작 조건**: 후속 회차 1·2가 모두 끝나고(사용자 V11 포함), 사용자가 3단계 시작을 지시한다. 2026-11-20 회차 1·2가 모두 끝났으므로 남은 것은 사용자 지시다.

## 진행·종료

- 항목을 처리하면 결과를 [2단계 Feature](../Features/2_CombatCore.md)에 짧게 반영하고 이 표의 해당 행을 정리한다.
- 모든 항목을 확인하거나, 사용자 승인으로 다른 계획에 옮기거나 처리 방법을 정한 뒤에 이 계획을 삭제한다.
- 다른 단계 Plan이 항목을 맡으면 그 Plan에 ID를 그대로 옮기고 이 표에는 이동 위치만 남긴다.
