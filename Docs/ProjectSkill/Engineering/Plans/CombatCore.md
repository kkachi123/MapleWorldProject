# CombatCore — 2단계 후속 확인 계획

## 목표·상태

2026-11-19 사용자 결정 "모바일연결이나 멀티환경 테스트는 하지는 않음. 그래도 2단계 완료는 해도 될것 같음."으로 2단계를 완료했다. 현재 결과는 [2단계 Feature](../Features/2_CombatCore.md)다.

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
| CombatCore-FU-03 | NOT_RUN | **시점**: DataSet 로더를 다시 고치는 회차. **기준**: 필수 열 누락 경고 한 줄을 실제로 실행해 확인한다. 지금은 결과 경로만 런타임으로 확인했고 경고 줄은 소스로 판단했다. 출처는 [Plan §24.9](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md). → 2026-11-19 (A), [후속 처리 계획](#후속-처리-계획2026-11-19) 후속 회차 1에서 실행 |

CombatFoundation-F07은 2026-11-19 사용자 "기존 수락으로 닫기"로 완료해 이 표에서 뺐다(PC Maker 기준). 상태와 근거는 [CombatFoundation](CombatFoundation.md)에서만 관리하고, 모바일·실기기 연출은 위 CombatCore-V11 행이 맡는다.

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
| CombatCore-FU-17 | PlayerCombatComponent `_T.resolveIndex` 제거(기록만 하고 읽지 않음) | 그 파일을 고치는 회차에서 함께. 2026-11-19 (A) 후속 회차 2 |

**연출·소리 조절**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-09 | 효과음 음량 열 | 사용자가 음량 조정을 원할 때. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-10 | 이펙트 배율·위치 열 | 사용자가 조정을 원할 때. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-11 | 클립·이펙트 재생 배율 분리 열(예: EffectPlayRate) | 사용자가 둘을 따로 조정하길 원할 때. 지금은 MotionPlayRate 하나가 둘에 같이 쓰인다. 2026-11-19 FQ-5 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-12 | 일시정지 중 이펙트 정지와 재생 중 이펙트의 슬로우 변화 추종(3칸 눈빛 포함, 회차 E 가드 이펙트 포함) | 2026-11-19 FQ-3 (가) "기존 이펙트 유지 방식". 후속 회차 2(회차 1 뒤) |
| CombatCore-FU-13 | 접근 클립 마무리 프레임(f4) 표시와 착지 순간 정지 0 | 사용자가 f4가 잘리거나 착지가 어색하다고 할 때. 착지 정지는 판정 뒤 시각을 바꾸는 사용자 결정이다. 2026-11-19 FQ-4 (가): 바꾸지 않음, 추적 유지 |
| CombatCore-FU-20 | 연출 표(PlayerActionFxData) 경고에 칸·값 넣기 | 사용자가 요청할 때만(새 요구). 2026-11-19 FQ-6 (가): 하지 않음, 추적 유지 |
| CombatCore-FU-21 | 위 공격 버튼 아이콘을 선택한 액티브 스킬 아이콘으로 연결. 지금은 칼 아이콘 | 액티브 스킬 선택이 생기는 단계(5단계). 2026-11-19 (C) 유지 |

**동작 관찰**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-14 | 관찰 O-1. 간헐적으로 클라이언트 접근이 멈춘다. 원인 미확인, QA14에서 재현 0/28 | 사용자가 "가끔 멈춤"을 보고하거나, 실접속·모바일 회차에서 재현될 때. 2026-11-19 (C) 유지 |
| CombatCore-FU-15 | 관찰 O-3. 구동 프레임 이벤트가 같은 ms에 2건 도착한다 | 프레임 이벤트에 기대는 새 기능을 만들 때, 또는 화면 문제로 확인될 때. 2026-11-19 (C) 유지 |
| CombatCore-FU-16 | 접근·복귀 이동을 서버 `OnUpdate`에서 매 틱 `SetPosition`으로 처리한다 | V11·실접속에서 끊김이 다시 보일 때. 6단계 몬스터 동작 일반화와 함께. 속도 기반 이동은 재증명이 필요한 새 결정이다. 2026-11-19 (C) 유지 |
| CombatCore-FU-19 | PlayerGuardComponent.SetGuarding에서 연출 호출이 상태 기록보다 앞에 있다. 리뷰 비차단 메모이며 결함이 아니다 | 이 함수를 다시 고치는 회차. 2026-11-19 (A) 후속 회차 2 |

**문서·운영**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-18 | 화면 표시 확인이 완료 기준에 있으면, 그 확인용 스크린샷의 허용 범위(목적·대략 장수)를 완료 기준에 함께 적는다 | 다음 Plan 작성 때(planner, 3단계 Plan 포함). 2026-11-19 (D), 후속 처리 계획 회차별 완료 기준에 먼저 적용 |
| CombatCore-FU-22 | 범위 밖 관찰. 플레이어 쪽 피해에 남은 HP 상한이 없고, 사망 직후 플레이어 HP 문자가 음수로 보일 수 있다(화면 미관찰) | 3단계 Plan 작성 때 후보로 검토(플레이어 HP 0 종료·승패). 2026-11-19 (D) |

## 사용자 결정 대기

| 항목 | 내용 | 원문 |
| --- | --- | --- |
| 3단계 시작 | 2단계 완료 뒤 다음 로드맵 단계. 사용자 시작 지시 대기. 2026-11-19 사용자 지시로 아래 후속 처리를 먼저 끝낸 뒤 진행한다 | [로드맵](../DevelopmentRoadmap.md) |
| CombatCore-FU-23 원장 문구 | `.maplestory-skill-maker-ledger.md`의 낡은 castleenemy 문구를 정리할 시점. → 2026-11-19 사용자 "먼저 처리". (A), 후속 회차 1. 범위는 FQ-7 (가) 기본안(23·24행 현재 상태 문구와 주석 1줄) | [Plan §23.6](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) |
| CombatCore-FU-24 기존 파일 이동 | 기존 DataSet 6종을 `@Assist/DataSet/`에서 `DataSet/`으로 옮길 회차와, 그 밖의 기존 파일 이동. → 2026-11-19 사용자 "DataSet 6종 이관" 먼저 처리. FQ-1 "파일 너가 이동시키고 내가 maker에 동기화 할게"(AI 이동, 사용자 Maker 동기화), FQ-2 "회차 1에 함께"(로더 3개·UI 2개·`@Assist` 계열 정리도 포함). 모두 (A) 후속 회차 1 | [FileStructure §5](../FileStructure.md) |
| CombatCore-FU-25 머쉬맘 수치 | 머쉬맘 수치 조절. 사용자가 CSV에서 직접 조절하며 AI 작업이 아니다 | [Plan §21 부채](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) |
| 부채 처리 시점 | 위 FU-04~FU-22를 언제 다룰지. → 2026-11-19 사용자 결정: 3단계 전에 먼저 처리. 항목별 분류·회차는 [후속 처리 계획](#후속-처리-계획2026-11-19) | 이 문서 |

에셋 목록의 최종 위치(8단계 전 결정)는 [로드맵 8단계 시작 전 결정 사항](../DevelopmentRoadmap.md#8-콘텐츠-데이터-제작)에서 관리한다.

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
  - 후속 회차 2: 범위 확정(FQ-3 (가)). 회차 1이 끝난 뒤(reviewer 판정, 회차 종료 커밋, 사용자 V11) 시작한다. 시작할 때 planner는 범위 확인만 한다.
  - 후속 회차 3: 회차 1에 합쳤다(FQ-2).
  - 후속 회차 4: 열지 않는다(FQ-4·FQ-5·FQ-6 모두 (가)).
- run: `.pipeline/20261119-combatcore-followup/run.md`. 기준 버전 16d70b3.
- WorkRecord: [CombatCoreWorkRecord](../WorkRecords/CombatCoreWorkRecord.md). 후속 처리 회차 기록이며 2단계 원본(기준 커밋 5efe005)과 다른 새 기록이다.
- 대상 맵은 map01이고 `TileMapMode` 0(MapleTile)이다(근거: [2단계 Feature](../Features/2_CombatCore.md), 2단계 WorkRecord의 MapBuilder 조회). 이 처리는 맵·Body·규칙·수치·입력 계약을 바꾸지 않는다.
- 작업 트리의 `map/map01.map` 변경은 범위 밖이다. 사용자가 "그대로 둠"으로 정했고, 어느 회차 커밋에도 섞지 않는다.

분류:

- **(A)** 지금 처리 가능: 새 규칙·수치 결정 없이 범위와 완료 기준을 정할 수 있다.
- **(B)** 사용자 결정 필요: 값·열 설계·보이는 결과를 바꾸는 선택이 있다. 질문으로만 남긴다.
- **(C)** 지금은 불가 또는 비효율: 뒤 단계 시스템이 없거나 재현 조건이 없다.
- **(D)** 3단계 Plan 작성 때 처리한다.

### 1. 분류

| ID | 분류 | 이유 | 처리 위치·남길 시점 |
| --- | --- | --- | --- |
| FU-03 | (A) | 기존 경고 줄을 실제로 실행해 보는 확인이다. 규칙 변경이 없다 | 후속 회차 1(이동 회귀와 함께) |
| FU-04 | (C) | 새 이름·폴더는 6단계 동작 유형 일반화(FileStructure §3 `Monster/Motions/{TypeName}/`)에서 정해진다. 지금 바꾸면 모델의 script 구성요소까지 두 번 바꾼다 | 6단계 몬스터 동작 일반화 |
| FU-05 | (C) | 새 열 설계가 필요하고, 6단계 동작 일반화와 같은 결정이다 | 6단계 |
| FU-06 | (C) | 사용자가 2026-11-06 "6단계로 미루기"로 정했다. 몬스터 공격 구성 질문 절차가 필요하다 | 6단계 |
| FU-07 | (C) | 두 번째 스킬이 없어 열의 쓰임을 검증할 수 없다 | 스킬 교체 시스템(5단계 액티브 스킬) |
| FU-08 | (B) | 새 표 설계다. 지금은 행별 Weight와 로드 로그 %로 조정한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-09 | (B) | 새 열과 빈 값 기본값을 정해야 한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-10 | (B) | 새 열과 빈 값 기본값을 정해야 한다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-11 | (B) | 새 열을 정해야 하고, 지금의 MotionPlayRate 하나의 뜻이 바뀐다 | FQ-5 (가): 하지 않음, 추적 유지 |
| FU-12 | (B) → 결정됨 | 정지·슬로우 추종 자체는 기존 규칙(GameDesign §4.3 "전투 연출을 모두 정지", §4.2 "행동·모션 진행 ×0.5")과 맞다. 엔진 `_EffectService`에는 재생 중 이펙트를 멈추거나 배율을 바꾸는 API가 없다(`PlayEffect`·`PlayEffectAttached`·`RemoveEffect`만 있음). 사용자가 FQ-3에서 (가) 기존 이펙트 유지 방식을 골랐다 | 후속 회차 2 |
| FU-13 | (B) | 착지 정지는 판정 뒤 시각을 바꾼다(2단계 Plan §22.13 "사용자 결정"). f4 잘림은 V11에서 수락됐다 | FQ-4 (가): 바꾸지 않음, 추적 유지 |
| FU-14 | (C) | 재현 0/28이고 재현 조건이 없다 | 사용자 "가끔 멈춤" 보고 또는 지연 있는 실접속·모바일 회차(늦어도 7단계) |
| FU-15 | (C) | 보이는 문제가 측정되지 않았다. 없애려면 구동 방식을 바꾸고 D-Q6을 다시 증명해야 한다 | 프레임 이벤트에 기대는 새 기능을 만들 때(6단계 동작 일반화 후보) |
| FU-16 | (C) | 속도 기반 이동은 시각·착지 x·D-Q6 재증명이 필요한 새 결정이다. 6단계 일반화가 이동 구조를 다시 정하므로 그때 한 번에 보는 것이 효율적이다 | 6단계 몬스터 동작 일반화. 앞당기려면 (B)로 바꿔 사용자가 정한다 |
| FU-17 | (A) | 기록만 하고 읽지 않는 필드 1줄 제거다(`PlayerCombatComponent` 268행, 읽는 곳 0 Grep 확인). 동작이 같아야 한다 | 후속 회차 2 |
| FU-18 | (D) | 다음 Plan 작성 원칙이다. **이 절의 회차별 완료 기준에 먼저 적용했다**(각 회차 "스크린샷" 줄) | 3단계 Plan 작성 때도 적용 |
| FU-19 | (A) | `SetGuarding`의 상태 기록을 연출 호출 앞으로 옮기는 순서 정리다. 가드 판정·연출 1회 결과가 같아야 한다 | 후속 회차 2 |
| FU-20 | (B) | 경고 문구에 칸·값을 넣는 것은 새 요구다(2단계 Plan §24.12) | FQ-6 (가): 하지 않음, 추적 유지 |
| FU-21 | (C) | 액티브 스킬 선택 시스템이 아직 없다 | 5단계 |
| FU-22 | (D) | 플레이어 HP 0 종료·승패는 3단계 범위다(GameDesign §4.2 끝) | 3단계 Plan 작성 때 후보로 검토 |
| FU-23 | (A) | 문서 문구 정리다. 원장 규칙(maplestory-skill-maker execution-core "Required progress ledger")에 낡은 내용 정리 조항이 없어 범위를 이 계획이 정한다. 사용자가 FQ-7에서 기본안을 골랐다 | 후속 회차 1 |
| FU-24 | (A) | DataSet 6종과 그 밖의 기존 파일(로더 3개·UI 2개) 이동, `@Assist` 계열 정리다. 대상·위치는 사용자가 승인한 [FileStructure §5](../FileStructure.md)이고, 참조는 경로가 아니라 이름·키다(아래 조사). 이동은 AI, Maker 동기화는 사용자다(FQ-1). 그 밖의 이동도 회차 1에 넣는다(FQ-2) | 후속 회차 1 |

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

### 3. 회차 계획

순서: **후속 회차 1 → 2**. 회차 3은 회차 1에 합쳤고(FQ-2), 회차 4는 열지 않는다(FQ-4~6). 회차마다 coder → 같은 버전 tester → reviewer → 사용자 V11로 돈다. 커밋 단위는 CLAUDE.md 기준을 따른다(`[CombatCore][code]` → `[CombatCore][review]`).

순서 이유:

- 회차 1은 사용자가 먼저 이름 붙인 항목이고, 코드 내용 변경이 없다(위치만 바뀜).
- 회차 2는 코드 정리다. 고칠 파일(PlayerCombatComponent·PlayerGuardComponent·MonsterAttackMotion 등)은 회차 1의 이동 대상이 아니다.

#### 후속 회차 1 — 기존 파일 이동·원장 문구·열 누락 경고 실행

**요구 ID**: CombatCore-FU-24(DataSet 6종·로더 3개·UI 2개 이동, `@Assist` 계열 정리), FU-03, FU-23.

**승인**: 2026-11-19 사용자 순서 지시와 FQ-1·FQ-2·FQ-7 답(위 "근거·상태").

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
   - `map/map01.map`은 회차 시작 때 해시 그대로이고 커밋에 섞지 않는다.
   - 다른 재저장은 분리해 기록한다.
9. 원장: Grep으로 편집 전 23·24행에 해당하는 줄에 `castleenemy`가 없고, 주석 1줄이 있으며, DATA-02 줄이 `Catalog/CombatRuleCatalog`를 가리킨다. 그 밖의 줄은 바뀌지 않았다(diff).

**완료 기준 — 사용자**

- 진행 조건: 1차·2차 Maker 동기화를 하고 완료를 알린다. 2차 때 빈 `@Assist`·`Player/@Assist` 폴더가 남았으면 Maker에서 지운다.
- V11 작업 공간: DataSet 폴더에 표 8개, Catalog 폴더에 스크립트 3개, UI 폴더에 스크립트 4개가 하나씩만 보인다. 옛 위치(`@Assist`, `Player/@Assist`, MyDesk 바로 아래 UIPopup·UIToast, Combat의 CombatRuleCatalog)에 항목이 없다. AI는 작업 공간 창을 볼 수 없다.
- V11 플레이: 전투·팝업·토스트 화면이 이전과 같다.

**스크린샷(FU-18)**: 0장. 화면이 바뀌지 않는 회차이고, 입력은 키 입력·프로브로 하므로 좌표가 필요 없다. 팝업·토스트 표시는 [VRF]와 Enable 프로브로 본다. 다른 목적의 스크린샷이 필요하면 찍기 전에 멈추고 메인에 묻는다.

**중단 조건**(대안 구현이나 자동 되돌리기 없이 그 상태에서 멈추고 메인에 돌려줌)

1. 1차 확인 실패: PlayerBaseStatData의 GetTable이 nil이거나 한쪽이라도 [VRF]가 없다. 또는 `_UIToast`가 nil이다.
2. 같은 이름 항목이 둘인 징후: build 경고, 옛 위치 파일이 다시 생김, 다른 위치에 새 `.codeblock`(새 Id)이 생김.
3. 래퍼의 id·EntryKey·name·serveronly, 또는 `.codeblock`의 EntryKey·Id·Name이 바뀌었다.
4. 동기화 뒤 build 오류(스크립트 미등록, Symbol not found 등)가 난다.
5. 표를 다시 만들거나 `.mlua`·`.codeblock`·`.directory`·`.model`·`.map`·`.ui`를 고쳐야 한다.
6. FU-03 복원 뒤 SHA-256이 다르다.
7. `map/map01.map` 내용이 회차 중에 바뀌었다.
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

**회차 종료 때 문서 정리(planner)**

- FileStructure §4(회차 기록), §5(완료 표시), §7(빈 폴더 결과);
- [2단계 Feature](../Features/2_CombatCore.md) 데이터 계약 "위치" 열(`DataSet/`);
- 현재 문서의 경로·링크:
  - Features/0_CombatPause.md(UIPopup·UIToast 링크);
  - Plans/MonsterCombat.md(MonsterData.csv 링크);
  - AssetList.md(패턴 표 경로);
- 이 계획의 FU-03·FU-23·FU-24 행.
- 지난 기록(WorkRecord 이전 절·run)은 고쳐 쓰지 않는다.

#### 후속 회차 2 — 플레이어 공격·가드 코드 정리 + FU-12 이펙트 정지·슬로우 추종((가) 방식)

**요구 ID**: CombatCore-FU-17, FU-19, FU-12(FQ-3 (가) "기존 이펙트 유지 방식").

**시작 조건**: 회차 1이 끝난 뒤(reviewer 판정, 회차 종료 커밋, 사용자 V11). FU-12가 같은 파일(PlayerCombatComponent·PlayerGuardComponent)을 고치므로 세 항목을 한 회차에서 한 번에 고친다.

**바꿀 파일**

- `Player/PlayerCombatComponent.mlua`: `self._T.resolveIndex = index` 한 줄을 지운다.
- `Player/PlayerGuardComponent.mlua` `SetGuarding`:
  - 시작 여부는 기록 전 값으로 판단한다.
  - `self.isGuarding` 기록을 연출 호출보다 앞에 둔다.
  - 시작 시각·시작 x·연출 1회는 그대로다.
- FU-12((가)):
  - `Monster/MonsterAttackMotion.mlua`(눈빛·먼지);
  - 위 두 파일의 이펙트 호출;
  - 정지·재개와 슬로우 시작·끝을 알리는 곳(`Combat/CombatPauseComponent`, `Monster/@StateControl/MonsterStateControl`). 실제로 고칠 파일은 coder가 정하고 개발 절에 적는다.
  - 새 `.model`은 만들지 않는다((가)).

**바꾸지 않을 파일**: 규칙·수치·DataSet·`.ui`·`.map`·`.model`, Player_Attack·Player_Guard·MonsterAttackComponent, 판정·피해 경로, 회차 1에서 옮긴 파일의 위치.

**coder가 정할 것**(FU-12, 승인 범위 안)

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
   - 패링 1회 성공(Pos2), 일반 가드 경감 40% 1회.
   - 연출 표가 무효인 상태는 회차 1의 FU-03 결과로 대신하지 않는다. `SetGuarding` 순서만 바뀌므로 소스 대조로 판단하고, 그렇다고 적는다.
4. FU-12:
   - 팝업 정지 중 눈빛·먼지·플레이어 공격·가드 이펙트의 재생 상태 [VRF];
   - 재개 뒤 남은 구간만 재생되고 끝 시각이 정지 시간만큼 밀리는지;
   - 슬로우 시작·끝 때 재생 중 눈빛의 배율이 ×0.5·×1로 바뀌는지;
   - 재생이 끝난 이펙트를 다시 내지 않는지;
   - 사망·Stop 때 추적이 정리되는지.
5. build 로그 오류 0, git 변경이 범위 파일뿐이다.

**스크린샷(FU-18)**: 목적은 "팝업 정지 중 이펙트가 멈춤/숨김/계속 재생 중 무엇으로 보이는지 확인" 하나다. 이펙트 종류마다 정지 직전·정지 중·재개 직후 3장 안팎, 회차 전체 12장 이하. 그 밖의 용도는 쓰지 않는다.

**사용자 V11**: 팝업 정지 중 이펙트 모습과 슬로우 중 눈빛 속도가 어색하지 않은지 본다.

**중단 조건**

- 판정·피해·가드 결과가 바뀐다.
- 범위 밖 파일을 고쳐야 한다.
- (가) 방식으로 정지·재개를 표현할 수 없다(측정 근거와 함께 메인에 반환).
- 새 모델이 필요해진다.

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
- **(B)·(C)·(D) 행**: 이 계획에 남긴다. 3단계 Plan이 FU-18·FU-22를 맡으면 그 Plan으로 ID를 옮긴다.
- **3단계 시작 조건**: 후속 회차 1·2가 모두 끝나고(사용자 V11 포함), 사용자가 3단계 시작을 지시한다.

## 진행·종료

- 항목을 처리하면 결과를 [2단계 Feature](../Features/2_CombatCore.md)에 짧게 반영하고 이 표의 해당 행을 정리한다.
- 모든 항목을 확인하거나, 사용자 승인으로 다른 계획에 옮기거나 처리 방법을 정한 뒤에 이 계획을 삭제한다.
- 다른 단계 Plan이 항목을 맡으면 그 Plan에 ID를 그대로 옮기고 이 표에는 이동 위치만 남긴다.
