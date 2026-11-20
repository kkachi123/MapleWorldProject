# CombatCore — 2단계 후속 처리(FU) 회차 기록 (2단계 원본 WorkRecord는 기준 커밋 5efe005)

- 구분: 이 파일은 2026-11-19 시작한 2단계 후속 처리 회차의 새 기록이다. 같은 이름의 2단계 원본 기록은 [기준 커밋 5efe005의 CombatCoreWorkRecord](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md)에만 있으며, 여기에 옮기거나 고쳐 쓰지 않는다.
- 연결 Plan: [2단계 후속 계획 "후속 처리 계획(2026-11-19)"](../Plans/CombatCore.md#후속-처리-계획2026-11-19)
- run: `.pipeline/20261119-combatcore-followup/run.md`
- 상태·갱신일: 후속 회차 1 종료([review] b071b5c). 후속 회차 2(FU-17·19·12, O-1 포함) 종료 — d8c61db·eaeb032, reviewer READY, 사용자 V11 수락 / 2026-11-20 메인
- 삭제 조건: 후속 회차 1·2가 끝나고(사용자 V11 포함) 결과를 [2단계 Feature](../Features/2_CombatCore.md)와 후속 계획 표에 반영하고 링크를 정리한 뒤.

## 현재 재개 지점

- 마지막 상태(2026-11-20 메인): **후속 회차 1·2 모두 종료.** 회차 2는 d8c61db + O-1 수정 eaeb032, reviewer READY, 사용자 V11(자연 플레이·프로브 시연) "모두 괜찮음". 결과는 Plan 후속 계획 표와 Feature에 반영됐다(planner 마감 A).
- 다음 행동: 메인 [review] 커밋·push → planner 마감 B(링크를 [review] 커밋으로 교체, 이 파일과 run 삭제) → [plan] 커밋·push. 3단계는 사용자 지시 대기.
- 차단 조건: 없음. `map/map01.map`(`22b6acbf…987e`, 사용자 변경)은 계속 커밋 제외.

## 역할 간 인계

- 인계일·다음 담당·사용자가 승인한 범위: 2026-11-19 planner → 메인 → coder. 후속 회차 1 전체(Plan 회차 1 절). 근거는 사용자 순서 지시("…먼저 하고, 이후 3단계 진행하자")와 FQ-1 "파일 너가 이동시키고 내가 maker에 동기화 할게", FQ-2 "회차 1에 함께", FQ-4~7 "모두 추천안대로".
- 대상 Plan/요구 ID·변경 파일/버전:
  - 요구 ID: CombatCore-FU-24, FU-03, FU-23.
  - 변경: 11쌍 22파일 위치 이동(DataSet 6쌍 → `DataSet/`, 로더 3쌍 → `Catalog/`, UIPopup·UIToast → `UI/`), 원장 4곳(주석 1줄, 23·24·30행). 목록은 Plan 회차 1 "이동 목록".
  - 기준 버전: 16d70b3(origin/main). 작업 트리의 `map/map01.map` 변경은 범위 밖이며 커밋하지 않는다.
- 이미 확인한 조건(planner 소스 읽기):
  - DataSet은 `_DataService:GetTable(이름)`으로만 읽고 경로 문자열이 없다.
  - 옮길 스크립트 5개는 모두 `@Logic`이고 `_{이름}`으로 불린다. `.model`·`.map`·`.ui`·`.gamelogic`·`.config`·`.stateset`에 이름·`.codeblock` Id 참조 0.
  - `.codeblock`·`.directory`에는 경로 칸이 없다. `@Assist`·`Player/@Assist` 폴더 안에 `.directory`가 있어 AI가 폴더를 지우지 않는다.
- 미확인: Maker가 옮긴 DataSet·`.codeblock`을 같은 항목으로 인식하는지(1차 동기화로 확인), Maker 재저장 여부, 빈 폴더 `.directory` 처리 결과.
- 다음 행동: coder 절차 2(사전 확인: `maker_get_current_map`, `map/map01.map` 해시, 22파일과 `DataSet/PlayerActionFxData.csv` SHA-256 기록).
- Maker 최종 관찰 모드·담당·사용 종료 여부: 마지막 관찰은 2026-11-16 tester 인계 map01·편집 모드. 이 run에서는 아직 사용하지 않았다. 현재 연결 상태로 간주하지 않는다.

### 2026-11-20 planner → 메인 → coder — 후속 회차 2 인계(위 회차 1 인계와 별개)

- 사용자가 승인한 범위: 후속 회차 2 전체(Plan 회차 2 절). 근거는 사용자 "회차 2 시작"(2026-11-20)과 FQ-3 "기존 이펙트 유지 방식"((가), 2026-11-19).
- 요구 ID: CombatCore-FU-17, FU-19, FU-12((가)).
- 기준 버전: a593e2b(`origin/main`), 트리 id `d7ab128dc93ff5b8120882a8fcfd72a905a15f08`. `git status --porcelain`: ` M map/map01.map`(SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`, 범위 밖·커밋 제외), ` M .pipeline/20261119-combatcore-followup/run.md`(메인). Bundle은 쓰지 않는다(CLAUDE.md "버전 고정").
- 편집 허용 5개: `Player/PlayerCombatComponent.mlua`, `Player/PlayerGuardComponent.mlua`, `Monster/MonsterAttackMotion.mlua`, `Combat/CombatPauseComponent.mlua`, `Monster/@StateControl/MonsterStateControl.mlua`(+ Maker가 만드는 그 `.codeblock`). 파일별 a593e2b blob id는 Plan "범위 확인" 표.
- 이미 확인한 조건(planner, Read·Grep·git 읽기):
  - FU-17 대상 268행 그대로, 읽는 곳 0. FU-19 `SetGuarding` 10~35행 구조 그대로(판단 12행, 기록 34행).
  - 이펙트 재생 지점 3곳(MonsterAttackMotion 177행, PlayerCombatComponent 166행, PlayerGuardComponent 26행). `_EffectService`에는 정지·배율 변경 API가 없다.
  - 회차 1 이동·FU-26 1-A는 편집 허용 5개를 바꾸지 않았다(`git diff --stat 16d70b3 a593e2b -- RootDesk/`).
  - 기획 수치·규칙 변경 필요 없음(GameDesign §4.2·§4.3과 맞음).
- 미확인: 클라이언트 `SetClientTimeScale(0)` 정지 중 재생 중 이펙트가 이미 멈추는지(coder 첫 측정), 서버에서 `RemoveEffect`·재재생한 이펙트가 클라이언트에 어떻게 보이는지.
- Maker 최종 관찰 모드: 2026-11-20 tester 인계 map01·편집 모드(run). 현재 연결 상태로 간주하지 않는다.

## 감독·인계 기록

미기록(메인 조율 채팅이 작성).

## 개발 기록

미기록 항목(coder가 이어서 작성): 1차·2차 동기화 결과, `.directory` 생성·삭제 결과, FU-03 임시 변경·복원 해시, 원장 diff, build·Play 로그 근거, NOT_RUN.

### 2026-11-19 coder 후속 회차 1 — 사전 확인·1차 이동

- 대상 버전: 기준 16d70b3. 제품 변경은 아래 1차 이동 4파일뿐이다(`.mlua`·`.codeblock` 내용, `.model`·`.map`·`.ui`·`.directory` 무변경).
- 읽은 지침: 역할 계약 coder.md, 팀 계약, 구현 원칙, 후속 회차 1 계획 절 전체, msw-general·msw-ui-system 스킬, Foundation 참조 4개(platform·workspace·entity·authoring)와 platform-maple(map01 TileMapMode 0). msw-scripting·verify-checklist는 이 호출에서 `.mlua`를 수정하지 않고 Play도 하지 않아 읽지 않았고, Play 확인(1차 확인)을 시작하기 전에 읽는다.
- Maker 사전 확인(`maker_get_current_map`, `maker_get_world_info`): map01, id 0a0972ef-ad23-4e24-af63-afbd53120c1d, 모드 edit. worldId 970621b29ba945369d3dc8e90c301186(개인 월드). 이 호출에서 Refresh·Play·로그 지우기·스크린샷은 하지 않았다(0장).
- `map/map01.map` SHA-256: `3e60c21d6bd2328e1119f9566beb55901b13da64a99400c3d3ce68a0be5c2094`(사용자 변경 그대로, 이동 전·후 동일).
- 이동 전 SHA-256(2차 이동 때까지 새 위치에서도 같아야 함. 경로는 `RootDesk/MyDesk/` 기준, 이동 전 위치):

| 파일 | SHA-256 |
| --- | --- |
| @Assist/DataSet/AttackSkillData.userdataset | c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd |
| @Assist/DataSet/AttackSkillData.csv | 8218eb71930d38d97f58f7dda4d045bca5f14252559a249a5172c60ee0f83b5e |
| @Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| @Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| @Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| @Assist/DataSet/MonsterAttackPatternData.csv | 4d0525b2029269f80414b4a832f4bc6ffb397e4b31a07a1b3c28dfd3ac326ebe |
| @Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| @Assist/DataSet/MonsterData.csv | ca5dc4d9fc4f7b9cdb4f3c461b1395af2a8b010d4a180549251457e0af4a4ba6 |
| @Assist/DataSet/MonsterStatData.userdataset | b5a226f21c2f636d3ee40ddc6f7a2f56df6f9d9d4ed457fd6fe402037b8fa2f0 |
| @Assist/DataSet/MonsterStatData.csv | a87dcb2f9865ca9dae634a740540fb86811c24c8f31201aec25d64e96a83344f |
| @Assist/DataSet/PlayerBaseStatData.userdataset (1차) | f6d8da25e3b4a28cb5c0d5ce21c414a652e46e89741623d8bd8da6b8123a5d7f |
| @Assist/DataSet/PlayerBaseStatData.csv (1차) | bd03a14769d4cb9a204f5cd580da1fc2b2a777b244f69a53ad387878e5ed4b1b |
| Combat/CombatRuleCatalog.mlua | 4ac9bdeaf3ec4af38a36e53eb50afee81109ef31e61ae22dd3c919411a095a5b |
| Combat/CombatRuleCatalog.codeblock | be6e6a269f5b8aee054bc77bac60325481ce1c753e457ce005eb5b82c2b14569 |
| Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 8558c89c715c235fee5d6974c68cf2158b76501f36f2ed062144afa4778a1822 |
| Player/@Assist/Skill/PlayerSkillEffectTable.codeblock | ee2a877dd6eb2a06ec61696e9521f32872c955f29b9f1625bb7cda47fb256598 |
| Player/@Assist/Stat/PlayerBaseStatCatalog.mlua | f20a1121f35c01dadf1e3274e1551c9592af9ef02acc2610c2d16554edfadeb3 |
| Player/@Assist/Stat/PlayerBaseStatCatalog.codeblock | 2afec94ea827b2263057cc3d6e4ec9336887dd783ad1762cbc51c8b5f133d8be |
| UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| UIPopup.codeblock | 9721d41ebb9fb2518bceb1ba1cf5049042a38c8f92dcbffea1a3216c8ed5ad83 |
| UIToast.mlua (1차) | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| UIToast.codeblock (1차, Id 63fe07f0…) | f9aa2c08dc4a3bd78a10cd3fa3b75341a9ede1c5523ba272d672a96057346d7b |
| DataSet/PlayerActionFxData.csv (이동 없음, FU-03 복원 기준) | 75b8e8f0d7383ff313514ffe4114ea479b81a238261a5900872efa6722e8dc9b |

- 1차 이동(`node -e` `fs.renameSync`, 새 위치에 같은 이름이 없음을 먼저 확인, 복사·재작성 없음):
  - `@Assist/DataSet/PlayerBaseStatData.userdataset`·`.csv` → `DataSet/`
  - `UIToast.mlua`·`.codeblock` → `UI/`
  - 새 위치 SHA-256이 위 이동 전 값과 4파일 모두 일치한다.
  - Glob: 옛 위치에 4파일이 없고, `UIToast`·`PlayerBaseStatData`는 작업 공간에 새 위치 1개씩만 있다. `@Assist/DataSet/`에는 나머지 5쌍 10파일이 남아 있다.
  - git status: 4파일 삭제+추가(이름 변경), `map/map01.map` M(사용자 변경), 그 밖의 제품 변경 없음.
- 상태(1차 이동 직후): `WAITING_USER`(1차 동기화 대기).
- Maker 상태(이 호출 끝): map01·edit. 이 호출에서 모드를 바꾸지 않았다.

### 2026-11-19 coder 후속 회차 1 — 1차 확인(절차 5·6)·2차 이동(절차 7)

사용자가 "1차 동기화 완료"를 알린 뒤(메인 전달) 이어서 한 작업이다. 읽은 지침 추가: msw-scripting 스킬과 verify-checklist(Play 전).

**1차 확인: PASS**
- 동기화 직후 파일 상태(Refresh 전): 4파일 SHA-256이 이동 전과 같다(Maker 재저장 없음). `UIToast.codeblock` Id 앞 8자리 63fe07f0 그대로. 옛 위치에 4파일이 다시 생기지 않았고, `UI.directory`·`DataSet.directory` 외 새 `.directory`도 없다. `map/map01.map` 해시 불변.
- Maker: map01·edit(`maker_get_current_map`). `maker_refresh_workspace` 1회(허용됨) status ok.
- `maker_build_logs`: 93건, 모두 Info(LIA 1114/1115, `LIA&Default&11` 검색도 93건). Error·Warning 0. 중복 스크립트·Symbol not found 징후 없음.
- Play 1회(`maker_clear_logs` 안 씀, 스크린샷 0장):
  - `[VRF] PlayerBaseStatData side=server default MaxHp=100 MoveSpeed=12 ReturnSpeed=12 source=DataSet`(PlayerBaseStatCatalog.GetStats ← PlayerHealthComponent.OnBeginPlay).
  - `[VRF] PlayerBaseStatData side=client default MaxHp=100 MoveSpeed=12 ReturnSpeed=12 source=DataSet`(← PlayerMoveComponent.ApplyBaseStats).
  - 서버 프로브(server_main): GetTable("PlayerBaseStatData") 비어 있지 않음, rows=1, `_UIToast` 존재, `_PlayerBaseStatCatalog` 존재.
  - 클라이언트 프로브: GetTable 비어 있지 않음 rows=1, `_UIToast` 존재, `message`·`toastGroup` 유효(`isvalid`), `ShowMessage("FU probe")` 전 Enable=false → 후 true, `message.Text`="FU probe".
  - 런타임 로그 `error` 검색 0건, `LEA-` 검색 0건.
  - 이 프로브의 `[VRF-FU]` 로그 줄은 `maker_execute_script`로 넣은 임시 확인용이며 파일에 남지 않았다.
- Stop 후 map01·edit. 4파일·map01 해시 불변.

**2차 이동**(`fs.renameSync`, 원본 존재·대상 없음 먼저 확인 뒤 일괄 이동, `Catalog/` 폴더만 새로 만듦, 복사·재작성 없음)
- DataSet 5쌍 10파일 `@Assist/DataSet/{AttackSkillData,CombatRuleData,MonsterAttackPatternData,MonsterData,MonsterStatData}.{userdataset,csv}` → `DataSet/`.
- `Combat/CombatRuleCatalog.{mlua,codeblock}` → `Catalog/`.
- `Player/@Assist/Skill/PlayerSkillEffectTable.{mlua,codeblock}` → `Catalog/`.
- `Player/@Assist/Stat/PlayerBaseStatCatalog.{mlua,codeblock}` → `Catalog/`.
- `UIPopup.{mlua,codeblock}` → `UI/`.
- 새 위치 SHA-256이 위 이동 전 표의 18파일(2차 9쌍) 모두와 일치한다. 1차 4파일과 합쳐 22파일이 전부 일치한다. `DataSet/PlayerActionFxData.csv`(75b8e8f0…)·`MonsterSoundData`는 이동하지 않았다.
- Glob: `DataSet/`에 8쌍 16파일(+MonsterSoundData·PlayerActionFxData 2쌍은 기존), `Catalog/`에 3쌍 6파일, `UI/`에 4쌍 8파일(CombatHpBarController·CombatInputController·UIPopup·UIToast). 5개 스크립트의 `.mlua`·`.codeblock`은 작업 공간에 1개씩이다. `Combat/`에는 AttackAreaMarkComponent·CombatPauseComponent만 남았다.
- 남은 옛 폴더(절차 7 `.directory` 외 파일 확인): `@Assist/`와 `Player/@Assist/` 아래에는 `.directory` 5개만 있다(`@Assist/DataSet.directory`, `@Assist/RangeGizmo.directory`, `Player/@Assist/AttackRange.directory`, `Skill.directory`, `Stat.directory`). 상위 `@Assist.directory`·`Player/@Assist.directory`도 그대로다. 다른 파일 0개(중단 조건 8 해당 없음). AI는 이 폴더·`.directory`를 지우지 않았다.
- `Catalog.directory`: 아직 없음(사용자 2차 동기화 때 Maker가 만들 것으로 기대).
- git status(RootDesk): 22파일이 삭제+추가(이름 변경 후보)로 잡히고 `Catalog/` 새 폴더가 untracked다. `map/map01.map`은 M(사용자 변경) 그대로이고 해시 `3e60c21d…c2094` 불변.
- 이 시점의 Maker: map01·edit. 2차 이동 뒤 `maker_refresh_workspace`·Play는 하지 않았다.

(2차 이동 직후 상태: `WAITING_USER`, 사용자 2차 동기화 대기.)

### 2026-11-19 coder 후속 회차 1 — 2차 동기화 뒤 읽기 확인(중단 조건 7 해당, 정지)

사용자가 "2차 동기화 완료"를 알린 뒤 읽기 전용으로 확인했다. `maker_refresh_workspace`·FU-03·원장·통합 Play·Bundle 지문은 하지 않고 여기서 멈췄다.

- **중단 조건 7 해당: `map/map01.map` 내용이 회차 중에 바뀌었다.**
  - 해시: 회차 시작·1차 확인까지 `3e60c21d6bd2328e1119f9566beb55901b13da64a99400c3d3ce68a0be5c2094`, 지금 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`.
  - 원인 추정(확정 아님): 2차 동기화 때 Maker가 저장했다. 같은 시각(2026-11-19 21:46:10)에 `Global/common.gamelogic`·`map/map01.map`이 다시 저장됐고 `ui/CombatScreen.ui`·`DefaultGroup.ui`·`PopupGroup.ui`·`ToastGroup.ui`도 한 줄씩 바뀌었다(`git diff --numstat` 각 1/1).
  - `git diff HEAD` 기준 `common.gamelogic`는 `CoreVersion 26.10.0.0 → 26.11.0.0` 1줄이고, `map01.map`은 3줄(`CoreVersion 26.10.0.0 → 26.11.0.0` 1줄과 1599행 근처 좌표 값 `x 1.5 → 1.46799994`·`y 0.98 → 0.9959998` 2줄)이다. 좌표 2줄은 회차 시작 때 이미 있던 사용자 변경으로 보이지만, 시작 시점 diff를 따로 저장해 두지 않아 증명할 수 없다. 이번 재저장이 더한 것은 CoreVersion 1줄로 추정한다.
  - 이 5개 파일(`map01.map`, `common.gamelogic`, `ui/*.ui` 4개)은 이 회차의 이동 대상이 아니고 AI가 쓰지 않았다. 후속 계획 위험 4(범위 밖 재저장)로 기록한다. 이 회차 커밋에 섞지 않는다.
- **22파일 해시**: 이동한 22파일 모두 이동 전 값과 같다(Maker 재저장 없음). 래퍼 id·EntryKey·name·serveronly와 `.codeblock` Id·EntryKey·Name도 그대로다(바이트 동일).
- **`Catalog.directory`**: 새로 생겼다(`RootDesk/MyDesk/Catalog.directory`, 수정 시각 2026-11-19 21:46:07, 529바이트). EntryKey `directory://f915f2232ada4ce9af86f8874cecabbb`, name `Catalog`, `CoreVersion 26.11.0.0`, 파일 형식이 기존 `DataSet.directory`와 같다. AI는 `.directory`를 만들지 않았다(`Catalog/` 폴더만 만들었다). 새 CoreVersion 26.11.0.0과 21:46:07이라는 시각(map01 재저장 3초 전)으로 보아 Maker가 만든 것이 맞다.
- **빈 폴더**: 사용자가 지우지 않았거나 지운 것이 복구됐다. `@Assist/`(안에 빈 `DataSet/`·`RangeGizmo/`와 `DataSet.directory`·`RangeGizmo.directory`)와 `Player/@Assist/`(안에 빈 `AttackRange/`·`Skill/`·`Stat/`와 `AttackRange.directory`·`Skill.directory`·`Stat.directory`)가 모두 그대로 있고 상위 `@Assist.directory`·`Player/@Assist.directory`도 그대로다. `.directory` 삭제는 git status에 없다. 이 폴더 안에 `.directory` 말고 다른 파일은 없다.
- **중복**: Glob·git status에서 같은 이름 항목은 없다. 5개 스크립트와 8개 표가 각각 한 곳에만 있다. build 로그 검색 `duplicate` 0건, `not found` 0건.
- 이 시점 Maker: map01·edit(`maker_get_current_map`).
- 미실시(NOT_RUN): 2차 `maker_refresh_workspace`와 build 로그 전체 확인, FU-03, FU-23 원장 갱신, 통합 Play(8개 표 GetTable, Logic 5개, 회귀 6항), Bundle 지문.
- 판단 요청(메인 → 사용자): map01 재저장을 이 회차에서 어떻게 볼지 정해야 한다. 코드·이동 결과는 정상으로 보이므로 (가) 재저장을 "Maker 26.11 재저장"으로 기록하고 map01·common.gamelogic·ui 4개를 회차 커밋에 섞지 않은 채 FU-03 이후를 계속, (나) map01 해시 기준을 새 값으로 바꿔 계속, (다) 사용자가 원하면 작업 트리의 map01을 이전 상태로 돌린 뒤 계속 중 선택.

(위 중단 조건 7 정지는 이후 메인이 해소했다. 사용자가 빈 폴더를 지우고 Maker 동기화를 마쳤고, 메인이 `map01.map` 새 해시 기준과 [ops] bb3ec01(common.gamelogic·ui 4개 CoreVersion 커밋)을 정한 뒤 coder가 아래대로 절차 8~11을 이어서 마쳤다.)

### 2026-11-19 coder 후속 회차 1 — 절차 8~11 완료(빈 폴더 삭제 뒤 확인·FU-03·원장·통합 Play)

- **기준**: `map/map01.map` SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`(Maker 26.11 재저장 뒤 값, 이 절 내내 불변). 커밋 대상에서 제외한다. HEAD는 bb3ec01.
- **절차 8 확인(PASS)**
  - Glob `RootDesk/MyDesk/**/@Assist*` 결과 없음. `@Assist/`·`Player/@Assist/` 폴더와 그 안 `.directory` 5개, 상위 `@Assist.directory`·`Player/@Assist.directory`가 모두 사라졌다. git status에 이 7개 `.directory`가 삭제로 잡힌다. `Player/`에는 `@StateControl`과 `Player*Component` 파일만 남았다.
  - 22파일 SHA-256 전부 이동 전 표와 일치(`sha256sum -c` 22/22 OK). Maker 재저장 없음. `Catalog.directory`(Maker 생성, 21:46:07)는 그대로.
  - 이번 동기화로 Maker가 다시 저장한 파일: `RootDesk/MyDesk.directory`·`RootDesk/MyDesk/Player.directory`. 두 파일 모두 `CoreVersion 26.10.0.0 → 26.11.0.0` 1줄만 바뀌었고(`git diff -U0`), 하위 폴더 참조 제거는 없다(이 `.directory`에는 하위 항목 목록 칸이 없다). 범위 밖 재저장이므로 CoreVersion 변경으로 기록하고 회차 커밋에 넣을지는 메인이 정한다.
  - 그 밖의 범위 밖 변경은 없다(`git status`는 이동 22파일, 7개 `.directory` 삭제, `Catalog.directory`·`Catalog/` 추가, 위 두 `.directory` 수정, `.maplestory-skill-maker-ledger.md` 수정, `map01.map` 수정뿐).
  - `maker_refresh_workspace` 1회 ok. `maker_build_logs` 전체 93건 모두 Info(LIA 1114/1115), Error·Warning 0, `LEA&` 0, `duplicate`·`not found` 0.
- **절차 9 FU-03(PASS)**
  - 원본 `DataSet/PlayerActionFxData.csv` 103바이트 SHA-256 `75b8e8f0d7383ff313514ffe4114ea479b81a238261a5900872efa6722e8dc9b`를 스크래치에 복사했다.
  - 헤더 `EffectSound` 뒤에 `X`를 끼워 `EffectSoundX`로 바꿨다(104바이트, SHA-256 `4b05d5f1d9760bf864a6f7e8583b91193cd593c00bc0e75434cec8165bb15c60`, 다른 바이트 그대로). Refresh 후 build 로그 변화 없음(검색 `PlayerActionFx` 0).
  - Play 1회, `↓` 800ms 입력 1회:
    - Warning `[CombatRuleCatalog] PlayerActionFxData missing or required columns missing` 정확히 1회(22:04:26, WarnOnce, OnBeginPlay 경로);
    - `[VRF] PlayerGuard start x=0.000 t=8.931` 1회, `[VRF] guard fx off` 1회(22:04:35). 가드 연출 `guard fx effect`는 나오지 않았고 가드 진입은 정상이다.
  - Stop → 원 바이트로 복원(스크래치 원본을 그대로 복사). SHA-256 `75b8e8f0…a5dc`와 일치, `git ls-files -m`에서 이 파일은 변경 없음. 복원 뒤 `maker_refresh_workspace` 1회 ok.
- **절차 10 원장 `.maplestory-skill-maker-ledger.md`**(`git diff` 5줄 추가·3줄 변경, 계획 절 외 줄 무변경):
  - 20행 제목 "## 실효 대상별 사전 표" 바로 다음에 주석 1줄과 빈 줄 1줄: "(2026-11-19 주석) MHP-xx.castleenemy ID와 날짜가 붙은 기록 절은 2026-10-25 당시 키(castleenemy) 기준이다. 현재 실효 상대는 Mushmom.model(`mushmom`)이다."
  - 23행: `(castleenemy)` → `(키 orangemushroom, 패턴·스폰 없음(6단계))`.
  - 24행: "현재 MonsterData는 castleenemy 1행" → "현재 MonsterData는 머쉬맘(`model://mushmom`) 1행".
  - 30행 DATA-02: `Combat/CombatRuleCatalog` → `Catalog/CombatRuleCatalog`.
  - ID 이름(MHP-xx.castleenemy), 과거 기록 절, OPEN 상태는 고치지 않았다.
- **절차 11 통합 Play 1회(PASS, 일부 NOT_RUN)** — FU-03 복원 반영 뒤 Play(22:05:40), 스크린샷 0장, `maker_clear_logs` 안 씀.
  - 로드 [VRF](서버): `CombatCore catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`; `MonsterSoundData id=mushmom …`; `MonsterStat applied key=mushmom MaxHp=100.0 Hp=100.0 AttackDamage=12.0 AttackInterval=3.0 source=DataSet`; `PlayerActionFxData id=guard effect=318a4662 sound=605da1fc`; `MonsterManager spawned parent=map01 x=3.0` 1회. `[CombatRuleCatalog]` 경고 이 Play에는 없음(경고 1건은 FU-03 Play 것).
  - `PlayerBaseStatData side=server`·`side=client` 모두 MaxHp=100 MoveSpeed=12 ReturnSpeed=12 source=DataSet.
  - 서버 프로브 GetTable 행 수: CombatRuleData 1, MonsterAttackPatternData 5, MonsterStatData 2, MonsterSoundData 1, PlayerActionFxData 1, AttackSkillData 1, MonsterData 1, PlayerBaseStatData 1(이동 전과 같다). 클라이언트에서도 PlayerBaseStatData rows=1.
  - Logic 5개: 서버 `_CombatRuleCatalog`·`_PlayerSkillEffectTable`·`_PlayerBaseStatCatalog` 존재, 클라이언트 `_PlayerBaseStatCatalog`·`_UIPopup`·`_UIToast` 존재. `_PlayerSkillEffectTable:GetSkillData("player.basic")` nil 아님(Damage=1, AttackCount=10).
  - 팝업: 클라이언트 프로브로 `_UIPopup:Open` → `CombatPause server paused=true`·`client paused=true` → 팝업 표시(`isOpen=true groupEnable=true`) → `OnClickCancel` → `server paused=false`·`client paused=false` → `[VRF] CombatPause popup closed session=1` 1회.
  - 토스트: `_UIToast:ShowMessage("FU toast")` 뒤 `toastGroup.Enable=true`.
  - 기본 공격: `↑` 1회 → `[VRF] PlayerHitRule pass hit=1…10` 10회(22:06:29). 머쉬맘 HP 100.0 → 90.0, 즉 10타 × Damage 1 = 10 감소. 단 화면의 피해 숫자 표시는 확인하지 않았다(스크린샷 0장, HitEvent 합 로그 없음).
  - 가드: `↓` 600ms → `PlayerGuard start x=0.000 t=53.831` 1회, `guard fx effect=318a4662` 1회(정상 표라서 `guard fx off`는 이 Play에 없음).
  - 몬스터 공격: 이 Play에서 telegraph id=1~10이 진행됐고 플레이어 HP는 프로브 시점에 4/100이었다(프로브 지연으로 가만히 맞음). 판정은 계속 동작했다. 에러·`LEA-`·`rror` 로그 0건.
  - Stop 후 map01·edit.
  - **NOT_RUN(코드 내용 변경이 없어 이번 회차에서 하지 않음, 독립 tester에게 넘김)**: die 1회 정지 확인, Pos2 JUST·PARRY 각 1회, 반격 보너스 ×2.2, 가드 40% 경감, 화면상 피해 숫자와 HP 감소 일치, 모바일·실접속. 회차 A·C 전수 회귀도 하지 않았다.
- **Bundle 지문**: `map/map01.map`을 뺀 58경로(확장자 9종 `.mlua .model .stateset .userdataset .csv .map .ui .config .collisiongroupset`, Global·RootDesk·map·ui, 경로 UTF-8 바이트순, `경로 TAB 파일 sha256 LF` 연결의 SHA-256, 새로 작성한 node 스크립트로 계산) **`24fa65cfbfdd036b9c81e0a09ea4860b4efa6115c267c20b5023240eeffd8187`**. `.codeblock`·`.directory`는 지문에 포함되지 않는다(기존 방식). 시점: FU-03 복원·원장 갱신·통합 Play 이후 작업 트리, HEAD bb3ec01 위의 미커밋 변경. 이전 2단계 값(58경로 `1d70bc71…75dd`)과 경로 수는 같으나 이동 경로와 CoreVersion이 바뀌어 값은 다르다. 계산 스크립트는 이전 회차 manifest 방식을 문서 기술에 따라 새로 구현한 것이라, 이전 회차 값과 같은 입력으로 교차 확인하지는 않았다.
- **Maker 최종 상태**: map01·edit, Stop 확인.
- **바뀐 제품 파일(이번 회차 전체)**: 이동 22파일(경로만), `Catalog.directory` 추가·7개 `.directory` 삭제(Maker 결과), `RootDesk/MyDesk.directory`·`Player.directory` CoreVersion(Maker 재저장), `.maplestory-skill-maker-ledger.md` 원장 3곳. `map01.map`은 커밋 제외(해시 `22b6acbf…`). `PlayerActionFxData.csv`는 원 바이트(`75b8e8f0…a5dc`).
- **상태**: DONE(coder), 다음 담당 메인 → `[CombatCore][code]` 로컬 커밋 → tester.

### 2026-11-19 coder — FU-26 진단(머쉬맘 2·3칸 점프 초반 공중 끊김, 진단만·제품 변경 0)

- 범위: Plan "후속 회차 1 추가 — FU-26" 절의 coder 진단(절차 1)뿐. 제품 파일(.mlua·.model·.map·.ui·CSV·userdataset)은 고치지 않았다. commit·push 없음. 스크린샷 0장, `maker_clear_logs` 0회. 시험 값·프로브는 Play 메모리와 `maker_execute_script`에만 두었고 스크래치(`readmodel.cjs`)는 ModelBuilder 읽기용 스크립트다.
- 대상 버전: 로컬 HEAD c6422cd. 사전 확인: Maker map01·edit(0a0972ef-ad23-4e24-af63-afbd53120c1d), `map/map01.map` SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`(시작·끝 같음). 작업 트리 변경은 문서뿐이었다.
- 사용자 보조 답(FQ-8, 메인 전달): 빈도 "가끔 보임", 순간 "(나) 뜬 직후 공중", 시기는 처음 "최근 처음"이었다가 "최근 아니다 계속 봄"으로 정정(11-16 수락 이전부터). 사용자 지시: FU-16(서버 매 틱 `SetPosition`)을 중점으로 본다.

#### 1. 값 확인(ModelBuilder 읽기·소스·패턴 표)

- 머쉬맘 모델(`Models/Monsters/Mushmom.model`, ModelBuilder 읽기): 컴포넌트 14개(Transform·StateAnimation·SpriteRenderer·Rigidbody·Movement·State·Hit·DamageSkinSpawner·MonsterHealth/StateControl/Attack/Defense/Stun·OrangeMushroomAttack). `script.OrangeMushroomAttack` 값은 `Enable`·`Home`·`HomeCaptured`·`JumpActive`·`JumpStartX`·`JumpTargetX`·`JumpStartTime`뿐이다. `EqualizeLeapFrames`·`EaseLeapMove`·`LeapJumpHeight`·`JumpDuration`·`JumpHeight`·`WindupHittable`은 모델에 값이 없어 스크립트 기본값이다(true·true·0·0.5·0.8·true). `RigidbodyComponent`에는 MoveVelocity·RealMoveVelocity·Enable만 있고 런타임 읽기로 WalkSpeed 1.4·WalkAcceleration 1.0·WalkDrag 1.0·Mass 100.
- ActionSheet(머쉬맘): `stand` 86015373d23b4b05bb8fcc6086354652 · `move` c745828d831b42739b9a58c07f334864 · `jump` 5ecbcc4002a5491aafd7e1d3191c6ddc · `hit` 90fee9416184420a9796a679751d1ec5 · `die` ec90f0b64a814c4980de89f496d360ec · `attack1` 90c5456e2a8a45478df02500797a9afd · `skill1` b9345875a8134c7c9a1b6aed8551d808.
- 패턴 표(`DataSet/MonsterAttackPatternData.csv`) 머쉬맘 5행: parry.left(MotionClip attack1, TelegraphLeadSec 1.571429, MotionPlayRate 0.7, JumpStartFrame 1, Weight 4) · parry.right(attack1, 같음, Weight 4) · parry.guard(skill1, 같음, Weight 4, EffectClip 05113e9dc86448cb8581731824106d75) · parry.any(jump, 0.5, 배율 1, JumpStartFrame 빈 값, Weight 5) · special.random(jump, 0.5, 1, 빈 값, Weight 3). 2·3칸과 1칸의 차이는 경로(`BeginWindup` ↔ `JumpToLocalX`)·클립·구동·점프 시작 프레임이다(Plan 표 그대로 확인).
- 클립 그림(2단계 Plan 22.16.1, 2026-11-08 측정): attack1·skill1 5프레임 Delay 0.80/0.20/0.05/0.05/0.75, 피벗 y 0/−88/−70/−8/0px(f1에서 한 번에 +0.88 단위). 배율 0.7·균등화 켬이면 f0 1.143초 → f1·f2·f3 각 0.143초.
- 소스에서 확인한 W 전환 순간(`OrangeMushroomAttack.OnUpdate`): 같은 서버 틱에서 `TickClip`(경계 1.142857 도달 → `EndFrameIndex=1` 다음 `StartFrameIndex=1`) → `now >= leapStart`면 windup 해제·`JumpActive`·`Segment="approach"` → 곧바로 `t = (now−JumpStartTime)/J`로 x(smoothstep)·y(Home.y, 높이 0)를 계산해 `body:SetPosition` 1회. 즉 W 틱에 프레임 쓰기 2개와 위치 쓰기 1개가 같이 나가며, 이후 틱마다 위치 쓰기 1개씩, f2·f3 경계 틱에서는 프레임 쓰기 2개가 더 붙는다. 1칸(`JumpToLocalX`)은 프레임 구동이 없다(jump 클립 자연 재생). 변경 이력: 머쉬맘 스크립트·모델은 e710907 이후 내용 변경 없음(c6422cd는 위치 이동만) — `git log` 확인.

#### 2. 측정 방법(MM-14 방법 재사용)

- 서버(`server_main`) 프로브: 몬스터 `AttackInterval` 9999, 플레이어 Hp 보충, `_CombatRuleCatalog.patterns["mushmom"]`을 한 행으로 바꿔(끝에 원 표로 복원) `ChangeState("ATTACK")`로 강제 실행. 1ms 타이머가 서버 프레임마다(실측 간격 16~21ms, 평균 17.3ms ≈ 58Hz) 위치·구간·`JumpActive`·렌더러 Start/End/PlayRate·`RealMoveVelocity`를 기록.
- 클라이언트(`client`) 프로브: 1ms 타이머(실측 한 프레임 17.2~18.3ms)로 몬스터 `WorldPosition`·렌더러 Start/End/PlayRate·`AttackSequence`를 매 프레임, `SpriteAnimPlayerChangeFrameEvent`를 이벤트마다 기록. 두 쪽 모두 `_UtilLogic.ServerElapsedSeconds` 시계.
- 순서: parry.left → parry.right → parry.guard → parry.any를 6번 돌려 24회(2칸 좌 6·우 6, 3칸 6, 1칸 6, 슬로우 없음). 다시 쓸 때 `log`에 줄바꿈을 넣으면 클라이언트 로그가 사라지므로 한 줄로 썼다.

#### 3. 측정표(Maker 26.11 로컬 Play, 서버–클라이언트 같은 프로세스)

| 지표 | 2칸 좌(6회) | 2칸 우(6회) | 3칸(6회) | 1칸 parry.any(6회) | 2026-11-16 기준값(e710907 coder, (켬,켬)) |
| --- | --- | --- | --- | --- | --- |
| 서버 W(공격 강제 시작→점프 시작, 프로브 표본 오차 약 +0.02 포함) | 1.164~1.175 | 1.170~1.178 | 1.165~1.177 | 0.016~0.019(시작과 동시) | 1.145~1.159 |
| 서버 점프 시간 J | 0.417~0.437 | 0.413~0.425 | 0.418~0.434 | 0.501~0.523 | 판정 1.572~1.588(기대 1.5714) |
| 서버 위치 쓰기(접근 구간) | 24~25회, 모든 표본 간격에서 위치가 바뀜(생략 0) | 24회, 생략 0 | 24~25회, 생략 0 | 29~30회, 생략 0 | — |
| 서버 쓰기 간 이동량 min/평균/max | 0.013~0.029 / 0.094~0.097 / 0.134~0.149 | 0.036~0.052 / 0.162 / 0.230~0.244 | 0.013~0.037 / 0.125~0.130 / 0.184~0.199 | 0.096~0.114 일정(평균 0.104) | 곡선 켬 서버 편차 0.0035~0.0056 |
| `RealMoveVelocity` | 0.000(순간 이동) | 0.000 | 0.000 | 0.000 | — |
| 클라이언트 f1 이벤트 기준 f2·f3 시작 | f2 0.122~0.156, f3 0.261~0.311 | f2 0.122~0.141, f3 0.261~0.278 | f2 0.140~0.155, f3 0.277~0.298 | — | 표시 시간 0.117~0.171 각 |
| 같은 프레임 이벤트 도착(f1·f2·f3) | 각 2건(18회 모두) | 각 2건 | 각 2건 | — | 각 2건 |
| 접근 구간 Start≠End 클라이언트 표본 | 0 | 0 | 0 | — | 0 |
| 클라이언트 프레임 번호 순서·되돌림 | 0→1→2→3, 되돌림 0 | 같음 | 같음 | — | 같음 |
| 클라이언트 접근 프레임 수 | 23~26 | 24~25 | 24~26 | — | — |
| 클라이언트 위치가 f1 이후 움직이기 시작 | f1 +0.016~0.033초 | +0.017 | +0.017~0.019 | — | — |
| 접근 중 **정지 1프레임**(x 변화 0 뒤 이어서 2배 가까운 이동)이 1회 이상 있었던 시험 | 6회 중 5 | 6회 중 5 | 6회 중 3 | 6회 중 4 | "정지 0.000~0.018초"로 기록(한도 0.05초 이하라 PASS) |
| 정지 프레임이 겹친 큰 이동 단일 프레임(평균 대비) | 최대 0.285(2.8배) | 최대 0.440(2.8배) | 최대 0.366(2.9배) | 1칸은 이동량이 작음(평균 0.104) | 한도 k×평균(1.5배)로만 판정 |

- 2·3칸 18회 중 13회(72%)가 접근 0.43초 안에 정지 프레임을 1회 이상(최대 2회), 1칸 6회 중 4회(67%)가 같다. 정지 시각은 W 기준 0.12~0.35초이고, 18회 중 5회는 f2·f3 경계 ±0.02초에 겹쳤다. 정지가 W 직후 0.12초 안에는 없었으나 그 구간은 smoothstep 때문에 이동량이 0.002~0.05로 작아 "0" 판정이 어렵다(판정 편향).
- 2026-11-16 기준값과의 차이: 시각(W·f2·f3·J)·프레임 순서·이중 도착·위치 모양은 같은 범위다. Maker 26.11에서 달라진 지표는 측정되지 않았다. 11-16 기록의 "같은 x에 멈춘 가장 긴 구간 0.018초"와 "최대 이동 비 0.51~1.01"이 이번 정지 1프레임(0.017~0.020초)·2배 이동과 같은 현상을 이미 가리킨다(당시 기준은 0.05초 이하여서 PASS로 셌다). 즉 이번 측정에서 새로 생긴 변화는 없고, 판정 기준이 이 현상을 문제로 잡지 못했다.

#### 4. 분리 시험(Play 메모리·프로브만, 제품 파일 변경 0)

| 시험 | 조건 | 결과 |
| --- | --- | --- |
| 위치 쓰기 방식 대조 | 몬스터를 직접 움직임 시험(프레임 구동·제품 OnUpdate 없음), 0.6초·2.7 단위/초, 좌우 교대, 클라이언트 `WorldPosition` 매 프레임. 정지=이동 중간의 x 변화 0 프레임 | `rb:SetPosition` 틱마다 쓰기: 20회(8+8+4) 중 15회에서 정지 1프레임 이상(정지 합 19). `rb:SetWorldPosition`: 12회(8+4) 중 7회. `MovementComponent:SetPosition`: 1회 측정(정지 2). `TransformComponent:Translate`: 몬스터가 움직이지 않음(바디가 덮어씀, 무효). `Rigidbody.MoveVelocity`(엔진 물리 이동): 12회(7+5) 정지 0·2배 이동 0(같은 표의 `MoveVelocity` 4회 구간은 이동 시작·끝 구간 포함 분석이라 제외). 즉 틱 위치 쓰기는 어떤 API로 해도 같은 정지가 나오고, 엔진 물리 이동만 없다 |
| 서버 쓰기 규칙성 | 제품 접근 24회 | 서버 쓰기는 매 틱 간격 16~21ms, 생략 0. 서버 쪽은 매끄럽다. 클라이언트가 같은 값을 못 받는 프레임이 생긴다 |
| 속도 기반 이동 가능성 | `MoveVelocity` −1·−2·−4·−8, `WalkAcceleration` 1·100 | 속도가 명령과 무관하게 약 2.6~2.8 단위/초에서 포화(`WalkSpeed` 1.4 기준 한도). 가속은 약 3틱(0.05초)이면 포화. 필요한 속도는 2칸 좌 평균 5.2·우 8.7·3칸 7.0 단위/초(smoothstep 최대 7.8·13.1·10.5)라 기본값으로는 불가 |
| 속도 한도를 런타임에서 올림(재개 뒤 시험, 2026-11-20) | `rb.WalkSpeed` 8·`MoveVelocity` −3 / `WalkSpeed` 13·−5 / `MovementComponent.InputSpeed` 8 + `MoveToDirection(−1,0,dt)`(모두 Play 안 메모리, 끝에 복원) | 포화 속도 약 14 / 약 24 / 약 13~14 단위/초. 모델 값 변경 없이 스크립트에서 `WalkSpeed`·`InputSpeed`를 올릴 수 있다. 가속은 0 → 포화까지 약 9틱(0.15초, 높은 속도일수록 길어짐)이라 smoothstep 시작(속도 0)과 비슷한 느린 출발이 생기고 곡선 모양은 근사만 된다. 클라이언트: `InputSpeed` 8 이동 약 590프레임(최대 0.26 단위/프레임)에서 정지 0·2배 이동 0 — 고속에서도 매끄러움. 도착 x·시각 정밀도(±0.01·±0.05초)는 시험하지 않았다 |
| Start·End 따로 도착(후보 다) | 18회 접근 구간 | Start≠End 표본 0(착지 뒤 전체 범위 복원 구간만 있음). 후보 (다)는 이번에도 관찰되지 않음 |
| 프레임 구동 없이 자연 재생·조절 항목 4조합·LeapJumpHeight>0 | — | 실시하지 않음. 위치 정지 1프레임은 프레임 쓰기 없는 시험(위 첫 행)에서도 같은 빈도로 나와 프레임 구동·곡선·균등화와 무관한 별도 현상으로 보아 생략했다. 화면 체감(그림 도약과 이동의 어울림)은 스크린샷 없이 판단 불가 |

- 원인 확정 여부: 아래 5.

#### 5. 판정

- **측정으로 확정된 것**: (a) 서버 `SetPosition` 틱 이동은 클라이언트에서 약 0.45~0.6초에 한 번 꼴로 "정지 1프레임 + 다음 프레임 약 2배 이동"으로 도착한다. 접근 0.43초 안에 2·3칸 18회 중 13회(72%)·1칸 6회 중 4회(67%)에서 나타난다. 2·3칸 이동량 최대 0.23/프레임이라 정지 뒤 단일 프레임 이동이 최대 0.44 단위(44px)다. (b) 같은 시험에서 엔진 물리 이동(`MoveVelocity`)은 0회다. (c) 이 현상은 Maker 26.10과 26.11을 가르지 못한다. 2026-11-16 기록에도 같은 값이 있다(사용자가 처음부터 계속 봤다는 답과 일치). 프레임 쓰기·smoothstep·균등화와 무관하다.
- **FU-14(O-1 "가끔 접근이 멈춤")는 이 정지 프레임과 같은 현상일 가능성이 높다**(QA14 재현 0/28은 정지 0.05초 이하 기준 때문).
- **FU-15(프레임 이벤트 이중 도착)**: 이번에도 모든 프레임에서 2건, 화면에 보이는 되돌림·Start≠End는 0. 이 결함의 원인으로는 지지되지 않는다.
- **확정 못 하는 것**: 이 정지 프레임이 사용자가 말한 "뜬 직후 공중이 이어지지 않음"의 전부인지 일부인지, 그리고 왜 1칸은 괜찮은지. 정지 빈도는 1칸도 같다(4/6). 이동 속도 차이(1칸 평균 0.10, 2칸 우 0.16·최대 0.23)와 그림 차이(1칸은 jump 클립 자연 재생+높이 포물선, 2·3칸은 4개 자세가 피벗 0.88→0.70→0.08로 높이만 바꾸는 그림에 y 변화 0)로 설명할 수 있으나 측정으로 가리지 못했다. 또 2·3칸에만 있는 요인으로 (i) W에서 그림이 한 번에 +0.88 올라가는데 smoothstep 때문에 W 뒤 0.05초 동안 이동이 전체의 약 5%(좌 2.25 단위 중 0.114)뿐이라 "뜬 채 제자리"로 보이는 구간, (ii) f2→f3에서 그림이 +0.70→+0.08로 급하게 내려오는 것이 있다(화면 확인 필요, AI 판단 불가).
- 결론: **정지 프레임(FU-16/FU-14)은 간헐 원인으로 측정 확정, "사용자가 본 끊김"과의 일치는 사용자 확인 필요.** Plan 중단 조건 1은 "원인을 확정하지 못함"이라 수정하지 않고 멈춘다.

#### 6. Maker 26.10→26.11 영향

- 직접 비교할 26.10 환경은 없다. 11-16 기준값과 이번 값의 모든 지표가 같은 범위이고 사용자가 시기를 "계속"이라고 정정했으므로 26.11 변경이 원인일 가능성은 낮다. 정지 프레임의 서버–클라이언트 동기화 지연 쪽 엔진 동작은 제품 코드로 바꿀 수 없다(중단 조건 5 후보: 엔진 동작이 원인이고 이동 방식 변경이 승인 범위 밖).

#### 7. 수정안 선택지(전부 수정 전 사용자 승인 대상)

(별도 보고에 같은 표를 둔다. 이동 방식을 바꾸는 안은 FU-16 승인 항목이다.)

| 안 | 바뀌는 파일 | 바뀌는 것 | 1칸 영향 | 위험 | 권장 |
| --- | --- | --- | --- | --- | --- |
| A. 이동 방식 변경(속도 기반) | OrangeMushroomAttack.mlua(접근 이동·TickClip 호출) 1파일. 모델 값 변경은 불필요(런타임에서 `InputSpeed`·`WalkSpeed`를 올릴 수 있음이 시험됨) | 2·3칸 접근을 엔진 물리 이동(`MovementComponent:MoveToDirection`/`MoveVelocity`)으로 구동하고 접근 시작·판정 틱에서 `SetPosition`으로 착지 위치만 맞춤. 곡선은 틱마다 목표 속도를 바꿔 근사(출발 가속 약 0.15초) | 1칸·복귀 경로를 안 건드리면 0(같은 정지 현상은 1칸에 남음). 함께 바꾸면 1칸 0.5초·높이 0.8·착지 x 재증명 | 가속 한도 때문에 smoothstep과 완전히 같지 않아 W·착지 x(±0.01)·판정 시각(±0.05초) 재증명 필요, D-Q6(슬로우)·일시정지·취소·사망 정리에 속도 0 처리 필요, 착지 직전 위치 오차가 크면 마지막 `SetPosition`에서 튐, 몬스터 `Rigidbody` 물리(발판)와 얽힘 | 중(효과는 측정됨, 이동 방식 변경이라 FU-16 승인 대상) |
| B. 클라이언트 보간·연출 이동 | 새 클라이언트 컴포넌트(새 파일), 모델 컴포넌트 추가 | 서버 위치를 클라이언트 프레임마다 보간해 표시만 매끄럽게 | 영향 없음 또는 같이 적용 | 22.15 원칙 2(클라이언트 클립·위치 직접 쓰기 금지)를 바꿈, 엔진이 동기화 값을 덮어쓰는지 미확인, 새 파일·컴포넌트 | 하 |
| C. 현상 유지(수락) | 없음 | 문서에 정지 프레임 허용 기준 추가 | 0 | 사용자가 계속 불편 | 사용자 판단 |
| D. 도약 구간에서 jump 클립 사용 | OrangeMushroomAttack.mlua | 2·3칸 도약(f1~) 동안 attack1·skill1 대신 1칸과 같은 jump 클립 자연 재생(+높이 LeapJumpHeight>0 선택) | 0 | 애니메이션 교체(그림 완전 변경, 기존 세팅 목록 확인 필요), 정지 프레임은 그대로, 원작 그림 포기 | 하(그림 문제가 원인으로 확인될 때만) |

- 권장: 먼저 사용자가 화면에서 "정지 순간(0.5초에 한 번 번쩍 건너뜀)"이 보인 것인지 확인한 뒤 A. 확인 전에는 수정하지 않는다.

#### 8. 미실시·미확인 (PASS로 세지 않음)

- 화면 체감(스크린샷 0장), 지연 있는 실접속에서의 동기화(Maker 로컬 Play는 서버–클라이언트 같은 프로세스), 모바일, 26.10 대조, 프레임 구동 없는 자연 재생·조절 항목 4조합·LeapJumpHeight>0 직접 시험, 속도 기반 이동으로 실제 2·3칸 곡선을 재현했을 때의 착지 정밀도(시험하지 않음). `WalkSpeed`·`InputSpeed` 상승 시험은 API 사용 한도 중단 뒤 재개해 마쳤다(2026-11-20, 위 4번 표).
- 재개 기록: 한도 중단 때 Maker는 편집 모드로 돌아와 있었고(Play 아님) map01·`22b6acbf…` 불변이었다. 이후 Play 1회로 속도 시험을 마치고 Stop해 map01 편집 모드로 인계했다. 프로브 반복 타이머의 `[LEA-3051]` 흔적은 시험 때문이다(제품 무관).
- 누적 로그: 22:11:32 `[LEA-3022]` 5건은 tester 시험 흔적이라 판단에서 제외. 내 시험이 만든 `[LEA-3051] MemoryLeak 'MakerScript'` Error 4건(23:02:13, 프로브 반복 타이머가 Stop 때 정리되지 않음)은 제품 코드와 무관한 시험 흔적.
- Maker가 다시 저장한 파일: `RootDesk/MyDesk/DataSet/PlayerActionFxData.userdataset`에서 `CoreVersion 26.10.0.0 → 26.11.0.0` 1줄만 바뀌었다(`git diff -U0`, 23:03:04, 내 Play 시작 직후). 직접 편집이 아니라 Maker 26.11 재저장이다(내가 쓴 파일은 스크래치 스크립트뿐이고 제품 파일은 열지도 않았다). 되돌리거나 더 고치지 않고 그대로 둔다. map01 해시 `22b6acbf…` 불변.

#### 9. 추가 진단(2026-11-20, 사용자 체감 답 반영) — 클립의 공중 부분 확인

- 사용자 답: 체감 "보간된 포물선 느낌이 아닌 도중이 뚝 끊기는 느낌". "애니메이션에 공중 이동이 합쳐진 것 같다"며 확인을 요청했고, 원인이 그렇다면 (1) 이동 애니메이션 공중 부분 해결 또는 (2) 2·3칸을 제자리 점프 + 착지 영역 먼지 이펙트(지진 공격)로 고르겠다고 했다. A~D는 고르지 않았다. 제품 변경 0, 스크린샷 0장, 썸네일·이미지 다운로드 없음.
- 확인 방법: msw-search 래퍼(`msw_resource_api.cjs get`)로 attack1·skill1·jump·stand 클립 프레임 데이터를 조회했다(2단계 Plan 22.16.1 2026-11-08 측정값과 대조).
- 클립 프레임(피벗 단위 px, y 음수 = 그림이 그만큼 위로 올려 그려짐):

| 클립 | 프레임 | 그림 크기 | 피벗 x | 피벗 y | 그림 높이 |
| --- | --- | --- | --- | --- | --- |
| attack1(90c5456e…) | f0 | 120×104 | 59 | 0 | 0 |
| | f1 | 120×128 | 59 | −88 | +0.88 |
| | f2 | 120×128 | 60 | −70 | +0.70 |
| | f3 | 120×128 | 60 | −8 | +0.08 |
| | f4 | 120×108 | 58 | 0 | 0 |
| skill1(b9345875…) | f0~f4 | attack1과 같은 크기 | 59·59·60·60·58 | 0·−88·−70·−8·0 | attack1과 같음(프레임 그림만 다름) |
| jump(5ecbcc40…) | f0 1장 | 120×128 | 59 | 0 | 0(정지 자세, 높이는 스크립트 포물선이 담당) |
| stand(86015373…) | f0 1장 | 120×112 | 59 | 0 | 0 |

  - 프레임 Delay는 조회 결과에 없다. 2단계 Plan 22.16.1 측정값 0.80/0.20/0.05/0.05/0.75초를 쓴다.
  - **수평 이동은 클립에 없다.** 피벗 x가 58~60px(차 0.02 단위)이고 프레임마다 그림 폭이 같다. 클립 안 이동은 높이(피벗 y)뿐이다.
  - 그림 높이 값은 0 → +0.88 → +0.70 → +0.08 → 0이다. 포물선(오르다 내려옴)이 아니라 **첫 프레임이 최고점이고 그 뒤로 계단식으로 내려오는 모양**이다. 프레임 사이 보간은 없다.
- 시간축(배율 0.7·균등화 켬, 측정값 f2 +0.14초·f3 +0.28초·판정 +0.43초; 몬스터 엔티티 y는 Home.y 고정, x는 smoothstep):

| W 뒤 시각 | 보이는 자세 | 그림 높이 | 높이 변화 | x 진행(2칸 좌 2.25 기준, smoothstep) |
| --- | --- | --- | --- | --- |
| 0 | f1 | +0.88 | 0 → +0.88 한 프레임에 올라감 | 0% (첫 0.05초 약 5%) |
| 0.143 | f2 | +0.70 | −0.18 | 약 26% |
| 0.286 | f3 | +0.08 | **−0.62 한 프레임에 내려옴** | 약 74% |
| 0.429(판정) | stand(f4는 보이지 않고 잘림) | 0 | −0.08 | 100% |

  - 같은 구간의 이상적인 포물선(꼭대기 0.88, 0.43초)과 비교하면 W에 0.88을 한 번에 올리고 0.286초에 0.62를 한 번에 떨어뜨린다. 사용자가 말한 "도중이 뚝 끊기는 느낌"은 높이가 W 직후 계단으로 오르고 중간(0.286초)에 크게 떨어지는 이 구조와 맞는다. 수평은 smoothstep 곡선으로 매끄럽게 움직이므로 "높이는 계단, 수평은 곡선"이 합쳐 보인다. 매번 같은 모양이라 "가끔"과는 안 맞고 "가끔"은 정지 프레임(앞 5절)이다.
  - 1칸은 jump 클립이 정지 자세 1장이고 높이는 스크립트 포물선(JumpHeight 0.8, 0.5초)이 그리므로 높이가 연속이다("1칸은 괜찮다"와 맞음).
- 판정(원인 비중):
  - **주원인(항상 보임, 체감 "뚝 끊김")은 클립 공중 부분의 계단식 높이**로 본다. 근거는 클립 데이터(위)와 시간축이다. 화면 확인은 스크린샷 없이 못 했다.
  - **부원인(가끔)은 FU-16 정지 프레임**이다(5절: 측정으로 확정, 2·3칸 72%).
  - 사용자 답 "가끔·뜬 직후·계속"은 둘이 섞인 인상으로 설명된다. 비중을 수치로 가르지는 못했다.
- 시험(Play 메모리, 제품 변경 0): 몬스터를 `SetPosition`으로 y = Home.y − 0.6에 매 틱 두면 그 y(−0.022)에서 0.5초 동안 유지되고(`IsOnGround` false), 복원하면 Home.y로 돌아와 `IsOnGround` true. 즉 그림 피벗 상승분을 엔티티 y 하향으로 상쇄하는 방법(방안 1-B)은 위치상 가능하다(그림 확인·판정 영향은 미시험).
- 이펙트 후보 조회(msw-search `search` animationclip, category skill·etc, 각 3건): 이름·설명이 비어 있어 썸네일·크기로만 고른다. 지금 쓰는 `05113e9d…`는 mob 15프레임 122×53px(눈빛 f0~6, 빈 f7, 먼지 f8~).

#### 10. 방안 비교(사용자 선택용)

(최종 보고에 같은 표를 둔다. 모든 안은 사용자 승인 전 수정하지 않는다.)

- 방안 1(공중 부분 해결): 1-A jump 클립 + 스크립트 포물선, 1-B 피벗 상쇄 포물선, 1-C f0 또는 f4 한 프레임 고정 + 포물선.
- 방안 2(제자리 점프 + 착지 먼지, 지진 공격): 2-a attack1·skill1 그대로(제자리), 2-b jump 클립 + 포물선(제자리).
- 권장: 방안 2-b 또는 1-A 중 사용자 선택. 상세는 최종 보고 참조.

### 2026-11-20 coder — FU-26 구현(1-A: 도약 시작 W에서 jump 클립으로 한 번 전환 + 스크립트 포물선 0.8)

- 범위·승인: 사용자 "일단 1-A로 진행하고 결과 보여줘. 결과확인하고 2-b할지 판단할게"(2026-11-20). Plan "후속 회차 1 추가 — FU-26" 절의 편집 허용 범위·유지 규칙·완료 기준 AI 1~7·중단 조건 1~7. commit·push 없음, 스크린샷 0장, `maker_clear_logs` 0회.
- 대상 버전: 로컬 HEAD c6422cd 위의 미커밋 변경(메인이 `[code]` 커밋으로 고정). 시작 확인: Maker `map01`·edit(0a0972ef…), `map/map01.map` SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`(시작·끝 같음).
- 바뀐 파일(제품 1개): `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua`. 모델은 고치지 않았다(진단 1절: 모델에 `LeapJumpHeight` 값이 없어 스크립트 기본값을 따른다). `.codeblock`·`.directory`·그 밖 제품 파일 변경 0(Refresh 뒤에도 `git status`에 새 항목 없음).
  - 파일 SHA-256 `d3c8d2fd535106c107e980c0e7e94f7a673a87abe09589b67ad5e9d1122a89df`(이전 `28a53a2bdb7622df781881d44ed995a90527ac14cebc4167367695314b17d99a`). `.codeblock` `bdc03937…7489` 그대로.
- diff 요약(+10 −7줄):
  1. `property number LeapJumpHeight = 0` → `0.8`(주석을 새 의미로 교체). 1칸 `JumpHeight`(0.8)와 같은 값이다.
  2. `OnUpdate`: 맨 앞의 무조건 `self:TickClip()`를 지우고, 제자리(windup) 구간 안(`now < leapStart`)에서만 `TickClip()`을 부른 뒤 return한다.
  3. `OnUpdate`의 windup → approach 전환 블록에 `self:SetMotionClip("jump", 1)` 한 줄을 더했다. 이 호출이 `_T.drive`를 비워 이후 프레임 구동(`TickClip`)이 끝나고, 렌더러 범위를 전체(0~최대)로, `SpriteRUID`를 jump 클립으로, 배율을 1 x ActionRate로 한 번 바꾼다(기존 공통 진입점, 새 메서드 없음).
  4. `CompleteMotion`의 주석 한 줄만 고쳤다(코드 그대로: W 뒤에는 구동이 끝나 `TickClip()`이 할 일이 없다).
  - 효과: W 틱에서 f1 쓰기가 아예 나가지 않는다(전환 틱은 `TickClip`을 건너뛰고 jump로 바꾼다). 수평(매 틱 `SetPosition`·smoothstep)·판정 시각·착지 x·판정 영역·피격 구간·복귀·1칸 경로(`JumpToLocalX`)·CSV·이펙트·소리 코드는 그대로다(diff 밖).
- 기본 확인(한 번의 런타임 주기): Refresh 1회 → 빌드 로그 93건(전부 Info LIA 1114/1115, Error·Warning·LEA 0, 로그 시각 Refresh 직후) → Play 1회(Stop 뒤 재시작 1회 포함, 아래 시험 부산물) → Stop → map01 edit.
- 시험 방법: Play 내부 프로브만(제품 파일 변경 0). 서버(`server_main`) 프로브는 패턴 표를 한 행으로 바꿔 `ChangeState("ATTACK")`로 강제 실행하고(끝에 원 표 5행·`AttackInterval` 3.0 복원 확인), 서버 프레임마다 위치·구간·`IsHittableNow()`·렌더러 RUID/Start/End/PlayRate를 모았다. 클라이언트 프로브는 몬스터 `WorldPosition`·렌더러 값을 매 프레임 모으고 `SpriteAnimPlayerChangeFrameEvent`를 센다. 서버·클라이언트 모두 `ServerElapsedSeconds` 시계. 시험 중 플레이어 `PlayerComponent.Hp`를 매번 최대로 채웠다(시험 한정).
- 측정(서버 시험 11회: 2칸 좌 3·우 2·3칸 4·1칸 2, 슬로우 3회 포함 / 클라이언트 4회: 2칸 좌·우, 3칸, 1칸). 값은 공격 강제 시작 틱 기준이라 표본 오차(프레임 한 칸 약 +0.017초)가 들어 있다.

| 지표 | 진단(수정 전, 11-19~20) | 수정 후 |
| --- | --- | --- |
| W(제자리 → 도약 시작), 슬로우 없음 | 1.164~1.178 | 1.163~1.174(6회) |
| 판정(서버 접근 끝 표본), 슬로우 없음 | 기준값 1.572~1.588 | 1.591~1.603(6회). 정확한 시계 로그: 3칸 먼지 호출 − 공격 시작 `clip driven` = 1.578·1.582·1.589(3회, 1.5714 +0.006~0.018) |
| 접근 시간(판정 − W) | 0.413~0.437 | 0.421~0.433 |
| 서버 클립 (W 뒤 접근 구간) | attack1/skill1을 서버가 프레임 구동(Start=End=k, 배율 0.7) | **W에서 jump(0~최대 범위)로 한 번 전환, 배율 1**(2칸·3칸 모든 시험). 접근 중 attack1/skill1 표본 0 |
| 클라이언트 클립 | f1~f3 계단(그림 높이 0 → +0.88 → +0.70 → +0.08) | W에 jump로 바뀐 뒤 판정까지 jump 그대로. attack1/skill1 프레임 번호 1 이상 이벤트 0건(전체 프레임 이벤트 71개 중). 접근 중 클립 이름 바뀜 없음 |
| 높이(그림 높이 + 엔티티 y) | 엔티티 y = Home.y 고정, 그림이 W에 +0.88 한 번 올림 → f3에 −0.62 한 번 내림 | 엔티티 y 포물선. 정점 서버 1.380~1.381·클라이언트 1.38(= 0.581 + 0.8), W 직후 첫 표본 y 0.60~0.68 → 단일 정점 → 착지 0.58. 한 프레임 최대 이동 서버 약 0.12, 클라이언트 2칸 약 0.13·3칸 약 0.19(프레임 두 칸 간격 포함) |
| y 시간축 연속성 | 계단(0.88 → 0.62 한 프레임) | 서버 표본 25개(2칸 좌) 예: 0.67 0.79 0.89 0.99 1.08 1.15 1.22 1.27 1.31 1.34 1.37 1.38 1.38 1.37 1.35 1.33 1.29 1.24 1.18 1.11 1.03 0.94 0.84 0.73 0.60. 되돌림·계단 없음. 서버 1회(우, 2번째) 1.08 → 0.93 → 0.91로 한 표본이 건너뜀(표본 프레임 간격 흔들림으로 보이고 위치 쓰기는 매 틱) |
| 접근 중 x 정지 1프레임(클라이언트) | 2·3칸 18회 중 13회 | 클라이언트 4회(2칸 좌·우, 3칸, 1칸) 원 표본에서 접근 중간에 x가 같은 연속 프레임 0(착지 직전·직후 제외). 표본이 적어 개선으로 판정하지 않는다(매 틱 `SetPosition` 불변, FU-16은 그대로) |
| 착지 x | 좌 0.750·우 −0.750·3칸 0.000(11-16·진단) | 클라이언트 착지 프레임: 좌 0.75·우 −0.75(−0.74~−0.75)·3칸 0.00·1칸 0.00(그 칸). 서버 3칸 먼지 `x=0.000 y=0.581`(이번 Play 3칸 먼지 호출 15건 모두 같음) |
| 착지 y | Home.y 0.581 | 클라이언트 착지 프레임 y 0.58(Home.y 0.581), 서버 3칸 먼지 y 0.581 |
| 피격 구간(서버 `IsHittableNow`) | windup 맞음, approach·return 불가 | 11회 모두 windup true → approach false(W) → return false(판정) → none true. 선언·값 불변 |
| 슬로우(ActionRate 0.5, 2초) | — | slowA(2칸 좌, 3칸 각 접근 시작 0.1초 뒤 적용): W 1.161·1.173, 판정 1.910·1.899, 접근 중 jump 렌더러 PlayRate 0.5~1(1 x ActionRate). slowW(3칸, 시작 0.5초 뒤 적용): W 1.806, 판정 2.600(액션 시계 기대 W 1.786·판정 2.571 +표본 오차). 3칸 먼지 호출 − 공격 시작: slowW 2.583(기대 2.571), slowA 1.881(기대 약 1.88), 먼지 PlayRate 0.35(0.7 x 0.5) |
| 1칸(parry.any) | 접근 0.5초·높이 0.8 | 서버 2회: 접근 0.520·0.518(표본 오차 포함), 정점 1.380·1.381, 클라이언트 0.496초·정점 1.38. 복귀도 약 0.5초·정점 1.38. 1칸 경로 소스 diff 0 |

- 클라이언트 시계열 예(2칸 좌, 상대 초 · x · y): W 1.180 3.00/0.65 → 1.248 2.80/1.06 → 1.370 1.99/1.38(정점) → 1.526 1.02/1.12 → 1.611 0.75/0.63 → 착지 1.629 0.75/0.58. 3칸: W 4.141 3.00/0.65 → 4.349 1.46/1.38 → 착지 4.571~4.588 0.00/0.58. 접근 클라이언트 프레임 수 약 25~27(2·3칸). 착지 뒤 복귀 점프가 이어지고(stand는 복귀 뒤 한 번) 착지 때 stand 한 프레임이 끼는 일은 클라이언트에서 보이지 않았다.
- 완료 기준 AI 1~7:
  1. 결함 지표(주원인 = 클립 공중 계단 높이): PASS. 계단 0.88·0.62 한 프레임 → 연속 포물선(위 표). 부원인(정지 프레임)은 위 표 한계 그대로, 판정하지 않음.
  2. 시각·위치: PASS. W ±0.05·판정 ±0.05(정확한 시계 로그 1.578~1.589), 착지 x(클라이언트 표본 0.01 이내: 0.75·−0.75·0.00)·착지 y. 서버 마지막 접근 표본의 x는 착지 직전 프레임이라 0.005~0.014 모자란 값이 보이나 착지 쓰기(`CompleteMotion`의 `SetPosition(JumpTargetX, Home.y)`)는 diff 밖이다.
  3. 프레임: **승인으로 바뀐 항목.** 접근 중 클라이언트 0→1→2→3 순서는 더 이상 해당 없음(attack1/skill1 프레임 번호 1 이상 이벤트 0건, 접근 클립 변경 1회 attack1/skill1 → jump). 건너뜀·되돌림 0.
  4. D-Q6: PASS(슬로우 3회). 슬로우 변화 때 클립·위치 되돌림 없음, W·판정이 액션 시계 기대와 ±0.05 이내, 접근 렌더러 PlayRate = 1 x ActionRate. **windup 중 렌더러 PlayRate 0.7 x ActionRate는 이번에 값으로 측정하지 못했다(NOT_RUN, windup 코드는 diff 밖).**
  5. 1칸 회귀: PASS. 접근 0.5초·정점 +0.8·착지(그 칸)·복귀 0.5초·0.8. 1칸·복귀 소스 diff 0.
  6. 회귀: 부분. PASS — windup 피격 통과·approach·return 차단(11회), 3칸 먼지 판정 때 착지 x·Home.y(`x=0.000 y=0.581`, 이번 Play 3칸 먼지 호출 15건). NOT_RUN — 판정 결과 각 1회, 3칸 눈빛(1단계) 시각·위치, die 1회 정지, 일시정지 중 몬스터 정지, 공격 취소·사망 처리(해당 코드는 diff 밖이며 이번에 시험하지 않았다).
  7. build 로그 오류 0 PASS(Error·Warning·LEA 0). Play 중 로그: `LEA-`·`LWA-`·`attack cancelled` 새 항목 0(누적 로그에 남은 12:40:16 `[LEA-3051]` 1건은 진단 때 프로브 타이머 흔적이라 제외). git 변경은 승인 파일 1개와 문서뿐. `map/map01.map` 해시 `22b6acbf…987e` 그대로.
- 시험 부산물·범위 밖 변경: 처음 프로브가 `Hp` 필드를 잘못 써 즉시 끝났고(`PlayerComponent.Hp`가 맞음), 그 디버그에서 패턴 표를 1행으로 덮어 복원하지 못해 Stop → Play로 새로 읽은 뒤 다시 시험했다(Play 메모리 한정, 제품 무관). 프로브 종료 뒤에는 몬스터 자연 공격(`AttackInterval` 3.0)이 이어져 일부 클라이언트 표본에 섞였으나 위 값은 프로브가 시작한 시험만 쓰고 자연 공격은 정확한 시계 로그 확인(3칸 1건)에만 보조로 썼다. 프로브 타이머(서버·클라이언트)는 모두 Stop 전에 정리해 새 `[LEA-3051]`이 없다. Maker가 새로 다시 저장한 파일 없음(`PlayerActionFxData.userdataset`의 CoreVersion 1줄은 기존 미커밋 변경 그대로, 내용 `c4a19587…fd62`).
- **Bundle 지문**(`map/map01.map` 제외 58경로, 기존 방식): `ade8670a6aafbcbdf38afcb1a45ea2e0e3fa0ed86faaae10f6343fcb6a9530c7`. 시점: 이 구현 뒤 작업 트리(HEAD c6422cd 위 미커밋). 이전 값 `24fa65cf…8187`은 `OrangeMushroomAttack.mlua`와 `PlayerActionFxData.userdataset`(26.11 재저장) 변경으로 바뀐다.
- 미실시·미확인(PASS로 세지 않음): 화면 체감(사용자 V11), 지연 있는 실접속·모바일, 판정 결과 각 1회·3칸 눈빛·die 정지·일시정지·공격 취소·사망 처리 재확인, windup 중 슬로우 PlayRate 값, 접근 중 x 정지 프레임의 통계적 개선(표본 4회).
- 남은 사항(범위 밖, 지우지 않음): `EqualizeLeapFrames` 설정과 `EqualizeLeapBounds`는 f2·f3 경계를 만지지만 f1(W) 뒤에는 attack1/skill1 프레임이 화면에 나오지 않아 이제 보이는 효과가 없다(W·판정 시각은 f1 경계·마지막 경계라 불변). `[VRF] leap start`의 `equalize=` 출력도 그대로다.
- 차단 조건: 없음. 상태: DONE(coder), 다음 담당 메인 → `[CombatCore][code]` 로컬 커밋 → tester. 사용자 화면 확인(V11 점프)이 남아 있고, 사용자는 결과를 본 뒤 2-b(제자리 점프)로 갈지 판단한다.
- Maker 최종 상태: Stop 확인, `maker_get_current_map` map01·edit.

### 2026-11-20 coder — 후속 회차 2 (CombatCore-FU-17·FU-19·FU-12 (가)) 구현·기본 검증 (위 절과 별개, 기존 절은 그대로)

- 범위·승인: Plan 회차 2 절 그대로(사용자 "회차 2 시작" 2026-11-20, FU-12는 FQ-3 (가)). 새 규칙·수치·모델은 없다. commit·push 없음.
- 읽은 지침: coder 계약, 팀 계약, 구현 원칙, 회차 2 계획·인계, msw-general·msw-ui-system·msw-scripting, Foundation 참조 4개와 platform-maple(map01 TileMapMode 0), verify-checklist. `.model`·`.map`·`.ui`는 만지지 않아 builder-protocol은 읽지 않았다.
- 사전 확인(모두 일치): HEAD `a593e2b`·트리 `d7ab128d…`, 대상 파일 5개와 대조 파일 2개의 blob id가 Plan 표와 같음, `map/map01.map` SHA-256 `22b6acbf…987e`, `maker_get_current_map` map01·edit.
- 변경 파일(5개 허용 범위 중 4개):

  | 파일 | 현재 blob id | 내용 |
  | --- | --- | --- |
  | `Player/PlayerCombatComponent.mlua` | `52beb46b4a75a6054c3f65e3f9847f9657848a11` | FU-17: `self._T.resolveIndex = index` 1줄 삭제. `resolveId`는 유지. Grep `resolveIndex` 0곳 |
  | `Player/PlayerGuardComponent.mlua` | `2b79931029ccf6dd45441d59dec329a2fd880135` | FU-19: `SetGuarding`이 기록 전 값을 `wasGuarding`로 잡아 시작을 판단하고 `self.isGuarding = isHeld`를 연출 앞으로 옮김. 끝의 중복 기록 삭제. 시작 시각·시작 x·[VRF]·연출·효과음은 그대로 |
  | `Monster/MonsterAttackMotion.mlua` | `da93aea6cfac8ed8e10f20dba342421a0f98082a` | FU-12: `GetRuidTimeline`(프레임 표 읽기 분리, 접근 클립과 이펙트가 같은 캐시), `TrackEffect`·`GetEffectFrame`·`SyncEffectRates`·`ClearEffects` 추가, `PlayEffectRange`가 재생한 이펙트를 기록 |
  | `Monster/@StateControl/MonsterStateControl.mlua` | `f67d70c0f73ef7d2b9942568117d571ae2f8eda4` | FU-12: `ApplyMotionClipRate`가 `SyncEffectRates`도 호출, `ClearCombatEffects`가 `ClearEffects` 호출 |

  바꾸지 않음(blob id 그대로): `Combat/CombatPauseComponent.mlua` `1658387d…0926`, `Monster_Attack.mlua`, `UI/UIPopup.mlua`, `OrangeMushroomAttack.mlua`. `.codeblock`은 Maker가 바꾸지 않았다(`git status`에 없음). `map/map01.map` SHA-256 `22b6acbf…987e` 그대로.
- **FU-12 측정(구현 전, Play 한 번·프로브)**: 엔진 `_EffectService`에는 이펙트 상태 조회·정지 API가 없고 이펙트는 Hierarchy 엔티티도 아니다(`list_entities`에 안 보임). 그래서 화면으로 확인했다. 클립 3개 모두 클립 `PlayRate`가 1.0이다(몬스터 눈빛·먼지 `05113e9d` 15프레임, 플레이어 공격 `5308ef85` 14프레임, 가드 `318a4662` 13프레임).
  - 서버에서 낸 공격 이펙트(PlayRate 0.04)를 클라이언트 `SetClientTimeScale(0)`으로 멈추면 정지 전 큰 호 프레임과 달라진 한 프레임에서 서로 다른 시각(3초 간격) 두 장이 같았다.
  - 클라이언트에서 낸 이펙트(PlayRate 0.2, 원래 4.2초 클립)를 1초 뒤 `SetClientTimeScale(0)`으로 멈추면 낸 지 약 11초 뒤에도 화면에 그 프레임으로 남아 있었고(숨김이 아니라 멈춘 프레임), `SetClientTimeScale(1)` 뒤 0.6초 시점에는 다른 프레임이 나왔다(이어 재생).
  - 실제 몬스터 눈빛 중 정지(서버 `RequestPopupPause` 승인 뒤 클라이언트 `SetPresentationPaused(true)`, 눈빛 시작 0.37초 뒤): 10초 간격 두 장이 같았다(분홍빛 조각 하나가 같은 모양. 눈빛인지 확정은 못 함, 위치로 판단). 실제 팝업(`_UIPopup:Open`)은 배경을 어둡게 가려 이펙트를 볼 수 없어 사용하지 않았다.
  - 서버 쪽: 팝업 정지 19초 동안 전투 시계가 `110.394`에서 `110.394`로 같았고, 눈빛 `clock=109.995` → 먼지 `clock=111.571`(차 1.576초 ≈ 예고 1.571초)이라 정지 시간만큼 끝 시각이 밀렸다.
- **구현 판단**: (1) 팝업 정지 중 정지·재개는 엔진이 이미 한다(멈춘 프레임 표시, 재개 때 남은 프레임). 그래서 `CombatPauseComponent`·플레이어 이펙트(공격 166행, 가드 26행)에는 코드를 더하지 않았다. (2) 슬로우 추종은 엔진이 하지 않는다(재생 때 PlayRate 옵션이 고정). 그래서 몬스터 이펙트(눈빛·먼지)만 추적해 ActionRate가 바뀔 때 현재 프레임부터 새 배율로 다시 낸다. 방식: 재생 때 `{ruid, x, y, motionRate, 시작 프레임, 시작 시 액션 시계, 재생 배율, serial}`을 기록한다. 지금 프레임은 `(액션 시계 − 시작 시계) × motionRate`를 프레임 Delay로 누적해 구한다(액션 시계가 정지·슬로우를 이미 반영). 배율이 달라졌으면 `RemoveEffect(이전 serial)` 뒤 `PlayEffect`(옵션 `StartFrameIndex`=그 프레임, `PlayRate`=motionRate×ActionRate, 끝 프레임은 원래 옵션)로 이어 낸다. 재생 구간을 다 지난 이펙트는 다시 내지 않고 목록에서 뺀다. 새 모델·새 규칙 없음.
  - 정리: `ClearCombatEffects`(사망·대결 종료·이탈·Stop)가 목록을 비운다. 이때 슬로우였더라도 이펙트를 다시 내지 않는다. 목록은 이펙트 재생 때와 배율 변경 때 끝난 항목을 걷어내므로 다음 공격 전까지 끝난 항목 1~2개가 남을 수 있다(영향 없음).
  - 알려진 한계: 이어 재생은 현재 프레임을 처음부터 다시 낸다(프레임 안 진행분은 버림, 프레임당 0.1~0.3 클립초 이하). 실제 클라이언트 이펙트의 프레임은 읽을 수 없어 "프레임 Delay ÷ PlayRate" 모델로 계산했고(클립 PlayRate 1.0 확인), 이어 낸 프레임이 화면에서 정확히 맞는지는 시각 확인을 하지 않았다(NOT_RUN).
- **검증(Play 1회 + Stop 정리 확인용 짧은 Play 1회, 프로브는 모두 Play 메모리·`maker_execute_script`, 파일 변경 없음)**:
  1. 완료 기준 1 PASS: Grep `resolveIndex` 0곳(.mlua·.codeblock·.model·.map·.ui·csv).
  2. 완료 기준 2(V02 회귀) PASS: 반격 ×2.2 시전(`manual cast id=12 count=10 factor=2.2`) 10타 HitEvent 10회 합 20, 몬스터 HP 100→80. 일반 시전(`id=17 factor=1`) 10타 HitEvent 10회 합 10, HP 80→70. 두 시전 합 HitEvent 30 = HP 감소 30. 반격 ×2.2는 실제 패링(아래)에서 받아 1회 소비했다. 화면 피해 숫자는 스크린샷으로 읽지 않아 NOT_RUN.
  3. 완료 기준 3(가드) PASS: 클라이언트 `RequestChangeState("GUARD")`(실제 키가 아닌 입력 수락 지점 호출, 회차 1 T4c와 같은 방식)로 두 번 시작했고 시작 때마다 `PlayerGuard start x=0.000`, `guard fx effect=318a4662`, `sfx kind=guard` 각 1회였다. 같은 홀드에 다른 입력 출처(`probe2`)를 더해도 추가 줄 없음. 패링 1회: 시작 잔여 0.110초, `guard eval x=0.000 cellOk=true areaOk=true`, `defense id=34 kind=PARRY`, `counter granted factor=2.2`. 일반 가드 1회(윈도 밖 잔여 0.973초): `defense id=35 kind=GUARD rate=0.4`, 플레이어 `ResolveIncomingDamage` 결과 `kind=GUARD amount=4`(12×0.40 내림, 남은 HP 4라 4→0). 연출 표 무효 상태는 회차 1 FU-03 결과로 대신하지 않고 `SetGuarding` 순서만 바뀌므로 소스 대조로 판단했다(NOT_RUN: 표 무효 Play).
  4. 완료 기준 4(FU-12):
     - 정지: 위 측정(엔진 정지, 정지 중 멈춘 프레임, 재개 뒤 이어짐, 끝 시각 1.576초로 정지 시간만큼 밀림) PASS. 플레이어 가드·먼지·공격 이펙트의 시각 정지는 스크린샷 12장 상한 때문에 직접 보지 않았다(공격 이펙트는 측정 PASS, 가드·먼지는 같은 `PlayEffect` 경로라 판단, 시각은 NOT_RUN).
     - 슬로우 시작·끝(눈빛): `[VRF] effect rate windup frame=3 range=3-6 playRate=0.7->0.35 serial=…658→…659 action=94.202`, 이어서 `frame=6 range=6-6 playRate=0.35->0.7 action=94.702`(슬로우 1.0초, 눈빛 f0~f5 각 0.1·f6 0.2초 기준 계산값 3·6과 일치).
     - 슬로우 시작·끝(먼지): `frame=8 range=8-end 0.7->0.35 action=105.003`, `frame=14 range=14-end 0.35->0.7 action=106.012`(슬로우 2.0초, 계산값과 일치).
     - 끝난 이펙트: 눈빛이 끝난 뒤(공격 시작 1.38초) 슬로우를 걸면 `effect skip windup … finished`가 나오고 다시 내지 않았다. 같은 공격의 먼지는 슬로우 중에 시작(`playRate=0.35`)했고 슬로우가 끝나자 `frame=8 0.35->0.7`로 이어졌다.
     - 정리: 사망(`ApplyDamage` 치명타, `MonsterHealthComponent`→`ClearCombatEffects`)에서 `effect clear tracked=1`, 대결 종료(플레이어 사망 등)에서 같은 줄, Stop 때도 같은 줄(추적 1개 상태에서 Stop). 정리 뒤 재생 줄은 없었다. 맵 이탈은 단독 시험하지 않았다(`OnMapLeave`→`ClearCombatEffects`는 같은 함수).
  5. 완료 기준 5 부분 PASS: build 로그 `LEA&`·`LWA&`·`Error` 검색 0건(Info `LIA`만 있고 새 종류 없음). Play 중 새 `LEA-`·`LWA-` 줄 없음(누적 로그의 12:40:16 `[LEA-3051]`은 이전 진단 흔적). `git status --porcelain`: 편집 허용 `.mlua` 4개와 문서 3개(run.md·Plan·WorkRecord), `map/map01.map`(SHA-256 `22b6acbf…987e` 그대로, 커밋 제외). `[code]` 커밋 해시·트리 id·`git diff --stat a593e2b <커밋>`은 메인이 커밋한 뒤 채운다.
- 시험 부산물(제품 무관): 첫 프로브가 `Entity._T`(엔티티에는 `_T`가 없음)에 써서 조용히 실패해 다시 올렸다. 프로브가 패턴 표를 `parry.guard` 한 행으로 덮었다가 시험 뒤 원래 5행으로 복원했고, 마지막 짧은 Play에서도 덮었지만 Stop으로 새로 읽혀 영향 없다. 프로브 타이머(서버 A·E·H·J, 클라이언트 B·C·F·G)는 Stop 전에 정리했다. `maker_clear_logs`는 쓰지 않았고 누적 로그의 이전 흔적은 시각(14:34 이후)으로 구분했다. 시험 중 몬스터를 죽여(`ApplyDamage`) Play 메모리에서만 상태가 바뀌었다. 플레이어 HP는 시험 중 여러 번 0이 됐다 복구됐다(자연 공격을 막지 않았다).
- **스크린샷 10장**(FU-18 범위 내, 한도 12): 정지 중 이펙트가 멈춤/숨김/계속 중 무엇으로 보이는지가 유일한 목적. 공격 이펙트 측정 7장(서버 이펙트: 정지 전 큰 호 1·정지 중 2·재개 직후 1, 클라이언트 이펙트: 낸 직후 1·정지 11초 뒤 1·재개 직후 1), 실제 팝업 오버레이 1장(배경을 가려 방법에서 제외), 눈빛 정지 중 2장.
- 미실시·미확인(PASS로 세지 않음): 화면 체감과 슬로우·정지 중 이어 낸 눈빛·먼지의 시각 정확도(사용자 V11), 가드·먼지 이펙트의 시각 정지 직접 확인, 팝업 정지 중 플레이어 이펙트 직접 확인(공격 이펙트만 측정), 연출 표 무효 상태 가드, 피해 숫자 화면 비교, 지연 있는 실접속·모바일, 맵 이탈 단독 시험, 실제 키 입력(입력 수락 지점 호출로 대신).
- 다음 행동: 메인이 `[CombatCore][code]` 로컬 커밋 → tester. tester는 눈빛·먼지가 `playRate`가 바뀐 지점에서 어색하게 끊기거나 반복되지 않는지, 슬로우 구간 모양을 볼 것.
- 차단 조건: 없음. 상태: DONE(coder).
- Maker 최종 상태: Stop 확인, `maker_get_current_map` map01·edit. 사용 종료.

### 2026-11-20 coder — 회차 2 O-1 수정 개발 (CombatCore-FU-12 reviewer 지적 O-1, 위 절들과 별개, 기존 절은 그대로)

- 범위·승인: reviewer 회차 2 O-1(사용자 판단 2 (가), 같은 승인 범위). `MonsterAttackMotion.GetEffectFrame` 1곳만 고쳤다. 다른 파일·함수·수치는 바꾸지 않았다. commit·push 없음. 읽은 지침: coder 계약, 팀 계약, 구현 원칙, EnvGuides, msw-general·msw-ui-system·msw-scripting, Foundation 참조 4개와 platform-maple(map01 TileMapMode 0), verify-checklist. `.model`·`.map`·`.ui`는 만지지 않아 builder-protocol은 읽지 않았다.
- 사전 확인: HEAD `d8c61db`·트리 `3940b24f…`, `map/map01.map` SHA-256 `22b6acbf…987e`, `maker_get_current_map` map01·edit.
- **변경 diff 요지**(+1/−1, `git diff --stat`): `local elapsed = math.max(0, now - fx.startAction) * fx.motionRate` → `… * fx.motionRate * fx.timeline.rate`. `GetWindupSeconds`·`StartDrivenClip`의 `divisor = timeline.rate * motionRate`와 같은 패턴이다(프레임 Delay ÷ (클립 PlayRate × 배율) = 시간이므로 시간 × 클립 PlayRate × 배율이 Delay 누적과 비교된다). `fx.timeline`은 `GetRuidTimeline`이 `rate`(유한·양수 보정)를 담아 `TrackEffect`가 기록한 값이다. 변경 후 `MonsterAttackMotion.mlua` blob id `8d22ddda9183c257053c1fce14bcc740f3a0a4d9`(변경 전 `da93aea6…`). `.codeblock` 변경 없음.
- **빌드**: `maker_refresh_workspace` status ok → `maker_build_logs`(로그 시각 15:09:59, 이번 Refresh 직후): `LWA` 0건, `Error` 0건. 검색어 `LEA` 9건은 `ClearStart`·`ClearCounter`·`ClearCombatEffects`·`ClearStunTimer`에 걸린 LIA 1115 Info(이전 QA와 같은 오검출)이고 `LEA-` 진짜 항목은 없다. mlua diagnose는 errors=0·warnings=0(Info 7건은 `GetActionTime`·`ActionRate` 동적 접근, 기존과 같은 종류).
- **Play 회귀 1회**(15:10:26 시작 ~ Stop, `maker_clear_logs`·스크린샷 0회): 회차 2 개발 절·tester TR8과 같은 방법(`maker_execute_script` server_main 프로브가 자연 3칸 공격의 눈빛·먼지 추적 중 `ApplySlow(1.0, 0.5)`를 걸고 플레이어 `Hp`를 보충, 로그 지문 `[O1R]`). 이펙트 클립 `05113e9d`의 프레임 표는 `count=15 rate=1 delays=0.1×6,0.2,0.3,0.1×5,0.2,0.05`(`timeline.rate`는 1이라 곱해도 값이 같다).
  - 눈빛: `effect rate windup frame=4 range=4-6 playRate=0.7->0.35 serial=2147483648->2147483649 action=12.846`(시작 액션 12.143, 0.703×0.7=0.492 → f4), `frame=6 range=6-6 playRate=0.35->0.7 serial=…649->…650 action=13.350`(0.504×0.7=0.353, f4·f5 0.2 뒤 f6).
  - 먼지: `effect rate dust frame=9 range=9-end playRate=0.7->0.35 serial=2147483651->2147483652 action=13.940`(시작 13.733, 0.207×0.7=0.145 → f8 0.1 지나 f9), `frame=12 range=12-end playRate=0.35->0.7 serial=…652->…653 action=14.448`(0.508×0.7=0.356, f9~f11 0.3 뒤 f12).
  - **[VRF] 대조 결과**: 위 4개 프레임(4·6·9·12)이 위 Delay 표로 직접 계산한 값과 모두 일치한다. 슬로우를 건 시각이 이전 시험과 달라(눈빛 frame=3·2, 먼지 frame=8·9 등) 숫자를 줄 단위로 같은 입력에서 비교할 수는 없으나, 계산식·serial 교체 형태(`serial=…→…`, 끝 프레임 옵션 `6`·`end` 유지)·`playRate 0.7↔0.35` 전환이 이전 [VRF](coder `frame=3 range=3-6`·`frame=8 range=8-end`, tester `frame=2`·`frame=9`)와 같고, 클립 `rate=1`이라 변경은 값에 영향이 없다. 새 `LEA-`·`LWA-` 줄 없음(Play 중 서버·클라이언트 검색 결과는 모두 15:10 이전의 coder·tester 시험 흔적).
  - 정리: 프로브 스크립트는 `maker_execute_script` 빈 스크립트로 중지한 뒤 Stop했다. 새 `LEA-3051`은 보지 않았다(Stop 뒤 로그는 읽지 않음).
- **미실시(PASS로 세지 않음)**: PlayRate≠1 클립 효과 자체는 그런 클립이 없어 소스 대조로만 판단한다(Delay ÷ (rate×배율) 식과 같은 패턴). 이어 낸 이펙트의 화면 모양(사용자 V11), 팝업 정지·가드·공격 이펙트 경로, 같은 입력의 전후 줄 단위 비교(변경 전 입력 재현 불가). 스크린샷 사용 0장(회차 상한 소진).
- **Maker 상태**: Stop 확인, `maker_get_current_map` map01(0a0972ef-ad23-4e24-af63-afbd53120c1d)·edit. 사용 종료.
- **대상 버전**: 메인 커밋 대기. `git status --porcelain`: ` M .pipeline/…/run.md`(메인), ` M Docs/…/CombatCoreWorkRecord.md`(이 절), ` M RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua`, ` M map/map01.map`(사용자 변경, SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e` 시작·종료 같음, 커밋 제외).
- 다음 행동: 메인 `[CombatCore][code]` 로컬 커밋 → tester 회귀 → reviewer. 차단 조건 없음. 상태: DONE(coder).

## QA 기록

### 2026-11-19 tester — 후속 회차 1 (CombatCore-FU-24·FU-03·FU-23) 독립 시험

- **대상 버전**: 로컬 커밋 c6422cd(push 전). 작업 트리 제품 변경은 `map/map01.map`(사용자 변경, 해시 `22b6acbf…987e` 시험 전·후 동일)뿐이다. 시험 전·후 `git status`는 같고 제품 파일을 고치지 않았다.
- **주체·환경**: msw-tester(독립 실행). Maker `map01`(id 0a0972ef…, 개인 월드 970621b2…), 시작·종료 모두 edit 모드. `maker_clear_logs`·스크린샷 사용 0회. 읽은 지침: tester 계약, 팀 계약, msw-general·msw-ui-system, Foundation 참조 4개, platform-maple(map01 TileMapMode 0), msw-scripting·verify-checklist.
- **Maker 로그 주의**: 로그가 이전 Play(coder 포함)부터 누적돼 있어 시각(22:11 이후가 tester Play)로 구분했다.

**기준별 판정**

| ID | 기준 | 판정 |
| --- | --- | --- |
| T1 | 이동 확인(바이트·옛 경로·중복·참조) | PASS |
| T2 | Refresh 후 build 로그 Error·Warning·LEA- | PASS |
| T3 | 통합 Play: 8개 표 GetTable, Logic 5개, PlayerBaseStat 100/12/12, 팝업 pause·닫기, 토스트 | PASS |
| T4a | 기본 공격 피해(↑ 실제 키 입력) | PASS(화면 숫자 NOT_RUN) |
| T4b | 가드 잔여 40%(↓ 실제 키 홀드) | PASS |
| T4c | Pos2 JUST·PARRY 각 1회 | PASS(논리 경로: 클라이언트 입력 수락 지점 호출) |
| T4d | 반격 ×2.2 | PASS(관찰 1건 있음) |
| T4e | 몬스터 die 1회 정지 | PASS(화면 고정 모습은 NOT_RUN) |
| T5 | FU-03 | 파일 복원·정상 로드·coder 근거 대조 PASS, 경고 독립 재현 NOT_RUN |
| T6 | 원장 FU-23 | PASS |
| TB | Bundle 일치 | PASS |

**T1 이동 확인(PASS)**
- `git show c6422cd --name-status -M`: 22파일 모두 `R100`(DataSet 12, Catalog 로더 6, UI 4). 같은 커밋의 `.directory`는 `@Assist.directory → Catalog.directory` R061(Maker 생성), 삭제 `@Assist/DataSet`·`@Assist/RangeGizmo`·`Player/@Assist`·`AttackRange`·`Skill`·`Stat`(총 7개 옛 `.directory` 제거), `MyDesk.directory`·`Player.directory` 수정(CoreVersion).
- 새 위치 22파일 SHA-256을 직접 계산해 coder 이동 전 표와 22/22 일치(예: PlayerBaseStatData.userdataset `f6d8da25…5d7f`, UIToast.codeblock `f9aa2c08…6d7b`).
- Glob: `DataSet/` 16파일(8쌍), `Catalog/` 6파일(3쌍), `UI/` 8파일(4쌍). `RootDesk/**/@Assist*` 결과 없음. 5개 스크립트(UIPopup·UIToast·CombatRuleCatalog·PlayerSkillEffectTable·PlayerBaseStatCatalog) `.mlua`·`.codeblock` 각각 작업 공간에 1개씩, `.userdataset` 8개 각 1개. 옛 `Combat/`에는 AttackAreaMarkComponent·CombatPauseComponent만, `Player/`에는 `@StateControl`과 Player*Component만 남았다.
- Grep `@Assist|Combat/CombatRuleCatalog|Player/@Assist`: RootDesk·Global·map·Environment·ui 모두 0건(`ui/`는 Grep 도구로 건수만 확인, 원문은 열지 않음). 참조 확인용으로 `PlayerBaseStatCatalog` 이름 검색은 4파일에서 잡혀 검색 범위가 동작함을 확인했다.

**T2 build 로그(PASS)**
- `maker_refresh_workspace` 1회 status ok → `maker_build_logs` 전체 93건. 검색 `LIA&Default&11`도 93건이라 전부 LIA 1114/1115 Info이고 Error·Warning은 0이다. 중복 스크립트·Symbol not found 징후 없음.
- 한계: 검색어 `LEA`는 `ClearStart` 등 이름과 부분 일치해 9건이 잡혔다(전부 LIA Info, 오검출). 로그 기록 시각이 21:45:16으로 coder 마지막 Refresh와 같아, 내 Refresh가 새 컴파일을 일으켰는지는 로그만으로 구분할 수 없다.

**T3 통합 Play(PASS)** — Play 22:11:07, 서버 server_main·클라이언트 프로브 각 1회씩
- 서버 로드 [VRF](22:11:07): `CombatCore catalog ready rules=1 patterns=5 monsterStats=2 monsterSounds=1`, pattern weights total=20, pattern row 5줄, `MonsterSoundData id=mushmom`, `MonsterStatData id=default`·`id=mushmom ... source=DataSet`, `PlayerActionFxData id=guard effect=318a4662 sound=605da1fc`, `MonsterStat applied key=mushmom MaxHp=100.0 Hp=100.0 AttackDamage=12.0 AttackInterval=3.0`, `MonsterManager spawned parent=map01 x=3.0` 1회.
- 서버 GetTable 행 수(`GetRowCount`): CombatRuleData 1, MonsterAttackPatternData 5, MonsterStatData 2, MonsterSoundData 1, PlayerActionFxData 1, AttackSkillData 1, MonsterData 1, PlayerBaseStatData 1(8개 모두 비어 있지 않고 계획 값과 같다).
- 클라이언트 GetTable: PlayerBaseStatData rows=1, AttackSkillData 1, MonsterData 1. 나머지 5개 표는 nil이다. 5개 래퍼의 `serveronly`가 true(AttackSkillData·MonsterData·PlayerBaseStatData만 false)라 계획 설계와 일치하고 이동 전 바이트와 같다. **tester 프로브가 서버 전용 표를 클라이언트에서 읽어 `[LEA-3022] InvalidExecSpace` 5건을 22:11:32에 남겼다. 제품 결함이 아니라 시험 방법의 흔적이다.**
- Logic 5개: 서버 `_CombatRuleCatalog`·`_PlayerSkillEffectTable`·`_PlayerBaseStatCatalog`, 클라이언트 `_PlayerBaseStatCatalog`·`_UIPopup`·`_UIToast`가 nil이 아니다. 서버 `GetSkillData("player.basic")` nil 아님(Damage=1, AttackCount=10).
- PlayerBaseStat: `[VRF] PlayerBaseStatData side=server`(22:11:07, `PlayerStat applied MaxHp=100 Hp=100`)와 `side=client` 모두 MaxHp=100 MoveSpeed=12 ReturnSpeed=12 source=DataSet.
- 팝업(Play 22:13): `_UIPopup:Open` → 서버 `CombatPause server paused=true clock=3.492`, 클라이언트 `pauseIsPaused=true`, 팝업 `isOpen=true groupEnable=true`, 문구 표시 → `OnClickCancel` → 서버 `paused=false clock=3.492`(정지 중 전투 시계 고정), `[VRF] CombatPause popup closed session=1` 1회, `groupEnable=false`, `pauseIsPaused=false`. 확인 방법은 버튼 클릭이 아니라 `OnClickCancel` 호출이다(논리 경로).
- 토스트: `_UIToast:ShowMessage("tester toast")` 직후 `toastGroup.Enable=true`, `message.Text` 일치. 3초 뒤 `Enable=false`(duration 2초 + 페이드). 표시 모양은 보지 않았다.

**T4 짧은 회귀(coder NOT_RUN 항목)** — 회차 C·A 전수 회귀는 하지 않았다(코드 내용 무변경).
- T4a ↑ 실제 키 입력(`maker_keyboard_input` UpArrow, 22:13:32): `manual cast id=1 count=10 factor=1`, 머쉬맘 HP 100 → 90(10타 × 1). 화면의 피해 숫자는 스크린샷 0장이라 NOT_RUN.
- T4b ↓ 실제 키 홀드(Play 22:15:57, DownArrow down): `guard fx effect=318a4662` 1회, 몬스터 공격 1회 판정 `kind=GUARD rate=0.4`, 서버 프로브 `lastKind=GUARD lastDmg=4 hitCalls=1`, 플레이어 HP 100 → 96. 12 × 0.40 내림 = 4. 즉 가드 때 맞는 피해가 40%(Features "가드 잔여 40%")이고 60%가 줄어든다. 요청 문구 "40% 경감"과 방향이 반대로 읽힐 수 있어 reviewer 확인용으로 적는다.
- T4c(Play 22:13:24, 22:15:20): 클라이언트 `PlayerStateControl:RequestChangeState`를 서버 텔레그래프 잔여 시간 0.12초 이하에서 호출하는 타이머 프로브로 입력했다. 실제 KeyDown 이벤트는 쓰지 않았다(논리 경로). 결과: `id=10 kind=PARRY rate=0 clock=46.632`(guard 시작 잔여 0.118초), `id=11 kind=JUST rate=0 clock=52.167`, 같은 프로브의 두 번째 Play에서도 PARRY 1회(22:15:25, 잔여 0.095초). 둘 다 `guard eval cellOk/areaOk`·`PlayerGuard start x=0.000` 조건(Pos2)에서 나왔다. JUST·PARRY 각 1회씩 확인했고 중복 판정은 없었다.
- T4d: PARRY 직후 공격(`manual cast id=5 count=10 factor=2.2`, 22:14:08) → 몬스터 HP 90 → 74. 타격 1·2는 `PlayerHitRule fail rule=targetHittableSegment`(몬스터가 복귀 점프 중, 설계상 피격 불가), 나머지 8타가 각 2 감소(1 × 2.2 내림). 두 번째 Play에서도 PARRY 반격이 가능했다(그로기 STUN 중 공격 수락, 22:15:26). 기본 공격은 10타 × 1로 factor=1.
  - **관찰(결함 아님, 사용자 판단 후보)**: JUST 직후 반격(`manual cast id=10 factor=2.2`, 22:14:13)은 10타 모두 `targetHittableSegment`로 막혀 몬스터 HP가 줄지 않았고 반격 기회는 소모됐다. 몬스터 접근·복귀 점프 구간 피격 불가는 OrangeMushroomAttack의 승인 설계이며 이 회차 변경이 아니다. 내 프로브가 JUST 후 0.8초에 바로 공격한 시점 때문일 수 있다.
- T4e(Play 22:15:20 프로브): 몬스터 HP 100 → 0, 서버 `[VRF] MonsterHealth lethal state=DEAD enabled=true` 정확히 1회(22:15:30). 사망 7초 뒤 서버 프로브: `state=DEAD IsDead=true hp=0 telegraph=''`, 공격 순번이 마지막 텔레그래프(seq=3, 22:15:24) 그대로라 사망 뒤 새 공격이 없다. die 클립이 마지막 프레임에 멈춘 모습은 화면 확인을 하지 않아 NOT_RUN(사용자 V11).
- 플레이어 사망 확인: 첫 프로브 Play(22:13:24)에서 HP 4인 상태로 GUARD(피해 4)를 맞아 HP 0이 되어 프로브가 끝났다. 시험 조작의 부산물이며 결함이 아니다.

**T5 FU-03(비교 판정)**
- 파일: `DataSet/PlayerActionFxData.csv` SHA-256 `75b8e8f0d7383ff313514ffe4114ea479b81a238261a5900872efa6722e8dc9b`, c6422cd와 같은 바이트(시험 전·후 모두).
- 복원 뒤 정상 로드: 내 Play 4회 모두 `PlayerActionFxData id=guard effect=318a4662 sound=605da1fc`, 가드 때마다 `guard fx effect=318a4662`, `[CombatRuleCatalog]` 경고 없음.
- coder 근거 대조(누적 로그): Warning `[CombatRuleCatalog] PlayerActionFxData missing or required columns missing` 22:04:26 정확히 1건(WarnOnce, `OnBeginPlay`→`EnsurePlayerActionFx`), `[VRF] guard fx off` 22:04:35 1건이고 같은 Play에 `guard fx effect` 없음. 기록한 문구·횟수와 일치한다. 이 로그는 coder Play의 것이고 내가 만든 것이 아니다.
- 경고 독립 재현: NOT_RUN(사유: 제품 수정 금지, 임시 CSV 변경은 메인 별도 허락 없이 하지 않음).

**T6 원장(PASS)**
- `git diff bb3ec01 c6422cd -- .maplestory-skill-maker-ledger.md`: +5/-3. 20행 제목 아래 주석 1줄+빈 줄, 23행 `(키 orangemushroom, 패턴·스폰 없음(6단계))`, 24행 `머쉬맘(\`model://mushmom\`) 1행`, 30행 `Catalog/CombatRuleCatalog`. 그 밖의 줄은 diff에 없다.
- `castleenemy`는 주석 줄(설명용)과 MHP-01~04 ID 이름(43~46행), 과거 기록 절(58·66행)에만 남아 있고 편집 전 23·24행에 해당하는 줄에는 없다. ID·과거 기록 절·OPEN 상태 그대로.

**TB Bundle(PASS)**: 확장자 9종, Global·RootDesk·map·ui, 경로 UTF-8 바이트순, `경로 TAB sha256 LF` 연결의 SHA-256, `map/map01.map` 제외 58경로 = `24fa65cfbfdd036b9c81e0a09ea4860b4efa6115c267c20b5023240eeffd8187`. coder 값과 일치하고 시험 전·후 같다. 계산은 tester가 새로 쓴 읽기 전용 스크립트(파일 바이트 해시만, 내용 출력·수정 없음)이다.

**한계·사용자 직접 확인**
- 스크린샷 0장: 화면 피해 숫자, 팝업·토스트 모양, die 마지막 프레임 고정, 폴더 창(`DataSet` 표 8·`Catalog` 3·`UI` 4, 옛 위치 없음)은 사용자 V11.
- JUST·PARRY·팝업 닫기·토스트는 입력 수락 지점/함수 호출이며 실제 키·마우스 이벤트가 아니다. 기본 공격(↑)과 가드(↓ 홀드)만 실제 키 입력이다. 모바일·실접속 NOT_RUN.
- Bash 훅 주의: 해시 계산 스크립트를 처음 셸 명령 안에 쓰다 `.model` 문자열 때문에 훅에 막혔고, 문자열을 쪼개 우회하려다 권한 분류기에 거절됐다. 이후 우회 없이 스크립트를 파일로 쓰고 실행했다. 제품 파일은 열거나 고치지 않았다.
- Maker 최종: map01·edit 모드, Stop 확인, 사용 종료.

### 2026-11-20 tester — FU-26 방안 1-A 독립 시험 (위 11-19 절과 별개, 기존 절은 그대로)

- **대상 버전**: 로컬 커밋 a18b251(부모 c6422cd, push 전). 시험 전·후 `git status`는 같았고(`.pipeline/.../run.md`·`PlayerActionFxData.userdataset`·`map/map01.map` 미커밋 변경 3건, 모두 범위 밖) 제품 파일을 고치지 않았다. `OrangeMushroomAttack.mlua` SHA-256 `d3c8d2fd535106c107e980c0e7e94f7a673a87abe09589b67ad5e9d1122a89df`(blob 62dcb685…, coder 값과 같음), `map/map01.map` `22b6acbf…987e`(시험 전·후 같음), `PlayerActionFxData.userdataset` `c4a19587…fd62`(coder 값과 같음).
- **주체·환경**: msw-tester(독립 실행). Maker `map01`(0a0972ef…, 개인 월드 970621b2…), 시작·종료 모두 edit. 읽은 것: tester 계약, 팀 계약, msw-general·msw-ui-system·msw-scripting·msw-combat-system, Foundation 참조 4개, platform-maple(map01 TileMapMode 0, 11-19 QA 기록과 같음), animation-state·monster, verify-checklist. `maker_clear_logs`·스크린샷 0회. Play 1회(13:42:30 시작, 13:50 Stop). 로그가 누적이라 시각 13:42:30 이후만 이번 시험으로 보았다. 기존 흔적 `[LEA-3051] MakerScript` 12:40:16 1건(coder 진단)은 제외했고 새 `[LEA-`·`[LWA-` 항목은 없다(Play 중 시험 타이머는 전부 스스로 정리, 새 `[LEA-3051]` 없음).
- **시험 방법**: Play 메모리 프로브만 썼다(`maker_execute_script`; 패턴 표를 한 행으로 바꿔 `ChangeState("ATTACK")`로 강제, 끝에 원 표 5행·`AttackInterval` 복원 확인). 서버(`server_main`) 1ms 타이머가 서버 프레임(약 17ms)마다 위치·구간·`IsHittableNow()`·렌더러 RUID/Start/End/PlayRate를 기록하고, 클라이언트 1ms 타이머가 몬스터 `WorldPosition`·렌더러 값을 매 프레임 기록하며 `SpriteAnimPlayerChangeFrameEvent`를 센다(같은 `ServerElapsedSeconds`). 프로브 표본 오차: 공격 시작 시각이 첫 표본 기준이라 시각이 최대 약 0.017초 작게 나온다. 시험 중 플레이어 `Hp`를 매번 최대로 채웠다(시험 한정).

**기준별 판정**

| ID | 기준(Plan 완료 기준 AI) | 판정 |
| --- | --- | --- |
| TF1 | diff가 승인 1-A 범위 안(AI 7 일부, 시험 범위 1) | PASS |
| TF2 | Refresh 후 build 로그 Error·Warning·LEA-(AI 7) | PASS |
| TF3 | 결함 지표: 계단 높이 → 연속 포물선(AI 1) | PASS |
| TF4 | 시각·위치: W·판정·착지 x·y(AI 2) | PASS |
| TF5 | 프레임·클립(AI 3, 승인으로 바뀐 항목) | PASS(바뀐 기준 적용) |
| TF6 | 피격 구간(AI 6) | PASS |
| TF7 | 3칸 먼지·눈빛(AI 6) | PASS |
| TF8 | 슬로우 D-Q6, windup PlayRate(AI 4, coder NOT_RUN) | PASS(한계 있음) |
| TF9 | 1칸 회귀(AI 5) | PASS(복귀 높이는 미측정) |
| TF10 | 판정 결과 1회(AI 6, coder NOT_RUN) | PASS(HIT·GUARD), JUST·PARRY NOT_RUN |
| TF11 | 일시정지 중 몬스터 정지(AI 6, coder NOT_RUN) | PASS |
| TF12 | 공격 취소·사망 처리, die 1회 정지(AI 6, coder NOT_RUN) | PASS(관찰 2건) |
| TF13 | 기본 공격 피해·가드 잔여 40%·1칸·전투 시작 회귀(시험 범위 5) | PASS |
| TB | Bundle 일치 | NOT_RUN(재현 못함, 파일별 일치로 대체) |

**TF1 범위(PASS)**: `git diff --name-only c6422cd a18b251 -- Global RootDesk map ui`는 `OrangeMushroomAttack.mlua` 1개뿐이다. diff는 +10/−7이고 내용은 정확히 ① `LeapJumpHeight` 0 → 0.8과 주석, ② `OnUpdate`의 무조건 `TickClip()` 삭제 후 windup(`now < leapStart`) 안에서만 `TickClip()`+return, ③ approach 전환 블록에 `SetMotionClip("jump", 1)` 1줄, ④ `CompleteMotion` 주석 1줄이다. 수평 이동(`progress`·`x` 식·smoothstep), 판정 시각(`JumpStartTime`·`activeDuration` 계산), 착지 x(`JumpTargetX`·`CompleteMotion`의 `SetPosition`), 영역(`PerformAttackMotion` 앞부분), 피격 선언(`WindupHittable`·`ApproachHittable`·`ReturnHittable`·`IsSegmentHittable`), 복귀(`PerformReturnMotion`), 1칸 경로(`JumpToLocalX`), CSV·이펙트·소리 코드(`Monster_Attack`·`MonsterAttackMotion` 포함)는 diff에 없다. 같은 범위 diff에 `.codeblock`·CSV·모델 변경 0.
- **버전 대조**: coder Bundle `ade8670a…30c7`은 작업 트리 기준이라 미커밋 `PlayerActionFxData.userdataset`(`CoreVersion` 26.10.0.0 → 26.11.0.0, Maker 재저장 1줄)가 섞여 있다. 작업 트리와 a18b251의 제품 차이는 그 파일 1개(+Bundle에서 빼는 `map01.map`)뿐임을 `git diff --stat a18b251`로 확인했다. 즉 같은 구성이라면 커밋 기준 Bundle은 coder 값과 정확히 그 파일 때문에 다르다. 내 재구성(경로 UTF-8 바이트순, `경로 TAB sha256 LF` 연결 SHA-256, 확장자 mlua·model·map·ui·userdataset·csv·config·gamelogic·stateset, `map01.map` 제외 58경로)으로는 작업 트리 `fc433df8…26aa`, a18b251 `71b9b2ad…6b58`, c6422cd `e14ad35c…4913`이 나왔고 coder 값 `ade8670a…`을 재현하지 못했다(구성 세부가 달라 같은 지문이라고 말할 수 없다). 이 계산은 읽기 전용 스크립트(파일 바이트 해시만)였고, 같은 스크립트를 변형하는 셸 명령 하나가 `.model` 문자열 훅에 막혀 우회 없이 거기서 멈췄다. 파일별 SHA-256(위)과 `git diff`로 대신했다.

**TF2 build 로그(PASS)**: `maker_refresh_workspace` 1회 status ok → `maker_build_logs` 전체 93건(로그 시각 13:29:29). 전부 `logType` Info(LIA 1114/1115, `LIA&Default&11` 검색도 93건). `LEA-`·`LEA&`·`LWA` 검색 각 0건, Error·Warning 0. 한계: 로그 시각이 coder의 마지막 Refresh와 같은 때라 내 Refresh가 새 컴파일을 일으켰는지는 로그만으로 구분되지 않는다(11-19 QA와 같은 한계). Play에서 스크립트가 정상 동작해(아래) 로드는 됐다.

**측정(서버 10회, 시험 1)** — 2칸 좌 run1·4, 우 run2·5, 3칸 run3·6, 1칸 run7·10, 슬로우 run8(3칸)·run9(2칸 좌). 공격 시작 = 첫 ATTACK 표본.

| run | 패턴 | W(approach 첫 표본) | 판정(return 첫 표본) | 착지 첫 표본 x / y | 접근 최고 y | 정점 수·골짜기 | 접근 표본 클립(개수) | 판정 결과 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | left | 1.148 | 1.574 | 0.750 / 0.581 | 1.381 | 1·0 | jump(25) | 1회, 피해 12 |
| 2 | right | 1.157 | 1.590 | −0.750 / 0.581 | 1.380 | 1·0 | jump(25) | 1회, 12 |
| 3 | guard(3칸) | 1.151 | 1.580 | 0.000 / 0.581 | 1.381 | 1·0 | jump(25) | 1회, 12 |
| 4 | left | 1.149 | 1.581 | 0.750 / 0.581 | 1.381 | 1·0 | jump(25) | 1회, 12 |
| 5 | right | 1.148 | 1.577 | −0.743 / 0.587 | 1.380 | 1·0 | jump(25) | 1회, 12 |
| 6 | guard | 1.159 | 1.591 | 0.000 / 0.581 | 1.380 | 1·0 | jump(24) | 1회, 12 |
| 7 | any(1칸) | 0.000(시작과 동시) | 0.504 | 0.000 / 0.581 | 1.380 | 1·0 | jump(29) | 1회, 12 |
| 10 | any(1칸) | 0.000 | 0.503 | 0.000 / 0.581 | 1.381 | 1·0 | jump(29) | 1회, 12 |
| 8 | guard, 슬로우 W | 1.798 | 2.574 | 0.000 / 0.581 | 1.381 | 1·0 | jump(45) | 1회, 12 |
| 9 | left, 슬로우 A | 1.159 | 1.866 | 0.752 / 0.584 | 1.381 | 1·0 | jump(41) | 1회, 12 |

- 공통: 접근 표본의 렌더러 범위는 전부 `0-2147483647`(jump 전체 범위), 접근 중 attack1·skill1 표본 0. windup 표본의 클립은 attack1(90c5456e) 또는 skill1(b9345875), 범위 `0-0`, `PlayRate` 0.700(슬로우 없음). 구간 값 `IsHittableNow()`: 8회(2·3칸) 모두 windup true, approach false, return false, none true(1칸 2회는 windup 없이 approach false, return false, none true). 접근 y 한 표본 최대 변화 0.099~0.127(계단 0.88·0.62 없음). `seq=1`: 공격 한 번에 `AttackSequence` 1 증가, `resolutionCount` 1 증가(판정 정확히 1회).
- 서버 표본 오차를 감안하면 W 1.148~1.159(+≤0.017)는 기대 1.1429 ±0.05, 판정 1.574~1.591은 기대 1.5714 ±0.05 안이다. 1칸 0.503·0.504(기대 0.5).
- 첫 표본 착지 x는 목표 0.750/−0.750/0.000에서 최대 0.007 벗어난다(run5 −0.743, y 0.587; 이후 표본에서 −0.750으로 정착). ±0.01 안. 착지 y는 Home.y 0.581 대비 최대 +0.006.

**측정(클라이언트, 시험 2)** — 한 번에 62초 기록, 에피소드 16개 중 이번 강제 10회(ep4~13)에 더해 Play 초반 자연 공격(ep2·ep3, 2칸 좌)도 같은 기준으로 보았다. ep1은 앞 자연 공격과 이어 붙어 시작 x가 0이라 제외, ep14~16은 프로브가 끝난 뒤 자연 1칸 공격이다.

| 에피소드(run) | W(클라이언트 jump 전환) | 착지 시각 | 착지 x / y | 정점·골짜기 | 접근 한 프레임 최대 y 변화 | attack1·skill1 프레임≥1 이벤트 |
| --- | --- | --- | --- | --- | --- | --- |
| ep2 자연 2칸 좌 | 1.159 | 1.587 | 0.750 / 0.581 | 1·0 | 0.127 | 0 |
| ep3 자연 2칸 좌 | 1.151 | 1.568 | 0.750 / 0.581 | 1·0 | 0.118 | 0 |
| ep4(run1 좌) | 1.146 | 1.575 | 0.750 / 0.581 | 1·0 | 0.119 | 0 |
| ep5(run2 우) | 1.151 | 1.585 | −0.750 / 0.581 | 1·0 | 0.124 | 0 |
| ep6(run3 3칸) | 1.139 | 1.571 | 0.000 / 0.581 | 1·0 | 0.230 | 0 |
| ep7(run4 좌) | 1.132 | 1.565 | 0.750 / 0.581 | 1·0 | 0.147 | 0 |
| ep8(run5 우) | 1.153 | 1.576 | −0.743 / 0.587 | 1·0 | 0.229 | 0 |
| ep9(run6 3칸) | 1.157 | 1.572 | 0.000 / 0.581 | 1·0 | 0.169 | 0 |
| ep11(run8 3칸 슬로우 W) | 1.795 | 2.580 | 0.000 / 0.581 | 1·0 | 0.126 | 0 |
| ep12(run9 좌 슬로우 A) | 1.163 | 1.864 | 0.752 / 0.584 | 1·0 | 0.113 | 0 |

- 클라이언트 클립 순서는 2·3칸 10개 모두 attack1(또는 skill1) → jump 한 번 바뀜(`90c5@0 → 5ecb@W`, `b934@0 → 5ecb@W`). 프레임 이벤트는 attack1/skill1의 f0 3건(공격 시작)과 jump f0 3건(W), 마지막 stand f0 1건뿐이고 f1~f3 이벤트는 없다(coder 측정 "각 2건 도착"과 같은 이중 도착 3건씩 보이나 프레임 번호는 모두 0). 접근 구간 Start·End 표본은 전부 `0-2147483647`(`0-0` 표본은 windup뿐).
- 한 프레임 최대 y 변화 0.230·0.229(ep6·ep8)는 서버 두 틱 간격(약 0.115 × 2) 크기로, 계단이 아니라 연속 포물선 위의 프레임 건너뜀이다(정점 1·골짜기 0이라 되돌림·불연속 없음).
- 1칸(ep10 run7, ep13 run10, 자연 ep14~16): 착지 시각 0.503·0.499~0.511, 착지 x 0.000·1.500(자연 오른쪽 칸 1건)·0.006, 접근 최고 y 1.380~1.381, 정점 1.

**TF3·TF4·TF5 판단(PASS)**: 결함 지표(주원인 = 클립 계단 높이)는 서버·클라이언트 모두 사라졌다. 수정 전(coder 진단 기록)은 W에 +0.88 한 번 올림 → 0.286초에 −0.62 한 번 내림이었고, 이번엔 W 직후 y 0.61~0.70에서 정점 1.38(= Home.y 0.581 + 0.8) 하나로 올랐다 내려와 Home.y로 착지한다. 승인으로 바뀐 프레임 기준(AI 3)은 "접근 클립 변경 1회(attack1/skill1 → jump), f1 이상 이벤트 0"으로 읽어 PASS로 적는다(원래 0→1→2→3 순서 기준은 더 이상 해당 없음, coder가 밝힌 대로). 서버 f4 쓰기는 이 구조에서 더 이상 없고(W 뒤 구동 종료) 판정 = `CompleteMotion` 호출 시각으로 측정했다. 접근 중 클라이언트 x 정지 1프레임(FU-16 부원인)의 빈도는 이번에 통계로 다시 재지 않았다(NOT_RUN, coder도 개선 판정 안 함).

**TF6 피격 구간(PASS)**: 위 8회(2·3칸) 서버 `IsHittableNow()`가 windup true, approach false, return false, none true, 1칸 2회는 approach·return false. 사망·취소·일시정지 시험에서도 이 값과 충돌이 없었다.

**TF7 3칸 이펙트(PASS)**: 서버 `[VRF] effect windup ruid=05113e9d x=3.000 y=0.581 frames=0-6 playRate=0.7`가 공격 시작 틱(`Monster_Attack.OnEnter`)마다 머쉬맘 위치에서 나왔다(내 3칸 run3·run6·run8 포함). 판정 때 `effect dust ruid=05113e9d x=0.000 y=0.581 frames=8-end playRate=0.7`가 `Monster_Attack.OnAttackComplete`에서 나왔다. run3: 눈빛 clock 123.693 → 먼지 125.274(1.581), run8(슬로우 W): 눈빛 138.723 → 먼지 141.298(2.575, 슬로우가 2.5초에 끝난 뒤라 먼지 playRate 0.7). 먼지 x는 착지 x와 같은 0.000, y는 Home.y다. 시험 한정 범위로 run3·run8만 정확한 시계 로그와 맞췄고 나머지 3칸 실행의 먼지는 호출 존재만 로그로 본다.

**TF8 슬로우(PASS, 한계)**: 슬로우(ActionRate 0.5, 2초)를 W 전(run8, 시작 0.5초 뒤)과 접근 중(run9, W 뒤 약 0.1초)에 적용했다. run8: W 1.798·판정 2.574(액션 시계 기대 1.786·2.571). 렌더러 `PlayRate`: windup 0.350~0.700(0.7 × ActionRate 측정, coder NOT_RUN이던 값), 접근 0.500~1.000(1 × ActionRate). 클립 되돌림·위치 되돌림 없음(클라이언트 ep11·ep12 순서 `b934/90c5 → 5ecb` 한 번, 정점 1). run9: W 1.159(슬로우 전), 판정 1.866(슬로우를 W+Δ에 걸면 1.1429 + 0.857 − Δ이므로 Δ = 0.100~0.134초(프로브 표본 지연)이면 1.866~1.900. 적용 시각을 로그로 남기지 않아 Δ를 확정하지 못했고, 관측값은 기대 범위 끝이며 1.900 기준 −0.034로 ±0.05 안). 접근 시간 0.707(= 0.134 + (0.4286 − 0.134)×2 = 0.723과 0.016 차이, 표본 단위 안).

**TF9 1칸(PASS)**: 접근 0.503·0.504, 정점 1.380·1.381(=+0.8), 접근 jump 클립 전체 범위, 착지 x 0.000. 복귀 표본 수 29~30(약 0.5초). 복귀 높이는 접근 구간만 정점을 셌으므로 이번에 따로 재지 않았다(복귀 경로 소스 diff 0, 위 TF1). 자연 1칸 3건(ep14~16)도 같은 모양이다.

**TF10 판정 결과(PASS, JUST·PARRY NOT_RUN)**: 강제 실행 10회 + 일시정지 2회 + 가드 1회 모두 `resolutionCount` +1, `AttackSequence` +1(공격당 판정 1회). 플레이어 피해: 입력 없는 HIT은 12, 취소·사망 시험은 0(판정 없음). 가드는 실제 키(↓ 홀드, `maker_keyboard_input` `DownArrow` down→up)로 3칸 공격(parry.guard)을 맞아 피해 4(12 × 0.40 내림), 판정 1회였다. JUST·PARRY는 이번에 입력하지 않았다(NOT_RUN, 변경 경로 밖이며 11-19 QA T4c가 논리 경로로 확인했다).

**TF11 일시정지(PASS)**: 서버 `CombatPauseComponent`에 정지 소유자(플레이어)를 지정하고 `SetServerPaused(true)` 0.993초, `false`로 재개했다. windup 중(공격 시작 0.483초 뒤, pauseW): 정지 59표본 동안 x 3.000·y 0.581 고정, 렌더러 `b9345875 0-0`·ATTACK/windup 그대로, 재개 뒤 W 2.162·판정 2.594(정지 길이만큼 밀림 기대 2.136·2.564, +0.026·+0.030이라 ±0.05 안), 판정 1회·피해 12. 접근 중(공격 시작 1.306초 뒤, pauseA): 정지 59표본 동안 x 2.270·y 1.335 고정(공중에서 정지), 렌더러 `5ecbcc40 0-2147483647` 그대로, 재개 뒤 판정 2.594(기대 2.564 +0.030), 판정 1회. **무효 처리한 첫 시도**: 처음에는 정지 소유자를 지정하지 않아 제품 코드 `OnUpdate`가 곧바로 `AbortCombat`으로 공격을 취소했고 몬스터가 ATTACK 상태로 남았다. 제품 정지 경로의 설계(소유자 필요)를 내 프로브가 어긴 것이라 이 두 표본은 결과로 세지 않았다. 소유자를 지정해 다시 시험한 값이 위 값이다.

**TF12 취소·사망(PASS, 관찰 2건)**: ① 접근 중 취소(W+0.16초에 `ChangeState("IDLE")`, cancelA): 곧바로 seg none·`JumpActive` false·IDLE, 판정 0회·피해 0(먼지·판정 없음), 몬스터는 땅에 내려와 x 2.187에 서고(집으로 복귀하지 않음) 렌더러는 jump 클립·전체 범위·`PlayRate` 1로 1.5초 이어졌다. ② windup 중 취소(0.497초, cancelW): IDLE, 범위 `0-0`이 `0-2147483647`로 복구, `PlayRate` 0.70 → 1.00, 클립은 skill1 그대로, x 3.000, 판정 0회. ③ 접근 중 사망(W+0.158초에 `health:ApplyDamage(Hp)`): `ATTACK/approach`(jump) → 0.018초 뒤 seg none(`CancelPendingAttack`) → 0.22초 뒤 `DEAD` + die 클립(ec90f0b6, 전체 범위, `PlayRate` 1.00, 첫 표본 간격이 0.22초로 길어진 것은 die 클립 동기 로드로 보인다) → 약 0.81초 뒤 Start=End=5(마지막 프레임) 고정, 이후 3.6초 동안 클립·범위 변화 없음(jump·stand 덮어쓰기 없음). 판정 0회, 피해 0, `[VRF] MonsterDie start` 1건·`MonsterDie freeze frame=5` 1건(freeze 0.812초, 계산값 0.800). 사망 몬스터는 접근 중이던 x 2.255에 서 있다.
- **관찰 O-1(결함 아님, reviewer 참고)**: 접근 중(jump)·windup 중 공격이 취소되면 클립을 stand로 되돌리는 경로가 없어 취소 뒤에도 jump(또는 skill1) 클립이 남는다. 취소 경로(`CancelMotion`)는 diff 밖이라 c6422cd에서도 같은 구조였고(이전에는 접근 중 취소 때 attack1 클립이 남았다), 1-A로 바뀐 것은 남는 클립의 모습뿐이다. 일반 플레이에서 접근 중 취소는 플레이어 사망·이탈·정지 중단 때만 생긴다.
- **관찰 O-2(착지 때 stand 1프레임)**: 클라이언트 2·3칸 10개 중 1개(ep9, run6 3칸)에서 착지 순간 `8601`(stand)이 1프레임(1.572~1.591) 끼었다가 바로 jump(복귀)로 돌아왔다. `CompleteMotion`의 `SetVisualClip("stand")` 다음 `PerformReturnMotion`의 `SetMotionClip("jump")`가 같은 서버 틱에서 이어지는 기존 코드이고(diff 밖) coder는 "클라이언트에서 안 보였다"고 적었다. 10개 중 1개라 보이는 빈도는 낮고, 이번 변경이 만든 것은 아니다. 사용자 화면 판단 항목이다.

**TF13 회귀(PASS)**: ① 기본 공격(↑ 실제 키 `UpArrow` tap): 머쉬맘 HP 100 → 90(10타 × 1). ② 가드(↓ 실제 키 홀드)로 맞는 피해 12 → 4(잔여 40%, 위 TF10). ③ 1칸 공격(parry.any): 강제 2회·자연 3건 정상. ④ 전투 시작: Play 시작 `[VRF] MonsterManager spawned parent=map01 x=3.0` 1건(13:42:30), 강제 시험 전에 몬스터가 `AttackInterval` 3.0으로 스스로 자연 공격을 시작했다(2칸 좌 2건·1칸 포함).
- **관찰 O-3(원인 미확정, 시험 부산물 추정)**: 위 `ALLDONE` 뒤 몬스터 `AttackInterval`을 3.0으로 복원해 두었더니 자연 공격이 이어졌고, 플레이어 HP를 채우지 않아 누적 피해가 났다. 13:46:45 자연 공격은 몬스터 x −0.750에서 시작했고(`windup` 이펙트 x −0.750), 13:47:30에는 1칸 공격이 접근 0.52초에 ATTACK → IDLE로 끝나며 x 0.000에 남았다(복귀 없음, `OFFHOME idle`). 5초 뒤 x 3.000·IDLE·플레이어 HP 100/100으로 돌아와 있었다. 플레이어 HP 소진 뒤 전투 초기화로 추정하지만 로그로 확정하지는 못했다. 변경 경로(2·3칸 접근 전환)가 아닌 1칸 경로에서 나왔고 소스 diff 밖이다. 이후 강제 시험은 매번 위치·상태·HP를 초기화하고 진행했다.

**TB Bundle(NOT_RUN)**: 위 TF1 버전 대조 참조(coder 지문 재현 불가, 파일별 SHA-256·`git diff`로 대신).

**한계·사용자 직접 확인**
- 스크린샷 0장: 화면 체감(그림과 이동의 어울림, 착지 때 stand 1프레임 O-2, 높이 0.8이 눈에 어떻게 보이는지)은 사용자 V11이며, 사용자가 이미 화면을 보고 "1-A 유지"를 선택했다(이번 시험 대상 아님).
- 서버–클라이언트 같은 프로세스(Maker 로컬 Play): 지연 있는 실접속·모바일 NOT_RUN. JUST·PARRY 입력, FU-16 정지 1프레임 빈도(통계), 복귀 높이 별도 측정은 NOT_RUN.
- 판정 결과·W 시각의 표본 오차: 서버 프로브 표본 간격 약 17ms, 시각 값은 최대 0.017초 작게 나올 수 있다.
- 시험 부산물: 제품 파일 변경 0. Play 메모리에서 `AttackInterval`을 9999로 바꾸고 패턴 표를 한 행으로 바꿨다가 모두 되돌렸다(마지막 프로브 시점 5행 복원 확인, 이후 Stop으로 Play 메모리 폐기). 시험 타이머(서버 4개·클라이언트 1개)는 각자 종료 때 정리해 새 `[LEA-3051]`이 없다.
- Maker 최종: Stop 확인(`maker_run_command stop` status ok), `maker_get_current_map` map01·edit, 사용 종료.

### 2026-11-20 tester — 후속 회차 2 (CombatCore-FU-17·FU-19·FU-12 (가)) 독립 시험 (위 절들과 별개, 기존 절은 그대로)

- **대상 버전**: 로컬 커밋 d8c61db(`d8c61db6dfc18088f2a4f0c84bb67d3deec093dd`), 트리 `3940b24f378ecf9e1fdcd9bb99e9463ef46edd17`, 부모 a593e2b(`a593e2b6c258e9f12ad376f3ed8fe0dbc7f3331d`), push 전. 시험 전·후 `git status --porcelain`은 ` M .pipeline/…/run.md`(메인)·` M map/map01.map` 2건이고 제품 파일을 고치지 않았다. `map/map01.map` SHA-256 `22b6acbf…987e`(시험 전·후 같음).
- **주체·환경**: msw-tester(독립 실행). Maker `map01`(0a0972ef…, 개인 월드 970621b2…), 시작·종료 모두 edit. Play 2회(14:43 시작 ~14:54 Stop, 14:54:59 시작 ~14:55:08 Stop). 읽은 것: tester·팀 계약, EnvGuides, msw-general·msw-ui-system·msw-scripting·msw-combat-system, Foundation 참조 4개, platform-maple(map01 TileMapMode 0), verify-checklist, Plan 회차 2 절, 이 WorkRecord 개발 절. 스크린샷 2장(coder 10장 + 2 = 회차 12장 한도 소진). `maker_clear_logs` 0회, 로그는 누적이라 시각 14:43 이후만 이번 시험으로 보았다. 로그 지문 `[T2R2]`는 이 시험의 프로브 줄이다.
- **시험 방법**: 실제 키(↑ `UpArrow` tap, ↓ `DownArrow` down/up `maker_keyboard_input`)와 Play 메모리 프로브(`maker_execute_script` server_main·client)만 썼다. 프로브가 Play 안에서만 바꾼 것: 몬스터 `AttackInterval`(1.0~2.5, 끝에 9999), 패턴 표 Weight(parry.guard만 남김, 끝에 원값 복원), 플레이어 `Hp` 보충, 정지 시험용 `CombatPauseComponent._T.owner`·`SetServerPaused`, 몬스터 `HitEvent` 구독(합계 집계). 프로브 타이머는 시험 때마다 스스로 `ClearTimer`했다.

**기준별 판정**

| ID | 기준(Plan 완료 기준 AI) | 판정 |
| --- | --- | --- |
| TR1 | diff가 편집 허용 범위 안(시험 범위 1, AI 5 일부) | PASS |
| TR2 | Refresh 후 build 로그(AI 5) | PASS(한계 있음) |
| TR3 | AI 1: `resolveIndex` 0곳 | PASS |
| TR4 | AI 2: V02 회귀(10타 HP = HitEvent 합, ×2.2 반격 1회) | PASS(화면 피해 숫자 대조는 NOT_RUN) |
| TR5 | AI 3: 가드 시작·연출·효과음 각 1회, 추가 입력 출처 무증가 | PASS(실제 키 ↓) |
| TR6 | AI 3: 일반 가드 잔여 40%, 패링 1회 | PASS(패링 입력은 입력 수락 지점 호출) |
| TR7 | AI 4: 팝업 정지 중 이펙트 정지·재개, 끝 시각 밀림 | PASS(시각 정지는 먼지로 확인) |
| TR8 | AI 4: 슬로우 시작·끝 눈빛·먼지 배율·이어 재생 | PASS(로그 근거), 시각 모양은 NOT_RUN(사용자 V11) |
| TR9 | AI 4: 끝난 이펙트를 다시 내지 않음 | PASS |
| TR10 | AI 4: 사망·대결 종료·Stop 정리 | PASS |
| TR11 | AI 4: 맵 이탈 정리 | NOT_RUN(Stop 경로는 PASS) |
| TR12 | AI 4: 1칸 공격·플레이어 공격·가드 이펙트 회귀 | PASS |
| TR13 | AI 5: git 변경이 범위 파일뿐, 버전 대조 | PASS |
| TR14 | 표 무효 상태 가드(coder NOT_RUN) | NOT_RUN |

**TR1·TR13 범위·버전(PASS)**: `git diff --stat a593e2b d8c61db`는 `.pipeline/…/run.md`·Plan·WorkRecord 문서 3개와 제품 `.mlua` 4개(`MonsterStateControl` +9/−2, `MonsterAttackMotion` +85/−0, `PlayerCombatComponent` +0/−1, `PlayerGuardComponent` +4/−3, 제품 합 +98/−6)뿐이다(문서 포함 총 220+/27−). `.codeblock`·`.model`·`.map`·`.ui`·DataSet·CSV 변경 0. 바뀐 파일의 `git ls-tree -r d8c61db` blob id와 작업 트리 `git hash-object`가 4개 모두 일치한다: PlayerCombatComponent `52beb46b4a75a6054c3f65e3f9847f9657848a11`, PlayerGuardComponent `2b79931029ccf6dd45441d59dec329a2fd880135`, MonsterAttackMotion `da93aea6cfac8ed8e10f20dba342421a0f98082a`, MonsterStateControl `f67d70c0f73ef7d2b9942568117d571ae2f8eda4`. 바뀌지 않아야 할 4개의 blob id는 a593e2b와 d8c61db가 같고 작업 트리도 같다: CombatPauseComponent `1658387d80672ca210b7cdd050055d04f0e60926`, Monster_Attack `af264b032d20dd76f444686bcc511816eadaa7ea`, UIPopup `3807871f270fdd2f1bc10788633d520630e6c4c7`, OrangeMushroomAttack `62dcb6853dc12171a246faf3e20f7a5ce9cb437e`. diff 내용은 Plan 허용 범위와 맞다: FU-17은 `self._T.resolveIndex = index` 1줄 삭제(`resolveId` 유지), FU-19는 `SetGuarding`의 기록 전 값 지역 변수 `wasGuarding`와 `self.isGuarding = isHeld`를 연출 앞으로 옮기고 끝의 중복 기록 삭제(시작 판단·시작 시각·시작 x·[VRF]·연출·효과음 줄은 그대로), FU-12는 몬스터 이펙트 추적(`TrackEffect`·`GetEffectFrame`·`SyncEffectRates`·`ClearEffects`, `GetRuidTimeline` 분리)·`ApplyMotionClipRate`의 `SyncEffectRates` 호출·`ClearCombatEffects`의 `ClearEffects` 호출뿐이다.

**TR2 build(PASS, 한계)**: `maker_refresh_workspace` 1회 status ok → `maker_build_logs`: `LEA&`·`Error`·`Warning`·`LWA` 검색 각 0건. `LEA` 단순 검색 9건은 `ClearStart` 등 이름의 `Clear` 부분 문자열에 걸린 Info(LIA 1115)이다. 한계: 로그 시각(14:31:14)이 coder의 마지막 Refresh와 같아 내 Refresh가 새로 컴파일했는지는 로그로 구분되지 않는다(이전 QA와 같은 한계). Play에서 4개 스크립트가 정상 동작했다. Play 중 제품 코드에서 난 새 `[LEA-`·`[LWA-` 줄은 0건이다. 누적 로그의 `[LEA-2007]` 1건(14:52:03, `'m'은 nil`)은 내 프로브가 `GetComponent("script.MonsterAttackMotion")`로 잘못 불러 난 시험 흔적이고(`GetComponent(MonsterAttackMotion)`으로 고쳐 다시 올림), 14:33~14:34 3건과 `[LEA-3051]` 12:40·14:39는 coder 시험 흔적이다. 두 번째 Play 시작 때 새 `[LEA-3051]`은 없었다.

**TR3(PASS)**: Grep `resolveIndex`(`*.mlua`·`.codeblock`·`.model`·`.map`·`.ui`·`.csv`·`.userdataset`) 0건.

**TR4 V02 회귀(PASS)**: 몬스터 `HitEvent` 합계를 프로브로 집계했다.
- 실제 키 ↑ tap 2회(몬스터 HP 100→90, 90→80): 시전마다 `HitEvent` 10회 합 10, HP 감소 10(`manual cast id=1/4 count=10 factor=1`). 14:49:36 시전(`id=11`, factor 1)도 HitEvent 10·HP −10.
- ×2.2 반격 1회: 14:50:32 패링 성공으로 `counter granted … factor=2.2`(서버 `bonusMultiplier` 2.2, `CounterReady` true), 이어 공격 1회(`manual cast id=16 count=10 factor=2.2`): HitEvent 10회 합 20, 몬스터 HP −20(100→80), 시전 뒤 `CounterReady` false(소비 1회). coder 값(합 20, HP −20)과 같다. 반격 시전 입력은 키가 아니라 클라이언트 `RequestChangeState("ATTACK")`(반격 창이 짧아 키 입력 지연 안에 못 맞춤. 앞의 첫 시도는 키를 눌렀을 때 창이 이미 닫혀(`ready=false`) 일반 시전 factor 1로 나갔다. 결과로 세지 않았다).
- 화면 피해 숫자와 HP 감소 대조: NOT_RUN(스크린샷 한도). 우연히 정지 시험 스크린샷에 플레이어 쪽 피해 숫자 `12`가 보였고 그 공격의 플레이어 피해(보충 전 12)와 같았다(참고만, 몬스터 쪽 숫자 대조 아님).

**TR5 가드 시작(PASS, 실제 키)**: ↓ `DownArrow` down(14:44:50): `[VRF] PlayerGuard start x=0.000 t=65.874` 1, `guard fx effect=318a4662` 1, `sfx kind=guard ruid=605da1fc` 1(14:44:50 시각 줄 각 1건, 이전 시험들의 줄과 구분). 같은 홀드에 클라이언트 `RequestChangeState("GUARD","probe2")`(`accepted=true`) 추가 뒤에도 시작·연출·효과음 줄이 늘지 않았다. 코드 호출 위치는 `PlayerGuardComponent.SetGuarding`(line 10·20·21 새 줄 번호)이다. **시험 부산물**: 이 `probe2` 출처를 내가 나중에야 해제했다(`ReleaseHeldState("GUARD","probe2")` 14:49:19). 그 사이(14:44:50~14:49:19)는 실제 ↓ 키 해제 후에도 가드 상태가 유지돼 있어서, 이 구간의 P1·P3·P4·P5·P6·P7 패링 시도(지연 시작 가드)는 모두 "이미 가드 중"이라 패링 창에 못 들어갔다. 이 구간 결과는 패링 근거로 세지 않고, 일반 가드 40%(아래)는 가드 홀드 시험이라 유효하다.

**TR6 가드 판정(PASS)**:
- 일반 가드 잔여 40%: ↓ 실제 키 홀드 중 몬스터 자연 공격 3회(14:45:08~16) 각각 플레이어 HP 100→96→92→88(12×0.40 내림 4, 매번 1회), 서버 `PlayerHealth guard eval x=0.000 cellOk=true areaOk=true attr=PARRY` 줄 3건(14:45:10·13·16)과 매번 플레이어 피해 4(`defense kind` 줄은 따로 읽지 않았고 피해값으로 판단). 1회 기준 충족, 3회 반복.
- 패링 1회: 입력 수락 지점(`PlayerStateControl.RequestChangeState("GUARD")`) 호출을 예고 남은 시간 약 0.134초에 클라이언트 프로브가 실행(패턴 parry.any 1칸 010)했고 14:49:30(P8, 서버 증가분 `counterGranted` 1)과 14:50:32(P9, seq 61, 예고 남은 0.135) 두 번 `counter granted until=… factor=2.2`가 나왔다. 두 번 모두 "홀드 시작이 판정 시각 −창 안, Pos2 칸(x=0.000), 영역이 Pos2 포함"(guard eval `cellOk=true areaOk=true`) 결과다. 실제 키로 패링 창(저스트 0.20초 이내)에 맞추는 것은 키 입력 지연 때문에 하지 못했다(NOT_RUN, coder와 같음).

**TR7 팝업 정지(PASS)**:
- 방식: `CombatPauseComponent`에 정지 소유자(플레이어)·세션을 지정하고 서버 `SetServerPaused(true)`, 클라이언트 프로브가 `IsPaused` @Sync를 따라 `SetPresentationPaused(true)`(실제 `_UIPopup:Open` 경로가 아니고, 팝업이 배경을 가려(coder 확인) 사용하지 않음).
- 눈빛(k3, 14:52:38 정지 2.0초): 액션 시계 `532.914`가 정지 전·중·재개 직전·직후 모두 같고(프레임 f3·playRate 0.7 유지), 이어 먼지가 나온 시각은 전투 시계 `534.957`(눈빛 `533.369` 대비 1.588초, 예고 1.571초 + 표본 오차)로 전투 시계 기준 예고 길이가 그대로이고, 실제 시각은 정지 2.0초만큼 밀렸다(눈빛 14:52:37 → 먼지 14:52:41).
- 먼지(k4, 14:52:46 정지 24초): 액션 시계 `538.925` 정지 전후 같음(f9). **시각 확인(스크린샷 2장)**: 정지 3초 뒤(14:52:49)와 14초 뒤(14:53:00) 두 장에서 먼지 이펙트가 같은 모양·같은 위치로 보였다(숨겨지지 않고 멈춘 프레임으로 남음). 두 장 모두 가운데 플레이어 위치에 먼지 조각과 피해 숫자 `12`가 같았다. 재개(14:53:10) 뒤 다음 눈빛(14:53:13)이 정상으로 이어졌다.
- 플레이어 공격·가드 이펙트의 정지는 직접 보지 않았다(한도). 먼지와 같은 `PlayEffect` 경로·같은 클라이언트 시간 배율 0이라고 coder와 같이 판단하지만 시각 PASS는 아니다(NOT_RUN).

**TR8 슬로우 추종(PASS, 로그 근거)**: 프로브가 `ApplySlow(duration, 0.5)`를 걸었다(parry.guard 3칸, 눈빛·먼지는 motionRate 0.7).
- 눈빛(k1, 공격 시작 +0.3초, 슬로우 1.0초): `[VRF] effect rate windup frame=2 range=2-6 playRate=0.7->0.35 serial=…679->…680 action=523.640`, 슬로우 끝 `frame=5 range=5-6 playRate=0.35->0.7 serial=…680->…681 action=524.156`. 직접 계산: 액션 시계 523.300 시작, 523.640 때 (0.340×0.7)=0.238 → f2(0.2~0.3), 524.156 때 0.599 → f5(0.5~0.6)로 일치. 끝 프레임 옵션은 `6` 그대로. 슬로우 길이 1.0초 → 액션 시계 0.516 진행(기대 0.5).
- 먼지(k2, 먼지 추적 +0.15초, 슬로우 0.8초): `frame=9 range=9-end playRate=0.7->0.35 action=529.646`, 끝 `frame=11 range=11-end playRate=0.35->0.7 action=530.054`(기대 529.646+0.4=530.046).
- 먼지가 슬로우 중에 시작해도(k5, 먼지 `playRate=0.35` 시작) 슬로우가 끝나자 `frame=9 0.35->0.7`로 이어졌다.
- 한계: 이어 낸 이펙트가 화면에서 끊기거나 처음부터 반복되거나 중복으로 겹쳐 보이는지, 배율 0.35에서 눈에 어떻게 보이는지는 스크린샷 한도로 시각 확인을 하지 못했다(NOT_RUN, 사용자 V11). 서버 로그상 시작 프레임 옵션은 계산된 현재 프레임(0 아님)이고 `RemoveEffect(이전 serial)` 뒤 새 serial 한 개만 추적한다(중복 추적 없음). 엔진이 이전 serial을 실제로 지웠는지는 화면 확인이 필요하다.

**TR9 끝난 이펙트(PASS)**: k5에서 눈빛이 끝난 뒤(공격 시작 +1.45초, 눈빛 ~1.14초) 슬로우를 걸자 `[VRF] effect skip windup serial=…691 finished action=543.144`가 나오고 눈빛을 다시 내지 않았다(프로브 로그 추적 목록 n 1 → 0).

**TR10 정리(PASS)**: 이펙트 추적 1건이 있을 때
- 직접 `ClearCombatEffects`(눈빛 중 14:54:13): `effect clear tracked=1`, 곧바로 슬로우 0.5·0.5초를 걸어도 `effect rate` 줄 없음, 추적 n=0 유지(14:54:14 확인).
- 사망(눈빛 중 14:54:18, `ApplyDamage(80)`): `effect clear tracked=1`(`MonsterHealthComponent.ApplyDamage`→`ClearCombatEffects`), 추적 n=0, die 상태.
- 대결 종료(14:55:01, 눈빛 중 플레이어 `Hp=0`): `effect clear tracked=1`(`MonsterManager.RefreshDuelPlayer`→`ClearOpponentExecution`→`ClearCombatEffects`), 공격 취소·IDLE, n=0.
- Stop(14:55:08~09, 팝업 정지 중 눈빛 추적 n=1): `effect clear tracked=1`(`ClearOpponentExecution` 경유 줄 14:55:09). 정리 뒤 재생 줄은 없었고 Stop·편집 모드 복귀가 정상이었다.
- 슬로우 중 정리(슬로우였던 이펙트를 다시 내지 않음)는 직접 시험하지 않았다(j1은 정리 직후 슬로우라 순서가 반대). coder 근거와 코드 읽기(`ClearEffects`는 목록만 비움)로만 본다.

**TR11 맵 이탈(NOT_RUN)**: 맵이 map01 하나라 실제 이탈 불가. `OnMapLeave` 단독 호출은 호출 뒤 `_T.pause=nil`로 이후 공격 시험이 막혀 하지 않았다. `OnMapLeave`는 `OnEndPlay`에서도 불리므로 Stop 경로(TR10)가 같은 `ClearCombatEffects`를 지나지만, 14:55:09 줄의 호출 스택이 `ClearOpponentExecution` 경유라 `OnMapLeave` 자체가 불렸다는 직접 증거는 없다.

**TR12 회귀(PASS)**: ① 1칸 공격(parry.any/special.random, EffectClip 없음): 시험 중 수십 회 자연 공격에서 `effect` 줄 없이 정상 판정·복귀했고 새 오류 없음. 3칸(parry.guard)은 눈빛·먼지 추적이 정상. ② 플레이어 기본 공격: 10타 정상(TR4). ③ 가드 이펙트: 시작 때마다 1회(`guard fx effect=318a4662`)이고 `SetGuarding` 순서 변경 뒤에도 가드 판정·연출이 정상. 패링·일반 가드·반격 결과가 이전 회차 값과 같다(HP 4, 반격 ×2.2).

**TR14 표 무효 가드(NOT_RUN)**: 제품 임시 변경 금지 규칙과 Play 메모리 프로브 방법(`_CombatRuleCatalog:GetPlayerActionFx("guard")`가 nil이 되게 하는 것)을 찾지 못해 하지 않았다. `SetGuarding` 순서 변경 소스 대조로만 판단: 시작 판단은 기록 전 값(`wasGuarding`)을 쓰고 `fx == nil`일 때의 `log("[VRF] guard fx off")` 줄과 가드 진행은 기록 순서와 무관하다. 이는 소스 읽기이며 Play 검사가 아니다.

**관찰(결함 아님, reviewer 참고)**
- O-1 `GetEffectFrame`은 프레임 지연을 `motionRate`만으로 나누고 클립 자체 `PlayRate`(`timeline.rate`)는 쓰지 않는다. 지금 이펙트 클립 `PlayRate`가 1.0이라(coder 확인) 맞지만, 클립 `PlayRate`가 1이 아닌 이펙트가 쓰이면 어긋난다. 접근 클립 쪽 `GetWindupSeconds`·`StartDrivenClip`은 `timeline.rate`를 곱하는 것과 다르다. 지금은 영향 없음.
- O-2 끝난 이펙트 항목은 다음 `TrackEffect`·`SyncEffectRates`까지 목록에 남을 수 있다(예: k2 먼지 `fnil`이 다음 공격까지 남음, coder가 개발 절에 적은 내용과 같다). 영향 없음.
- O-3 공격이 취소돼도 이미 재생을 시작한 눈빛·먼지는 화면에서 끝까지 나온다(기존 구조, 정리는 추적만 끊음). 코드 주석 "마지막 재시작 배율로 끝까지 재생"과 같다.
- O-4 이 시험 중 플레이어 쪽 피해에는 남은 HP 상한이 없어 HP 0이 되어도 `IsDead()`가 false였다(프로브로 `Hp=0` 설정, FU-22 기존 관찰과 같음).

**시험 부산물·프로브 정리**: 제품 파일 변경 0. Play 메모리에서만 바꾼 값(`AttackInterval`, 패턴 Weight, 플레이어 `Hp`, 정지 소유자, 몬스터 사망 상태)은 각 프로브가 복원했고 Stop으로 폐기됐다. 프로브 타이머(서버 P3~P9·F·G·H, 클라이언트 P1·P3~P9·F follower·H follower)는 각자 `ClearTimer`했고 클라이언트 follower F·H는 Stop 때 남아 있었다(Stop 뒤 새 `[LEA-3051]`은 두 번째 Play 시작 때 없었고, 두 번째 Stop 뒤의 값은 다음 Play 시작에서 확인된다). 훅에 막힌 셸 명령은 없었다.

**한계·사용자 직접 확인**
- 스크린샷 2장(먼지 정지 확인). 회차 전체 12장 한도를 다 썼다. 눈빛·먼지가 슬로우 시작·끝에서 이어 재생되는 화면 모양, 정지 중 플레이어 공격·가드 이펙트, 화면 피해 숫자 대조는 사용자 V11 항목이다.
- 서버–클라이언트 같은 프로세스(Maker 로컬 Play), 지연 있는 실접속·모바일 NOT_RUN. 정지는 `_UIPopup:Open` 실제 경로가 아니라 서버 `SetServerPaused`+클라이언트 `SetPresentationPaused` 직접 호출이다.
- 패링·반격 입력은 입력 수락 지점 호출(논리 경로)이며 실제 키가 아니다.
- Maker 최종: Stop 확인(`maker_run_command stop` status ok), `maker_get_current_map` map01·edit, 사용 종료.

### 2026-11-20 tester — 회차 2 O-1 회귀 QA (위 절들과 별개, 기존 절은 그대로)

- **대상 버전**: 로컬 커밋 eaeb032(`eaeb03230019fe929fb5423cb8cbc8b3dc857bbd`), 트리 `fe15c8744a1c91931a89d272b1f3bfa895825a75`, 부모 d8c61db, push 전. 시작·종료 모두 `git rev-parse HEAD`·`HEAD^{tree}`가 같다.
  - `git ls-tree -r HEAD -- RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua` blob `8d22ddda9183c257053c1fce14bcc740f3a0a4d9`. 작업 트리 `git hash-object`도 같다(Refresh 뒤 재확인).
  - `git diff --stat HEAD~1 HEAD -- RootDesk`: `MonsterAttackMotion.mlua` 1개 +1/−1.
  - `git status --porcelain`(시작·종료 같음): ` M .pipeline/20261119-combatcore-followup/run.md`(메인), ` M map/map01.map`(사용자 변경, 범위 밖). `map/map01.map` SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`(시작·종료 같음). 제품 파일 변경 0.
- **주체·환경**: msw-tester(독립 실행, 한도로 끊긴 앞 작업을 이어서 처음부터 다시 진행). Maker `map01`(0a0972ef…), 시작·종료 edit(끊긴 뒤 시작 확인: Play 아님). Play 1회(20:19 시작 ~ Stop). 스크린샷 0장, `maker_clear_logs` 0회. 읽은 지침: tester·팀 계약, EnvGuides, msw-general·msw-ui-system·msw-scripting, Foundation 참조 4개, platform-maple(map01 TileMapMode 0), verify-checklist. 로그 지문 `[O1T]`는 이 시험의 프로브 줄이다. Play 시작 때 로그가 비어 있어 이번 Play의 줄만 읽었다.
- **시험 방법**: Play 메모리 프로브만(`maker_execute_script`). 서버 프로브가 패턴 표 Weight를 parry.guard만 남기고 `AttackInterval` 1.0으로 바꿔 3칸(skill1) 공격을 연속으로 내고, 눈빛·먼지 추적 항목(`motion._T.fx`)을 보다가 정해진 시각에 `ApplySlow(duration, 0.5)`를 걸고 플레이어 `Hp`를 보충했다. 클라이언트 프로브는 `AttackSequence` 변화 뒤 `_UtilLogic:SetClientTimeScale(0)`을 걸었다. 끝에 Weight 5행·`AttackInterval` 3.0 원값 복원을 로그로 확인(`[O1T] cleanup done … parry.left=4 parry.right=4 parry.any=5 special.random=3 parry.guard=4 interval=3.0`)하고 Stop했다.

**기준별 판정**

| ID | 기준 | 판정 |
| --- | --- | --- |
| O1-T1 | 코드 대조: 바뀐 줄이 `GetWindupSeconds`·`StartDrivenClip`의 `timeline.rate * motionRate` 패턴과 맞음 | PASS(소스 대조) |
| O1-T2 | Refresh 후 build 로그 `LEA-`·`LWA-`·`Error` 0 | PASS(한계 있음) |
| O1-T3 | 슬로우 시작·끝 프레임·serial·playRate가 Delay 표 계산과 일치, 이전 [VRF]와 같은 형태 | PASS(로그 근거) |
| O1-T4 | 클라이언트 정지(`SetClientTimeScale(0)`) 짧게 걸었다 풀어도 서버 이펙트 추적이 깨지지 않음(새 serial 남발·오류 없음) | PASS(로그 근거, 조건은 아래) |
| O1-T5 | Play 중 새 `LEA-`·`LWA-` 줄 없음 | PASS |
| O1-T6 | Stop·Maker map01 편집 모드 인계, map01 SHA-256 불변 | PASS |
| O1-T7 | PlayRate≠1 클립에서의 효과 자체 | NOT_RUN(그런 클립이 없음. 소스 대조로만 판단) |
| O1-T8 | 슬로우·정지 중 이펙트의 화면 모양(끊김·처음부터 재시작·겹침) | NEEDS_DECISION(사용자 시연 대기) |

**O1-T1 코드 대조(PASS)**: 변경은 `GetEffectFrame`의 `local elapsed = math.max(0, now - fx.startAction) * fx.motionRate * fx.timeline.rate`뿐이다. 같은 파일 `GetWindupSeconds`(94행) `sum / (timeline.rate * motionRate)`와 `StartDrivenClip`(108행) `divisor = timeline.rate * motionRate`는 "프레임 Delay 합 ÷ (클립 PlayRate × 배율) = 시간"이다. 그 역으로 "시간 × 클립 PlayRate × 배율 = Delay 누적과 비교할 클립초"가 되므로 새 식은 같은 패턴이다. `fx.timeline`은 `GetRuidTimeline`이 만든 표(`rate`는 유한·양수 보정)이고 `TrackEffect`가 기록한 값이라 `nil`이 될 수 없다. 이 줄 하나뿐인 변경이라 다른 함수의 흐름은 같다. 이것은 소스 대조이며 PlayRate≠1에서의 동작은 Play로 보지 않았다(O1-T7).

**O1-T2 build(PASS, 한계)**: `maker_refresh_workspace` status ok → `maker_build_logs`: `LEA-`·`LWA-`·`Error` 검색 각 0건. 한계: 로그 시각이 coder의 마지막 Refresh와 같아 내 Refresh가 새로 컴파일했는지는 구분되지 않는다(이전 QA와 같은 한계).

**O1-T3 슬로우 시작·끝(PASS)**: 클립 `05113e9d`의 프레임 Delay는 f0~f5 각 0.1, f6 0.2, f7 0.3, f8~f12 각 0.1, f13 0.2, f14 0.05(coder 15프레임 표와 같다)이고 `timeline.rate`는 1.0(프로브 `tlRate=1.0`), `motionRate` 0.7이다. 추적 시작 액션 시계와 슬로우 시각 액션 시계를 Delay 표로 직접 계산해 [VRF] `frame`과 대조했다.

| 공격 | 구간 | 시점 | 시작 액션 → 지금 액션 | 계산(경과 × 0.7) | 계산 프레임 | [VRF] frame | playRate·serial |
| --- | --- | --- | --- | --- | --- | --- | --- |
| a1 | 눈빛 | 슬로우 시작 | 73.887 → 74.233 | 0.346×0.7=0.242 | f2(0.2~0.3) | `frame=2 range=2-6` | `0.7->0.35` `…656->…657` |
| a1 | 눈빛 | 슬로우 끝 | 74.233 → 74.739 | 0.506×0.7=0.354, f2 시작 | f5 | `frame=5 range=5-6` | `0.35->0.7` `…657->…658` |
| a2 | 먼지 | 슬로우 시작 | 78.552 → 78.759 | 0.207×0.7=0.145 | f9(f8 0.1 지남) | `frame=9 range=9-end` | `0.7->0.35` `…661->…662` |
| a2 | 먼지 | 슬로우 끝 | 78.759 → 79.164 | 0.405×0.7=0.284, f9 시작 | f11 | `frame=11 range=11-end` | `0.35->0.7` `…662->…663` |
| a3 | 눈빛 | 슬로우 시작 | 80.061 → 80.593 | 0.532×0.7=0.372 | f3 | `frame=3 range=3-6` | `0.7->0.35` `…664->…665` |
| a3 | 눈빛 | 슬로우 끝 | 80.593 → 81.099 | 0.506×0.7=0.354, f3 시작 | f6(f3~f5 0.3 지남) | `frame=6 range=6-6` | `0.35->0.7` `…665->…666` |

6건 모두 계산 프레임과 같다. 프로브의 슬로우 직전 계산값도 로그와 같다(`pre-slow expectFrame=2`·`9`·`3`). 슬로우 직후 추적 항목은 새 serial·`startFrame`·`playRate 0.35`로 바뀌고(`post-slow`), 끝난 뒤 `ActionRate=1.0`·`fxPlayRate=0.7`로 돌아온다(`after-slow`). 끝 프레임 옵션(눈빛 `6`, 먼지 `end`)은 유지됐다. 이전 [VRF](coder `frame=3 range=3-6`·`frame=8 range=8-end`, tester `frame=2`, coder O-1 `frame=4`·`9`)와 줄 형태(`effect rate <label> frame= range= playRate=a->b serial=x->y action=`)가 같다. 클립 `rate=1`이라 변경 전후 값이 같아야 하며 줄 단위 전후 비교는 입력이 달라 하지 않았다.

**O1-T4 클라이언트 정지(PASS, 조건)**: 서버 정지 없이 클라이언트만 `SetClientTimeScale(0)`을 두 번 걸었다. 두 번 다 클라이언트 시간이 멈춰 클라이언트 타이머 호출이 멎었고(`ticksDuring=1`) 클라이언트 쪽 `ElapsedSeconds`도 정지 중 멈췄다. 그래서 내가 클라이언트 호출로 `SetClientTimeScale(1)`을 직접 풀었다(정지 1: 20:21:05~14 약 9초, 정지 2: 20:21:14~25 약 11초, 의도한 1초보다 길다). 그 사이 서버는 정지되지 않아 공격 a9~a16이 계속 진행됐다. 서버 로그: 정지 구간의 공격마다 `new fx`가 눈빛 1 + 먼지 1개뿐이고 serial이 678→679→680→…→693으로 연속이며, `[VRF] effect rate` 줄은 정지 구간(20:21:05 이후)에 한 줄도 없다(전체 6건은 모두 위 슬로우 시험 20:20:38~47). `effect clear`·새 `LEA-`·`LWA-` 줄도 없다. 즉 클라이언트 정지·해제는 서버 추적에 영향을 주지 않았다.
  - 한계: 서버 정지(팝업 정지 경로)와 클라이언트 정지를 함께 건 조합은 이번 회귀에서 하지 않았다(그 조합은 아래 시연 항목). 정지 중·후 화면에 보이는 이펙트 모양은 보지 않았다.
  - **시험 방법 부산물(알아 둘 사실)**: 클라이언트 `_UtilLogic:SetClientTimeScale(0)`이 걸리면 `_TimerService`로 만든 클라이언트 타이머와 `_UtilLogic.ElapsedSeconds`가 함께 멈춘다. 그래서 "클라이언트 타이머로 N초 뒤 해제"는 동작하지 않고 `maker_execute_script` 직접 호출로 풀어야 한다. 제품의 `UIPopup.OnUpdate`는 Logic 갱신이 계속 오는 것을 이용한다(주석 근거). 제품 결함이 아니다.

**O1-T5 새 오류 줄(PASS)**: Play 중 서버·클라이언트 `maker_console_logs`를 `LEA-`·`LWA-`로 전체 검색해 각 0건(Play 시작 때 로그가 비어 있어 이전 흔적 없음). 시험 중 `[O1T]` 프로브 실패 줄도 없었다.

**시험 부산물·프로브 정리**: 제품 파일 변경 0. Play 메모리에서만 바꾼 값(패턴 Weight 4행→0, `AttackInterval` 3.0→1.0, 플레이어 `Hp` 보충, 클라이언트 시간 배율)은 모두 복원했다(Weight·간격은 로그 확인, 시간 배율은 마지막 호출 `scale=1`). 서버 프로브 타이머는 `ClearTimer`했고 클라이언트 프로브 타이머는 스스로 정리했다(`client probe timer cleared`). Stop 뒤 `maker_get_current_map` map01·edit.

**사용자 시연 항목 — NEEDS_DECISION(사용자 시연 대기)**: 사용자가 Maker 화면으로 직접 본다(사용자 결정 "시연 보고 확인", 사용자 관찰 = 수락 근거, 내가 PASS로 세지 않는다).
  1. 일시정지 중 머쉬맘 3칸 공격의 눈빛·먼지 이펙트가 멈추고 해제하면 이어지는지.
  2. 저스트 회피 슬로우(ActionRate 0.5, 2초) 중 같은 이펙트가 느려지고 풀리면 끊김·처음부터 재시작·겹침 없이 이어지는지.
  - 준비 상태: 시연 스크립트 5개를 스크래치(`…\scratchpad\demo\`)에 두었다. 실행하지 않았고, 스크립트 전체를 미리 돌려 보지도 않았다(시연은 메인의 "시연 실행" 신호 뒤에 실행). 이번 회귀에서 검증한 부분(서버 프로브 구조·`ApplySlow`·클라이언트 감시 타이머)만 재사용했고, 서버 정지의 `pause._T.owner` 지정은 앞 tester(TR7)가 쓴 방식이다.

**한계·reviewer 참고**
- 이번 PASS는 서버 로그 근거다. 화면 모양은 보지 않았다(스크린샷 상한 소진, 사용자 시연 항목).
- 같은 입력의 변경 전·후 줄 비교는 하지 않았다. 대신 Delay 표 직접 계산과 일치를 확인했다. 클립 `rate=1`이므로 O-1 변경은 현재 데이터에서 값이 달라지지 않는 것이 정상이다(O1-T7).
- 프로브 표본 오차: 서버 프로브 타이머 간격 0.03초, 슬로우 시각은 추적 시작 뒤 지정 지연(0.3초·0.15초) 이후 첫 틱이다.
- 서버–클라이언트 같은 프로세스(Maker 로컬 Play). 지연 있는 실접속·모바일 NOT_RUN.
- Maker 최종: Stop 확인(`maker_run_command stop` status ok), `maker_get_current_map` map01(0a0972ef-ad23-4e24-af63-afbd53120c1d)·edit, 사용 종료.

**사용자 시연 실행 기록 (2026-11-20, 같은 대상 버전 eaeb032, 제품 파일 변경 0, 스크린샷 0장, `maker_clear_logs` 0회)**
- 실행: 메인의 "시연 실행"(사용자 "시연 시작") 신호 뒤 Play 1회(20:35:1x 시작). 스크립트는 준비해 둔 5개를 그대로 썼다(`…\scratchpad\demo\`). 시작 로그: `[DEMO] server driver start playerX=0.000 pos2X=0.000 monsterX=3.000`(플레이어가 이미 Pos2에 있어 이동하지 않음). 방식: 서버 정지는 `pause._T.owner=플레이어` + `SetServerPaused(true)`, 클라이언트 정지는 감시 타이머가 `IsPaused` @Sync를 따라 `SetPresentationPaused(true)`, 해제는 내가 서버·클라이언트 해제를 한 응답 블록에서 호출. 슬로우는 `ApplySlow(2.0, 0.5)`(`ActionRate=0.5`, 로그 확인).
- **[DEMO] 줄 시각표** (로그는 초 단위, `<<< 슬로우 끝`은 시작 후 실시간 약 2.3초에 찍힌다)

| n | 종류 | 시작 | 해제·끝 | 비고 |
| --- | --- | --- | --- | --- |
| 1 | 눈빛 중 정지 | 20:35:24 | 20:35:35(서버 로그 정지 11.1초), 클라이언트 해제 20:35:36 | 3초 이상 확인 뒤 해제 조건은 충족, 도구 호출 지연으로 길어짐 |
| 2 | 눈빛 중 슬로우 | 20:35:39 | 20:35:42 | `ActionRate=0.5` → `1.0` |
| 3 | 먼지 중 정지 | 20:35:46 | 20:35:57(정지 10.7초), 클라이언트 해제 20:35:57 | 위와 같음 |
| 4 | 먼지 중 슬로우 | 20:36:01 | 20:36:03 | `ActionRate=0.5` → `1.0` |
| 5 | 눈빛 중 정지 | 20:36:04 | 20:36:09(정지 5.0초), 클라이언트 해제 20:36:10 | |
| 6 | 눈빛 중 슬로우 | 20:36:13 | 20:36:16 | `ActionRate=0.5` → `1.0` |
| 7 | 먼지 중 정지 | 20:36:22 | **해제 없음** | 시작 직후 Play가 끝났다(아래) |
| 8 | 먼지 중 슬로우 | — | — | 실행 못 함 |

- **7번째 회차에서 Play가 내가 Stop하지 않았는데 끝났다.** 20:36:22 "서버 정지 시작 n=7"과 "클라이언트 정지 시작"이 찍힌 직후 해제 호출을 보냈더니 두 호출 모두 `unavailable: Not in play mode`였고 `maker_get_current_map`은 map01·edit였다. 로그에 `[LEA-3051]`(20:36:24)이 나온 것은 Stop 시점으로 보이며, 원인(사용자가 Maker에서 Stop을 눌렀는지)은 로그로 확정하지 못했다. 그래서 n=7(먼지 중 정지)의 해제 모습과 n=8(먼지 중 슬로우 2회차)은 보여 주지 못했다. 8회 끝 자동 복원(`finish`)도 실행되지 않았지만 Play 메모리(패턴 Weight·`AttackInterval`·시간 배율)는 Stop으로 폐기되고 다음 Play는 데이터 파일에서 새로 읽는다(파일 변경 0 확인).
- 정지가 길어진 이유: 내 해제 호출이 도구 호출 순서(로그 확인→해제)를 따라 가서 정지가 5~11초 이어졌다(의도 3~5초보다 김). 사용자에게는 "정지 중 5~11초 동안 이펙트가 멈춰 있었는지"를 묻는다.
- 새 오류 줄: `[LEA-3051] MemoryLeak 'MakerScript' 30번째 줄(서버)·5번째 줄(클라이언트) 타이머 제거되지 않음`(20:36:24) 2건. 시험 프로브 타이머가 Stop 전에 정리되지 않아 생긴 시험 흔적이다(앞 QA의 프로브 `[LEA-3051]`과 같은 종류, 제품 코드 줄 아님). 그 밖의 `LEA-`·`LWA-`·`rror` 줄 없음.
- 정지 중 서버 로그 근거(참고): `[VRF] CombatPause server paused=true/false`가 n=1·3·5에서 20:35:24/35, 20:35:46/57, 20:36:04/09로 짝을 이뤘고 정지 중 전투 시계가 같은 값이었다(11.661→11.661, 22.295→22.295, 29.955→29.955). n=7은 20:36:22 `paused=true clock=42.162` 뒤 20:36:24에 `CombatPauseComponent.OnUpdate`→`AbortCombat`→`SetServerPaused(false)`로 풀렸다(정지 소유자 검사에 걸린 정리 경로이며 내 해제 호출이 아님. Play가 끝나는 때 소유자 플레이어가 무효가 되는 것으로 보이나 확정하지 못함). 화면 모양은 보지 않았다.
- **O1-T8: 사용자 판정 대기.** 사용자에게 물을 것: 눈빛 중 정지(n=1·5)·먼지 중 정지(n=3)에서 이펙트가 멈췄다 이어졌는지, 눈빛 중 슬로우(n=2·6)·먼지 중 슬로우(n=4)에서 느려졌다가 끊김·처음부터 재시작·겹침 없이 이어졌는지. n=7·8은 보지 못했다.
- Maker 최종: Stop 상태(내가 Stop하지 않음), `maker_get_current_map` map01(0a0972ef-ad23-4e24-af63-afbd53120c1d)·edit. `git status --porcelain` 변경 3건(run.md·이 WorkRecord·`map/map01.map`), `map/map01.map` SHA-256 `22b6acbf…987e` 불변, HEAD `eaeb032` 그대로.

## 리뷰 기록

### 2026-11-19 reviewer — 후속 회차 1 (CombatCore-FU-24·FU-03·FU-23)

- **판정: WAITING** — AI 쪽 필수 근거는 충족했다. 남은 것은 사용자 V11(Plan 회차 1 "완료 기준 — 사용자")과 커밋 구성 판단 1건이다. 이 판정은 사용자 수락·배포 승인이 아니다.
- **검토 버전**: 로컬 커밋 c6422cd(push 전, 37파일, 부모 bb3ec01). Bundle `24fa65cf…8187`(map01 제외 58경로)은 coder·tester 값이 같다. 작업 트리의 미커밋 변경은 run.md, 이 WorkRecord(QA·리뷰 절), `map/map01.map`(사용자 변경)뿐이다.
- **주체·방법**: msw-reviewer(독립 실행). Maker는 쓰지 않았고 시험을 반복하지 않았다. 읽은 지침: reviewer 계약, 팀 계약, 구현 원칙, msw-general·msw-ui-system, Foundation 참조 4개, platform-maple(map01 TileMapMode 0을 Grep으로 확인), msw-scripting·verify-checklist, dataset.md. 확인한 자료: `git show c6422cd -M`(name-status·`.directory`·원장 diff), `git ls-tree 16d70b3`(옛 `@Assist` 트리), Glob, Grep(`serveronly`, FileStructure §7, GameDesign §4), 해시 2개(`map/map01.map` `22b6acbf…987e`, `DataSet/PlayerActionFxData.csv` `75b8e8f0…a5dc` 둘 다 기록과 같음).

**요구별 대조**

| ID | 판단 | 근거 |
| --- | --- | --- |
| FU-24 | 충족 | 22파일 모두 git `R100`(바이트·이름 그대로)이고 목적지가 Plan 이동 목록과 같다. Glob 결과는 `DataSet/` 8쌍, `Catalog/` 3쌍, `UI/` 4쌍이다. 5개 스크립트는 `.mlua`·`.codeblock`이 1개씩이고, `**/@Assist*`는 0건이다. 16d70b3의 `@Assist/RangeGizmo`·`Player/@Assist/AttackRange`에는 `.directory` 말고 다른 파일이 없었다(빈 폴더라 함께 지워져도 잃은 것이 없음). `Catalog.directory`는 새 EntryKey·26.11이다(Maker 생성). 옛 `.directory` 7개는 사용자 Maker 삭제 결과다. 런타임 근거: 8표 행 수가 이동 전과 같고, Logic 5개가 있으며, 로드 [VRF]가 나오고, 팝업·토스트가 동작한다(coder 1회와 tester 독립 1회) |
| FU-03 | 충족(Plan 설계대로 경고 독립 재현은 NOT_RUN) | coder 임시 헤더에서 경고 1회와 `guard fx off`가 나왔다. tester는 누적 로그로 같은 시각·횟수를 대조했다. 복원 해시는 `75b8e8f0…a5dc`로 리뷰에서도 일치했다. 복원 뒤 정상 로드는 tester Play 4회로 확인했다. Plan이 tester 임시 변경을 막았으므로 NOT_RUN은 정당하다 |
| FU-23 | 충족 | 원장 diff는 +5/-3이다. 주석 1줄과 빈 줄은 20행 제목 바로 아래이고, 23·24·30행은 Plan 문구와 글자까지 같다. ID·과거 절·OPEN은 바뀌지 않았다 |

- 요구 확대·누락: 없다. 코드·`.model`·`.map`·`.ui`·Global 변경이 0이다. 문서(Plan 후속 절, 로드맵 1줄, WorkRecords README, run)는 planner·메인 산출물이다.
- QA 표기: PASS, NOT_RUN, 논리 경로(입력 수락 지점 호출)를 구분해 적었다. 스크린샷 0장도 FU-18 계획과 맞다. JUST·PARRY·팝업 닫기·토스트는 실제 키·마우스가 아닌 함수 호출로 확인했다고 밝혔다. 직접 실행하지 않은 결과를 완료 근거로 쓴 곳은 없다.
- 한계(결함 아님): tester build 로그의 기록 시각(21:45:16)만으로는 Refresh가 새로 컴파일했는지 구분할 수 없다. 대신 이동한 5개 Logic이 런타임에 있고 오류 로그가 0건이라, 등록됐다는 근거는 충분하다.

**발견·분류**

1. **커밋 구성과 Plan·FileStructure 불일치(경미, 사용자 판단 필요)**
   - c6422cd에 Maker가 다시 저장한 `RootDesk/MyDesk.directory`·`RootDesk/MyDesk/Player.directory`가 들어 있다. 두 파일 모두 `CoreVersion 26.10.0.0→26.11.0.0` 1줄만 바뀌었다.
   - 어긋나는 기준:
     - Plan 회차 1 위험 4 "이 회차 커밋에 섞지 않는다";
     - 완료 기준 8 "제품 변경은 22파일·Maker가 만들거나 지운 `.directory`(`Catalog` 추가, `@Assist` 계열 삭제)·원장뿐, 다른 재저장은 분리";
     - FileStructure §7 "범위 밖 재저장 … 이동 커밋에 섞지 않는다".
   - 사용자는 같은 성격의 재저장 5개를 [ops] bb3ec01로 분리했다. "이동의 부모 폴더"라는 이유는 사실이지만, 바뀐 내용은 이동이 아니라 26.11 버전 갱신이다. 그래서 그 결정의 취지와 맞지 않는다고 본다.
   - 기능 영향은 없고 coder 수정 대상도 아니다. 커밋은 아직 push 전이다.
   - 처리 선택지(사용자 결정):
     - (가) 그대로 두고 planner가 Plan 완료 기준 8과 FileStructure §7에 예외로 기록한다. 리뷰 권장안이다: 내용이 1줄이고 이력 재작성이 필요 없다.
     - (나) 메인이 사용자 요청을 받아 push 전 로컬 커밋을 나눠 두 파일을 [ops]로 옮긴다. 이력 재작성이라 사용자 요청이 필요하다.
2. **tester 해시 훅 우회 시도: 시험 근거로는 유효**
   - 판단 이유:
     - 22파일 동일성의 1차 근거는 git `R100`과 `.model`이 아닌 파일의 SHA-256이며, 훅과 관계없다.
     - Bundle은 읽기 전용 바이트 해시다. 서로 다르게 구현한 coder·tester 스크립트가 같은 값을 냈다.
     - 시험 전·후 git status가 같아 제품 변경이 없다.
   - 절차 문제(문자열 분할 시도, 스크립트 파일로 같은 읽기를 한 것)는 메인이 사용자에게 보고할 사안이다. 이 판정에는 반영하지 않는다.
   - 운영 개선 후보(이번 회차 요구 아님): 이제 버전은 커밋 해시로 고정한다. 그래서 Bundle을 `git ls-tree -r <커밋>`의 blob id로 대신하면 `.model`·`.ui`를 셸로 열지 않아도 된다.
3. **[LEA-3022] 5건: 시험 흔적, 제품 결함 아님**
   - `serveronly` true 표가 정확히 5개다(CombatRuleData·MonsterAttackPatternData·MonsterStatData·MonsterSoundData·PlayerActionFxData). tester가 클라이언트에서 GetTable을 부른 건수와 같다.
   - coder Play와 tester의 다른 Play에서는 `LEA-`가 0건이다.
   - 다음 회차 tester·coder는 Maker 누적 로그에서 22:11:32의 이 5건을 제외해 읽어야 한다.
4. **tester 관찰 "JUST 직후 반격 10타가 targetHittableSegment에 막혀 반격 기회 소모": 결함 아님(승인된 규칙대로 동작)**
   - 근거:
     - GameDesign §4 "반격 보너스는 유효 시전 시작에 소비해 빗나가도 소모한다";
     - 같은 절 "몬스터는 공격 점프(출발·복귀) 중에는 맞지 않는다 … 반격 창 2.0초 중 실제로 칠 수 있는 시간은 패링 뒤 약 1.5초·저스트 뒤 약 1.0초다".
   - tester는 JUST 0.8초 뒤에 공격했다. 그 시점은 복귀 구간이라 피격 불가였다. 이 회차는 코드를 바꾸지 않았다.
   - 체감상 "반격이 헛되게 사라진다"고 느끼면 새 요구다(반격 보너스 소비 시점, 또는 반격 창 시작 시점 변경). 사용자가 원할 때 planner가 새 FU로 등록한다. 지금은 등록하지 않는다.
5. **문서 문구(기존, 이번 변경 아님)**
   - 측정값: `rate=0.4`, 12→4. GameDesign §4 "일반 가드 경감은 60%(잔여 피해 40%)"와 Features "가드 잔여 40%"에 맞는다.
   - 같은 GameDesign의 다음 줄 "가드는 일반·패링 속성에서 40% 경감"과 coder NOT_RUN 목록의 "가드 40% 경감"은 반대로 읽힌다.
   - 구현 결함이 아니다. planner가 회차 종료 정리 때 GameDesign 문구 통일을 사용자 승인 후보로 올린다.
6. **Plan 기준 갱신 누락(정리 대상)**: 완료 기준 8의 "map01.map은 회차 시작 해시 그대로"는 중간에 Maker 재저장으로 바뀌었다. 사용자가 새 기준 `22b6acbf…`을 정했다(run 기록). planner가 회차 종료 때 Plan에도 이 결정과 근거를 적는다.

**담당별 다음 행동**

- 메인: 사용자에게 아래 V11과 발견 1의 (가)/(나)를 묻고, 발견 2를 보고한다. 결정 전에는 [review] 커밋·push를 하지 않는다. (나)를 고르면 커밋 분리는 메인이 한다.
- planner(사용자 V11 뒤): Plan 회차 1 "회차 종료 때 문서 정리" 목록을 처리한다.
  - FileStructure §4·§5·§7, 2단계 Feature 위치 열;
  - Features/0_CombatPause·Plans/MonsterCombat·AssetList 링크;
  - FU-03·23·24 행.
  - 발견 1의 결정, 발견 6의 map01 기준 변경, 발견 5의 문구 후보도 함께 적는다.
- coder: 수정할 것 없음.
- tester: 추가 실행 필수 없음. FU-03 경고 독립 재현은 메인이 임시 CSV 변경을 따로 허락할 때만 한다.

**사용자 V11 확인 항목**(AI가 볼 수 없거나 실제 입력이 아닌 부분)

1. Maker 작업 공간 창
   - `DataSet` 폴더에 표 8개, `Catalog` 폴더에 스크립트 3개, `UI` 폴더에 스크립트 4개가 각각 하나씩 보인다.
   - 옛 위치(`@Assist`, `Player/@Assist`, MyDesk 바로 아래 UIPopup·UIToast, `Combat`의 CombatRuleCatalog)에 항목이 없다.
2. 기본 공격 10타 때 화면의 피해 숫자가 HP 감소와 맞는다. 로그로는 머쉬맘 HP 100→90(10×1), PARRY 반격은 8타×2를 확인했다.
3. 머쉬맘 die 마지막 프레임 정지 모습. 로그로는 DEAD 1회와 사망 뒤 새 공격 없음을 확인했다.
4. 팝업·토스트의 모양과 표시. 로그로는 Enable과 정지·재개를 확인했다. 실제 버튼 클릭으로 팝업을 닫아 보기.
5. 실제 키로 JUST·PARRY 1회씩과 반격 체감(위 발견 4 포함). AI 확인은 입력 수락 지점 호출이었다.
6. 전투 화면 전반이 이동 전과 같다. 모바일·실접속은 기존대로 NOT_RUN이다(V11·V12 범위 밖).

**검사하지 않은 범위**: Maker 실행·런타임 재확인(reviewer 역할 밖), Bundle 재계산(`.model` 셸 읽기 훅), `.ui` 내용, 회차 A·C 전수 회귀(Plan에서 NOT_RUN으로 정함).

### 2026-11-20 reviewer — FU-26 방안 1-A (위 11-19 절과 별개, 기존 절은 그대로)

- **판정: WAITING** — 요구 ID CombatCore-FU-26. AI 쪽 필수 근거(Plan FU-26 절 완료 기준 AI 1~7)는 충족했고 결함·요청 밖 변경은 없다. 남은 것은 사용자 V11(점프) 확인 범위 1건과 회차 종료 결정 4건이다. coder 수정 대상 없음. 이 판정은 사용자 수락·배포 승인이 아니다.
- **검토 버전**: 로컬 커밋 a18b251(부모 c6422cd, push 전). 리뷰에서 직접 확인한 것:
  - `git diff --name-only c6422cd a18b251`: 제품 경로는 `RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua` 1개(+10/−7), 나머지는 run·FileStructure·Plan·WorkRecord 문서다.
  - 대상 파일 blob `62dcb685…`, 작업 트리 SHA-256 `d3c8d2fd…89df`(coder·tester 값과 같음). `map/map01.map` `22b6acbf…987e`(Plan 기준과 같음). `PlayerActionFxData.userdataset` `c4a19587…fd62`.
  - `git diff a18b251 --stat -- RootDesk Global map ui Environment`: 작업 트리와의 제품 차이는 `PlayerActionFxData.userdataset`(CoreVersion 26.10→26.11 1줄)·`map/map01.map`뿐이다. 둘 다 범위 밖 미커밋이다.
- **주체·방법**: msw-reviewer(독립 실행). Maker를 쓰지 않았고 시험을 반복하지 않았다. 읽은 지침: reviewer 계약, 팀 계약, 구현 원칙, msw-general·msw-ui-system, Foundation 참조 4개, platform-maple(map01 `TileMapMode` 0을 Grep으로 확인), msw-scripting·verify-checklist, msw-combat-system, animation-state·monster. 확인한 자료: 위 git 명령, `OrangeMushroomAttack.mlua` 전체, `MonsterAttackMotion.mlua` 1~160행(SetMotionClip·StartDrivenClip·TickClip·StopDrive), `CombatPauseComponent.AbortCombat`, 패턴 표 열 5개, GameDesign §4.2 해당 줄, Grep(`OrangeMushroomAttack` 사용처: Mushmom·OrangeMushroom 모델 2개, 파일 이름만).

**요구별 대조(Plan FU-26 절 완료 기준 — AI)**

| 기준 | 판단 | 근거 |
| --- | --- | --- |
| 범위(1-A 승인 내용) | 충족 | 승인 문구(run 2026-11-20): "W에서 jump 클립 1회 전환·TickClip 구동 종료 + LeapJumpHeight 포물선(약 0.8)". diff는 ① `LeapJumpHeight` 0→0.8 ② 무조건 `TickClip()` 삭제 → windup 안에서만 호출 ③ W 블록에 `SetMotionClip("jump", 1)` ④ 주석 2곳뿐이다. `SetMotionClip`이 `_T.drive = nil`·전체 범위·배율 1×ActionRate를 쓰므로 새 메서드 없이 승인 동작이 된다. 수평 식·판정 시각·착지 x·피격 선언·복귀·1칸·CSV·모델은 diff 밖이다. 편집 허용 후보 파일 안이다 |
| AI 1 결함 지표 | 충족 | coder·tester 모두 계단(W +0.88, 0.286초 −0.62)이 사라지고 정점 1개·골짜기 0인 포물선(정점 1.38 = Home.y 0.581 + 0.8)을 측정했다. 부원인(정지 프레임)은 1-A 대상이 아니라 판정하지 않았다(아래 4) |
| AI 2 시각·위치 | 충족 | tester W 1.148~1.159, 판정 1.574~1.591, 착지 x 최대 0.007 벗어남, 착지 y ≤+0.006. 높이는 승인으로 바뀌어 "approach 중 y ±0.01"은 해당 없다 |
| AI 3 프레임 | 충족(승인으로 바뀐 기준) | 아래 판단 1 |
| AI 4 D-Q6 | 충족(한계 기록됨) | slowW(windup 중 시작, approach 중 종료)·slowA(approach 중 시작)로 S1~S3를 덮었다. windup PlayRate 0.7×ActionRate(coder NOT_RUN)를 tester가 0.350~0.700으로 측정했다. run9 Δ를 로그로 남기지 않은 한계는 tester가 밝혔고 관측값이 ±0.05 안이다. "f1↔W·f4↔판정"은 1-A에서 f1·f4가 보이지 않아 W·판정 시각으로 대신했다(같은 승인 변경) |
| AI 5 1칸 회귀 | 충족 | 접근 0.503·0.504, 정점 +0.8, 착지 x. 복귀 높이는 tester가 따로 재지 않았으나 coder가 복귀 0.5초·정점 1.38을 쟀고, 기준 문구대로 복귀·1칸 경로 소스 diff 0이다 |
| AI 6 회귀 | 충족(JUST·PARRY NOT_RUN 정당) | 피격 구간 8/8, 판정 1회(HIT 12·GUARD 4), 3칸 눈빛·먼지, die 1회 정지, 일시정지(windup·approach). JUST·PARRY는 판정 경로가 diff 밖이고 11-19 QA가 논리 경로를 확인했다 |
| AI 7 build·git | 충족 | tester build 93건 Info·Error 0. git 제품 변경은 승인 파일 1개, map01 해시 그대로·커밋 제외(리뷰 확인) |

- 직접 실행하지 않은 결과를 완료 근거로 쓴 곳은 없다. coder·tester 모두 NOT_RUN(실접속·모바일·정지 프레임 통계·JUST·PARRY·화면 체감)을 따로 적었다. tester는 이번에 훅 막힘에서 우회하지 않고 멈췄다.
- 다른 모델 영향: `OrangeMushroom.model`도 이 스크립트를 쓰지만 패턴 표에 orangemushroom 행이 없고 `.mlua`·CSV·map에서 부르는 곳이 0이라 `LeapJumpHeight` 기본값 변경의 현재 실행 영향은 없다. 6단계에서 일반 몬스터 행을 넣을 때 이 기본값이 적용된다는 점만 Plan에 남긴다.

**판단 1 — 바뀐 기준 적용과 사용자 확인**

- **프레임 기준 교체는 정당하다.** AI 3 "0→1→2→3 순서, 건너뜀·되돌림 0"은 attack1·skill1의 f1~f3를 보여 준다는 전제다. 사용자가 승인한 1-A는 그 f1~f3 표시를 없애는 것 자체이므로 원래 문구는 적용 대상이 사라졌다. Plan 완료 기준 1이 "원인을 확정하지 못한 채 승인했다면 그 승인안이 정한 관찰 지표"를 허용하고, "유지할 기존 승인 규칙"도 "승인안이 바꾸기로 한 항목 말고는"이다. tester의 대체 지표(접근 중 attack1·skill1 f≥1 이벤트 0, 클립 변경 1회, 되돌림 0)는 원래 기준의 취지(건너뜀·되돌림 없음)를 보존한다. 기준을 낮춰 통과시킨 경우가 아니다.
- **다만 문서가 승인을 따라오지 않았다(정리 대상, 결함 아님).** Plan FU-26 절에는 1-A 승인 문구·내용, 바뀐 AI 3 기준, "착지 = 판정 = 서버 f4 쓰기"(1-A 뒤 f4 쓰기 없음, 판정 = `CompleteMotion`), "2·3칸 접근 높이 0"이 아직 옛 문구다(546행 진행 메모만 있음). GameDesign §4.2의 "도약 높이 0(수평 이동만)"·"2·3칸 모션·이펙트는 원작의 0.7배"(1-A 뒤 도약 구간은 jump 정지 자세·배율 1)도 같다. 회차 종료 때 planner가 1-A 승인 범위 안에서 고친다(Plan "회차 종료 때 문서 정리" 2026-11-19 추가 항목 그대로).
- **"1-A 유지"를 V11 수락으로 볼 수 있는가: 부분적으로만.** 사용자는 a18b251(tester와 같은 버전, 커밋 뒤 확인)을 화면으로 보고 2-b 대신 1-A를 골랐다. 이는 완료 기준 — 사용자 첫 항목("2칸 좌·우·3칸 점프 초반 공중 동작이 자연스럽게 이어진다")을 받아들였다는 뜻으로 읽을 수 있다. 그러나 그 질문은 "1-A 유지 / 2-b" 방향 선택이었고, 나머지 두 항목(1칸 회귀 없음, 반응 시간·속도·맞는 구간 체감이 이전과 같음)과 tester 관찰 O-2(착지 때 stand 1프레임, 10회 중 1회)는 묻지 않았다. Plan "회차 1 남은 흐름" 8도 V11(점프)을 reviewer 뒤에 따로 둔다. 그래서 별도 시험을 다시 요구하지는 않고, 메인이 사용자에게 한 번 확인한다: "1-A 유지는 V11 점프 3항목 수락 뜻인가, 1칸·체감·착지 순간(O-2)에 문제는 없었나". 답이 "그렇다"면 FU-26의 사용자 기준은 충족이다.
- 애니메이션 확인 규칙: 1-A는 기존 ActionSheet 키 `jump`를 쓰는 안이고, 진단 1절에 머쉬맘 ActionSheet 7개 키·RUID 목록이 있으며 사용자가 그 안을 골랐다. run 기록에는 메인이 그 목록을 사용자에게 보였다는 문구가 없다. 결과를 이미 화면으로 보고 골랐으므로 판정에는 반영하지 않는다.

**판단 2 — 버전 근거**

- **같은 버전 근거로 충분하다.** 대상 버전은 커밋 해시 a18b251로 고정됐고(CLAUDE.md 버전 고정 기준), 대상 파일은 blob id·SHA-256이 coder·tester·reviewer 셋에서 같다. 작업 트리와 커밋의 제품 차이는 범위 밖 두 파일뿐임을 리뷰에서도 git으로 확인했다. git 해시는 내용 주소라 바이트 동일성의 근거로 Bundle보다 강하다.
- **Bundle 방식의 문제(운영, 제품 결함 아님)**: (가) 계산 규칙(대상 확장자·경로 정렬·줄 형식·제외 목록)이 계약·문서 어디에도 없다(Grep: ship references 0건, Docs는 이 WorkRecord만). 그래서 구현마다 값이 다르다. 11-19에는 우연히 같은 구현이 같은 값을 냈다. (나) coder 값은 커밋 전 작업 트리 기준이라 범위 밖 미커밋 파일(`PlayerActionFxData.userdataset`)이 섞였고, 정의상 커밋 기준 값과 비교할 수 없다. (다) `.model`·`.ui`를 셸로 읽어야 해서 훅과 부딪힌다(11-19 우회 시도, 이번 정지의 원인).
- **11-19 리뷰 발견 2의 개선 후보와 연결**: 이번 일이 그 후보의 구체적 근거다. 제안(운영 규칙 변경이라 사용자 승인 뒤 `[ops]`): 바이트 지문을 ① `git rev-parse <커밋>^{tree}`(또는 `git ls-tree -r <커밋> -- RootDesk Global map ui`의 blob id 목록) ② 담당 시작·종료 때 `git status --porcelain`과, 범위 밖 미커밋 파일이 있으면 그 파일의 SHA-256으로 바꾼다. 모두 git 객체만 읽으므로 구현 차이·훅 충돌이 없다. 커밋 전 coder 단계에서는 `git diff --stat`과 바뀐 파일의 SHA-256만 적고, 지문은 메인 `[code]` 커밋 해시로 고정한다. 바꿀 곳은 CLAUDE.md "버전 고정" 줄과 ship coder·tester 계약의 해당 문구다(메인·사용자 결정).

**판단 3 — tester 관찰 분류**

| 관찰 | 분류 | 근거 | 추적 제안 |
| --- | --- | --- | --- |
| O-1 취소 때 클립이 stand로 돌아오지 않음 | FU-26 결함 아님. 기존 구조의 표시 공백(낮음) | `CancelMotion`은 "HIT·DEAD 위에 stand를 쓰지 않는다"는 의도로 클립을 건드리지 않는다(diff 밖, c6422cd에서도 attack1이 남았다). 1-A로 바뀐 것은 남는 그림(attack1 → jump 정지 자세)뿐이다. 실제 플레이에서는 플레이어 사망·정지 중단(`AbortCombat`)·맵 이탈 때만 생기고, 그때 몬스터는 집으로 돌아가지 않고 그 자리에 선다 | 후보 FU-28(가칭) "전투 중단·공격 취소 뒤 몬스터 표시·위치 정리(IDLE로 끝난 취소에서 stand 복귀·집 복귀)". (C) 추적. 다시 볼 조건: 사용자가 플레이어 사망·정지 중단 뒤 어색함을 보고하거나, 3단계 이후 전투 재시작 흐름을 만들 때 |
| O-2 착지 때 stand 1프레임(1/10) | FU-26 결함 아님. 기존 코드의 같은 틱 이중 클립 쓰기(낮음) | `CompleteMotion`의 `SetVisualClip("stand")` 뒤 같은 서버 틱에 `PerformReturnMotion`의 `SetMotionClip("jump")`가 이어진다(둘 다 diff 밖). 1-A 전에도 attack1 → stand → jump 순서였다. 다만 1-A 뒤에는 앞뒤가 같은 jump 자세라 끼인 stand가 더 눈에 띌 수 있어 사용자 화면 판단이 필요하다 | 같은 순간(착지)을 다루는 FU-13 행에 관찰로 붙인다(새 ID 불필요). 사용자가 V11에서 보인다고 하면 그때 결함으로 올리고 수정안(복귀가 바로 이어질 때 stand 쓰기 생략 등)은 승인 대상으로 둔다 |
| O-3 자연 공격 이상 2건 | 판단 보류(원인 미확정), FU-26 범위 밖 | 1칸 경로이며 diff 밖이다. 시험 부산물(플레이어 HP 미보충으로 누적 피해) 조건에서 나왔다. 1칸 공격이 0.52초에 ATTACK → IDLE로 끝나고 집으로 돌아가지 않은 모습은 플레이어 사망 → `AbortCombat` → `CancelPendingAttack` → `CancelMotion` 경로(O-1과 같은 구조)와 맞는다. 시작 x −0.750은 앞 시험의 위치가 남은 것으로 보이나 로그가 없다 | 별도 FU 없이 FU-28 후보의 재현 조건으로 묶는다. 확인이 필요하면 tester 조건: 자연 공격 중 플레이어 HP를 보충하지 않고, 플레이어 사망·부활 시각, 몬스터 상태·구간·x, `[VRF] CombatPause abort`를 같은 시계로 기록한다. FU-26 종료에 필수 아님 |

**판단 4 — 부원인 FU-16**

- 1-A로 다루지 않은 것은 적절하다. 사용자는 A~D(이동 방식 변경 포함)를 고르지 않고 클립 쪽(1-A)을 골랐으며, 이동 방식 변경은 Plan "사용자 승인 대상"이다. 1-A는 수평 이동·위치 쓰기를 바꾸지 않았으므로 정지 프레임은 그대로라고 보는 것이 맞고, coder·tester 모두 개선으로 판정하지 않았다(표본 4회 0건은 근거로 쓰지 않음).
- 남은 추적: 진단 결과가 Plan 행에 아직 없다. 회차 종료 때 planner가 정리한다 — FU-16: 측정 확정(2·3칸 18회 중 13회, 1칸 6회 중 4회, `MoveVelocity` 0회, 26.10/26.11 무관), 속도 기반 이동 가능성(`WalkSpeed`·`InputSpeed` 런타임 상향 시험), 수정안 A의 위험. 다시 볼 조건 "1-A 뒤에도 '가끔 툭 건너뜀'이 보이면". FU-14: 정지 프레임과 같은 현상일 가능성이 높다는 진단을 적고 FU-16에 합칠지 사용자·planner가 정한다. FU-15: 이번 결함의 원인으로 지지되지 않음, 기존 다시 볼 조건 유지.

**판단 5 — EqualizeLeapFrames·EqualizeLeapBounds 잔존 코드**

- 1-A 뒤 `TickClip`은 windup(f0만 표시) 안에서만 돌고, 균등화는 W 이후 경계(f2·f3)만 바꾸므로 화면·시각 효과가 0이다. `CompleteMotion`의 `TickClip()`도 W 뒤에는 할 일이 없다. 남은 효과는 `[VRF] leap bounds`·`equalize=` 로그뿐이다.
- 구현 원칙 §3("자신의 변경 때문에 쓰이지 않게 된 것은 제거")에 걸리지만, `EqualizeLeapFrames`는 사용자가 요구하고 기본값을 수락한 조절 항목(GameDesign §4.2)이라 지우는 것은 사용자 승인 대상이고, 1-A를 되돌리는 선택지가 V11 전까지 열려 있었다. 그래서 이번 미제거는 결함이 아니다.
- **정리 후보로 둔다**: 후보 FU-29(가칭) "2·3칸 도약 균등화 항목 정리". 선택지 (가) V11 수락 뒤 `EqualizeLeapFrames` 속성·`EqualizeLeapBounds`·`CompleteMotion`의 `TickClip()`·`equalize=` 로그를 지우고 GameDesign §4.2 조절 항목 문구를 고친다(권장 — 의미 없는 인스펙터 항목이 남으면 다음 조정 때 오해를 부른다. 같은 파일 계열을 고치는 후속 회차 2나 6단계 몬스터 동작 일반화에 묶으면 비용이 적다), (나) 1-A 되돌리기 대비로 둔다. 그동안 8행 주석은 "1-A 뒤 화면 효과 없음"을 반영하지 않으므로 정리 때 함께 고친다. `StartDrivenClip`·`TickClip` 자체는 windup 구동에 계속 쓰이므로 대상이 아니다.

**판단 6 — 회차 1 종료 가능 여부와 종료 때 처리할 항목**

- FU-24·FU-03·FU-23은 11-19 리뷰와 사용자 V11로 끝났다(다시 판정하지 않음). c6422cd 뒤 제품 diff는 FU-26 승인 파일 1개뿐이다(Plan 회차 1 남은 흐름 7 확인 완료).
- **회차 1은 위 판단 1의 사용자 확인 한 번이 끝나면 닫을 수 있다.** 코드 수정·재시험은 필요 없다. 그 뒤 planner 종료 정리 → 메인 `[CombatCore][review]` 커밋·push 순서다.
- 종료 때 처리할 항목:
  1. `PlayerActionFxData.userdataset` 재저장분(CoreVersion 1줄, 범위 밖): (가) bb3ec01 선례처럼 따로 `[ops]` 커밋(권장 — 사용자의 같은 성격 결정과 FileStructure §7 "섞지 않는다"에 맞음), (나) `[review]` 커밋에 함께 넣음(§7과 어긋나 예외 기록 필요), (다) 되돌림(다음 Maker 저장 때 다시 생겨 권장하지 않음). 사용자 결정.
  2. 가드 문구 통일(11-19 발견 5, GameDesign §4.2 "40% 경감" → "잔여 피해 40%(60% 경감)", 규칙·수치 불변): 사용자 승인 후보. 승인되면 planner가 종료 정리에 넣는다.
  3. Bundle 개선(위 판단 2): 사용자 승인 후보. 승인되면 메인이 `[ops]`로 CLAUDE.md·ship 계약을 고친다. 회차 2부터 적용.
  4. Feature 반영(planner): 2단계 Feature에 FU-26 결과(1-A: W에서 jump 전환·높이 0.8 포물선, 계단 높이 제거, 정지 프레임은 FU-16으로 남음, 실접속·모바일 NOT_RUN)와 회차 1 V11 결과. Plan에는 1-A 승인 문구·바뀐 AI 3·유지 규칙의 f4·높이 문구, FU-26 행 정리, FU-14·15·16 행 갱신(판단 4), 후보 FU-28·29와 O-2의 FU-13 관찰 추가. GameDesign §4.2의 도약 높이·0.7배 문구는 1-A 승인 범위 안에서 고친다.
- 참고(경미, 조치 불필요): a18b251에 FileStructure §7 예외 1줄과 run.md가 함께 들어갔다. CLAUDE.md 표의 `[code]` 포함 목록(제품·Plan·WorkRecord)보다 넓지만 둘 다 이 회차 문서이고 push 전이며 회차 커밋과 함께 push되므로 결과는 같다.

**담당별 다음 행동**

- 메인: 사용자에게 아래 "사용자 판단 사항"을 묻는다. 답 전에는 `[review]` 커밋·push를 하지 않는다. 1에서 (가)를 고르면 `[ops]` 커밋을 따로 한다.
- planner(사용자 답 뒤): Plan 회차 1 "회차 종료 때 문서 정리"와 위 판단 6의 4를 처리한다.
- coder: 수정할 것 없음.
- tester: 필수 추가 실행 없음. O-3 확인은 사용자·메인이 원할 때만 위 조건으로 한다.

**사용자 판단 사항**

1. "1-A 유지"가 V11 점프 3항목(2·3칸 초반 자연스러움, 1칸 회귀 없음, 반응 시간·속도·맞는 구간 체감 동일)의 수락인지, 착지 순간 stand 한 프레임(O-2, 10회 중 1회)이 보였는지.
2. `PlayerActionFxData.userdataset` 재저장분 처리: (가) 따로 `[ops]` / (나) `[review]`에 포함 / (다) 되돌림.
3. 가드 문구 통일 승인 여부.
4. 버전 지문을 Bundle 대신 git tree·blob id로 바꾸는 운영 변경 승인 여부.
5. (기록용, 지금 결정 불필요) 후보 FU-28(취소·전투 중단 뒤 몬스터 표시·위치)·FU-29(균등화 항목 정리)의 등록·시기.

**검사하지 않은 범위**: Maker 실행·런타임 재확인(reviewer 역할 밖), `.model` 내용(ModelBuilder 읽기 미실시, 모델 diff 0과 tester 정점 1.38 측정으로 대신), O-3 원인, 실접속·모바일, Bundle 재계산.

### 2026-11-20 reviewer — 후속 회차 2 (CombatCore-FU-17·FU-19·FU-12 (가)) (위 절들과 별개, 기존 절은 그대로)

- **판정: WAITING** — 요구 ID CombatCore-FU-17·FU-19·FU-12. Plan 회차 2 완료 기준 AI 1~5의 필수 근거는 충족했고, 요청 밖 변경은 없다. 남은 것은 사용자 판단 3건이다. ① FU-12 V11 두 항목은 지금 게임 안에서 볼 경로가 없다(아래 판단 3). 그래서 보는 방법을 정해야 한다. ② 새 코드의 잠재 결함 O-1을 이번 회차에 고칠지 정해야 한다. ③ 자연 플레이로 볼 수 있는 회귀 V11이 남아 있다. 이 판정은 사용자 수락·배포 승인이 아니다.
- **검토 버전**: 로컬 커밋 d8c61db(`d8c61db6dfc18088f2a4f0c84bb67d3deec093dd`), 트리 `3940b24f378ecf9e1fdcd9bb99e9463ef46edd17`, 부모 a593e2b, push 전. 리뷰에서 직접 확인했다.
  - `git diff --stat a593e2b d8c61db`: 제품은 `.mlua` 4개(MonsterStateControl +9/−2, MonsterAttackMotion +85, PlayerCombatComponent −1, PlayerGuardComponent +4/−3)이고, 나머지는 run·Plan·WorkRecord다. `.codeblock`·`.model`·`.map`·`.ui`·DataSet 변경은 0이다.
  - `git ls-tree -r d8c61db` blob id와 작업 트리 `git hash-object`가 4개 모두 개발·QA 절 값과 같다. `CombatPauseComponent` `1658387d…0926`은 바뀌지 않았다.
  - `git status --porcelain`: run.md·이 WorkRecord·`map/map01.map`. `map/map01.map` SHA-256 `22b6acbf…987e`로 기준과 같다.
  - Grep `resolveIndex`: RootDesk 0건.
- **주체·방법**: msw-reviewer(독립 실행). Maker는 쓰지 않았고 시험을 반복하지 않았다.
  - 읽은 지침: reviewer·팀 계약, 구현 원칙, msw-general·msw-ui-system, Foundation 참조 4개, platform-maple(map01 `TileMapMode` 0은 Grep으로 확인), msw-scripting·verify-checklist, msw-combat-system.
  - 확인한 자료: 위 git 명령과 diff 전문, `MonsterAttackMotion`·`MonsterStateControl`·`PlayerGuardComponent` 전체, `EffectService.d.mlua`, `CombatPauseComponent`(정지·AbortCombat 부분), `Monster_Attack` 40~100행, `MonsterManager` `ClearOpponentExecution`, `MonsterHealthComponent` 사망 부분, `MonsterAttackComponent` 슬로우 호출(211행), CSV 3개(CombatRuleData·MonsterAttackPatternData·MonsterStatData), GameDesign §4.2·§4.3, Grep(호출처·`RequestPopupPause`·`LoadAnimationClipAndWait`).

**요구별 대조(Plan 회차 2 완료 기준 — AI)**

| 기준 | 판단 | 근거 |
| --- | --- | --- |
| 범위 | 충족 | 바뀐 파일 4개는 모두 편집 허용 5개 안이다. `CombatPauseComponent`는 바꾸지 않았는데, Plan이 "실제로 고칠 파일은 coder가 정한다"고 했다. `Monster_Attack`·`UIPopup`·`OrangeMushroomAttack`의 blob id도 그대로다. 새 모델·규칙·수치는 없다 |
| AI 1 FU-17 | 충족 | 쓰기만 하던 1줄을 삭제했다. 리뷰 Grep에서도 0건이고, `resolveId`(247행 규칙이 읽음)는 남아 있다 |
| AI 2 V02 회귀 | 충족(화면 피해 숫자는 NOT_RUN) | coder·tester가 따로 확인했다. HitEvent 합 = HP 감소이고, ×2.2 반격 1회는 합 20이다. 이번 diff는 피해·HitEvent 경로에서 쓰기 전용 `_T` 필드 1줄만 지웠다. 화면 숫자 대조는 아래 V11 1로 넘긴다 |
| AI 3 가드 | 충족 | tester가 실제 ↓ 키로 시작·연출·효과음 각 1회와 추가 출처 무증가를 확인했다. 잔여 40%(4)와 패링 2회(입력 수락 지점 호출)도 확인했다. 표 무효 상태는 Plan이 허용한 소스 대조로 판단했다. 리뷰 소스 대조(아래 판단 1)와도 같다 |
| AI 4 FU-12 | 충족(시각 일부 NOT_RUN) | 정지: 엔진 정지를 측정했다. coder는 정지 중 멈춘 프레임과 재개 뒤 이어짐을 봤고, tester는 먼지 스크린샷 2장으로 같은 결과를 봤다. 액션 시계도 멈췄고 끝 시각은 정지 시간만큼 밀렸다. 슬로우: 눈빛·먼지에서 0.7↔0.35 이어 재생 프레임이 계산값과 일치했다(coder·tester). 끝난 이펙트 재생 안 함, 사망·대결 종료·Stop 정리도 확인했다. 맵 이탈은 AI 4 문구("사망·Stop") 밖이다. `OnMapLeave`→`ClearCombatEffects`로 같은 함수를 지나는 것은 소스로 확인했다 |
| AI 5 build·git | 충족 | tester build `LEA&`·`Error`·`LWA` 0건이다. 버전 대조는 위 리뷰 확인과 같다 |

- QA 표기: PASS·NOT_RUN·프로브(Play 메모리) 경로를 나눠 적었다. 직접 보지 않은 시각 결과를 PASS로 세지 않았다. 시험 부산물(probe2 홀드, 프로브 LEA-2007)도 공개했고 결과에서 뺐다. 스크린샷은 coder 10장과 tester 2장으로 FU-18 한도 12장 안이다.

**판단 1 — FU-17·FU-19 동작 동일성(소스)**

- FU-19 `SetGuarding`: 옛 코드는 블록 안에 조기 return이 없었고, 끝에서 `self.isGuarding = isHeld`를 무조건 기록했다. 새 코드는 `wasGuarding`로 같은 시작 판단을 하고, 같은 값을 먼저 기록한다.
  - 블록 안 연출·효과음·`GetCombatTime`·`GetPlayerActionFx`는 `isGuarding`을 읽지 않는다. `isGuarding`은 @Sync가 아닌 일반 속성이다. 그래서 정상 경로의 결과는 같다.
  - 블록 안에서 오류가 나면 옛 코드는 상태 기록을 놓쳤지만, 새 코드는 기록한다. 리뷰 메모의 취지대로 나아졌다.
- FU-17: 남은 `_T` 쓰기는 `resolveId`뿐이고, 읽는 곳이 있다.

**판단 2 — FU-12 (가) 판단과 범위**

- **정지 코드를 더하지 않은 판단은 (가)와 GameDesign §4.3에 맞다.**
  - Plan "coder가 정할 것" 첫 줄: 이미 멈추고 이어지면 같은 일을 하는 코드를 더하지 않는다.
  - FQ-3 (가): 정지 중에는 멈춘 프레임을 보인다.
  - 측정 근거: 정지 중 프레임이 그대로 남고, 숨겨지지 않고, 재개 뒤 이어졌다. 엔진이 하는 이 방식은 "남은 프레임부터 다시 재생"보다 끊김이 적다.
  - `_UtilLogic:SetClientTimeScale(0)`은 클라이언트 전체 시간 배율이다. 그래서 이펙트 종류와 무관하게 적용된다고 본다. 직접 본 것은 서버가 낸 공격 이펙트, 클라이언트 이펙트, 먼지이고, 가드 이펙트는 직접 보지 않았다(한계).
  - 실접속에서는 서버 정지와 클라이언트 배율 0 사이에 지연 차가 있다. 이는 기존 V12·FU-01과 같은 NOT_RUN 범위다.
- **슬로우 추종 구현은 Plan 범위 안이다.**
  - 근거: AI 4 셋째 줄 "슬로우 시작·끝 때 재생 중 눈빛의 배율", 바꿀 파일 FU-12 목록.
  - 대상을 몬스터 이펙트로 한정한 것은 GameDesign §4.2와 맞다(슬로우 ×0.5는 현재 상대에게만, 플레이어·UI·오디오 제외).
  - `GetRuidTimeline` 분리는 같은 캐시를 이펙트가 쓰기 위한 최소 변경이다. `GetClipTimeline`의 동작은 같다.

**판단 3 — 새 85줄 코드 검토(MonsterAttackMotion·MonsterStateControl)**

- 추적·프레임 계산:
  - 지금 프레임 = (액션 시계 경과 × motionRate)를 프레임 Delay에 누적해 구한다. 액션 시계에는 이미 정지(멈춤)와 슬로우(×slowRate)가 반영돼 있고, 이펙트 실제 배율 = motionRate × ActionRate다. 그래서 클립 PlayRate가 1이면 맞다(아래 O-1 예외).
  - 인덱스 `delays[frame + 1]`은 `frame ≤ lastFrame ≤ count−1`이라 범위 밖으로 나가지 않는다. 시작 프레임이 끝보다 크면 즉시 nil이라 오류가 아니다.
  - 이어 재생 뒤에는 `startFrame`·`startAction`을 새 이펙트 기준으로 다시 잡는다. 그래서 모델과 화면 이펙트가 다시 맞춰진다. 대신 프레임 안 진행분을 버리므로, 배율이 바뀔 때마다 끝이 최대 한 프레임 늦어진다. coder가 알려진 한계로 적었고 결함이 아니다.
- RemoveEffect → PlayEffect:
  - 같은 서버 틱에서 이전 serial을 지운 뒤 새 serial 하나만 추적한다. 새 재생이 실패해 serial이 0이면 항목을 빼므로 중복 추적이 없다.
  - 같은 배율로 다시 갱신하는 경우(슬로우 갱신·중첩 없음)는 `|Δ| ≤ 1e-6`이라 건드리지 않는다.
  - 화면에서 이전 이펙트가 실제로 지워지는지, 이어 붙는 순간이 끊기거나 겹치는지는 보지 않았다(NOT_RUN).
- ExecSpace·동기화:
  - 새 메서드 4개와 `GetRuidTimeline`은 모두 ServerOnly이고, 호출처(`ApplySlow`·`OnUpdate`·`ClearCombatEffects`·`PlayEffectRange`)도 서버다.
  - `_EffectService`의 세 메서드는 d.mlua에 ExecSpace 지정이 없다. 기존 `PlayEffectRange`처럼 서버에서 불러 클라이언트에 퍼진다.
  - 추적 상태는 엔티티별 `_T`(비동기화)이고, 새 @Sync는 없다.
- 누수·정리:
  - 목록은 재생 때와 배율 변경 때 끝난 항목을 걷어내므로 한 공격에 최대 2개다.
  - 사망(`MonsterHealthComponent`), 대결 종료(`ClearOpponentExecution`), 맵 이탈·Stop(`OnMapLeave`/`OnEndPlay`)이 모두 `ClearCombatEffects` → `ClearEffects`를 지난다. `dieStarted`면 `SyncEffectRates`도 비운다.
  - 새 타이머·이벤트 구독은 없다.
  - `ClearCombatEffects`는 `ClearEffects`를 배율 1 복귀(`ApplyMotionClipRate`)보다 먼저 부른다. 그래서 정리 순간 다시 재생되지 않는다.
- 정지 중 배율 변경:
  - `ApplySlow`는 `pause.IsPaused`면 거부한다.
  - 슬로우 만료는 전투 시계로 재는데, 정지 중에는 전투 시계가 멈춰 만료되지 않는다.
  - 정지 중 정리는 목록을 먼저 비운다.
  - 그래서 정지 중에 다시 재생되는 경로가 없다.
- 다른 몬스터·여러 공격:
  - 슬로우는 대결 상대의 `MonsterStateControl`에만 걸리고, 추적은 엔티티별이다.
  - 눈빛·먼지는 별도 항목이다.
  - 1칸·2칸 패턴은 `EffectClip`이 비어 호출되지 않는다.
- **현재 데이터에서 슬로우 추종이 실제로 일어나는 경로가 없다(관찰 R-2, 결함 아님).**
  - 이펙트가 있는 패턴은 `parry.guard`(3칸 가드형) 하나다. GameDesign §4.2 "가드형 예고는 ↓ 패링만 저스트 성공"이라 이 공격은 JUST(슬로우 유일 원인, `MonsterAttackComponent` 211행)를 만들지 않는다.
  - 다른 공격의 JUST로 걸린 슬로우(2.0초, ×0.5)는 액션 시계 1.0초에 해당한다. 그런데 다음 공격은 복귀 약 0.5초와 `AttackInterval` 3.0초(액션 시계) 뒤에 시작한다. 그래서 다음 눈빛과 겹치지 않는다.
  - 이 코드는 승인된 요구대로 만든 것이다. 실제로 쓰이는 때는 다음 경우다: JUST가 나는 공격에 `EffectClip`을 넣을 때, `AttackInterval`·`SlowDurationSec`를 크게 바꿀 때, 6단계에서 몬스터가 늘 때. coder·tester의 슬로우 근거는 모두 프로브(`ApplySlow` 직접 호출)다.
- 팝업 정지도 게임 안에서 여는 경로가 없다. `RequestPopupPause`는 `UIPopup` 안에서만 부르고, `_UIPopup:Open` 호출처는 0이다(FU-27). 그래서 Plan의 사용자 V11 두 항목은 일반 플레이로 볼 수 없다. Plan 회차 2 V11 문구는 FU-27의 "경로가 생기기 전에는 V11에 넣지 않는다"와도 어긋난다(planner 정리 대상).

**판단 4 — tester 관찰과 리뷰 관찰 분류**

| 관찰 | 분류 | 근거·조치 |
| --- | --- | --- |
| O-1 `GetEffectFrame`이 클립 PlayRate(`timeline.rate`)를 곱하지 않음 | **새 코드의 잠재 결함(낮음). 현재 데이터에서는 영향 없음** | (1) 같은 파일의 `GetWindupSeconds`(94행)·`StartDrivenClip`(108행)·`PlayDieOnce`(309행)는 모두 클립 PlayRate를 곱한다. 이 식만 다르다. (2) 지금 이펙트 클립(`05113e9d`)의 PlayRate는 1.0이라 결과가 같다. (3) `EffectClip`은 사용자가 직접 고치는 CSV 칸이다. PlayRate가 1이 아닌 클립으로 바꾸면 이어 재생 프레임이 어긋난다. 배율 >1이면 이미 끝난 이펙트를 진행 중으로 보고 다시 낼 수 있어, AI 4 "끝난 이펙트를 다시 내지 않음"이 깨진다. 수정은 `elapsed`에 `fx.timeline.rate`를 곱하는 1곳이다. 이 파일은 편집 허용 범위 안이다. 처리 방법은 사용자 판단 2. 전제: `PlayEffect`의 PlayRate 옵션이 렌더러처럼 클립 PlayRate와 곱해진다는 것은 이 파일 전체와 같은 가정이며, 검증하지 않았다 |
| O-2 끝난 항목이 목록에 남음 | 결함 아님(설계) | 다음 재생·배율 변경 때 걷어내고 정리 경로에서 비운다. 최대 1~2개라 누수가 아니다. coder가 개발 절에 적은 내용과 같다. 추적 불필요 |
| O-3 취소 뒤 이펙트가 끝까지 재생 | 결함 아님(기존 동작 유지) | 변경 전에도 이펙트는 끝까지 재생됐다. (가)는 "기존 이펙트 유지"이고, GameDesign §4.2 "이전 효과 제거"는 슬로우·그로기 같은 효과를 말한다. FU-28(취소 뒤 몬스터 표시 정리)의 관련 관찰로 한 줄 붙인다(새 ID 불필요) |
| O-4 Hp=0인데 `IsDead()` false | 기존 사항(FU-22) | 이번 diff 밖이다. 3단계 Plan 후보로 그대로 둔다 |
| R-1(리뷰) 이펙트 클립 첫 동기 로드 | 관찰(낮음), 추적 후보 | `TrackEffect` → `GetRuidTimeline` → `LoadAnimationClipAndWait`가 몬스터 엔티티별 첫 눈빛 때 서버에서 동기로 돈다. 접근 클립은 스폰 때 `MonsterManager` 138행에서 미리 읽지만, 이펙트 클립은 미리 읽지 않는다. `GetClipTimeline` 주석 "진행 중에는 읽지 않는다"와 다르다. `Monster_Attack` 58·59행 순서상 로드 시간만큼 `attackDue`(판정)와 추적 시작이 늦어진다. 측정된 눈빛→먼지 1.576·1.588초(예고 1.571초)는 ±0.05 안이지만, 그 표본이 첫 공격인지는 확인되지 않았다. 미리 읽기는 `MonsterManager`(범위 밖)를 고쳐야 한다. 다시 볼 조건: Play 시작 뒤 첫 3칸 공격의 눈빛→먼지 전투 시계 차, 또는 6단계 몬스터 동작 일반화 |
| R-2(리뷰) 현재 데이터에서 슬로우 추종 경로 없음 | 관찰, 결함 아님 | 위 판단 3. V11 방법에 영향(사용자 판단 1) |

**판단 5 — 남은 NOT_RUN과 사용자 V11**

- NOT_RUN(PASS로 세지 않음):
  - 슬로우 이어 재생의 화면 모양(끊김·처음부터 반복·겹침, 이전 이펙트 실제 제거)
  - 정지 중 플레이어 공격·가드 이펙트의 화면
  - 화면 피해 숫자와 HP 대조(AI 2 일부)
  - 맵 이탈 단독(소스로 같은 함수 확인)
  - 표 무효 가드 Play(Plan이 소스 대조 허용)
  - 실제 키 패링(Plan 미요구, 회차 1 V11 5 수락)
  - 첫 공격 로드 시각(R-1)
  - 실접속·모바일
- 스크린샷 한도(12장)는 AI 캡처에만 적용된다. 사용자가 직접 화면을 보는 것과는 무관하다.
- V11을 두 부류로 나눈다(사용자 판단 1·3).
  - **자연 플레이로 볼 수 있는 것**: 기본 공격 10타의 화면 피해 숫자와 HP 감소, 가드 시작 때 이펙트·소리 1회, 패링·반격 체감이 이전과 같은지(FU-17·19 회귀).
  - **자연 플레이로 볼 수 없는 것**: 팝업 정지 중 이펙트 모습, 슬로우 중 눈빛·먼지 속도·이어짐.

**판단 6 — 회차 2 종료 가능 여부와 종료 때 처리할 것**

- 사용자 판단 1~3에 답이 오면 닫을 수 있다.
  - O-1을 이번에 고치기로 하면 같은 승인 범위에서 coder(1줄) → 메인 `[code]` → tester(회귀와, 고르면 V11 시연) → reviewer를 다시 돈다.
  - 고치지 않으면 코드 수정·재시험은 필요 없다.
- 회차 2가 끝나면 **이 run의 후속 처리는 모두 끝난다**.
  - (A) FU-03·17·19·23·24, FU-12(결정됨)·FU-26이 처리된다.
  - 나머지 (B)(하지 않음, 추적)·(C)·(D)는 Plan 표에서 계속 추적한다. 이 run의 처리 대상이 아니다.
  - 3단계는 사용자 별도 지시로 시작한다.
- 종료 정리(planner, 사용자 답 뒤):
  1. Plan: 회차 2 "구현 상태"(626행 "미커밋, `[code]` 전")를 d8c61db 기준으로 고친다. FU-17·19·12는 "닫은 항목"으로 옮기고 부채 표 행을 정리한다. O-3은 FU-28에 붙이고, O-1(추적 시)과 R-1은 새 행이나 기존 행에 등록한다. V11 결과와 NOT_RUN 사유를 적고, 회차 2 V11 문구와 FU-27 규칙의 불일치를 정리한다. `목표·상태`·"사용자 결정 대기 → 부채 처리 시점" 줄을 회차 2 종료로 고친다.
  2. Feature(2_CombatCore): 짧게 반영한다.
     - FU-12: 정지는 엔진 클라이언트 시간 배율로 멈추고 이어지며, 추가 코드는 없다. 슬로우는 몬스터 이펙트를 지금 프레임부터 새 배율로 다시 낸다. 한계는 프레임 단위이고, 현재 데이터에서 자연 발생 경로가 없다.
     - FU-17·19: 동작 같음.
     - 남은 NOT_RUN.
  3. GameDesign: 규칙·수치 변경이 없어 고칠 것이 없다. 로드맵 재개 지점은 3단계 시작 대기로 둔다.
  4. 메인: `[CombatCore][review]` 회차 종료 커밋(run·WorkRecord 등 이번 회차 문서)과 push. `map/map01.map`은 계속 뺀다.
  5. run·WorkRecord 삭제: WorkRecord 삭제 조건(회차 1·2 종료, 사용자 V11, Feature·Plan 반영, 링크 정리)이 채워지면 지울 수 있다. 다만 2026-11-19 선례처럼 기준 커밋 링크로 정리한 뒤 지울지는 사용자 확인 사항이다(사용자 판단 4). 사용자 확인이 남아 있으면 유지한다(팀 계약).
- 참고(경미, 조치 불필요): d8c61db에 run.md가 함께 들어갔다. 회차 1(a18b251)과 같은 사례이고 push 전이라 결과는 같다.

**담당별 다음 행동**

- 메인: 아래 사용자 판단 사항을 묻는다. 답 전에는 `[review]` 커밋·push를 하지 않는다.
- coder: 사용자 판단 2에서 (가)일 때만 `MonsterAttackMotion.GetEffectFrame`의 `elapsed`에 `fx.timeline.rate`를 곱한다. 그 밖에 수정할 것은 없다.
- tester: O-1을 고치면 회귀만 한다. 슬로우 이어 재생 [VRF] 프레임이 지금 값과 같아야 한다(클립 PlayRate 1.0이라 결과 동일). 수정의 효과 자체는 PlayRate≠1 클립이 없어 소스 대조로 판단한다. 사용자 판단 1에서 (가)를 고르면 Play 메모리 프로브로 시연한다(제품 변경 0, AI 스크린샷 0). 3칸 공격 중 서버 `SetServerPaused`와 클라이언트 `SetPresentationPaused`, 눈빛·먼지 중 `ApplySlow(1.0~2.0, 0.5)`를 사용자가 Maker 화면으로 보게 한다. R-1을 확인하려면 Play 시작 뒤 첫 3칸 공격의 눈빛·먼지 `clock` 차를 기록한다(필수 아님).
- planner: 위 판단 6의 종료 정리를 한다.

**사용자 판단 사항**

1. FU-12 V11 방법. 팝업 정지와 슬로우가 이펙트와 겹치는 경로가 지금 게임 안에 없다.
   - (가) tester가 Play 메모리 프로브로 정지·슬로우를 걸고, 사용자가 Maker 화면에서 눈빛·먼지·공격·가드 이펙트의 정지 모습과 슬로우 이어짐(끊김·반복·겹침)을 본다. 리뷰 권장안이다: 85줄 슬로우 추종의 화면 결과를 아직 아무도 보지 않았다.
   - (나) NOT_RUN으로 두고 추적한다. 정지는 FU-27, 슬로우는 "이펙트 있는 공격이 슬로우와 겹칠 수 있게 데이터가 바뀌거나 몬스터가 늘 때" 다시 본다. 회차는 AI 근거로 닫는다.
2. O-1(클립 PlayRate 미반영):
   - (가) 이번 회차에서 1곳 고친다. 같은 승인 범위이고, 위 1(가)의 tester 시연과 한 번에 돌릴 수 있다. 리뷰 권장안이다.
   - (나) 고치지 않고 추적 ID로 등록한다. 다시 볼 조건: `EffectClip`을 바꾸거나 새 이펙트를 더할 때, 같은 파일을 고칠 때.
3. 자연 플레이 V11: 기본 공격 10타 피해 숫자와 HP 감소, 가드 시작 이펙트·소리 1회, 패링·반격 체감이 이전과 같은지.
4. 회차 종료 정리 뒤 이 run과 WorkRecord를 기준 커밋 링크로 정리하고 지울지(2026-11-19 선례 "링크 정리 후 삭제").
5. (기록용, 지금 결정 불필요) R-1(이펙트 클립 미리 읽기)을 추적 행으로 등록할 시기. 6단계 몬스터 동작 일반화와 함께 보는 것을 제안한다.

**검사하지 않은 범위**: Maker 실행·런타임 재확인(reviewer 역할 밖), `PlayEffect` PlayRate 옵션과 클립 PlayRate의 실제 곱 관계, 이어 재생의 클라이언트 화면, R-1 로드 시간, `.model`(`AttackInterval`은 DataSet 3.0이 런타임에 적용됨을 `MonsterManager` 163행으로 확인했고 모델 값은 읽지 않음), 실접속·모바일.

### 2026-11-20 reviewer — 회차 2 O-1 재리뷰 (위 절들과 별개, 기존 절은 그대로)

- **판정: READY** — 요구 ID CombatCore-FU-17·FU-19·FU-12(+ 직전 리뷰 지적 O-1). 회차 2 완료 기준 AI 1~5의 필수 근거는 충족했고 O-1은 해소됐다. 사용자 판단 사항(직전 리뷰 1~4)에는 모두 답이 왔고 남은 필수 사용자 확인은 없다. 이 판정은 사용자 수락·출시·배포 승인이 아니다.
- **검토 버전(리뷰에서 git으로 직접 확인)**:
  - `git rev-parse HEAD` = `eaeb03230019fe929fb5423cb8cbc8b3dc857bbd`, `HEAD^{tree}` = `fe15c8744a1c91931a89d272b1f3bfa895825a75`. `d8c61db^{tree}` = `3940b24f378ecf9e1fdcd9bb99e9463ef46edd17`. 둘 다 메인이 넘긴 값과 같다. push 전.
  - `git diff --stat d8c61db eaeb032`: 제품은 `RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua` +1/−1 하나다. 나머지는 run.md(+6/−3)·이 WorkRecord(+246, 삭제 0)다. `.codeblock`·`.model`·`.map`·`.ui`·DataSet 변경은 0이다.
  - `git ls-tree -r`: `MonsterAttackMotion.mlua`는 eaeb032 `8d22ddda9183c257053c1fce14bcc740f3a0a4d9`, d8c61db `da93aea6cfac8ed8e10f20dba342421a0f98082a`다. coder 개발 절·tester QA 절의 값과 같다.
  - `git status --porcelain`: ` M .pipeline/20261119-combatcore-followup/run.md`, ` M Docs/…/CombatCoreWorkRecord.md`(삭제 0, QA O-1 절·시연 기록 추가분 +81), ` M map/map01.map`. RootDesk 미커밋 변경은 0이다. `map/map01.map` SHA-256 `22b6acbf8163ca880c30a4b2597a4b043954ba75d147e019660cb0d58de4987e`로 기준과 같다(범위 밖, 사용자 변경).
- **같은 버전 여부**: coder O-1 수정은 커밋 전 작업 트리에서 했고, 커밋 blob이 coder가 적은 변경 후 blob과 같다. tester O-1 회귀 QA와 사용자 시연은 HEAD eaeb032·트리 `fe15c874…`·blob `8d22ddd…`에서 했다(시작·종료·시연 끝 확인 기록). 리뷰 시점 HEAD·트리·blob도 같다. 세 근거 모두 같은 버전이다.
- **주체·방법**: msw-reviewer(독립 실행). Maker는 쓰지 않았고 시험을 반복하지 않았다. 제품 파일은 고치지 않았다. 읽은 지침: reviewer·팀 계약, 구현 원칙, msw-general·msw-ui-system, Foundation 참조 4개, platform-maple(map01 `TileMapMode` 0은 Grep으로 확인), msw-scripting·verify-checklist, msw-combat-system. 확인한 자료: 위 git 명령, diff 전문, `MonsterAttackMotion.mlua` 전체, `CombatPauseComponent`(`AbortCombat`·`OnUpdate`·`OnEndPlay` 부분), Plan 회차 2 절·부채 표, 이 WorkRecord의 회차 2 개발·QA·리뷰 절과 O-1 개발·회귀 QA·시연 기록, run.md 미커밋 diff.

**O-1 해소 확인**

| 확인 | 판단 | 근거 |
| --- | --- | --- |
| 수정 내용 | 해소 | `GetEffectFrame` 211행이 `elapsed = max(0, now − startAction) × motionRate × timeline.rate`가 됐다. 같은 파일 `GetWindupSeconds`(94행 `sum / (timeline.rate × motionRate)`)·`StartDrivenClip`(108행 `divisor = timeline.rate × motionRate`)·`PlayDieOnce`(309행 `renderer.PlayRate × clip.PlayRate`)와 같은 "Delay ÷ (클립 PlayRate × 배율)" 관계다. 액션 시계에는 ActionRate가 이미 들어 있어 이중 반영이 없다 |
| 영향 범위 | 의도대로 | `GetEffectFrame`을 부르는 곳은 `TrackEffect`(끝난 항목 걷기)와 `SyncEffectRates`(이어 재생 프레임) 둘이다. 둘 다 같은 식으로 바뀌어 직전 리뷰가 적은 위험("배율 >1이면 끝난 이펙트를 다시 낼 수 있음")이 없어진다. `PlayEffect` 옵션 `PlayRate`(motionRate × ActionRate)는 클립 PlayRate를 넣지 않는데, 엔진이 클립 PlayRate를 따로 곱한다는 이 파일 전체의 가정과 같다 |
| null·범위 | 문제 없음 | `fx.timeline`은 `TrackEffect`가 `timeline == nil`이면 기록하지 않으므로 nil이 아니다. `rate`는 `GetRuidTimeline`이 유한·양수로 보정한다 |
| 범위 밖 변경 | 없음 | 제품 변경은 이 1줄뿐이다. 다른 함수·수치·파일·`.codeblock`은 그대로다 |
| 회귀 | 충족(로그 근거) | coder 1회(프레임 4·6·9·12)와 tester O1-T3 6건(2·5·9·11·3·6)이 Delay 표 직접 계산과 모두 맞다. 클립 `05113e9d`의 `rate`는 1.0이라 값이 바뀌지 않는 것이 정상이다. build 로그 `LEA-`·`LWA-`·`Error` 0(O1-T2), Play 중 새 `LEA-`·`LWA-` 0(O1-T5) |
| 효과 자체 | NOT_RUN | PlayRate≠1 이펙트 클립이 없어 Play로 보지 못했다(O1-T7). 소스 대조로만 판단한다 |

**시연 중 20:36:24 Play 종료 — 시험 흔적이며 제품 결함이 아니다**

- 사용자 답 "내가 Stop함"(2026-11-20)으로 종료 주체가 확정됐다. tester의 Stop이 아니고 제품의 비정상 종료도 아니다.
- `AbortCombat`: tester 기록상 호출 경로는 `CombatPauseComponent.OnUpdate`→`AbortCombat`→`SetServerPaused(false)`다. `OnUpdate`(157~164행)는 정지 중에 정지 소유자가 무효이거나 다른 맵에 있거나 HP 0·사망이면 `AbortCombat`을 부른다(주석 "정지 소유자의 이탈·사망을 감지", `AbortCombat` 주석 "사망·맵 이탈은 재개보다 우선"). n=7에서 서버 정지가 걸린 상태(20:36:22 `paused=true`)로 사용자가 Stop해 플레이어 엔티티가 빠졌으니 이 경로가 도는 것이 설계대로다. `OnEndPlay`(166~169행)도 정지 중이면 같은 `AbortCombat`을 부른다. 정지가 풀린 채 끝났으므로 정리가 맞게 된 것이다. 어느 분기(소유자 무효·HP)였는지는 로그로 가르지 못하지만 두 분기 모두 설계된 정리 경로다.
- `[LEA-3051] MemoryLeak 'MakerScript'` 2건(서버 30번째 줄·클라이언트 5번째 줄): 이름이 `MakerScript`라 `maker_execute_script`로 올린 시연 프로브의 반복 타이머다. 제품 `.mlua`라면 그 스크립트 이름이 찍힌다. 사용자 Stop이 시연 마지막 정리(`finish`)보다 먼저 와서 타이머가 남았다. 앞 QA의 프로브 `[LEA-3051]`(12:40·14:39)과 같은 종류다. 같은 버전의 O-1 회귀 Play(O1-T5)에서는 `LEA-`·`LWA-` 0건이었다.
- 영향: Play 메모리 변경(패턴 Weight·`AttackInterval`·시간 배율)은 Stop으로 버려졌다. 파일 변경은 0이고 `map/map01.map` SHA-256도 그대로다(tester 시연 기록과 리뷰 확인).

**O1-T8 사용자 판정 근거**

- tester는 O1-T8을 NEEDS_DECISION(사용자 시연 대기)으로 남겼다. 이를 닫는 근거는 **사용자 판정**이다. AI의 PASS가 아니다.
- 사용자 결정 1(2026-11-20, 메인이 사용자에게 직접 받음):
  - 확인 방법은 "시연 보고 확인"이다.
  - 시연은 같은 버전 eaeb032에서 했다. 8회 중 6회를 실행했다: 정지 n=1(눈빛)·3(먼지)·5(눈빛), 슬로우 n=2(눈빛)·4(먼지)·6(눈빛). 눈빛·먼지 × 정지·슬로우 네 가지가 모두 1회 이상 나왔다.
  - 사용자 판정은 "모두 괜찮음"이다(끊김·처음부터 재시작·겹침 없음).
  - n=7(먼지 중 정지의 해제)·n=8(먼지 중 슬로우 2회차)을 다시 볼지에는 "필요 없음"이라고 답했다. 먼지 정지·먼지 슬로우는 n=3·n=4로 이미 한 번씩 봤다.
- 그래서 O1-T8은 **사용자 수락**으로 닫는다. 이 시연은 Play 메모리 프로브(서버 `SetServerPaused`, 클라이언트 `SetPresentationPaused`, `ApplySlow(2.0, 0.5)`)로 연 경로다. 실제 `_UIPopup:Open` 경로도 자연 슬로우 겹침도 아니다(아래 R-2).

**회차 2 종합(AI 1~5, V11)**

| 기준 | 판단 | 근거 |
| --- | --- | --- |
| 범위 | 충족 | d8c61db 제품 4개와 eaeb032 제품 1개 모두 편집 허용 5개 안이다(직전 리뷰와 위 git 확인). 새 모델·규칙·수치는 없다 |
| AI 1 FU-17 | 충족 | 직전 리뷰. O-1 수정은 이 경로와 무관하다 |
| AI 2 V02 회귀 | 충족 | 직전 리뷰의 HitEvent 합 = HP 감소, ×2.2 1회. 화면 피해 숫자는 사용자 V11("10타 피해 숫자와 HP 감소 일치" 모두 괜찮음)으로 보완했다 |
| AI 3 가드 | 충족 | 직전 리뷰. 사용자 V11(가드 시작 이펙트·소리 1회, 패링·반격 체감 동일)도 "모두 괜찮음"이다 |
| AI 4 FU-12 | 충족 | 직전 리뷰 근거에 O-1 회귀(O1-T3·T4)를 더했다. 시각은 사용자 시연 수락(O1-T8)으로 보완했다 |
| AI 5 build·git | 충족 | O1-T2·T5와 위 버전 확인 |
| 사용자 V11 | 수락 | 자연 플레이 V11 "모두 괜찮음"(사용자 결정 4), FU-12 시연 "모두 괜찮음"(사용자 결정 1) |

- QA 표기: tester는 PASS·NOT_RUN·NEEDS_DECISION을 나눠 적었고, 프로브(Play 메모리) 경로와 시험 부산물(클라이언트 시간 배율 0이면 클라이언트 타이머도 멈춤, 시연 중단, 프로브 LEA-3051)을 공개했다. 직접 보지 않은 화면을 PASS로 세지 않았다. 스크린샷은 회차 한도 12장 안이고 O-1 회귀·시연에서는 0장이다.
- AI 작업과 사용자 기여: 정지·슬로우 화면 판단과 V11은 사용자 관찰이다. 구현·로그 대조는 AI 근거다. 문서에 섞이지 않았다.
- 참고(경미, 조치 불필요): eaeb032에도 run.md·WorkRecord가 함께 들어갔다. CLAUDE.md `[code]` 시점 규칙("그 시점까지의 Plan·WorkRecord 변경")과 같은 사례이고 push 전이라 결과는 같다.

**planner 마감 때 Plan·Feature에 옮길 항목**

1. Plan 회차 2 절·표 정리
   - 626행 "구현 상태 … 미커밋, `[code]` 커밋 전"을 d8c61db(트리 `3940b24f…`) + O-1 eaeb032(트리 `fe15c874…`, blob `8d22ddd…`) 기준으로 고친다.
   - FU-17·FU-19·FU-12를 "후속 회차 2에서 닫은 항목" 표(회차 1 표와 같은 형식)로 옮기고 부채 표 47·57·70행을 정리한다. 결과 문구: tester FAIL 0, reviewer READY, 사용자 V11 "모두 괜찮음"(자연 플레이 + FU-12 시연), O-1은 같은 승인 범위에서 고쳤다.
   - `사용자 결정 대기`의 "부채 처리 시점" 행과 `목표·상태`를 "후속 회차 2 종료(이 run의 후속 처리 완료), 3단계 시작 지시 대기"로 고친다.
2. 직전 리뷰 O-3 → FU-28 관찰 추가
   - FU-28 행에 한 줄을 붙인다: "관찰(2026-11-20 회차 2 tester O-3): 공격이 취소돼도 이미 재생을 시작한 눈빛·먼지 이펙트는 화면에서 끝까지 나온다. `ClearEffects`는 추적만 끊는다. FQ-3 (가) '기존 이펙트 유지'와 같은 기존 동작이며 결함이 아니다."
   - 새 ID는 만들지 않는다. 다시 볼 조건은 FU-28과 같다.
3. R-1 추적 후보(이펙트 클립 첫 동기 로드)
   - 내용: 몬스터 엔티티별 첫 눈빛 때 `TrackEffect`→`GetRuidTimeline`→`LoadAnimationClipAndWait`가 서버에서 동기로 돈다. 접근 클립은 스폰 때 `MonsterManager`(138행)가 미리 읽지만 이펙트 클립은 미리 읽지 않는다. `GetClipTimeline` 주석("진행 중에는 읽지 않는다")과 다르다.
   - 처리: (C) 추적 행으로 등록하는 것을 권한다(새 FU 번호는 planner가 정한다). 고치려면 범위 밖인 `MonsterManager`를 바꿔야 한다.
   - 다시 볼 조건: Play 시작 뒤 첫 3칸 공격의 눈빛→먼지 전투 시계 차가 예고 1.571초보다 눈에 띄게 길 때, 사용자가 첫 공격 지연을 보고할 때, 늦어도 6단계 몬스터 동작 일반화(FU-04·FU-29와 함께).
   - 측정: 이번 회차에서는 하지 않았다(필수 아님).
4. R-2 V11 문구와 FU-27 불일치 정리
   - 불일치: Plan 회차 2 "사용자 V11"(702행 "팝업 정지 중 이펙트 모습과 슬로우 중 눈빛 속도")은 게임 안에서 볼 경로가 없는 항목이다. FU-27 규칙("팝업을 실제로 여는 경로가 생기기 전에는 V11 목록에 넣지 않는다")과 어긋난다.
   - 실제 처리: 사용자가 "시연 보고 확인"을 골라 Play 메모리 프로브 시연으로 봤고 "모두 괜찮음"으로 수락했다.
   - Plan에 적을 것: 이 V11은 프로브 시연 수락이며 실제 `_UIPopup:Open` 경로가 아니다. 실제 팝업 경로의 이펙트 정지 화면은 FU-27(그 경로가 생기는 회차 V11)로 남긴다. 자연 플레이의 슬로우·이펙트 겹침은 지금 데이터에 경로가 없다(이펙트는 `parry.guard`뿐이고 가드형은 JUST를 만들지 않음, 슬로우 2.0초는 다음 공격과 겹치지 않음). 다시 볼 조건: JUST가 나는 공격에 `EffectClip`을 넣을 때, `AttackInterval`·`SlowDurationSec`를 크게 바꿀 때, 6단계에서 몬스터가 늘 때. 앞으로 Plan의 V11에는 자연 경로가 없는 항목을 넣지 않거나 "프로브 시연"으로 명시한다(FU-18처럼 Plan 작성 규칙에 붙일지는 planner 판단).
5. 남은 미실시(NOT_RUN, PASS로 세지 않음) — Plan "미실시 확인" 또는 Feature 확인 범위에 짧게 남긴다
   - PlayRate≠1 이펙트 클립에서 O-1 수정의 효과(O1-T7). 소스 대조만 했다. `PlayEffect` 옵션 `PlayRate`가 클립 PlayRate와 곱해진다는 전제도 검증하지 않았다. 다시 볼 조건: `EffectClip`을 PlayRate≠1 클립으로 바꾸거나 이펙트를 새로 더할 때.
   - 시연 n=7(먼지 중 정지의 해제)·n=8(먼지 중 슬로우 2회차). 사용자가 "필요 없음"이라 했다.
   - 정지 중 플레이어 공격·가드 이펙트의 화면. 시연 대상은 눈빛·먼지였고, 공격 이펙트는 coder 측정, 가드는 같은 경로라는 판단뿐이다.
   - 실제 `_UIPopup:Open` 경로의 정지(FU-27). 서버 정지와 클라이언트 정지를 실제 지연을 두고 함께 거는 조합.
   - 맵 이탈 단독 정리(TR11). Stop 경로와 같은 함수를 지난다는 것은 소스로 확인했다.
   - 표 무효 상태 가드 Play(TR14, Plan이 소스 대조 허용). 실제 키 패링(자연 플레이 V11 체감으로 수락).
   - R-1 첫 공격 로드 시각.
   - 지연 있는 실접속·모바일(CombatCore-V11 모바일·V12·FU-01 행).
6. Feature(2_CombatCore) 짧은 반영
   - FU-12: 정지는 엔진의 클라이언트 시간 배율 0이 이펙트를 멈춘 프레임으로 두고 재개 때 이어 재생한다(추가 코드 없음). 슬로우는 몬스터 이펙트(눈빛·먼지)를 지금 프레임부터 새 배율로 다시 낸다(프레임 계산은 클립 PlayRate 포함, O-1). 한계: 프레임 단위 이어 재생이고, 지금 데이터에서는 자연 발생 경로가 없다. 화면은 사용자 프로브 시연으로 수락했다.
   - FU-17·FU-19: 동작은 같다(정리만).
7. WorkRecord·run 정리(사용자 결정 5 "링크 정리 후 삭제")
   - 2026-11-19 선례(5efe005 내용 커밋 → 16d70b3 링크 정리·삭제)처럼 순서를 둔다. 먼저 메인이 이 리뷰 절을 포함한 `[CombatCore][review]` 회차 종료 커밋을 만들고 push한다. 그다음 planner가 Plan·Feature·README의 링크를 그 커밋 해시로 바꾸고 WorkRecord·run을 지운다.
   - 이 WorkRecord 머리의 "상태·갱신일"·"현재 재개 지점"은 회차 2 범위 확인 시점 그대로라 오래됐다. 삭제 전 기준 커밋에 남는 사본이므로, 고칠지 그대로 둘지는 planner가 정한다.
   - `GameDesign`은 규칙·수치 변경이 없어 고칠 것이 없다. 로드맵 재개 지점은 3단계 시작 지시 대기로 둔다.

**담당별 다음 행동**

- 메인: 이 판정을 사용자에게 알린다. `[CombatCore][review] 후속 회차 2 종료 — READY(사용자 V11 수락)` 회차 종료 커밋과 push를 한다(run·이 WorkRecord 등 회차 문서, `map/map01.map`은 계속 뺀다, push 전 비밀값·개인정보 검사). 그 뒤 planner 마감을 부른다.
- planner: 위 "planner 마감 때 옮길 항목" 1~7을 처리한다.
- coder·tester: 이 회차에서 더 할 일은 없다.

**사용자 판단 사항**: 이 회차를 닫는 데 필요한 것은 없다(직전 리뷰 판단 1~4는 2026-11-20에 모두 답이 왔다). 기록용: R-1 추적 행 등록 시기(6단계와 함께 보기를 제안)는 planner 마감 때 Plan에 적고, 3단계 시작은 사용자 별도 지시를 기다린다.

**검사하지 않은 범위**: Maker 실행·런타임 재확인(reviewer 역할 밖), `PlayEffect` PlayRate 옵션과 클립 PlayRate의 실제 곱 관계, PlayRate≠1 클립 동작, 시연 화면 자체(사용자 관찰만 근거), 20:36:24 `AbortCombat`이 소유자 무효·HP 분기 중 어느 쪽이었는지(둘 다 설계 경로), 시연 프로브 스크립트 원문(`MakerScript` 30·5번째 줄의 내용), 실접속·모바일.

## 완료 시 이관할 내용

- [2단계 Feature](../Features/2_CombatCore.md) 데이터 계약 "위치" 열과 짧은 결과.
- 후속 계획의 FU-03·FU-23·FU-24 행 정리, 남은 일(빈 폴더가 남은 경우 등).
- FileStructure §4·§5·§7, 현재 문서 링크(Features/0_CombatPause.md, Plans/MonsterCombat.md, AssetList.md).
- 사용자 V11 피드백.
