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
- 항목의 원문·당시 근거는 [2단계 Plan](2_CombatCore.md)과 [CombatCore WorkRecord](../WorkRecords/CombatCoreWorkRecord.md)에 있다. CombatFoundation-F07은 2026-11-19 닫혔으므로 두 문서의 삭제 여부는 사용자가 정한다. 삭제할 때는 이 표의 원문 링크를 Feature나 커밋 기준으로 바꾼다.

상태: **NOT_RUN** = 하지 않음(통과 아님) / **대기** = 조건·사용자 결정 대기.

## 미실시 확인 (NOT_RUN, PASS로 세지 않음)

| ID | 상태 | 실행 시점·확인 기준 |
| --- | --- | --- |
| CombatCore-V11(모바일·실기기 부분) | NOT_RUN(2026-11-19 사용자가 하지 않기로 함) | **시점**: 모바일 실기기 연결 때. 늦어도 7단계 헤네시스 기준 PC·모바일 검증. **기준**: [Plan §7](2_CombatCore.md) V11의 남은 부분. 예고 방향·속성 구별, 0.20초 타이밍·반격 체감, 실제 터치와 키·터치 혼합 조작, 버튼 크기·화면 잘림, HP·피해 숫자 가독성, 피격·die 연출, 음향. PC(Maker) 부분은 회차별로 수락됐다. CombatFoundation-F07의 모바일 연출도 이 행에서만 추적하며 F07은 다시 열지 않는다 |
| CombatCore-V12(실제 외부 환경 부분) | NOT_RUN(2026-11-19 사용자가 하지 않기로 함) | **시점**: 비전투 몬스터나 다른 플레이어가 같은 맵에 있는 환경이 생길 때. 4단계 Run 격리 또는 다중 접속 확인 회차. **기준**: 현재 상대 외 개체에 공격·슬로우·그로기·UI가 퍼지지 않는다. 단일 참조·교체·사망 뒤 무효 부분은 AI PASS(QA1). 검증을 위해 다중 전투 체계를 새로 만들지 않는다 |
| CombatCore-FU-01 | NOT_RUN | **시점**: 지연 있는 실접속·모바일 확인 회차. **기준**: 실접속 지연에서 Pos2 경계(±0.75, 이동 속도 12에서 약 0.0625초에 지남)의 저스트·패링 판정 위치가 화면과 맞다. 출처는 [Plan §21](2_CombatCore.md) 위험과 §22.14 NOT_RUN |
| CombatCore-FU-02 | NOT_RUN | **시점**: 맵이 늘어나는 단계(4단계). **기준**: 맵 이동 뒤 복귀·재접속 때 플레이어 최대 HP가 PlayerBaseStatData 값과 같다. 출처는 회차 B NOT_RUN([Plan §20](2_CombatCore.md)) |
| CombatCore-FU-03 | NOT_RUN | **시점**: DataSet 로더를 다시 고치는 회차. **기준**: 필수 열 누락 경고 한 줄을 실제로 실행해 확인한다. 지금은 결과 경로만 런타임으로 확인했고 경고 줄은 소스로 판단했다. 출처는 [Plan §24.9](2_CombatCore.md) |

CombatFoundation-F07은 2026-11-19 사용자 "기존 수락으로 닫기"로 완료해 이 표에서 뺐다(PC Maker 기준). 상태와 근거는 [CombatFoundation](CombatFoundation.md)에서만 관리하고, 모바일·실기기 연출은 위 CombatCore-V11 행이 맡는다.

## 부채·남은 과제 (구현 승인 아님)

원문은 [Plan §21 부채](2_CombatCore.md)·§22.13·§24.12다. 다시 볼 조건이 오면 사용자 승인으로 새 회차 범위를 정한다.

**스크립트·데이터 구조**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-04 | OrangeMushroomAttack 스크립트와 `Monster/OrangeMushroom` 폴더 이름 정리 | 6단계 몬스터 동작 일반화 |
| CombatCore-FU-05 | 피격 가능 구간 선언을 패턴 데이터로 옮길지 | 6단계 |
| CombatCore-FU-06 | 주황버섯(일반 몬스터)의 공격 패턴·스폰·MonsterData·MonsterStatData 행 | 6단계. 사용자가 planner 질문 절차로 정한다(2026-11-06 "6단계로 미루기") |
| CombatCore-FU-07 | 스킬별 타격 간격·프레임 지연 열 | 스킬 교체 시스템 단계 |
| CombatCore-FU-08 | 묶음(1·2·3칸) 단위 비율 표 | 사용자 요청 때. 지금은 행별 Weight로 조정한다 |
| CombatCore-FU-17 | PlayerCombatComponent `_T.resolveIndex` 제거(기록만 하고 읽지 않음) | 그 파일을 고치는 회차에서 함께 |

**연출·소리 조절**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-09 | 효과음 음량 열 | 사용자가 음량 조정을 원할 때 |
| CombatCore-FU-10 | 이펙트 배율·위치 열 | 사용자가 조정을 원할 때 |
| CombatCore-FU-11 | 클립·이펙트 재생 배율 분리 열(예: EffectPlayRate) | 사용자가 둘을 따로 조정하길 원할 때. 지금은 MotionPlayRate 하나가 둘에 같이 쓰인다 |
| CombatCore-FU-12 | 일시정지 중 이펙트 정지와 재생 중 이펙트의 슬로우 변화 추종(3칸 눈빛 포함, 회차 E 가드 이펙트 포함) | 이펙트 일시정지 부채를 다루는 회차 |
| CombatCore-FU-13 | 접근 클립 마무리 프레임(f4) 표시와 착지 순간 정지 0 | 사용자가 f4가 잘리거나 착지가 어색하다고 할 때. 착지 정지는 판정 뒤 시각을 바꾸는 사용자 결정이다 |
| CombatCore-FU-20 | 연출 표(PlayerActionFxData) 경고에 칸·값 넣기 | 사용자가 요청할 때만(새 요구) |
| CombatCore-FU-21 | 위 공격 버튼 아이콘을 선택한 액티브 스킬 아이콘으로 연결. 지금은 칼 아이콘 | 액티브 스킬 선택이 생기는 단계(5단계) |

**동작 관찰**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-14 | 관찰 O-1. 간헐적으로 클라이언트 접근이 멈춘다. 원인 미확인, QA14에서 재현 0/28 | 사용자가 "가끔 멈춤"을 보고하거나, 실접속·모바일 회차에서 재현될 때 |
| CombatCore-FU-15 | 관찰 O-3. 구동 프레임 이벤트가 같은 ms에 2건 도착한다 | 프레임 이벤트에 기대는 새 기능을 만들 때, 또는 화면 문제로 확인될 때 |
| CombatCore-FU-16 | 접근·복귀 이동을 서버 `OnUpdate`에서 매 틱 `SetPosition`으로 처리한다 | V11·실접속에서 끊김이 다시 보일 때. 6단계 몬스터 동작 일반화와 함께. 속도 기반 이동은 재증명이 필요한 새 결정이다 |
| CombatCore-FU-19 | PlayerGuardComponent.SetGuarding에서 연출 호출이 상태 기록보다 앞에 있다. 리뷰 비차단 메모이며 결함이 아니다 | 이 함수를 다시 고치는 회차 |

**문서·운영**

| ID | 내용 | 다시 볼 조건·시점 |
| --- | --- | --- |
| CombatCore-FU-18 | 화면 표시 확인이 완료 기준에 있으면, 그 확인용 스크린샷의 허용 범위(목적·대략 장수)를 완료 기준에 함께 적는다 | 다음 Plan 작성 때(planner, 3단계 Plan 포함) |
| CombatCore-FU-22 | 범위 밖 관찰. 플레이어 쪽 피해에 남은 HP 상한이 없고, 사망 직후 플레이어 HP 문자가 음수로 보일 수 있다(화면 미관찰) | 3단계 Plan 작성 때 후보로 검토(플레이어 HP 0 종료·승패) |

## 사용자 결정 대기

| 항목 | 내용 | 원문 |
| --- | --- | --- |
| 3단계 시작 | 2단계 완료 뒤 다음 로드맵 단계. 사용자 시작 지시 대기 | [로드맵](../DevelopmentRoadmap.md) |
| CombatCore-FU-23 원장 문구 | `.maplestory-skill-maker-ledger.md`의 낡은 castleenemy 문구를 정리할 시점 | [Plan §23.6](2_CombatCore.md) |
| CombatCore-FU-24 기존 파일 이동 | 기존 DataSet 6종을 `@Assist/DataSet/`에서 `DataSet/`으로 옮길 회차와, 그 밖의 기존 파일 이동 | [FileStructure §5](../FileStructure.md) |
| CombatCore-FU-25 머쉬맘 수치 | 머쉬맘 수치 조절. 사용자가 CSV에서 직접 조절하며 AI 작업이 아니다 | [Plan §21 부채](2_CombatCore.md) |
| 부채 처리 시점 | 위 FU-04~FU-22를 언제 다룰지 | 이 문서 |

에셋 목록의 최종 위치(8단계 전 결정)는 [로드맵 8단계 시작 전 결정 사항](../DevelopmentRoadmap.md#8-콘텐츠-데이터-제작)에서 관리한다.

## 연결된 외부 추적 ID

이 계획에서 상태를 바꾸지 않는다. 2단계 완료나 V11 회차 수락만으로 완료 처리하지 않는다. 사용자가 명시적으로 결정한 항목만 원 계획에서 상태를 바꾼다.

- [CombatFoundation](CombatFoundation.md): F01 재시작 경고, F02 배포 개발 도구 차단, F03 실제 맵 전환, F04 PC·모바일 UI, F05 성능 실측. F07 피해·표시 일치는 2026-11-19 사용자 결정 "기존 수락으로 닫기"로 완료(PC Maker 기준, 모바일은 위 CombatCore-V11).
- [CombatPause](CombatPause.md): F01 실제 맵 전환, F02 PC·모바일 화면·음향.

## 진행·종료

- 항목을 처리하면 결과를 [2단계 Feature](../Features/2_CombatCore.md)에 짧게 반영하고 이 표의 해당 행을 정리한다.
- 모든 항목을 확인하거나, 사용자 승인으로 다른 계획에 옮기거나 처리 방법을 정한 뒤에 이 계획을 삭제한다.
- 다른 단계 Plan이 항목을 맡으면 그 Plan에 ID를 그대로 옮기고 이 표에는 이동 위치만 남긴다.
