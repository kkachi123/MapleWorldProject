# CombatCore — 2단계 후속 처리(FU) 회차 기록 (2단계 원본 WorkRecord는 기준 커밋 5efe005)

- 구분: 이 파일은 2026-11-19 시작한 2단계 후속 처리 회차의 새 기록이다. 같은 이름의 2단계 원본 기록은 [기준 커밋 5efe005의 CombatCoreWorkRecord](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md)에만 있으며, 여기에 옮기거나 고쳐 쓰지 않는다.
- 연결 Plan: [2단계 후속 계획 "후속 처리 계획(2026-11-19)"](../Plans/CombatCore.md#후속-처리-계획2026-11-19)
- run: `.pipeline/20261119-combatcore-followup/run.md`
- 상태·갱신일: 후속 회차 1 coder 완료(절차 8~11: 2차 확인·FU-03·원장·통합 Play, 일부 회귀 NOT_RUN), 메인 `[code]` 커밋 후 tester 대기 / 2026-11-19 coder
- 삭제 조건: 후속 회차 1·2가 끝나고(사용자 V11 포함) 결과를 [2단계 Feature](../Features/2_CombatCore.md)와 후속 계획 표에 반영하고 링크를 정리한 뒤.

## 현재 재개 지점

- 마지막 상태: planner가 FQ-1~7 답을 Plan에 반영하고 후속 회차 1의 범위·절차·완료 기준·중단 조건을 확정했다(2026-11-19).
- 다음 행동: 메인이 git 작업 트리를 확인하고 coder에게 후속 회차 1을 넘긴다. coder는 사전 확인 → 1차 이동(시험 2쌍) 뒤 `WAITING_USER`로 돌려준다.
- 차단 조건: 사용자 Maker 동기화 완료 알림(1차·2차). 그 전에는 이동 확인을 진행하지 않는다.

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

## QA 기록

미기록(tester가 작성).

## 리뷰 기록

미기록(reviewer가 작성).

## 완료 시 이관할 내용

- [2단계 Feature](../Features/2_CombatCore.md) 데이터 계약 "위치" 열과 짧은 결과.
- 후속 계획의 FU-03·FU-23·FU-24 행 정리, 남은 일(빈 폴더가 남은 경우 등).
- FileStructure §4·§5·§7, 현재 문서 링크(Features/0_CombatPause.md, Plans/MonsterCombat.md, AssetList.md).
- 사용자 V11 피드백.
