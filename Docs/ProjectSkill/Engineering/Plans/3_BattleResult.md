# 3단계 — BattleResult — 전투 한 방 완성 계획

## 목표·상태

머쉬맘 1개체와의 전투 한 번이 **준비 → 진행 → 승리 또는 패배 → 정산 → 결과 표시**로 한 번씩만 진행된다. 승리하면 처치 경험치를 전투가 끝난 뒤 한 번만 Level·EXP에 반영하고, 결과를 다시 열거나 같은 요청이 두 번 와도 다시 지급하지 않는다. 결과 팝업의 "다시 전투"로 새 전투를 반복할 수 있다. 화면 하단에 메이플식 Level·EXP를 표시한다(회차 2).

- 상태: **Q1~Q16·스크린샷 상한 확정(2026-11-20 사용자 답, 메인 전달). 구현 지시 대기.** 이 Plan의 확정은 구현 승인이 아니다(사용자 "Plan만 커밋"). 회차 1 coder는 아래 [회차 1 시작 조건](#회차-1-coder-절차)을 모두 채운 뒤 시작하며, 남은 조건은 1번(사용자 구현 지시)뿐이다.
- run: `.pipeline/20261120-stage3-battle-result/run.md`(메인 관리). WorkRecord는 구현 승인 뒤 만든다.
- 상위 규칙: [GameDesign §4.2 끝·§6·§7.2·§7.4·§7.6](../GameDesign.md), [로드맵 §2 3단계 행·§3 "3:"](../DevelopmentRoadmap.md).
- 2026-11-20 사용자 결정 Q2("그 판 EXP 전부 회수", "회수는 4단계에서")는 GameDesign §6·§8과 로드맵 §2·§3에, Q1(패배 우선)은 사용자 "둘 다 반영"으로 GameDesign §4.2 끝·§8 전투 구성 행에 반영했다. 그 밖의 규칙·수치는 바꾸지 않았다.

## 이미 정해진 규칙(따름)

| 규칙 | 출처 |
| --- | --- |
| 1인, 각 전투는 플레이어 1명 대 현재 상대 1개체. 단일 소유권 유지, 다중 대상 체계를 만들지 않는다 | GameDesign §1·§4.2, 로드맵 §1 |
| 적 HP 0이면 그 전투 승리. die 1회 재생 뒤 끝 프레임 정지(2단계 완료). 암전·다음 Stage 전환은 4단계 | GameDesign §4.2 끝 |
| 플레이어 HP 0이면 한 판 종료 | GameDesign §4.2 끝 |
| 처치 경험치는 해당 전투 종료 후 정산하고 Level·EXP를 갱신한다. 전투 중에는 즉시 반영하지 않는다 | GameDesign §6 |
| 이미 정산한 경험치는 중복 지급하지 않는다. 전투 종료 정산과 Run 결과를 구분한다 | GameDesign §6, 로드맵 §3 "3:" |
| **사망(실패) 시 그 판에서 얻은 경험치는 전부 회수한다(레벨 되돌림 포함). 구현은 4단계**(2026-11-20 사용자 결정, Q2) | GameDesign §6·§8 |
| 레벨에 따른 스킬 포인트 지급·사용은 5단계 | GameDesign §6, 로드맵 §3 "5:" |
| 전투 HUD 하단에 메이플식 Level·EXP. 전투 중 정산 전 값 유지, 종료 후 반영 | GameDesign §7.4 |
| 결과 화면·암전 중에는 뒤의 전투 입력을 차단한다(키보드·터치 동일) | GameDesign §7.6 |
| 사망·맵 이탈·종료는 재개보다 우선한다 | GameDesign §4.3, [0단계](../Features/0_CombatPause.md) |
| DataSet = 정적 데이터, DataStorage = 플레이어별 결과(5단계 연결) | 로드맵 §1·§3 "5:" |
| 에셋은 MSW 리소스(msw-search)에서 찾고, 없으면 사용자 제공·msw-painter 중 무엇으로 할지 묻는다 | 로드맵 §1 에셋 원칙 |
| 새 애니메이션을 연결하기 전에 기존 세팅 목록을 사용자에게 보여 주고 무엇을 쓸지 묻는다 | 사용자 요청(작업 규칙) |

## 사용자 결정 (2026-11-20, Q1~Q7)

Q10~Q16(모두 (가))과 스크린샷 상한도 같은 날 확정했다. "남은 질문 > 회차 1 결정"과 "회차 1 coder 절차 > 스크린샷 상한"에 있다. Q1은 GameDesign §4.2 끝·§8 전투 구성 행에도 반영했다.

| ID | 결정 | 반영 |
| --- | --- | --- |
| Q1 | **패배 우선.** 같은 판정 순간 양쪽이 HP 0이면 처치를 인정하지 않고 패배, EXP 0 | R04 |
| Q2 | 사망(실패) 시 **그 판 EXP 전부 회수**(레벨 되돌림 포함). **회수는 4단계에서.** 3단계에서는 사망한 전투의 EXP만 0 | R08·R08a, GameDesign §6·§8, 로드맵 §2·§3 |
| Q3 | Level·EXP는 **Play 동안만(서버 메모리)**. 영구 저장은 5단계 | R09 |
| Q4 | 기본안대로: MonsterStatData `KillExp` 열, 새 PlayerLevelData(`Level`, `RequiredExp`), 아래 CSV 값, 이월·다단 상승·최고 레벨에서 더 쌓지 않음 | R06·R07 |
| Q5 | 결과 팝업의 **"다시 전투" 버튼.** 새 머쉬맘, 플레이어는 BattlePos2·최대 HP(패배면 부활) | R12 |
| Q6 | 플레이어는 **쓰러진 채 유지**(자동 부활을 막음). 몬스터는 **공격 취소 뒤 Home 위치에서 stand** | R03 |
| Q7 | **결과 팝업 + 레벨업 토스트**(기존 모양, 정지 요청 없이 엶). 승리는 die 직후, 패배는 쓰러진 직후 | R11 |

## 현재 처리 (2026-11-20 planner 소스 읽기, 기준 198ce80)

- 대상 맵: map01, `TileMapMode` 0(MapleTile), 플레이어 Body `RigidbodyComponent`(근거 [2단계 Feature](../Features/2_CombatCore.md)·2단계 MapBuilder 조회. coder가 시작할 때 다시 확인).
- 전투 시작: 별도 단계가 없다. `Managers/MonsterManager`(맵 @Component)가 `OnBeginPlay`에 MonsterData 행 하나로 몬스터를 한 번 스폰하고, 매 틱 `RefreshDuelPlayer`가 "맵의 유일한 생존 사용자 + 생존 몬스터 + 기본 능력치 준비"이면 대결 쌍을 세운다. 다시 스폰하는 경로는 없다.
- 승리: `Monster/MonsterHealthComponent.ApplyDamage`가 HP 0에서 `IsDead`·사망음·대기 공격 취소·효과 정리·die 클립·`DEAD` 상태를 한 번 처리한다. 그 뒤 승리·정산·결과 처리는 없다.
- 패배: 플레이어 HP·사망은 네이티브 `PlayerComponent`가 소유한다. 플레이어 `DEAD`는 `PlayerStateSet.stateset`의 엔진 StateType(`NSPawnDead`)이고, `PlayerStateControl`이 따로 정한 ActionSheet는 GUARD→alert·ATTACK→attack·MOVE→walk뿐이다(사망 모습은 엔진 기본). 엔진 기본 `RespawnDuration` 5초 뒤 자동 부활하면 대결 쌍이 다시 서서 전투가 저절로 이어진다(2026-11-20 tester 관찰 O-3). 공격이 취소된 몬스터는 그 자리·그 클립으로 남는다([CombatCore-FU-28](CombatCore.md)). 몬스터의 기존 복귀 동작은 `OrangeMushroomAttack`의 Home 포물선 복귀(jump 클립) → stand다.
- Level·EXP: 코드·데이터·UI 모두 없다.
- 팝업·토스트: `UI/UIPopup`·`UI/UIToast`는 있으나 게임 안에서 부르는 곳이 없다([CombatCore-FU-27](CombatCore.md)). `UIPopup`은 전투 정지 요청용이며 서버가 **플레이어 사망 상태면 정지 요청을 거부**한다(`CombatPauseComponent.RequestPopupPause`). 입력 차단은 `PlayerStateControl.SetInputBlocked(blocked, source)`의 출처별 차단이 있다.
- 플레이어 HP 표시: `UI/CombatHpBarController`가 `PlayerComponent.Hp`를 그대로 쓴다. 음수 문자가 보일 수 있다(화면 미관찰, [CombatCore-FU-22](CombatCore.md)).

## 범위

- 포함: 요구 BattleResult-R01~R13(R10은 회차 2). 맵은 map01 하나, 상대는 머쉬맘 하나.
- 제외:
  - Run·Stage 흐름, 방 카드, 암전, 다음 Stage 전환, Run 결과 화면(4단계). **실패 시 그 판 EXP 회수·레벨 되돌림의 실제 처리도 4단계**다. 3단계는 그 처리에 필요한 기록만 남긴다(R08a).
  - 3단계 "다시 전투"는 검증용 임시 경로이며 4단계 방 흐름이 대체한다(추적 `BattleResult-T01`).
  - 메소·드롭·장비 재료·소비아이템 보상(4·6단계). 실패 시 드롭·장비 유지 범위는 여전히 미결정이다.
  - 영구 저장(DataStorage, 5단계). 스킬 포인트, 레벨에 따른 능력치 변화(5단계). 3단계 레벨업은 표시만 한다.
  - 다른 몬스터·중간보스, 방별 상대 배정 규칙의 실제 구현(4·6단계).
  - 전투 중 팝업을 여는 새 기능, 모바일·실기기·다중 접속 확인.
  - [CombatCore-FU-29](CombatCore.md)(도약 균등화 잔존 코드). `OrangeMushroomAttack`을 고치더라도 이 정리는 범위가 아니다.

## 요구

ID 접두사는 `BattleResult-`다.

| ID | 요구 | 회차 |
| --- | --- | --- |
| R01 | **전투 수명 경계.** 서버가 전투마다 `준비 → 진행 → 종료(승리·패배·중단) → 정산 → 결과 표시` 상태를 소유한다. 진행으로 들어갈 때 전투 id를 발급하고, 종료는 전투 id당 한 번만 확정한다. 진행 상태에서만 플레이어 공격·몬스터 공격 시작을 받는다(기존 대결 쌍 규칙 유지). 시작 문구·준비 시간은 없다(Q10 (가)) | 1 |
| R02 | **승리 확정.** 현재 상대의 사망 확정 순간 한 번. 기존 사망 처리(die 1회·정지, 사망음, 대기 공격 취소)를 그대로 쓴다 | 1 |
| R03 | **패배 확정과 표시.** 플레이어 HP ≤ 0 또는 사망 상태가 된 순간 한 번. (a) 엔진 자동 부활을 막고 쓰러진 모습을 결과 표시 동안 유지한다. 부활은 "다시 전투"에서만 한다. (b) 몬스터는 대기 공격·효과를 취소한 뒤 Home 위치에서 stand로 선다. Home으로 가는 방식은 Q15 (가)(기존 복귀 동작). (c) 결과 표시 동안 몬스터는 공격을 시작하지 않는다 | 1 |
| R04 | **동시 전투 불능 = 패배 우선(Q1).** 같은 판정 순간 양쪽이 전투 불능이면 패배로 확정하고 처치를 인정하지 않는다(EXP 0). 서로 다른 순간이면 먼저 확정된 쪽이 결과다 | 1 |
| R05 | **중단.** 맵 이탈·접속 종료·Stop으로 끝난 전투는 승리·패배가 아니며 정산·결과 표시를 하지 않는다. 승리 확정 순간에 이미 끝난 정산은 유지한다 | 1 |
| R06 | **처치 경험치 데이터.** `DataSet/MonsterStatData.csv`에 `KillExp` 열. 빈 칸은 default 행 값. 0 이상의 정수 | 1 |
| R07 | **Level·EXP 데이터와 계산.** 새 `DataSet/PlayerLevelData`(아래 CSV). 시작 Lv1·EXP 0. 남는 EXP는 다음 레벨로 이월하고, 한 번의 정산에서 여러 레벨이 오를 수 있다. 표의 가장 큰 Level이 최고 레벨이며, 최고 레벨이면 EXP를 더 쌓지 않는다(EXP 0 유지, 넘친 양은 버림) | 1 |
| R08 | **전투 종료 정산(1회).** 승리 확정 뒤 서버에서 전투 id당 한 번만 정산한다. 패배·동시 전투 불능은 EXP 0으로 기록만 남긴다. 같은 id 정산 요청이 다시 오면 아무것도 하지 않는다. 클라이언트는 정산을 요청할 수 없다. 결과 표시와 이후 단계는 정산 기록만 읽는다 | 1 |
| R08a | **4단계 회수용 정산 기록(planner 판단, Q2).** 플레이어 서버 메모리에 전투마다 한 줄: `battleId`, `runId`(3단계는 비움), `result`(VICTORY·DEFEAT), `monsterKey`, `killExp`(표 값), `grantedExp`(실제 반영량. 최고 레벨이면 줄어듦), `levelBefore`·`expBefore`·`levelAfter`·`expAfter`. 이유: 4단계 회수는 "판 첫 정산의 Before로 되돌림"이 최고 레벨 상한·이월이 있어도 정확하고, `grantedExp` 합은 결과 화면의 획득 내역 표시에 쓴다. 3단계는 기록만 하고 회수하지 않는다. 기록 수명은 Play 세션 | 1 |
| R09 | **Level·EXP 소유·수명(Q3).** 서버의 플레이어 단위 소유자 하나가 Level·EXP·정산 기록을 바꾸고, HUD·결과 표시용 값을 동기화한다. Play 세션 동안만 유지(Stop·Play 다시 시작이면 Lv1·EXP 0) | 1 |
| R10 | **Level·EXP HUD.** 화면 하단 메이플식 표시. 전투 중에는 정산 전 값, 정산 뒤 새 값. 모양·에셋은 Q8 | 2 |
| R11 | **결과 팝업·레벨업 토스트(Q7).** 기존 PopupGroup·UIPopup·UIToast 모양을 쓰고 **정지 요청 없이** 연다. 승리는 die 재생이 끝난 직후, 패배는 쓰러진 직후에 연다(추가 대기 없음). 팝업 내용: 승리·패배, 상대 이름(MonsterData `name`), 획득 EXP(패배 0), Level·EXP 전→후, 레벨업이면 그 문구, "다시 전투" 버튼(Q16 (가)). 레벨업이면 토스트 1회(문구만, 연출은 Q9·회차 2). 팝업이 떠 있는 동안 전투 입력을 키보드·WASD·화면 버튼 모두 막는다. 결과 표시는 정산 기록을 읽기만 하므로 다시 열어도 지급하지 않는다. 기존 전투 중 정지 팝업 경로는 바꾸지 않는다 | 1 |
| R12 | **다시 전투(Q5, 임시 T01).** "다시 전투" 버튼 → 서버 요청. 서버는 요청자 = 현재 대결 플레이어, 현재 전투 종료됨, 전투 id 일치를 확인한다. 이전 머쉬맘을 지우고 새로 스폰(표 HP), 플레이어는 BattlePos2·최대 HP(패배였으면 부활)로 두고 새 전투 id로 시작한다. Level·EXP·정산 기록은 유지한다. 같은 id로 두 번 오면 두 번째는 무시한다 | 1 |
| R13 | **플레이어 HP 표시 하한(FU-22).** 플레이어 HP 문자·바는 0 아래로 보이지 않는다. 패배 판정은 "HP ≤ 0 또는 사망 상태"로 통일한다. 피해 숫자는 그대로(Q14 (가)) | 1 |

### Q4 값 (CSV, 2026-11-20 사용자 수락)

사용자가 나중에 CSV를 직접 고쳐 바꿀 수 있다(Maker Refresh → Play로 반영, 2단계 표와 같은 방식). 이 값은 규칙이 아니라 데이터다.

`RootDesk/MyDesk/DataSet/MonsterStatData.csv`(열 추가, 기존 값 불변):

```csv
id,MaxHp,AttackDamage,AttackInterval,KillExp
default,100,12,3.0,0
mushmom,100,12,3.0,120
```

`RootDesk/MyDesk/DataSet/PlayerLevelData.csv`(새 표, 첫 열 `id`는 DataSet 규칙. `RequiredExp` = 그 레벨에서 다음 레벨까지 필요한 EXP, 최고 레벨 행은 비움):

```csv
id,Level,RequiredExp
lv1,1,100
lv2,2,150
lv3,3,200
lv4,4,250
lv5,5,
```

- 이 표에는 default 행이 없다. 빈 칸을 default 행 값으로 채우는 기존 규칙 대신, **마지막 행의 빈 `RequiredExp` = 최고 레벨**로 읽는다(다른 행의 빈 칸은 오류).
- 검증(제안, 기존 표와 같은 정책): Level은 1부터 빈틈없이 연속, 최고 레벨 행이 아닌 행의 RequiredExp는 양의 정수, KillExp는 0 이상 정수. 열 누락·잘못된 값이면 경고 1회 뒤 몬스터 스폰을 거부한다(전투를 시작하지 않음). 일부 행·이전 캐시로 진행하지 않는다.
- 이 값이면 첫 승리(120)에 Lv2·EXP 20이 되고, 여섯 번째 승리에 Lv5(최고)에 닿는다.

## 예정 처리 (경계)

책임 배치는 [FileStructure §4](../FileStructure.md)를 따른다. 새 최상위 폴더는 만들지 않는다.

| 책임 | 위치 | 경계 |
| --- | --- | --- |
| 전투 수명·결과 확정·전투 id·다시 전투 | 추천: 기존 `Managers/MonsterManager.mlua` 확장(맵 @Component, 대결 쌍 소유자. `.map` 변경 없음). 별도 컴포넌트가 필요하면 `Managers/`에 만들고 MonsterManager와 같은 엔티티에 MapBuilder로 붙인다(map01.map 변경. 이유를 WorkRecord에 적고 `[code]` 커밋에 포함) | 맵 단위 수명, ServerOnly. `@Logic`에 두지 않는다 |
| Level·EXP·정산 기록 | 새 `Player/PlayerLevelComponent.mlua`(이름 제안). 기존 플레이어 스크립트 컴포넌트가 붙은 플레이어 모델에 ModelBuilder로 추가(대상 모델은 coder가 `ModelBuilder.read`로 확인. `Global/` 기존 모델이면 제자리 수정만) | 서버만 값 변경, 표시용 값 `@Sync`. Level·EXP는 한 번에 바꾼다(중간 조합 노출 방지) |
| 표 로더 | KillExp: `Catalog/CombatRuleCatalog.mlua`(`GetMonsterStats` 확장). 레벨 표: 새 `Catalog/PlayerLevelCatalog.mlua`(`{대상}Catalog` 규칙, @Logic) | 기존 경고 1회·거부 정책 |
| DataSet | `DataSet/MonsterStatData.csv` 열 추가, 새 `DataSet/PlayerLevelData.userdataset`·`.csv` 짝. 새 `.userdataset`의 CoreVersion은 그때의 `Environment/config` 값(현재 26.11.0.0) | `.userdataset` EntryKey UUID 새로 생성 |
| 패배 표시 | 자동 부활 억제: 플레이어 쪽(`Player/PlayerHealthComponent.mlua` 등, 방법은 `.d.mlua`·msw-defaultplayer로 결정). 몬스터 Home 복귀·stand: `Monster/OrangeMushroom/OrangeMushroomAttack.mlua`·`Monster/MonsterAttackMotion.mlua`·`Monster/@StateControl/MonsterStateControl.mlua` 중 필요한 곳 | 기존 사망 우선·정지 중단 경로 유지 |
| 결과 팝업·토스트 | `UI/UIPopup.mlua`(정지 없이 여는 경로 추가), 필요하면 새 `UI/BattleResultController.mlua`(이름 제안). `ui/PopupGroup.ui`는 UIBuilder로만 읽고 고친다. `UI/UIToast.mlua`는 기존 `ShowMessage` 사용 | UI는 클라이언트 전용. 서버 → 클라이언트는 정산 기록 값만 전달 |
| 입력 차단 | `Player/@StateControl/PlayerStateControl.mlua`의 `SetInputBlocked(…, "result")` 같은 새 출처 | 정지(`CombatPause`) 시계를 결과 표시에 쓰지 않는다 |
| HP 표시 하한 | `UI/CombatHpBarController.mlua` | 표시만. HP 단일 적용 경계는 그대로 |

2단계 계약 유지: HP 단일 적용, 몬스터 쪽 피해 숫자 = HP 감소, 판정 0.20초·Pos2 조건, 슬로우·그로기, 정지 시계, die 1회 정지. 맵 엔티티 배치·위치는 바꾸지 않는다.

## 회차 나누기

| 회차 | 범위 | 시작 조건 |
| --- | --- | --- |
| 회차 1 — 전투 경계·승패·정산·결과 | R01~R09, R08a, R11, R12, R13 | 아래 [회차 1 coder 절차](#회차-1-coder-절차)의 시작 조건 |
| 회차 2 — Level·EXP HUD·레벨업 연출 | R10, 레벨업 연출(Q9) | 회차 1 사용자 V11 수락, Q8·Q9 답(에셋 후보 검색 → 사용자 선택), 사용자 시작 지시 |

각 회차: coder → 메인 `[BattleResult][code]` 로컬 커밋 → 같은 버전 tester → reviewer → 사용자 V11.

## 회차 1 coder 절차

### 시작 조건

1. 사용자 구현 지시(메인 확인). **미충족 — 남은 유일한 조건.** 2026-11-20 사용자는 "Plan만 커밋"으로 답해 구현은 별도 지시를 기다린다.
2. ~~아래 "회차 1 기본값"(Q10~Q16)에 사용자 확인~~ **충족**: 2026-11-20 사용자 "모두 기본값"(Q10~Q16 모두 (가)), 스크린샷 상한 확정.
3. 기준 버전: 이 Plan 확정이 들어간 커밋. `git status --porcelain`이 비어 있거나, 범위 밖 변경이 있으면 SHA-256을 run에 적고 커밋에서 뺀다.
4. Maker 편집 모드, Play 중 아님, `maker_get_current_map`이 map01·root id와 일치. `MapBuilder.read("map/map01.map").getTileMapMode()` = 0.
5. 다른 담당이 Maker를 쓰고 있지 않음(tester·reviewer 종료 확인).

### 순서

1. **스킬·참조 로드**: msw-scripting + `references/verify-checklist.md`, msw-general `references/dataset.md`·`model.md`·builder-protocol(core + model, map을 고칠 때만 map), msw-defaultplayer, msw-ui-system + `references/runtime-patterns.md`·`component-api.md`, builder-protocol-ui §3, `references/animation-state.md`(사망 모습·몬스터 stand).
2. **사망 모습 사전 확인(애니메이션 규칙)**: 코드 변경 전에 지금 플레이어가 HP 0일 때 보이는 모습(엔진 기본 `DEAD` 매핑)을 Play에서 확인하고 스크린샷 1장(상한에 포함)을 남긴다. 자동 부활만 막아 **기존 모습을 그대로 유지**할 수 있으면 새 애니메이션을 연결하지 않는다. 기존 모습이 "쓰러진 모습"으로 보이지 않거나 부활을 막으면 모습이 바뀌면 **멈추고** 기존 세팅 목록(플레이어 ActionSheet GUARD→alert·ATTACK→attack·MOVE→walk, DEAD는 엔진 기본)과 후보 동작을 메인에 넘겨 사용자에게 묻는다. 몬스터 stand·Home 복귀(jump)는 기존 세팅이라 해당하지 않는다. 레벨업은 회차 1에서 문구 토스트뿐이라 해당하지 않는다(회차 2 연출은 Q9에서 같은 규칙).
3. **데이터**: MonsterStatData.csv에 `KillExp` 열 추가, PlayerLevelData 짝 생성(위 CSV) → `maker_refresh_workspace` → `maker_build_logs`.
4. **로더**: KillExp·레벨 표 읽기와 검증, 경고 1회, 무효면 스폰 거부.
5. **Level 소유자**: 플레이어 컴포넌트, 정산 함수(전투 id 중복 거부, 이월·다단·최고 레벨), 정산 기록(R08a), `@Sync` 표시 값. 모델에 붙일 때 ModelBuilder.
6. **전투 수명**: 전투 id 발급, 승리·패배·동시(패배 우선)·중단 확정 1회, 승리 때 정산 호출, 결과 표시 신호.
7. **패배 표시**: 자동 부활 억제, 쓰러진 모습 유지(2번 결과대로), 몬스터 공격·효과 취소 → Home → stand, 결과 표시 동안 공격 시작 없음.
8. **결과 팝업·토스트·입력 차단**: 정지 없이 여는 UIPopup 경로, 결과 내용, 레벨업 토스트, 입력 차단 출처 추가·해제.
9. **다시 전투**: 요청 검증, 이전 몬스터 제거·새 스폰, 플레이어 BattlePos2·최대 HP·부활, 입력 차단 해제, 새 전투 id. 이전 전투의 정지 저장 목록·칸 표시·이펙트 추적이 남지 않게 한다.
10. **HP 표시 하한**.
11. **`[VRF]` 로그**: 전투 id·결과·정산(grantedExp, Level·EXP 전후)·다시 전투·스폰 거부 이유.
12. **기본 검증**: 아래 AI 기준 V01·V02·V04(Stop)·V05·V06·V07·V09·V11a를 한 Play 주기 안에서 최소 1회씩, V10 핵심 회귀(피해 일치·×2.2·die 1회). 스크린샷은 상한 안에서만.
13. **인계**: Stop → 편집 모드 확인, WorkRecord 개발 절(변경 파일·검증·미실시·Maker 재저장 목록), 이 Plan 회차 1 상태를 "구현 후 확인 대기"로. commit은 하지 않는다(메인).

### 중단 조건

- 사망 모습이 기존 설정으로 유지되지 않음(위 2번) → 사용자 질문으로 돌린다.
- 결과 팝업을 정지 없이 열려면 기존 전투 중 정지 팝업 경로의 동작을 바꿔야 함 → 멈추고 planner·사용자 판단.
- map01.map·`Global/` 파일을 위 표 밖으로 고쳐야 함 → 범위 확인.
- 2단계 회귀(V10) 실패를 같은 회차에서 두 번 고쳐도 남음 → 보고.
- 환경 오류(MCP 인증·연결, 다른 월드, Stop 실패, 도구 거절) → [EnvGuides](../../EnvGuides/README.md)대로 `WAITING_ENV`.

### Maker 재저장 파일 처리

- Refresh가 새로 만든 이번 회차 파일의 `.codeblock`·`.directory`는 `[code]` 커밋에 넣는다(직접 만들거나 고치지 않음).
- 이번 범위가 아닌 파일을 Maker가 다시 저장하면(CoreVersion 1줄 등, 예: `Global/common.gamelogic`, `ui/*.ui`, 다른 `.userdataset`, `map/map01.map`) 경로와 diff 요약을 WorkRecord에 적고 메인에 알린다. 기본은 분리([FileStructure §7](../FileStructure.md) "범위 밖 재저장")이며, 메인이 `[ops]`로 따로 커밋하거나 남긴다. `map/map01.map`은 이번에 의도적으로 고치지 않았다면 커밋에 넣지 않고 SHA-256을 적는다.
- `ui/PopupGroup.ui`·플레이어 모델처럼 이번에 빌더로 고친 파일은 `[code]` 커밋에 넣는다.

### 스크린샷 상한 (CombatCore-FU-18 적용)

화면 표시 확인이 필요한 항목만 찍는다. 그 밖은 로그·프로브로 확인한다.

- coder: 최대 4장. 사망 모습 사전 확인 1, 승리 결과 팝업 1, 패배 결과 팝업(HP 0 문자 포함) 1, 레벨업 토스트 1.
- tester(회차 1): 최대 5장. 승리 팝업, 패배 팝업과 HP 0 문자·몬스터 stand, 레벨업 토스트, 다시 전투 직후 화면, 결과 팝업 중 입력 차단 상태.
- 회차 2 tester: HUD 정산 전·후 2장을 더한다(제안. 회차 2 시작 때 사용자에게 다시 확인).
- 2026-11-20 사용자 확정: coder 4장, 회차 1 tester 5장.

## 확인 기준

### AI 확인 (tester, 같은 버전)

결과는 `[VRF]` 로그·`maker_execute_script` 프로브·서버 값으로 본다. 로그만으로 화면 통과를 주장하지 않는다.

| ID | 조건·방법 | 기대 결과 |
| --- | --- | --- |
| V01 승리 1회 | 자연 공격으로 머쉬맘 HP 0. 치명타 뒤 남은 타격·HitEvent가 더 오게 한다 | 승리 종료 1회, 정산 1회, grantedExp = 120(Lv1 시작이면 Lv2·EXP 20). 치명타 직전까지 Level·EXP 불변. 결과 팝업은 die 끝 프레임 뒤에 열림 |
| V02 패배 1회 | 가드·회피 없이 맞아 HP 0. O-3(FU-28) 재현 기록: 사망 시각, 몬스터 상태·구간·x, `[VRF] CombatPause abort`를 같은 시계로 | 패배 종료 1회, EXP 0 기록(R08a), 5초 이상 지나도 자동 부활·전투 재시작 없음, 몬스터는 공격 취소 뒤 Home x에서 stand, 결과 표시 동안 몬스터 공격 시작 0 |
| V03 동시 전투 불능 | 프로브로 같은 서버 처리 순간 양쪽 치명 피해 | 패배 1개, 정산 EXP 0, 결과 팝업 1개 |
| V04 중단 | 전투 중 Stop, 정지 프로브 중 Stop. 맵 이탈은 실제 경로가 없어 NOT_RUN(4단계 [CombatFoundation-F03](CombatFoundation.md)) | 정산·결과 0, 남은 예약·입력 차단·UI 없음, 다음 Play 정상 시작 |
| V05 중복 지급 방지 | 같은 전투 id로 정산 함수 2회, 결과 팝업 2회 열기, 클라이언트에서 정산·다시 전투 요청 2회 | EXP 증가 1회, 클라이언트 정산 요청 거부, 다시 전투 1회 |
| V06 다시 전투 반복 | 승리·패배 뒤 다시 전투를 3회 이상 | 매번 새 전투 id, 새 머쉬맘 HP 100, 플레이어 BattlePos2·HP 100(패배 뒤 부활), Level·EXP·기록 유지. 이전 공격·효과·칸 표시·입력 차단 잔존 없음 |
| V07 Level 계산 | 프로브로 EXP를 경계 근처에 둔 뒤 정산: 정확히 필요량, 1 초과, 여러 레벨 한 번에, Lv4→Lv5, Lv5에서 승리 | 이월·다단 상승. Lv5 도달 때 넘친 양 버림·EXP 0, Lv5에서 grantedExp 0. 기록의 Before·After 일치 |
| V08 데이터 오류 | KillExp 빈 칸, 레벨 표 열 누락·Level 빈틈·잘못된 수(임시 변경 → 원 바이트 복원, SHA-256 일치) | 빈 칸은 default 행(0). 무효 표는 경고 1회·스폰 거부. 복원 뒤 정상 로드 |
| V09 HP 표시 하한 | 치명 피해가 남은 HP보다 큰 패배 | 플레이어 HP 문자·바 0. 피해 숫자는 실제 피해값 |
| V10 2단계 회귀 | 예고·대응, HitEvent 합 = HP 감소, ×2.2 반격, 슬로우·그로기, die 1회 정지, 정지 프로브·사망 우선 | 2단계와 같다 |
| V11a 빌드·로그 | refresh 뒤 `maker_build_logs`, Play 중 `maker_console_logs` | 빌드 오류 0, 런타임 Error 0. 새 Warning은 원인 기록 |

### 사용자 직접 확인 (V11, PC Maker, 회차 1)

모두 게임 안 실제 경로가 있다.

1. 머쉬맘을 처치하면 die 끝 모습에서 멈춘 뒤 승리 팝업이 뜨고, 획득 EXP 120과 Level·EXP 전→후(처음이면 Lv1 → Lv2), 레벨업 토스트가 보인다.
2. 일부러 맞아 HP가 0이 되면 쓰러진 채 패배 팝업이 뜬다. 5초가 지나도 일어나지 않고, 플레이어 HP 문자는 0이며, 머쉬맘은 처음 자리에서 서 있다.
3. "다시 전투"를 누르면 새 머쉬맘과 새 전투가 시작되고, 플레이어는 가운데 칸에 HP 가득으로 선다. Level·EXP는 이전 값 그대로다. 처치를 반복해 두 번째 레벨업(누적 270 → Lv3)을 본다.
4. 결과 팝업이 떠 있는 동안 방향키·WASD·화면 버튼이 전투 동작을 하지 않는다.
5. (FU-27 일부) 결과 팝업과 레벨업 토스트의 모양, "다시 전투" 버튼 동작에 이상이 없다.

**프로브 시연**(경로 없음, 사용자가 원할 때만): 동시 전투 불능. tester가 Play 중 `maker_execute_script`로 같은 서버 처리 순간에 플레이어·머쉬맘 HP를 0으로 만들고, 사용자는 패배 팝업 하나만 뜨고 EXP 0인지 본다. 프로브로 수락하면 실제 경로 확인은 V03 행으로 계속 추적한다. 최고 레벨(Lv5)은 실제 경로가 있으나(여섯 번 승리) 길어서 V11 필수 항목에서 뺐다. 원하면 직접 해 본다.

**NOT_RUN 예정(통과로 세지 않음):** 모바일·실기기 터치, 실제 맵 이탈 중 종료, 재접속 뒤 Level(세션 메모리라 범위 밖), 다중 접속, 판 단위 EXP 회수·Run 결과의 "다시 열기"(4단계).

## 4단계로 넘기는 것

- **실패 시 그 판 EXP 전부 회수(레벨 되돌림 포함)**: R08a 기록의 같은 `runId` 첫 정산 `levelBefore`·`expBefore`로 되돌리는 방식을 기본안으로 4단계 Plan에서 정한다. 회수 뒤 표시·결과 화면의 획득 내역(`grantedExp` 합)·회수 문구도 그때 정한다.
- `runId` 발급과 전투 id 접두(Q13 (가)의 확장).
- `BattleResult-T01`(다시 전투) 대체·삭제, 방 진입 때 상대 키 입력(Q11).
- 맵 이탈 중 종료(V04 NOT_RUN), CombatFoundation-F03·CombatPause-F01.

## 위험·주의

- **자동 부활 억제:** 엔진 기본 5초 부활이 남으면 패배 뒤 전투가 저절로 이어진다. 막는 방법이 서버·클라이언트에서 같게 보이는지, 부활을 막아도 `DEAD` 모습이 유지되는지 확인한다(위 coder 절차 2).
- **UIPopup 정지 거부:** 사망 상태에서는 정지 요청이 거부된다. 결과 팝업은 정지 없이 여는 별도 경로로 열고, 전투 중 정지 팝업 경로는 그대로 둔다. 두 경로가 `_UIPopup.isOpen`을 같이 쓰면 입력 차단 해제 순서를 확인한다.
- **같은 처리 순간 경쟁:** 서로 다른 틱이면 먼저 확정된 쪽의 사망 처리가 상대의 대기 공격을 취소한다는 가정을 coder가 소스로 확인한다. 다르면 R04 적용 지점을 다시 정한다.
- **@Sync 중간값:** Level·EXP를 따로 동기화하면 잠깐 맞지 않는 조합이 보일 수 있다. 결과 팝업은 정산 기록 값을 쓴다.
- **세션 메모리:** Stop·Play 다시 시작이면 Lv1로 돌아간다. 저장 실패로 기록하지 않는다.
- **재스폰 잔존:** 기존 `DoSpawn`은 새 몬스터를 만든 뒤 이전 것을 지운다. die로 멈춘 이전 몬스터·정지 저장 목록·칸 표시·이펙트 추적이 남지 않는지 본다.
- **Home 미기록:** `OrangeMushroomAttack.Home`은 첫 공격 때 잡힌다(`HomeCaptured`). 첫 공격 전에 패배하는 경우 Home이 없으면 지금 위치에서 stand로 둔다(제안, V02에서 확인).
- **MSW 공통:** 새 `.mlua`는 Refresh로 `.codeblock`이 생겨야 등록된다. `.model`·`.ui`는 빌더 전용. UI 컴포넌트는 서버에서 nil. Play 중 편집·refresh 금지.

## 이전 단계 후속 항목 분류

| ID | 분류 | 처리 |
| --- | --- | --- |
| CombatCore-FU-18 | 3단계 적용 | 위 "스크린샷 상한". 다음 Plan에서도 계속 적용 |
| CombatCore-FU-22 | 3단계 포함 | R13, V09 |
| CombatCore-FU-27 | 일부 포함·일부 이월 | 결과 팝업·레벨업 토스트가 실제 경로가 되어 V11 5번에 모양·버튼 확인을 넣었다. **전투 중 팝업 정지와 정지 중 이펙트 화면**은 3단계에도 경로가 없어 이월한다(Q12). CombatPause-F02의 팝업·토스트 화면도 같은 범위만 볼 수 있다 |
| CombatCore-FU-28 | 일부 포함 | 패배 때 몬스터 공격 취소 → Home → stand(R03, O-1 경로)와 O-3 재현 기록(V02). 정지 중단·맵 이탈 경로는 같은 처리로 해결되면 V04에서 함께 보고, 아니면 CombatFoundation-F03·CombatPause-F01(4단계)에 남긴다. 취소 뒤 이펙트 끝까지 재생(FQ-3 (가))은 바꾸지 않는다 |

[2단계 후속 계획](CombatCore.md)의 해당 행 상태는 회차 결과에 맞춰 메인 지시로 갱신한다.

## 남은 질문

### 회차 1 결정 (2026-11-20 사용자 확정, "모두 기본값" = 모두 (가))

| ID | 확정 (가) | 고르지 않은 대안 |
| --- | --- | --- |
| Q10 | (가) 전투 시작 문구·준비 시간 없이 지금처럼 바로 시작(상태 경계만). 시작 연출은 4단계 암전과 함께 정함 | (나) "전투 시작" 문구와 준비 시간(값 필요, R14 추가) |
| Q11 | (가) 3단계는 "전투 시작 입력 = 상대 몬스터 키 1개"만. 전투 방의 일반 몬스터 선택 규칙은 4단계 Plan. 이미 정한 것: 5번 중간보스·10번 최종보스(머쉬맘) | (나) 지금 선택 규칙을 정해 GameDesign에 넣음 |
| Q12 | (가) 전투 중 팝업을 여는 새 경로는 만들지 않음. FU-27 정지 화면은 계속 추적 | (나) 전투 중 일시정지 버튼을 새 요구로 추가 |
| Q13 | (가) 전투 id = 서버 발급(플레이어 userId + 세션 안 순번). 4단계에서 runId를 앞에 붙임 | (나) 몬스터 엔티티 id 기준(재스폰마다 바뀌어 Run 연결이 어려움) |
| Q14 | (가) HP 문자·바만 0 하한, 피해 숫자는 실제 피해값 | (나) 피해 숫자도 남은 HP까지만 |
| Q15 | (가) 패배 때 몬스터는 기존 복귀 동작(Home으로 jump 포물선)으로 돌아가 stand. 이미 Home이면 바로 stand | (나) 이동 연출 없이 Home으로 즉시 옮기고 stand |
| Q16 | (가) 결과 팝업 버튼은 "다시 전투" 하나. 누르면 팝업이 닫히고 새 전투 시작(닫기만 하는 버튼 없음) | (나) "닫기" 버튼도 둠(닫은 뒤 다시 여는 경로가 필요) |

### 회차 2 전에 정할 질문

| ID | 질문 | 추천안 | 대안 |
| --- | --- | --- | --- |
| Q8 | 하단 Level·EXP 표시 모양·에셋 | (가) msw-search·msw-ui-kit(메이플 테마) 후보를 찾아 보여 주고 고른다 | (나) 임시 막대+숫자 먼저, 아트는 UI 아트 스타일 결정 때 |
| Q9 | 레벨업 연출·소리 | (가) MSW 리소스의 메이플 레벨업 이펙트·소리 후보를 기존 세팅 목록과 함께 보여 주고 고른다. 없으면 문구만 | (나) 문구만 |
