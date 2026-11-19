# 2단계 — CombatCore — 전투 핵심

## 현재 결과

2026-11-19 사용자 결정 **“모바일연결이나 멀티환경 테스트는 하지는 않음. 그래도 2단계 완료는 해도 될것 같음.”**을 반영해 2단계를 완료했다. 플레이어 1명과 현재 상대 머쉬맘 1개체가 map01(MapleTile, `TileMapMode=0`)에서 예고 → 대응(회피·가드·저스트 회피·패링) → 성공 피드백 → 직접 공격 보너스로 이어지는 전투 한 판의 핵심이 동작한다. 슬로우·그로기, 판정 수치·플레이어 기본 수치·몬스터 수치·패턴·연출의 DataSet화, 조작 버튼 테마와 가드 연출까지 포함한다.

한계:

- V11의 모바일·실기기 터치 부분과 V12의 실제 외부 환경(비전투 몬스터·다른 플레이어) 부분은 사용자가 하지 않기로 했다. **NOT_RUN**이며 통과로 세지 않는다.
- [CombatFoundation-F07](../Plans/CombatFoundation.md)(피해·표시 일치)은 2026-11-19 사용자 결정으로 닫았다. **PC Maker 기준**이며, 모바일·실기기 연출은 V11 모바일 부분(NOT_RUN)으로 남는다.
- 승패·정산은 3단계, 암전·Stage 전환은 4단계 범위다. 3단계는 사용자 시작 지시 대기다.
- 남은 확인·부채는 [2단계 후속 계획](../Plans/CombatCore.md)에서 추적한다.

## 사용·조절 방법

### 입력 계약

| 입력 | 동작 |
| --- | --- |
| ↑ / W / 위 버튼 | 기본 공격(AttackSkillData 1행, 10타). 저스트 회피·패링 성공 뒤 2.0초 안에 시작한 다음 유효 시전 1회의 전체 타격에 ×2.2를 적용한다. 보너스는 시전 시작에 소비되며 빗나가도 소비된다 |
| ↓ / S / 아래 버튼 | 가드 홀드. 패링 속성 공격의 판정 직전 0.20초 안에 시작하면 패링이다 |
| ← / A / 왼쪽 버튼, → / D / 오른쪽 버튼 | 뒤·앞 회피(BattlePos1·3으로 이동). 판정 직전 0.20초 안에 유효 방향으로 시작하면 저스트 회피다 |

- 입력 수락·홀드 합산·복귀 잠금·예약 없음은 [1단계](1_MovementInput.md), 팝업 중 정지는 [0단계](0_CombatPause.md) 계약을 그대로 따른다.
- 저스트 회피·패링은 두 조건을 모두 만족해야 성공한다. 입력을 시작한 순간 플레이어가 2번 칸(중심 ±0.75) 안에 있어야 하고, 그 공격 범위가 2번 칸을 포함해야 한다. 끝 칸을 치는 1칸 공격에는 보상이 없다.
- 슬로우(2.0초 ×0.5)와 그로기(1.5초)는 현재 상대에게만 적용한다. 그로기는 패링 뒤 처음 위치로 복귀를 마친 시점부터 시작한다. 판정·피해 규칙 원문은 [GameDesign §4.2](../GameDesign.md)다.

### 표시 계약

- 예고: 맞는 BattlePos 칸만 예고 시작부터 판정까지 반투명 속성색으로 표시한다(일반 노랑·특수 적색·패링 보라). 예고 문구는 없다.
- 결과: 저스트 회피 성공·패링 성공·가드·피해 경감·회피·피격·가드 불가·반격 준비, 상대 그로기·슬로우 문구.
- 패링: 머리 위 별 표시를 키우고, 접촉 지점에 파티클을 한 번 낸다. 그로기 동안은 hit 클립을 보인다.
- 사망: die를 한 번 재생하고 끝 프레임에서 멈춘다.
- HP: 플레이어·몬스터 HP 바에 현재/최대를 표시한다. 피해 숫자는 실제 HP 감소와 같다.
- 머쉬맘 연출(패턴 표의 값):
  - 1칸 공격: jump 모션과 player 점프음.
  - 2칸 공격: attack1 모션.
  - 3칸 가드형: skill1 모션. 눈빛 이펙트는 예고 때, 먼지 이펙트는 착지 때 보인다.
  - 피격음·플레이어 피격음·사망음은 MonsterSoundData의 값이다.
- 조작 버튼: simplefantasy 원형 배경에 흰 아이콘(↑ 칼, 나머지 화살표).
- 가드: alert 모션. 가드를 시작할 때 로얄 가드 이펙트·효과음을 한 번씩 낸다.

### 데이터 계약

CSV를 고친 뒤 Maker Refresh → Play로 반영한다. 경로는 `RootDesk/MyDesk/` 기준이다.

| 표 | 위치 | 열(id 제외) | 현재 행 |
| --- | --- | --- | --- |
| CombatRuleData | `@Assist/DataSet/` | JustWindowSec, ParryWindowSec, GuardDamageRate, CounterWindowSec, CounterDamageMultiplier, SlowDurationSec, SlowRate, GroggyDurationSec | default 0.20·0.20·0.40·2.0·2.2·2.0·0.5·1.5 |
| PlayerBaseStatData | `@Assist/DataSet/` | MaxHp, MoveSpeed, ReturnSpeed | default 100·12·12 |
| AttackSkillData | `@Assist/DataSet/` | name, ruid, FrameCount, Direction, Damage, AttackCount | 1 player.basic(Damage 1·AttackCount 10) |
| MonsterData | `@Assist/DataSet/` | name, modelid | 1 머쉬맘 `model://mushmom` |
| MonsterStatData | `@Assist/DataSet/` | MaxHp, AttackDamage, AttackInterval | default·mushmom 100·12·3.0 |
| MonsterAttackPatternData | `@Assist/DataSet/` | modelId, ResponseType, AttackAttribute, AreaFromAnchor, AreaToAnchor, AreaPaddingX, AreaHeight, AreaOffsetY, TelegraphLeadSec, Weight, AreaTarget, MotionClip, AttackSound, EffectClip, MotionPlayRate, JumpStartFrame | mushmom 5행(parry.left·parry.right·parry.any·special.random·parry.guard) |
| MonsterSoundData | `DataSet/` | DamagedSound, HitPlayerSound, DieSound | mushmom |
| PlayerActionFxData | `DataSet/` | EffectClip, EffectSound | guard |

- **CombatRuleData·패턴 표**: 열 누락·빈 값·잘못된 수·중복 id·맞지 않는 조합이 있으면 해당 동작을 거부하고 경고를 1회 남긴다. 이전 캐시나 일부 행으로 실행하지 않는다.
- **MonsterStatData**: 빈 칸은 default 행 값을 쓴다.
- **PlayerActionFxData**: 빈 칸은 그 연출만 없다. 형식 오류나 행 없음이면 경고 1회 뒤 가드 연출만 끄고 전투는 계속한다.
- **Weight**: 상대값이다. 한 패턴의 확률은 그 Weight ÷ 같은 몬스터 Weight 합이다. 현재 4·4·5·3·4이고, 로드 로그에 비율을 %로 표시한다.
- **AttackInterval**: 공격이 끝난 뒤 다음 공격까지의 대기 시간이다. 공격 시작부터 다음 공격 시작까지는 약 4.0초다.
- **열 의미·검증 규칙**: 상세는 [Plan §5](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)와 회차별 절(§20·§21·§22·§24)이다.

### 최종 값이 있는 곳

- **판정·피해·시간**: CombatRuleData.
- **패턴별 범위·예고 시간·비중·모션·효과음·이펙트·재생 배율**: MonsterAttackPatternData.
  - 2·3칸 행: TelegraphLeadSec 1.571429, MotionPlayRate 0.7.
  - 1칸 행: 0.5, 1.
- **도약 조절 항목**: 데이터가 아니라 스크립트 속성 기본값이다.
  - OrangeMushroomAttack: JumpDuration 0.5, JumpHeight 0.8, LeapJumpHeight 0, EqualizeLeapFrames·EaseLeapMove·WindupHittable true.
  - MonsterAttackMotion: EffectWindupLastFrame 6·EffectDustFirstFrame 8.
  - 확정 표는 [Plan §22.16.9](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)다.
- **BattlePos1/2/3**: map01 엔티티 위치(X -1.5/0/1.5)다. Pos2 경계 ±0.75와 기준점 간격은 DataSet이 아니다. 이동 시점은 [로드맵 §3](../DevelopmentRoadmap.md)의 "2:" 절을 따른다.
- **에셋**: 모든 RUID는 임시·출시 미확정이다. 목록은 [AssetList](../AssetList.md), 파일 위치 기준은 [FileStructure](../FileStructure.md)다.
- **기존 모델**: 주황버섯 모델(`orangemushroom`)은 패턴·스폰 없이 남아 있다. 6단계에서 다룬다.

## 본인 결정·플레이 피드백

**전투 규칙**

- 2026-10-20: D01~D04를 선택·답변으로 정했다. 대응·0.20초 창·가드 잔여 40%·반격 2.0초 ×2.2·슬로우·그로기, 그리고 1:1 상대 고정이다.

**V11 피드백으로 바꾼 것 (2026-11-02~11-04)**

- 2026-11-02 부분 V11: 패링 뒤 복귀를 마친 다음 그로기를 시작하게 바꿨다. 맞는 칸 표시, 별 확대와 패링 파티클, 그로기에 기존 hit 모션 사용도 정했다.
- 2026-11-03:
  - 주황버섯 공격 범위와 1칸 공격을 정했다("1위치 공격은 필수"). 가중치 열도 이때 생겼다.
  - 예고 문구를 없애고 칸을 속성색으로 표시하게 했다.
  - 특수 1칸 무작위 공격 비중 약 1/7, "가드 불가" 문구, die 고정을 정했다.
  - 현재 상대가 머쉬맘이라고 설명했다.
- 2026-11-04 회차 A: die 1회 재생 뒤 정지를 정했다. 범위 밖 저스트가 "너무 쉬움"이라는 평가에서 Pos2 성공 조건을 정했다. V11은 "전부 ok"로 수락했다.

**회차 B·C·C2 (2026-11-05~11-08)**

- 2026-11-05 회차 B: 수치 DataSet화를 "전부 ok"로 수락했다. 공격 간격의 의미는 생각한 것과 같다고 확인했다.
- 회차 C:
  - 실제 머쉬맘 리소스로 바꾸고, 피격 규칙 충족형으로 바꾸고, 범위 도구를 지우기로 정했다.
  - 플레이어 기본 수치는 직접 100·12·12로 바꿨다.
  - 2026-11-06에 수락했다.
- 2026-11-08 회차 C2: 주황버섯 모델 이름을 Maker에서 직접 바꾸고 수락했다.

**회차 D·D2 (2026-11-05 결정 ~ 2026-11-16 수락)**

- 패턴별 모션, 3칸 가드형 공격, 비중 4·4·5·3·4, 효과음 종류를 정했다.
- 2·3칸 속도는 "원작 속도 1배"를 거쳐 0.7배로 정했다.
- 도약은 "조절 항목으로 넣고 비교"를 요구했다.
- 1칸 공격음을 player 점프음으로 바꿔 달라고 요청했다.
- 2026-11-16 "점프음 확인 완료"로 수락했다.

**회차 E (2026-11-06 선택, 2026-11-19 수락)**

- 버튼 메이플 테마와 가드 alert·이펙트·효과음을 골랐다.
- 2026-11-19 Maker 26.11에서 "다른 건 다 좋음"으로 수락했다. 무기 없을 때 공격·가드 모습이 같은 점과 이펙트 첫 프레임 흰 세로선도 수락 범위다.

**2단계 완료 (2026-11-19)**

- 모바일·다중 환경 시험 없이 2단계 완료를 결정했다.
- CombatFoundation-F07 실제 연출 평가(피해 숫자 가시성·피격·die 연출)를 "기존 수락으로 닫기"로 정했다. 회차 C V11 8번(모바일·터치·사운드·CF-F07) "이상 없음"(2026-11-06)과 회차 D·E의 PC 수락을 F07 완료로 인정했다. 평가 기준은 PC Maker이고, 모바일·실기기는 V11 모바일 부분 NOT_RUN으로 추적한다.

**이 문서에 없는 평가**

- 사용자 평가는 위 답변에 있는 것만 적는다.
- 회차 B에서 CSV를 직접 고쳐 봤는지는 확정되지 않았다.
- 기기·모바일별 관찰은 없다.

원인 분석·구현·자동 검증·독립 QA·리뷰는 AI 수행이다.

## 반영 결과·확인 범위

AI / 2026-10-24~2026-11-16 / map01·MapleTile / Maker server_main·client. coder 기본 검증 뒤 같은 버전으로 독립 QA 1~15회차와 독립 리뷰를 거쳤다. 최종 리뷰 판정은 2026-11-19 WAITING이며 결함은 없다. 실행 조건이 붙은 PASS는 그 조건에서만 유효하다. 상세는 [WorkRecord QA 기록](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md#qa-기록)·[리뷰 기록](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md#리뷰-기록)과 [Plan §7](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)이다.

| 검증 ID | 결과 |
| --- | --- |
| V01 예고·대응 | PASS. QA1 유효 행 전수 이후 패턴 변경마다 회귀. 현재 머쉬맘 5행 |
| V02 방어·피해 단일 적용 | QA1 FAIL(QA-F01, 치명 피해에서 숫자 불일치)를 수정한 뒤 QA2·QA3 PASS. HP 감소 = HitEvent 합 = 피해 숫자(DEFENSE 150 포함). CombatFoundation-F07의 수치 근거 |
| V03 타이밍·방향 경계 | PASS(실행 조건). 회차 A의 Pos2 조건은 QA8. 사람 손 0.20초 입력은 회차 A V11에서 사용자 확인. 모든 네트워크 도착 순서는 NOT_RUN |
| V04~V07 반격·슬로우·그로기·팝업 | PASS(실행 조건, QA1·QA2 외 회차별 회귀) |
| V08 사망·Stop·재진입 | PASS(실행 조건). 실제 다른 맵 전환은 NOT_RUN |
| V09 DataSet 반영·오류 거부 | PASS. 런타임 스키마는 QA1, CSV 변경 반영은 coder·QA9. 필수 열 누락 경고 줄은 직접 실행하지 않음(NOT_RUN) |
| V10 키·버튼 입력 | PASS(실제 키·마우스). 회차 E 버튼 교체 뒤 QA15 회귀. 모바일 다중 터치는 NOT_RUN |
| V11 사용자 직접 평가 | 사용자 / Maker(PC) / 2026-11-02~11-19 회차별 수락. **모바일·실기기 터치 부분은 NOT_RUN(사용자가 하지 않기로 함)** |
| V12 상대 격리 | AI PASS(QA1): 단일 참조·상대 교체 시 이전 참조 무효·사망 뒤 상대 없음에서 공격·효과 거부. **실제 비전투 몬스터·다른 플레이어 환경은 NOT_RUN(사용자가 하지 않기로 함)** |

- **주요 버전**:
  - 회차 A 7f2d0b4.
  - 회차 B 1b4f4ee.
  - 회차 C 종료 b93e2ac.
  - 회차 C2 7a796aa.
  - 회차 D·D2 마지막 제품 5ce65d6.
  - 회차 E coder 3e29a35, 리뷰 a81afcf.
  - 회차 E 종료 문서 정리 daf7c42.
- **그 밖의 NOT_RUN**(통과로 세지 않음):
  - 지연 있는 실접속에서의 위치 동기화.
  - 맵 이동 뒤 복귀·재접속 때 플레이어 최대 HP.
- **추적 위치**:
  - 위 NOT_RUN과 V11 모바일 부분(CF-F07의 모바일 연출 포함): [후속 계획](../Plans/CombatCore.md).
  - 실제 맵 전환: [CombatFoundation-F03](../Plans/CombatFoundation.md)·[CombatPause-F01](../Plans/CombatPause.md).
  - 기기 전반 UI·음향: [CombatFoundation-F04](../Plans/CombatFoundation.md)·[CombatPause-F02](../Plans/CombatPause.md).
- 이 결과는 경사·다른 Body 모드·다중 상대·성능 개선을 입증하지 않는다.

## 역할

- 본인: 전투 규칙 D01~D04와 회차별 변경 결정, 머쉬맘·버튼·연출 선택, 플레이어 기본 수치 직접 변경, Maker 모델 이름 변경, V11 직접 플레이·수락, 2단계 완료 결정, CF-F07 닫기 결정.
- AI: 계획·구현·원인 조사·Maker 자동 검증·독립 QA·리뷰·문서 이관.
- 엔진·외부 자료: 네이티브 공격·피격·HP·FSM·동기화, MSW 리소스(머쉬맘·효과음·이펙트·UI 테마, 모두 임시 에셋).
