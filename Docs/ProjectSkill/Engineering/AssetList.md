# 에셋 목록 (AssetList, 잠정)

> 작성: 2026-11-05(planner, 회차 C [Plan §21](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)). [로드맵 §1 에셋 목록](DevelopmentRoadmap.md#1-개발-기준)의 제안 위치에 잠정으로 만들었다. 최종 위치는 [8단계 시작 전 결정 사항](DevelopmentRoadmap.md#8-콘텐츠-데이터-제작)에서 정한다.
> 목적: 임시·대체 에셋을 추적한다. 9단계(출시 검증) 전에 출시 범위의 임시 에셋은 0이어야 한다. RUID는 msw-search 래퍼 응답에서 옮겼고 추측한 값이 없다.
> 아직 목록에 올리지 않은 기존 에셋(플레이어 기본 공격 이펙트, UI 이미지, 그로기 별 파티클 등)은 해당 시스템을 다룰 때 추가한다.

## 사용 중

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 1번 마을 최종보스 머쉬맘 모델(model://mushmom, 회차 C) | 리소스 팩 mob/6130101.img(머쉬맘, Mushmom) | stand → 86015373d23b4b05bb8fcc6086354652, move → c745828d831b42739b9a58c07f334864, jump → 5ecbcc4002a5491aafd7e1d3191c6ddc, hit(팩 hit1) → 90fee9416184420a9796a679751d1ec5, die(팩 die1) → ec90f0b64a814c4980de89f496d360ec | **임시**(2026-11-05 사용자 지시, 연결은 2026-11-05 사용자 확인) | 회차 C 사용자 V11 수락과 6단계 헤네시스 견본 아트 확정 때 사용자가 확정 |

연결(stand·move·jump·hit1·die1, move는 기본값 유지)은 2026-11-05 사용자가 확인했다(Plan §21).

### 회차 D 에셋 ([Plan §22](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md), 2026-11-16 사용자 V11 수락으로 "사용 예정"에서 옮김)

회차 D·D2 사용자 V11 수락(2026-11-16, 위치·크기·시점·음량 기본안 포함)으로 "사용 중"이 됐다. 그래도 아래는 모두 **임시**이며, 6단계 헤네시스 견본 아트·사운드 확정 때 사용자가 확정한다. 패턴 표는 `RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv`, 소리 표는 `RootDesk/MyDesk/DataSet/MonsterSoundData.csv`다.

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 머쉬맘 2칸 공격 모션 | mob/6130101.img | attack1 → 90c5456e2a8a45478df02500797a9afd(ActionSheet 키 `attack1`, 재생 0.7배) | 임시. 회차 D V11 수락(2026-11-16) | 6단계 견본 아트 확정 |
| 머쉬맘 3칸 공격 모션 | mob/6130101.img | skill1 → b9345875a8134c7c9a1b6aed8551d808(ActionSheet 키 `skill1`, 재생 0.7배) | 임시. 회차 D V11 수락 | 위와 같음 |
| 머쉬맘 3칸 공격 이펙트 | mob/6130101.img attack1/info/effect | 05113e9dc86448cb8581731824106d75(패턴 표 EffectClip). 두 단계 분할: 눈빛 프레임 0~6은 머쉬맘 위치·예고 시작 때, 먼지 프레임 8~끝은 착지 지점(Pos2)·판정 때, 1배 | 임시. 위치·크기는 회차 D V11 수락 | 위와 같음 |
| 2칸 공격 효과음 | mob/6130101.img _audio/Attack1 | f135fc39ffe94be18ef9c0f82d3669c5(패턴 표 AttackSound) | 임시. 회차 D V11 수락 | 위와 같음 |
| 3칸 공격 효과음 | mob/6130101.img _audio/Skill1 | 5da7bb48092947f395e9f76f601323ca(패턴 표 AttackSound) | 임시. 회차 D V11 수락 | 위와 같음 |
| 머쉬맘 피격음 | mob/6130101.img _audio/Damage | c611ae50c5d84814a6d2ccfad8a472c5(MonsterSoundData DamagedSound) | 임시. 시점 기본안 회차 D V11 수락 | 위와 같음 |
| 플레이어 피격음(머쉬맘 공격) | mob/6130101.img _audio/CharDam1 | 7c8e5f1ef0b549c59aec820909458d4f(MonsterSoundData HitPlayerSound) | 임시. 시점 기본안 회차 D V11 수락 | 위와 같음 |
| 머쉬맘 사망음 | mob/6130101.img _audio/Die | d48ec1cc57a247028f390041fc89c97f(MonsterSoundData DieSound) | 임시. 시점 기본안 회차 D V11 수락 | 위와 같음 |
| 1칸 공격 효과음(player 점프음, 2026-11-16 사용자 D-Q13, [Plan §22.17.4](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)) | **엔진 `MaplePreferencesLogic.JumpSound` 기본값**(`Environment/NativeScripts/Logic/MaplePreferencesLogic.d.mlua`). 프로젝트에서 덮어쓴 곳 없음(coder Grep), Play 중 서버·클라이언트 값 같음. 머쉬맘 팩 밖 | a49c4b3963e148f09b2eb9de98d42ef4(effect, 0.13초) → 패턴 표 parry.any·special.random AttackSound(5ce65d6) | 임시. 사용자 청취 확인(2026-11-16 "점프음 확인 완료") | 6단계 견본 아트·사운드 확정 때 다시 본다 |

~~회차 D 구현이 끝나면 이 표의 행을 "사용 중"으로 옮긴다.~~ → 2026-11-16 옮겼다. 고르지 않은 1칸 점프음 후보 3개는 아래 "후보"에 있다.

### 회차 E 에셋 ([Plan §24](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md), 2026-11-19 사용자 V11 수락으로 "사용 예정"에서 옮김)

2026-11-06 사용자 선택, 2026-11-16 구현(coder 3e29a35), 2026-11-19 사용자 V11 수락("다른 건 다 좋음", Maker 26.11, 바꿀 점 없음)으로 "사용 중"이 됐다. 버튼은 `ui/CombatScreen.ui`, 가드 연출 표는 `RootDesk/MyDesk/DataSet/PlayerActionFxData.csv`다. 출시용 확정 여부(임시인지)는 정하지 않았다. UI 아트 스타일이 미정(GameDesign §8 "UI 상세")이므로 그때 사용자가 정한다.

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 조작 버튼 4개 배경(BtnAttack·BtnGuard·BtnBack·BtnForward) | simplefantasy(메이플슬래시, msw-ui-kit) Slot_03/Btn_Attack | e314c09b9b39486bb1c68d018b2abded(기록 120×120 Sliced, 140×140으로 키움, 색 #FFFFFF). 눌림은 ColorTint 0.78 유지 | 회차 E V11 수락(2026-11-19). 출시용 확정은 미정 | UI 아트 스타일 결정 때 사용자(9단계 전 임시 0 기준) |
| ↑ 공격 버튼 아이콘(자식 `BtnAttack/Icon`) | simplefantasy Icon_Sword(틴트) | 3119d2807ea7466e8e9056d0590a35cc(기록 20×25, 60×60 상자·비율 유지, 색 #FFFFFF) | 위와 같음. GameDesign §7.4의 액티브 스킬 아이콘 연결은 Plan §24.12 | 위와 같음 |
| ↓ 가드 버튼 아이콘(`BtnGuard/Icon`) | simplefantasy Icon_Arrow_Down(틴트, core 팔레트 전용) | a714a1eaa4aa46098c0c265110ee91c0(기록 60×60, 색 #FFFFFF) | 위와 같음 | 위와 같음 |
| ← 뒤 버튼 아이콘(`BtnBack/Icon`) | simplefantasy Icon_Arrow_L(틴트) | 002ca90cd5794836b1e44da160de287a(기록 24×36, 색 #FFFFFF) | 위와 같음 | 위와 같음 |
| → 앞 버튼 아이콘(`BtnForward/Icon`) | simplefantasy Icon_Arrow_R(틴트) | 740aba24726c4c6580cf054b0e1e1fd5(기록 24×36, 색 #FFFFFF) | 위와 같음 | 위와 같음 |
| 버튼 입력 Highlight(BtnBack·BtnGuard·BtnForward, 회차 E 전부터 사용, 바꾸지 않음) | 출처 문서 없음(테마 밖) | 2860136c06ab075439721c027de365af(Sliced, 노란색) | V11에서 새 버튼과 함께 수락. 출시용 확정은 미정 | 위와 같음 |
| 가드 시작 이펙트(1회) | 로얄 가드 skill/5100.img/skill/51001006 effect | 318a46627eca4ae5b9c5d1fb16244e3c(animationclip, skill, 124×147, 13프레임) → PlayerActionFxData `guard` 행 EffectClip(E-Q1 답, Plan §24.10) | 회차 E V11 수락(크기·위치·방향, 첫 프레임 흰 세로선 O-3 포함). 출시용 확정은 미정 | 9단계 전 사용자 확정(임시 0 기준) |
| 가드 시작 효과음(1회) | 로얄 가드 skill/5100.img/skill/51001006 _audio/Use | 605da1fc42f34ef4a1468387004a6223(effect=소리, skill, 1.152초) → 같은 행 EffectSound | 회차 E V11 수락(소리 크기). 출시용 확정은 미정 | 위와 같음 |

UI RUID 5개(배경·아이콘 4종)는 msw-search 래퍼 색인에 없다(2026-11-16 get 404). msw-ui-kit simplefantasy 데이터로 골랐고, 2026-11-16 coder·QA15 Play와 2026-11-19 사용자 V11에서 화면에 보이는 것을 확인했다.

~~회차 E 구현이 끝나면 이 표의 행을 "사용 중"으로 옮기고, 아래 후보의 "회차 E가 바꿀 현재 조작 버튼 이미지" 행은 교체 기록으로 정리한다.~~ → 2026-11-19 옮겼고, 교체된 버튼 이미지 4개는 아래 "교체됨"에 적었다.

## 교체됨 (쓰지 않음, 기록만)

| 용도(교체 전) | 교체 | 이전 RUID | 비고 |
| --- | --- | --- | --- |
| 조작 버튼 4개 이미지(ui/CombatScreen.ui, 회차 E 전) | 회차 E coder 3e29a35(2026-11-16)에서 위 simplefantasy 배경 e314c09b…와 Icon 자식으로 바꿈. 2026-11-19 사용자 V11 수락 | BtnAttack fa75318d112040f9a941da89ad5d2e53, BtnBack b5c63f01645645c095611f64b34078df, BtnGuard 9eff8b12dcde45ca989e9cd5a95e441c, BtnForward 83feab30f7744c629ecc1344e1c4e49b | 원본이 Docs/UIimg의 free-icon 이미지(sword·defence·left/right arrow)라는 것은 추정이다(RUID와 파일 대응 문서 없음). 버튼 엔티티 UUID·크기·위치·ButtonComponent는 바꾸지 않았다 |
| 가드 모션 sit(PlayerStateControl GUARD 시트) | 회차 E에서 alert로 바꿈(사용자 Q4 a, V11 수락) | 아바타 기본 동작이라 RUID 없음 | 기록만 |

## 보관 (지금 스폰하지 않음)

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 일반 몬스터 주황버섯 모델(model://orangemushroom, 파일 `RootDesk/MyDesk/Models/Monsters/OrangeMushroom.model`·Name OrangeMushroom, 회차 C2 2026-11-08 수락. 회차 C 전에는 model://castleenemy로 머쉬맘 대신 쓰임) | 주황버섯 클립(팩은 미확인. "주황버섯" 팩 검색 결과 mob/9010026.img·mob/1210102.img·mob/2300102.img의 RUID와 다름) | stand → 96e955c1bf27415e84f96deea200a8f1(64×58), move → 6ad988b3ef6d4ceab3a504d300755a5b, jump → 94bbe2a7eb9c4f9caa10dd9de44ee860, hit → aec9504d5dc24aceb5646b79d30abad4, die → 65a2bfb039614f2e9e4ccc354340153d | 임시(일반 몬스터용 보관) | 6단계에서 주황버섯 공격 구성을 사용자가 정할 때 자원도 확정 |

## 후보 (쓰지 않음, 기록만)

| 출처 | 내용 |
| --- | --- |
| mob/6130101.img(머쉬맘) 나머지 | attack1·skill1·attack1 이펙트·효과음 5종은 2026-11-05 사용자 지시로 "사용 예정"(회차 D)으로 옮겼고, 2026-11-16 회차 D V11 수락으로 "사용 중"(회차 D 에셋)이 됐다 |
| 1칸 공격 점프음 후보(2026-11-10 D-Q10, 2026-11-16 D-Q13으로 쓰지 않음, [Plan §22.17.4](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)) | 머쉬맘 팩 밖, 원본 이름 없음(2026-11-10 msw-search 래퍼 `getResourcesBatch` 확인). 35ee15e50b17410093e768c33f7f76d6(effect, mob, 0.287초, 1b41f29~f78bab5 동안 기본값으로 들어 있었음), 64c83d144b5d46ffa6d460ca61a66f1d(effect, etc, 0.862초), 09df85566b984d72b97c7aa9860c4b18(effect, etc, 1.254초). 사용자가 player 점프음(a49c4b39…)을 골라 셋 모두 쓰지 않는다 |
| 좀비 머쉬맘 mob/6300005.img·mob/2400572.img, 블루 머쉬맘 mob/8645261.img·mob/8220007.img | 다른 보스 후보로만 기록 |
| 주황버섯 팩 mob/1210102.img | stand a95cfed2c8fe4d2cb64cbb62db051f92, move 8257566e41aa4234929e81c6c2dab2e4, jump 6df12df0c9ce4caea61385606a4d40d3, hit1 5ebbdaf503964f3e87de155d16650805, die1 dddbe2f162184ec89add7440da56eb75 |
| 회차 E 조작 버튼 테마 simplefantasy(메이플슬래시, msw-ui-kit)에서 고르지 않은 부품, [Plan §24](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md) | 2026-11-06 사용자 선택으로 배경 e314c09b…·Icon_Sword·Icon_Arrow_Down·Icon_Arrow_L·Icon_Arrow_R는 위 "회차 E 에셋"(사용 중, 2026-11-19 V11 수락)으로 옮겼다. 남은 후보: 눌림 스프라이트 4eed2985436c4007890c3314c4d42dc0(SpriteSwap 안, 고르지 않음), Icon_Arrow_Up 21a4739b4d654e51810c638f273d9c54(아이콘 안 1, 고르지 않음), ↓ 대안 Icon_Triangle_Down 0c2db2ad2c694210ba492d0ab060b5e7(틴트, 기록 20×20). 사용자가 V11에서 ↓ Icon_Arrow_Down을 수락해 ↓ 대안은 묻지 않았다. 화면 적합성 미확인 |
| ~~회차 E가 바꿀 현재 조작 버튼 이미지~~ | → 2026-11-19 위 "교체됨"으로 옮겼다 |
| 회차 E 가드 이펙트·소리 후보(스킬 팩, 2026-11-06 msw-search 재확인) | 로얄 가드 skill/5100.img/skill/51001006의 effect 318a4662…·소리 605da1fc…는 2026-11-06 사용자 선택으로 "사용 예정 (회차 E)"로 옮겼고 2026-11-19 V11 수락으로 위 "회차 E 에셋"(사용 중)이 됐다. 남은 후보(고르지 않음): 로얄 가드 강화 skill/40000.img/skill/400004230: effect a6c32468ecc14665baf9c056cfabae0c(138×156, 8프레임), effect_ple pre 0f93a8d6560547ddab87b8a0eb387e19·loop 12c03f6ac9374b5a91d993f09384c113·end f75c5a210fd24430b9e4a1122b6f82c8, 소리 6416b7d7c92148bfa05835e6b7aee9b0. 파워 가드 skill/800033.img/skill/80003317: effect af4e6abe766e4970a0e90aca58c6cc1c(64×85, 12프레임), effect0 a15d331295524094a9b1096df300022c, affected 1838b57cb0314900bc00b690580f8f36. 모습·크기 미확인 |
