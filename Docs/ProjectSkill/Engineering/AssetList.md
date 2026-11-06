# 에셋 목록 (AssetList, 잠정)

> 작성: 2026-11-05(planner, 회차 C [Plan §21](Plans/2_CombatCore.md)). [로드맵 §1 에셋 목록](DevelopmentRoadmap.md#1-개발-기준)의 제안 위치에 잠정으로 만들었다. 최종 위치는 [8단계 시작 전 결정 사항](DevelopmentRoadmap.md#8-콘텐츠-데이터-제작)에서 정한다.
> 목적: 임시·대체 에셋을 추적한다. 9단계(출시 검증) 전에 출시 범위의 임시 에셋은 0이어야 한다. RUID는 msw-search 래퍼 응답에서 옮겼고 추측한 값이 없다.
> 아직 목록에 올리지 않은 기존 에셋(플레이어 기본 공격 이펙트, UI 이미지, 그로기 별 파티클 등)은 해당 시스템을 다룰 때 추가한다.

## 사용 중

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 1번 마을 최종보스 머쉬맘 모델(model://mushmom, 회차 C) | 리소스 팩 mob/6130101.img(머쉬맘, Mushmom) | stand → 86015373d23b4b05bb8fcc6086354652, move → c745828d831b42739b9a58c07f334864, jump → 5ecbcc4002a5491aafd7e1d3191c6ddc, hit(팩 hit1) → 90fee9416184420a9796a679751d1ec5, die(팩 die1) → ec90f0b64a814c4980de89f496d360ec | **임시**(2026-11-05 사용자 지시, 연결은 2026-11-05 사용자 확인) | 회차 C 사용자 V11 수락과 6단계 헤네시스 견본 아트 확정 때 사용자가 확정 |

연결(stand·move·jump·hit1·die1, move는 기본값 유지)은 2026-11-05 사용자가 확인했다(Plan §21).

## 사용 예정 (회차 D, Plan §22, 사용자 시작 지시 뒤. 회차 C 사용자 V11 수락은 2026-11-06 충족)

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 머쉬맘 2칸 공격 모션 | mob/6130101.img | attack1 → 90c5456e2a8a45478df02500797a9afd(ActionSheet 키 `attack1`) | 임시 | 회차 D 사용자 V11 수락과 6단계 견본 아트 확정 |
| 머쉬맘 3칸 공격 모션 | mob/6130101.img | skill1 → b9345875a8134c7c9a1b6aed8551d808(ActionSheet 키 `skill1`) | 임시 | 위와 같음 |
| 머쉬맘 3칸 공격 이펙트 | mob/6130101.img attack1/info/effect | 05113e9dc86448cb8581731824106d75(패턴 표 EffectClip) | 임시. 위치·크기는 기본안(사용자 V11 확인) | 위와 같음 |
| 2칸 공격 효과음 | mob/6130101.img _audio/Attack1 | f135fc39ffe94be18ef9c0f82d3669c5(패턴 표 AttackSound) | 임시 | 위와 같음 |
| 3칸 공격 효과음 | mob/6130101.img _audio/Skill1 | 5da7bb48092947f395e9f76f601323ca(패턴 표 AttackSound) | 임시 | 위와 같음 |
| 머쉬맘 피격음 | mob/6130101.img _audio/Damage | c611ae50c5d84814a6d2ccfad8a472c5(MonsterSoundData DamagedSound) | 임시. 시점은 기본안(사용자 V11 확인) | 위와 같음 |
| 플레이어 피격음(머쉬맘 공격) | mob/6130101.img _audio/CharDam1 | 7c8e5f1ef0b549c59aec820909458d4f(MonsterSoundData HitPlayerSound) | 임시. 시점은 기본안(사용자 V11 확인) | 위와 같음 |
| 머쉬맘 사망음 | mob/6130101.img _audio/Die | d48ec1cc57a247028f390041fc89c97f(MonsterSoundData DieSound) | 임시. 시점은 기본안(사용자 V11 확인) | 위와 같음 |

회차 D 구현이 끝나면 이 표의 행을 "사용 중"으로 옮긴다.

## 보관 (지금 스폰하지 않음)

| 용도 | 출처 | 키 → RUID | 임시 여부 | 확정 조건 |
| --- | --- | --- | --- | --- |
| 일반 몬스터 주황버섯 모델(model://orangemushroom, 회차 C 전에는 model://castleenemy로 머쉬맘 대신 쓰임) | 주황버섯 클립(팩은 미확인. "주황버섯" 팩 검색 결과 mob/9010026.img·mob/1210102.img·mob/2300102.img의 RUID와 다름) | stand → 96e955c1bf27415e84f96deea200a8f1(64×58), move → 6ad988b3ef6d4ceab3a504d300755a5b, jump → 94bbe2a7eb9c4f9caa10dd9de44ee860, hit → aec9504d5dc24aceb5646b79d30abad4, die → 65a2bfb039614f2e9e4ccc354340153d | 임시(일반 몬스터용 보관) | 6단계에서 주황버섯 공격 구성을 사용자가 정할 때 자원도 확정 |

## 후보 (쓰지 않음, 기록만)

| 출처 | 내용 |
| --- | --- |
| mob/6130101.img(머쉬맘) 나머지 | attack1·skill1·attack1 이펙트·효과음 5종은 2026-11-05 사용자 지시로 "사용 예정"(회차 D)으로 옮겼다 |
| 좀비 머쉬맘 mob/6300005.img·mob/2400572.img, 블루 머쉬맘 mob/8645261.img·mob/8220007.img | 다른 보스 후보로만 기록 |
| 주황버섯 팩 mob/1210102.img | stand a95cfed2c8fe4d2cb64cbb62db051f92, move 8257566e41aa4234929e81c6c2dab2e4, jump 6df12df0c9ce4caea61385606a4d40d3, hit1 5ebbdaf503964f3e87de155d16650805, die1 dddbe2f162184ec89add7440da56eb75 |
| 회차 E 조작 버튼 테마 simplefantasy(메이플슬래시, msw-ui-kit), [Plan §24](Plans/2_CombatCore.md) | 배경 Slot_03/Btn_Attack e314c09b9b39486bb1c68d018b2abded(120×120 Sliced, 눌림 4eed2985436c4007890c3314c4d42dc0). 틴트 아이콘: Icon_Sword 3119d2807ea7466e8e9056d0590a35cc, Icon_Arrow_Up 21a4739b4d654e51810c638f273d9c54, Icon_Arrow_Down a714a1eaa4aa46098c0c265110ee91c0, Icon_Arrow_L 002ca90cd5794836b1e44da160de287a, Icon_Arrow_R 740aba24726c4c6580cf054b0e1e1fd5. 화면 적합성 미확인. 사용자 선택(Plan §24.6) 대기 |
| 회차 E가 바꿀 현재 조작 버튼 이미지(지금 사용 중, ui/CombatScreen.ui) | BtnAttack fa75318d112040f9a941da89ad5d2e53, BtnBack b5c63f01645645c095611f64b34078df, BtnGuard 9eff8b12dcde45ca989e9cd5a95e441c, BtnForward 83feab30f7744c629ecc1344e1c4e49b. Highlight 2860136c06ab075439721c027de365af는 유지 예정. 원본이 Docs/UIimg의 free-icon 이미지라는 것은 추정이다 |
| 회차 E 가드 이펙트·소리 후보(스킬 팩, 2026-11-06 msw-search 재확인) | 로얄 가드 skill/5100.img/skill/51001006: effect 318a46627eca4ae5b9c5d1fb16244e3c(124×147, 13프레임), 소리 605da1fc42f34ef4a1468387004a6223. 로얄 가드 강화 skill/40000.img/skill/400004230: effect a6c32468ecc14665baf9c056cfabae0c(138×156, 8프레임), effect_ple pre 0f93a8d6560547ddab87b8a0eb387e19·loop 12c03f6ac9374b5a91d993f09384c113·end f75c5a210fd24430b9e4a1122b6f82c8, 소리 6416b7d7c92148bfa05835e6b7aee9b0. 파워 가드 skill/800033.img/skill/80003317: effect af4e6abe766e4970a0e90aca58c6cc1c(64×85, 12프레임), effect0 a15d331295524094a9b1096df300022c, affected 1838b57cb0314900bc00b690580f8f36. 모습·크기 미확인 |
