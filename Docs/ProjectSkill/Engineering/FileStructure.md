# 파일 구조 기준 (FileStructure)

> 작성: 2026-11-05(planner). 사용자가 메인의 파일 구조 정리 추천안을 승인했다(run "2026-11-05 회차 C 질문 사용자 답변" 절). 이 문서는 기준만 정한다. **파일 이동은 이 문서로 하지 않는다.**
> 순서: (1) 이 기준 문서 작성 → (2) 회차 C([Plan §21](Plans/2_CombatCore.md)) coder가 새 파일을 기준 위치에 만든다 → (3) 기존 파일 이동은 회차 C가 끝난 뒤 별도 회차(사용자 시작 지시 필요).
> 근거: 2026-11-05 git ls-files로 본 RootDesk·ui·map 실제 파일, msw-general platform.md(§2 파일 위치, §3 .mlua·.codeblock 짝, .directory Refresh 규칙)·workspace.md(작업 공간 구조, 변경 뒤 refresh, Play 중 편집 금지).

## 1. 범위

| 대상 | 이 기준 적용 |
| --- | --- |
| RootDesk/MyDesk/ | 적용(아래 §3) |
| ui/·map/ | 적용(평면 구조 유지, §3) |
| 루트의 Portfolio·Resource_Root, Docs/UIimg·Docs/web | 위치 제안(§6) |
| Global/·Environment/ | 제외. Maker·엔진 관리(새 파일 금지, Global 기존 파일은 제자리 빌더 수정만) |
| 도구 폴더 .agents·.claude·.codex·.github | 제외 |
| 그 밖의 도구·실행 기록 .pipeline·.handoff-backups·.mswai·.vscode | 제외 |

## 2. MSW 제약 (이동·생성 때 지킬 것)

- Maker는 RootDesk/ 아래 새 파일만 등록한다. Global/에 새 파일을 만들지 않는다.
- 스크립트는 .mlua + .codeblock 짝으로만 동작한다. .codeblock은 Maker Refresh가 만들고 Id·Name을 스크립트 이름에 맞춘다. 에이전트는 .codeblock을 만들거나 고치지 않는다.
- .directory는 실제 폴더를 만든 뒤 Refresh가 만드는 산출물이다. 폴더만 만들고 메타데이터는 Refresh에 맡긴다.
- 파일을 만들거나 고치거나 지운 뒤에는 항상 refresh. Play 중에는 편집·refresh를 하지 않는다(Stop 먼저).
- 참조는 경로가 아니라 이름·키로 이어진다(스크립트 `script.이름`, 모델 `model://키`, DataSet `_DataService:GetTable(이름)`). 그래서 이동은 원칙상 참조를 깨지 않는다. 다만 Maker가 이동을 "같은 항목"으로 인식하는지는 참조 문서에 절차가 없다. 이동 회차에서 시험 이동 1건으로 먼저 확인한다(§5).
- .model·.ui는 셸로 읽거나 복사하지 않는다(빌더 전용 훅). 파일 단위 이동·삭제는 `node -e "require('fs')..."` 후 refresh로 한다.

## 3. 폴더별 용도와 이름 규칙

이름 규칙:
- 폴더·파일 이름은 영어 PascalCase다. 한글 파일 이름을 새로 만들지 않는다(화면 표시 이름은 DataSet name 열·모델 값에 둔다).
- 스크립트 파일 이름 = `script` 이름. DataSet 이름은 `{대상}Data`(예: MonsterStatData), 로더는 `{대상}Catalog`.
- 모델 파일 이름 = 모델 Name(PascalCase), 모델 키(EntryKey id)는 같은 말의 소문자(예: Mushmom.model / model://mushmom).
- `@` 접두사는 **기능 폴더 안의 부속 하위 폴더**에만 쓴다(그 기능이 직접 쓰는 상태 스크립트 등). 최상위 폴더나 잡동사니 보관에 쓰지 않는다. 지금 허용: `@StateControl`(StateType·상태 제어 스크립트와 .stateset).

RootDesk/MyDesk/ 목표 구조:

| 폴더 | 용도 | 예 |
| --- | --- | --- |
| Catalog/ | DataSet을 읽고 검증하는 @Logic 로더 | CombatRuleCatalog, PlayerSkillEffectTable, PlayerBaseStatCatalog |
| DataSet/ | 게임 정적 데이터 .userdataset + 같은 이름 .csv | MonsterStatData.userdataset·.csv |
| Combat/ | 맵 전투 공통 컴포넌트(정지·칸 표시 등) | CombatPauseComponent, AttackAreaMarkComponent |
| Managers/ | 맵 엔티티에 붙는 관리 컴포넌트 | MonsterManager |
| Monster/ | 몬스터 공통 컴포넌트 | MonsterHealthComponent, MonsterAttackMotion |
| Monster/@StateControl/ | 몬스터 상태 제어·StateType | MonsterStateControl, Monster_Attack |
| Monster/{MonsterName}/ | 한 몬스터 전용 스크립트(몬스터 종류별 폴더) | (예) Monster/Mushmom/ |
| Player/ | 플레이어 컴포넌트 | PlayerCombatComponent |
| Player/@StateControl/ | 플레이어 상태 제어·StateType·.stateset | PlayerStateControl, PlayerStateSet.stateset |
| UI/ | UI @Logic·컨트롤러 전부 | CombatInputController, UIPopup, UIToast |
| Models/{Category}/ | .model. 분류는 Monsters·MapObjects·Effects 등 | Models/Monsters/Mushmom.model |
| Dev/ | 개발 전용 도구(출시 전 제거 대상). 지금은 없음 | — |

ui/: .ui 파일 이름 = UIGroup(루트) 이름, 평면 유지. map/: 지금 map01 하나, 평면 유지.

몬스터 종류별 폴더 기준: 한 몬스터만 쓰는 스크립트는 `Monster/{MonsterName}/`에 둔다. 여러 몬스터가 같이 쓰는 동작 유형(6단계 몬스터 일반화, 예: 점프형)은 그 일반화 계획에서 `Monster/Motions/{TypeName}/` 같은 폴더를 정한다(지금 확정하지 않음). 지금 `Monster/OrangeMushroom/OrangeMushroomAttack`은 실제로 머쉬맘의 점프 동작이며, 이름·폴더 정리는 6단계 부채다([Plan §21](Plans/2_CombatCore.md)).

## 4. 새 파일을 어디에 둘지

1. Global/·Environment/에는 두지 않는다.
2. 파일 종류로 먼저 가른다: .model → Models/{Category}/, .userdataset·.csv → DataSet/, .ui → ui/, .map → map/.
3. .mlua는 역할로 가른다: DataSet 로더 → Catalog/, UI → UI/, 개발 도구 → Dev/, 상태 제어 → 그 대상의 @StateControl/, 한 몬스터 전용 → Monster/{MonsterName}/, 그 밖에는 소유 대상 폴더(Player/·Monster/·Combat/·Managers/).
4. 맞는 폴더가 없으면 새 최상위 폴더를 만들기 전에 planner Plan에 이유와 이름을 적고 메인 확인을 받는다.

회차 C에서 생기는 새 파일: `RootDesk/MyDesk/Models/Monsters/Mushmom.model` 하나다(다른 새 제품 파일 없음). 에셋 목록은 문서 `Docs/ProjectSkill/Engineering/AssetList.md`다.

## 5. 기존 파일 → 새 위치 대응표 (이동은 회차 C 뒤 별도 회차)

| 기존 | 새 위치 | 비고 |
| --- | --- | --- |
| @Assist/DataSet/AttackSkillData·CombatRuleData·MonsterAttackPatternData·MonsterData·MonsterStatData·PlayerBaseStatData(.userdataset·.csv) | DataSet/ | 짝으로 함께 |
| @Assist/DataSet/AssistModel(.userdataset·.csv) | 없음 | 회차 C에서 삭제 |
| @Assist/RangeGizmo/AttackRangeGizmo.model | 없음 | 회차 C에서 삭제 |
| Player/@Assist/AttackRange/AttackRangeGizmo·AttackRangeTuner | 없음 | 회차 C에서 삭제 |
| Combat/CombatRuleCatalog.mlua | Catalog/ | |
| Player/@Assist/Skill/PlayerSkillEffectTable.mlua | Catalog/ | 이름 유지(스킬 교체 단계에서 재검토 가능) |
| Player/@Assist/Stat/PlayerBaseStatCatalog.mlua | Catalog/ | |
| UIPopup.mlua·UIToast.mlua(MyDesk 바로 아래) | UI/ | |
| Models/Monsters/주황버섯.model | Models/Monsters/OrangeMushroom.model | 키 orangemushroom은 회차 C에서 먼저 정리. 모델 Name도 OrangeMushroom으로 |
| Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 유지 | 6단계 몬스터 일반화 때 이름·폴더 결정 |
| 빈 폴더 @Assist·Player/@Assist·Models/Effects | @Assist 계열은 제거, Effects는 유지 | 폴더 메타데이터 정리 방식은 이동 회차에서 확인 |
| 그 밖(Combat/·Managers/·Monster/·Player/·UI/·@StateControl, ui/·map/) | 유지 | |

## 6. 루트·Docs 기타 위치 제안 (이동은 같은 별도 회차, 사용자 확인)

| 현재 | 제안 | 이유·주의 |
| --- | --- | --- |
| Portfolio/Portfolio.md | Docs/Portfolio/Portfolio.md | 문서를 Docs 아래로 모은다. Features/README.md 링크 갱신 필요 |
| Resource_Root/레이징 블로우_elements.json | Docs/AssetSources/RagingBlow_elements.json | 기본 공격 이펙트 리소스 팩 요소 기록(AttackSkillData ruid 5308ef85…). 영어 이름, 에셋 목록에서 링크 |
| Docs/UIimg/*.png | Docs/AssetSources/UI/ | UI 원본 이미지. 업로드된 RUID는 경로와 무관 |
| Docs/web/DecisionSheet.html | 유지 | msw-planning 스킬이 이 경로를 고정으로 쓴다(decision-sheet.md) |

## 7. 이동할 때의 위험과 확인

| 위험 | 확인·대응 |
| --- | --- |
| Maker 재인식: 이동한 스크립트가 새 항목으로 잡히거나 옛 .codeblock이 남아 이름이 겹침 | Stop 상태에서 위험이 낮은 1건(예: UIToast .mlua+.codeblock 짝)을 먼저 옮겨 refresh → 빌드 로그 오류 0, 같은 이름 스크립트 1개, .codeblock Id 유지, Play [VRF]를 본다. 실패하면 이동을 멈추고 Maker UI 이동(사용자)으로 돌린다 |
| 모델·DataSet 재인식 | 모델 EntryKey와 DataSet 이름이 그대로인지(ModelBuilder.read, GetTable), 스폰·로드 [VRF] |
| 빈 폴더 .directory 잔존 | refresh 뒤 결과 기록. .directory를 손으로 고치지 않는다 |
| `.maplestory-skill-maker-ledger.md` 경로 | 지금 `RootDesk/MyDesk/Models/Monsters/주황버섯.model` 1곳을 가리킨다. 이동 회차에서 새 경로로 갱신(그 스킬 원장 규칙대로) |
| 문서 링크 | 현재 기준 문서(이 문서, 진행 중 Plan 대상 표, GameDesign·로드맵, Features/README)만 갱신. 지난 회차 기록(Plan 이전 절·WorkRecord·run)은 고쳐 쓰지 않는다 |
| 회차 A·B·C 회귀 | 이동 뒤 한 통합 회차: DataSet 로드 값과 실패 동작(회차 B), die 1회 정지(F12)·Pos2 JUST·PARRY(F13), 팝업 정지·토스트(UIPopup·UIToast), 머쉬맘 스폰·피격 규칙(회차 C) |
| 범위 밖 재저장 | refresh가 다른 파일을 다시 저장하면 기록하고 이동 커밋에 섞지 않는다 |
