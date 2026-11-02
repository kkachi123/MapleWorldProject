# CombatFoundation — 후속 확인용 임시 작업 기록

- 이관: 2026-10-19. 기존 안정화는 승인 범위에서 종결됐으며 이 파일은 남은 환경 확인의 재개용이다. 영구 기능 설명서·본인 기술 성과 기록이 아니다.
- 연결: [후속 계획](../Plans/CombatFoundation.md). 실제 확인 상태·실행 기준은 계획에서만 관리한다.
- 삭제 조건: 남은 후속 항목이 완료되거나 사용자 승인으로 처리되고, 필요한 결과를 해당 단계 Features에 반영한 뒤 연결 링크를 정리하고 삭제한다.
- 이번 이관에서는 코드 수정·새 Play 검증을 하지 않았다.

## 재개에 필요한 기존 계약

- 현재 입력·이동은 [1단계 결과](../Features/1_MovementInput.md), 정지는 [0단계 결과](../Features/0_CombatPause.md)를 따른다. 과거 즉시 이동 설명은 현재 기능으로 사용하지 않는다.
- AttackSkillData의 player.basic: Damage=1, AttackCount=10, FrameCount=14, 현재 상태 시간 0.84초. 실제 PlayerCombatComponent.HitInterval=0.045초이며 스킨 표시 간격과 별개다.
- 프로토타입 가드 잔여 피해율 0.4, 저스트/패링 창 0.2초, 자동 반격 배율 2.2. 2단계의 수동 공격 보너스·슬로우·그로기·판정 DataSet은 미구현이다.
- 공격 수락·상태는 PlayerStateControl, 공격/피해는 서버의 기존 네이티브 경로다. 플레이어 HP는 PlayerComponent, 몬스터 HP는 MonsterHealthComponent가 적용한다.
- 개발 Gizmo/Tuner는 Maker 제한 코드가 있으나 배포 환경 차단은 미확인이다. 직접 다른 맵 전환·실기기·성능·최종 피해 표시도 미확인이다.

## 기존 확인 요약

AI가 실제 Maker로 수행한 과거 기록을 짧게 보존한다. 이번 문서 이동을 신규 검증으로 해석하지 않는다.

| ID | 당시 범위·결과 |
| --- | --- |
| CombatFoundation-V01~V05 | 2026-10-18 map01: 기본 10타·피해 10, 시전 중 설정 분리·취소·단일 HP·기존 대응 |
| V06~V11 | 월드 판정/스폰·사망·혼합 입력. V11의 즉시 이동은 당시 버전 |
| V12~V18 | HUD·Gizmo·Maker 튜닝·데이터·보조 UI·스태미나 정리. 성능 실측 아님 |
| V19 / CombatFoundation-F06 | 2026-10-19 실제 StateComponent.Enable=false에서 진입/완료 전환 실패와 입력 복구·완료 잠금 확인 |

V19 발췌: `[VRF] MI V04/F06 final PASS=true stateRejected=true restored=true finishLocked=true`. F06은 완료 상태이며 다시 미실시로 돌리지 않는다. 과거 48개 PASS의 전체 원시 로그는 없다.

## 본인·AI 역할과 마무리

본인: 안정화/기획 확장 분리, 1인·스태미나 제거, 유지/제거 기준·후속 범위 승인과 직접 플레이 관찰. AI: 소스 분석·리팩토링·자동 검증. 구체적 원문이 없는 ‘확인사항 3가지 정상’ 보고를 개별 기기/기능 통과로 확대하지 않는다.

새 작업은 계획의 미실시 항목에 맞춰 기록한다. AI 시행착오를 본인 포트폴리오 사례로 바꾸지 않는다. 완료 후 전체 과거 원장을 Features에 복사하지 말고 해당 단계의 현재 동작·짧은 결과·미확인 범위만 반영한다.
