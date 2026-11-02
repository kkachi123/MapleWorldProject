# CombatCore — 임시 작업 기록

- 연결 Plan: [2_CombatCore](../Plans/2_CombatCore.md).
- 상태·갱신일: 2026-10-29 / 독립 QA2 종료·QA-F01 수치 PASS, 리뷰·사용자 V11 대기.
- 실행: [20261020-combat-core](../../../../.pipeline/20261020-combat-core/run.md).
- 삭제 조건: 승인된 범위 구현·필수 확인·결과/미완료 추적 이관·링크 정리 완료 후 삭제. 사용자 직접 확인이 남으면 유지한다.

## 현재 재개 지점

2026-10-29 사용자 재개 명령에 따라 coder_v4가 QA-F01을 최소 수정·기본 검증했고, 별도 tester_v2가 같은 새 52파일 Bundle e8a20728…a49에서 독립 QA2를 종료했다. QA-F01 원재현·후속 치명·보너스/DEFENSE/0피해 및 대표 입력·시간·팝업·사망 경계의 실제 결과는 아래 QA2를 따른다. 최종 map01/edit·Maker 사용 종료·제품 지문 전후 동일 확인. 다음 담당은 독립 reviewer이며 V11·CF-F07의 실제 연출 평가·기존 외부 NOT_RUN은 미완료다. P01b~P06은 🟡를 유지하고 과거 QA 실패는 당시 버전 근거로 보존한다.

### 과거 중단 기록 (2026-10-20)

사용자가 1단계 V08을 완료하고 2단계 진행을 승인했다. D01~D03은 제시한 A안, D04는 “전투하는 몬스터. 애초에 상대 몬스터는 1개체 고정(1:1대결)”로 답했다. 실제 확정 규칙·구현 범위는 Plan을 따른다. 기획 반영과 Plan 연결 확인 후 coder를 호출했으나 사용자가 남은 작업의 중단을 요청했다. 자동 재개하지 않는다.

## 과거 감독·인계 기록 (2026-10-20)

- 메인: /root. 독립 planner /root/combat_core_planner가 1단계 종료 정리·2단계 Plan 작성 후 사용자 답변을 반영 완료.
- coder /root/combat_core_coder: 사전 준비 중 사용자 요청으로 interrupt, 현재 interrupted. tester/reviewer는 미호출.
- Maker: coder의 사전 조회가 "user rejected MCP tool call"로 거절됐다. 재시도·우회·Play 없음. 직전 map01·edit은 과거 관찰이며 현재 상태로 간주하지 않는다.
- 새 QA/리뷰 결과: 아직 없음.

## 개발 기록

아래 문단은 2026-10-20 당시 중단 이력이다. 최신 재개·구현·검증은 뒤의 2026-10-24 절을 따른다.

제품 구현 완료 기록 없음. coder는 제품 편집 전 사전 문맥·소유자 점검 단계에서 중단됐다. 구현 ledger도 아직 생성되지 않았다. MapBuilder 읽기는 map01 id=0a0972ef-ad23-4e24-af63-afbd53120c1d, TileMapMode=0을 확인했다. 실제 Maker 연결/모드·런타임 검증은 조회 거절로 미확인이다. 사용자 재개 명령 후 실제 변경 범위와 환경을 확인해 이어간다.

## QA 기록

### 2026-10-29 독립 QA 2회차 — QA-F01 수치 재시험 PASS·리뷰 대기
- 담당: /root/combat_core_tester_v2. coder_v4 종료·사용 양도 후 별도 실행. 제품·모델·맵·UI·DataSet·CSV·원장 수정 없음. 과거 결과를 새 실행으로 세지 않았다.
- 대상: 52파일 Bundle SHA-256 e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49. 시험 전후 52/52 byte 일치. 변경된 PlayerCombatComponent.mlua 외 51파일은 2026-10-25 QA와 동일이며 이전 조건의 적용 한계를 유지한다. 전체 manifest는 뒤의 2026-10-29 개발절.
- 연결: 실제 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root·TileMapMode=0 일치. Play context server_main/client. build 오류0/경고0(Info79).
- 실제 시험 시각: 21:22~21:31 Maker 로그. keyboard_input W/방향키와 명시한 Play 내부 fixture·RPC/상태 진입 프로브 사용. HP/공격력/보너스 부여/시전 간격·길이/적 대기/패턴 선택/복귀 속도는 시험 세션 값뿐이다. 파일/CSV 변경·사용자 로그 clear 없음.

| ID·조건 | 이번 독립 실행 결과 | 판정·한계 |
| --- | --- | --- |
| QA-F01 / V02 원재현 HP5·Weapon10 | 실제 W 첫 native HitEvent5/Damages 합5/HP감소5. 1타·DeadEvent1회·DEAD, 이후 타격 제외 | PASS(수치). 과거 FAIL은 아래 1회차에 보존 |
| V02 후속 치명 HP25·Weapon10 | 실제 W native10,10,5의3타. HP/event/display 모두25·사망1회 | PASS(수치) |
| V02 비치명·보너스·DEFENSE·0피해 | 실제 W: 일반10타100, 보너스10타220, 실제 DEFENSE 첫6+후속16×9=150, DEFENSE 치명5의1타, Weapon0의0피해10타. 각 HP감소=TotalDamage합=Damages합 | PASS(수치). 보너스 부여는 GrantCounter fixture, DEFENSE는 실제 FSM 진입. 숫자 화면 가시성은 V11 |
| V02/V08 사망 뒤 추가 타격 | DEAD 상태에서 native AttackFast·같은 예약 재호출: extra event0/death0/HP변화0, DEAD 유지 | PASS(실행 조건), 일반 사망 프레임워크·연출 평가 아님 |
| V03/V10 지연 방향·거부 입력 | ATTACK 중 client ConfirmDirection(다음 epoch)→server ATTACK/pendingnil/start-1. 실제 GUARD 중 W 거부 후 같은 지연RPC도 GUARD/pendingnil/start-1/evadingfalse. 이후 actual Right가 정상 수락·endpoint 도달 | PASS(대표 조건). 모든 네트워크 도착 순열·실제 맵 이탈은 NOT_RUN |
| V04 진행 중 재성공·시전 실패 | actual W 시전 첫 native hit에서 GrantCounter fixture. 기존 cast multiplier1 유지·10타100, 다음 권한true. Weapon=-1 실제 W는 ATTACK 진입/activefalse/피해0/권한true(remaining .611) | PASS(대표 조건). 시전 데이터 실패 모든 조합은 새 전수 실행 아님 |
| V05 접근·실타격·복귀·만료 | 강제 GUARD/NORMAL 패턴 선택·FSM ATTACK에서 ApplySlow(2,.5). 접근 map .278/action .139=0.5, JumpActive/rate.5. 실타격1회 map1.019/action .5095, 예약due .5085. 복귀 JumpActive/action progress .1295/원래duration.5/targetHome/rate.5. map2.022 후 IDLE/slow0/native rate1. 다음 예고 sequence+1·같은 action clock .5비율, 효과만료 ActionRate1/native1/savednil | PASS(대표 경로). 다음 예고 계측은 명령·로그 사이 선수행분을 포함해 .396map/.198action 및 정렬 fixture .877map/.447action 관측; 이를 정확한 대기 종료시각 정량 PASS로 사용하지 않음. 전수 모션·음향·실기기 평가는 아님 |
| V07/V10 endpoint 실제 팝업 | actual Right 홀드→x1.5/HOLD/sequence17. 실제 _UIPopup.Open→ownertrue/pausedtrue, .5초 뒤 clockDelta0/xDelta0. 키해제·Close 뒤 actual W는 RETURNING/MOVE/held빈값/blockedtrue·sequence17 유지. 완료 후 x0/IDLE/NONE. server pausedfalse/evadeStart-1/evadingfalse/pendingnil | PASS(대표 조건). 복귀 중 관찰창 확보용 ReturnSpeed=.5 fixture 사용 후6복원, 최종 재진입6 확인. 모든 응답 순열·실제 모바일 입력 아님 |
| V08 death 뒤 늦은 metadata | native HitComponent.OnHit 치명 fixture 후 server/client DEAD, HP-25. 그 뒤 client ConfirmDirection은 server DEAD/pendingnil/start-1/evadingfalse | PASS(실행 조건). 수동 HP 차감 아님. 실제 맵 이탈·모든 외부 상태 순열은 NOT_RUN |
| V01/V06/V09/V12 등 무변경 경로 | 2026-10-25 QA·51파일 동일성을 대조. 이번 실제 재진입 rules .4/patterns8·기본상태 확인. 이전 예고·가드/패링·그로기·원자검증·상대 수명 결과는 당시 범위 근거로만 유지 | 새 전수 실행으로 세지 않음. CSV 재편집, 실제 두 사용자·다른 맵·비전투 몬스터 환경은 NOT_RUN 유지 |
| V11 / CF-F07 연출 | 실제 PC/모바일 가독성·타이밍 체감·터치/혼합 조작·화면 잘림·음향·피격/die 평가는 수행하지 않음 | NOT_RUN. CF-F07는 이번 수치 PASS만 추가, 전체 종결 금지 |

#### QA2 시험 오류·계측 한계
- 첫 새 몬스터가 HomeCaptured 되기 전 Home.y=0으로 배치해 낙하했다. lethal5의 event0, 최초 normal100의4타40은 잘못된 배치 조건이라 유효 제품 결과로 세지 않는다. MapBuilder의 발판 maxY=.580000043 및 기존 접지 높이 .581로 배치·Home fixture를 맞춰 동일 조건을 다시 시험한 retry 결과만 위 PASS로 사용했다. 제품 오류·수정 후 재검증 실패 횟수로 합산하지 않는다.
- maker_execute_script는 dispatch 완료일 뿐이다. 중간 시전실패 첫 준비의 대기/입력 순서는 별도 양성으로 사용하지 않고, grant 직후 actual W→ATTACK/activefalse/권한true를 재관찰한 결과만 기록했다.
- 다음 행동 대기의 내부 시계비율·실행 연결은 확인했지만 도구 dispatch 사이의 정확한 시작점 불확실성을 정밀 deadline 통과로 확대하지 않는다. 접근/복귀의 실타격 시각과 적분 배율을 실제 수집한 양성은 별개다.
- 이번 통합 회차 normal runtime 오류/경고0. 위 배치 실패는 로그/계측상 무피해 조건이며 예외 로그를 지우지 않았다.

#### QA2 사용 종료·다음 담당
- fixture HitEvent/DeadEvent·중간 성공/적 공격 관찰 핸들러 명시 Disconnect, runtime fixture=nil. 모든 키 up. 패턴 목록·복귀 속도는 세션 내 복원했고 Stop에서 시험 상태 폐기. 실제 다른 맵 이동·제품/CSV 수정 없음.
- actual Stop→다음Play(21:30:59~21:31:00) baseline: readytrue/Weapon1/10타/.045/range3×1/Counterfalse/fixture nil/evadeStart-1/pendingnil/적간격3/slow0/ActionRate1/jump.5/.8/patterns8/guard.4. client MoveSpeed6/ReturnSpeed6/popupfalse.
- 최종 actual maker_stop 성공 후 maker_get_current_map map01/edit 확인·Maker 사용 종료. 시험 후 52/52 동일 Bundle e8a20728…a49. tester가 제품을 고치거나 QA-F01의 과거 실패를 삭제하지 않았다.
- 다음은 독립 reviewer가 같은 새 버전·승인 요구·개발/QA·잔여 미실시를 대조한다. QA-F01 수치 수정은 PASS지만 V11·CF-F07 연출·실제 외부 환경은 미완료이며 단계 완료/Features 이관/Plan·WR 삭제를 하지 않는다.

### 2026-10-25 독립 QA 1회차 — 결함 1건·필수 미확인 유지
- 담당: /root/combat_core_tester, coder와 별도 실행. 제품·DataSet·CSV 수정 없음. 유일한 Maker 사용 담당으로 인수했으며 과거 coder 결과를 이번 실행으로 세지 않았다.
- 대상: 52파일 Bundle SHA-256 8be49440a9ebbda62fc38df333fb09673db66d2e60a8f873aa38012d7b505e21. 시험 전후 byte 지문 52/52 일치·묶음 동일. manifest/계산법은 뒤의 coder 2026-10-25 절.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186; MapBuilder TileMapMode=0/root 일치. 실제 context server_main/client. 기준 build 오류0·경고0(동적 참조 Info만 있음).
- 실행: Maker 로그 11:07~11:19. native keyboard_input, mouse_input 및 명시한 Play 내부 상태 fixture/논리 RPC 프로브. 임시 HP·무기 공격·행동 간격·타격 간격/시전 시간·패턴 목록은 Play 내부만 조절했다. CSV는 수정하지 않았다. 사용자 로그 clear 없음.

| 검증 ID | 이번 독립 결과·양성 근거 | 남은 범위·한계 |
| --- | --- | --- |
| V01 | PASS: 유효 8행을 각각 Prepare→native Resolve하고 재호출에도 resolutionCount +1. 중앙 HP/HitEvent/Damages 각각12. 별도 실제 클라이언트 HUD 8/8 방향·속성 문구와 3색 구별, 같은 snapshot response/attribute 일치. special+guard 데이터 거부 | 체감·가독성/기기 화면은 V11 |
| V02 / CF-F07 | FAIL: 일반/짧은 가드4·특수12·패링0·실패패링 가드4에서 HP=HitEvent.TotalDamage=Damages 합계. native W 보너스 22×10=220, 실제 DEFENSE 첫6+후속16×9=150도 세 값 일치. 다만 몬스터 HP5를 기본10 첫타로 처치하면 HP감소5·이벤트10·표시10으로 문자 기준 불일치(QA-F01) | CF-F07 종결 보류. 화면 숫자 가시성·die 체감은 V11 |
| V03 | PASS(실행 조건): 창 직전 -.200001/정확히-.20/안/공격시점/직후 .000001 = false/true/true/true/false. 해제된 최근 회피도 범위 밖 JUST 0피해·권한1회, wrong/future는 피해0·보상0. 실제 Left+A 추가출처 시작시각 불변, 다음 실제 RIGHT epoch=bound/미소비예약없음. 동일 client RPC에서 방향 선도착→Close의 pending 폐기와 이후 실제 MOVE 정상 | NOT_RUN: 모든 네트워크 도착 순열, 거부 ATTACK/실제 맵 이탈 뒤 metadata 도착. 직접 훅/시험 RPC는 실제 키 입력과 구분 |
| V04 | PASS(실행 조건): 실제 W와 실제 UI 공격 클릭. 10타 전부 동일 factor2.2, HP/event/display220. 거부 시전(Play 내부 WeaponAttack=-1)은 권한 보존, 실제 whiff는 HP변화0·소비1, 재성공 배율2.2 유지. 고정 맵시계 fixture에서 만료1us전 유지/정확만료 해제 | NOT_RUN: 이번 독립 회차의 진행 중 재성공 비소급·시전 데이터 실패 모든 조합. coder의 해당 근거는 개발 절에 별도 유지 |
| V05 | PASS(실행 조건): 적 action/map 진행 비율 .128/.256=.5, 재적용 rate=.5·남은2초로 비중첩. 실제 팝업에서 action/남은slow 동결, 사망 시 rate/slow 정리, 정상 재진입 rate1 | NOT_RUN: 접근·복귀·대기 전체 구간의 모션/실타격 시각 전수 대조, 오디오·실제 기기 관찰. 기존 coder 만료복원 근거와 구분 |
| V06 | PASS(실행 조건): 실제 그로기 STUN, .25초 뒤 재적용 deadline +.292초. native HitComponent.OnHit3 중 STUN/deadline 유지·HP3 차감. slow와 공존, 실제 팝업 중 잔여 동결, 몬스터 치명 후 DEAD/slow0/stunfalse | NOT_RUN: 모든 상태 조합·옛 completion 직접 재호출 전수. 별 표시 가시성은 V11 |
| V07 | PASS(실행 조건): _UIPopup.Open→RequestPopupPause의 실제 owner/IsPaused 확인. slow1.395·groggy.931·counter1.467·양쪽 진행시계 동결. 다중타격 시험용 HitInterval=.1/시전2초에서 8타 뒤 실제 팝업으로 정지, HP와 fired 불변, 닫은 후 잔여2타만 실행되어 총220·소비1 | NOT_RUN: 이번 독립 회차의 회피 endpoint 팝업·모든 응답 순서. 시험용 시전/간격은 Stop에서 폐기·기본값 재확인 |
| V08 | PASS(실행 조건): 몬스터 native 치명 DEAD/slow0/stunfalse, 실제 DoSpawn oldValidfalse·새상대 연결. 플레이어 actual DownArrow GUARD 중 특수12로 HP5→-7, native 이벤트·표시12. .2초 뒤 server/client DEAD, 가드false·시작시각-1/회피시각-1·보너스false·slow0·상대nil. 이후 실제 W+RightArrow도 sequence불변·DEAD 유지. 실제 Stop→다음Play 기본 설정·권한/효과0 | 사망 직후 순간 state=IDLE 관측을 이번 지연 DEAD 관측으로 보완. die 화면 평가 아님. 옛 Resolve 추가피해0은 자동 Respawn 뒤 관찰이므로 DEAD 상태 검증으로 확대하지 않음. 실제 맵전환은 기존 후속 |
| V09 | PASS(런타임 스키마): 빈값/NaN/nan/inf/음수창·1초과가드·0/1초과slow·0배율·빈id·중복·specialguard·nil table·실제 다른 DataSet의 누락열·무효 modifier 거부. 유효 cache rules default=.4/patterns8 유지. 정상 재진입 rules .4 | NOT_RUN: tester 역할상 실제 CSV 재편집/파일 삭제 시험. coder의 .30→NaN→원본복원 실제 CSV 근거와 현재 byte 지문을 확인했으며 새 독립 실행으로 세지 않음 |
| V10 | PASS(실행 조건): 실제 LeftArrow+A/RightArrow/DownArrow/W. 실제 mouse_input 공격 중심(960,340) 클릭으로 ActionSequence6→7/ATTACK. 실제 뒤 버튼(790,180) 홀드+A→UI해제 후 MOVE/heldLEFT/keyAtrue/ui없음, 마지막 A해제 뒤 중앙복귀. 앞선 방향 Close fixture 후 실제 RIGHT도 정상 | 첫 버튼 가장자리 클릭의 무반응은 좌표 조건으로 구분. 실제 모바일 다중터치·모든 동시 입력/차단 순열은 NOT_RUN/V11 |
| V11 | NOT_RUN | 사용자 직접 PC/mobile 가독성·체감·터치·화면/음향·피격/die 평가 필요 |
| V12 | PASS(실행 조건): 기존 단일 manager 참조, monster 실제 교체 old invalid/new opponent, player 사망 후 opponent nil·공격/효과 거부 | NOT_RUN: 실제 두 사용자·비전투 몬스터·다른맵 환경. 독립 Run 격리 완료로 표시하지 않음 |

#### CombatCore-QA-F01 — 치명 overkill에서 HP 감소와 숫자 불일치
- 요구: R02 / V02 / CombatFoundation-F07. 기대: Plan의 치명 포함 HP 감소=HitEvent 합계=피해 숫자 문자 기준.
- 재현: 같은 버전 map01 Play. 현재 상대 Hp=5, 플레이어 WeaponAttack=10, 기본 스킬·보너스없음·사거리 안. 기존 W 입력으로 정상 시전한다.
- 실제(11:17:32~33): 첫 native HitEvent.TotalDamage=10, Damages 합계10. MonsterHealth.Hp 5→0, 감소량5. 이후 타격은 DEAD 필터로 제외되고 effects는 정상 정리된다. [VRF][QA] lethal.monster.equality FAIL hpDelta=5.0 event=10 display=10.
- 코드 경계: PlayerCombatComponent.mlua:233은 합성 피해를 내림해 반환하며 남은 HP 상한을 두지 않는다. MonsterHealthComponent.mlua:25에서 이벤트 후 HP를 0으로 clamp한다. 기본 비치명·DEFENSE의 단일 차감은 통과했다.
- 영향/처리: 기존 clamp/overkill 표시 관행에서 발생하지만 승인된 문자 기준에는 FAIL이다. tester가 요구를 완화하거나 제품을 수정하지 않았다. reviewer가 native 단계·승인된 최종 피해 규칙과 수정 범위의 충돌 여부를 검토한 뒤 coder 재작업/기획 판단을 정한다. CF-F07은 미완료 유지한다.
- 재검증: 동일 5HP/10피해를 포함해 비치명·가드·저스트·패링·DEFENSE·두 번째 타격 시 남은 HP보다 큰 경우·사망 1회/숫자/연출을 변경 버전에서 다시 확인.

#### 시험 오류·불확실성 분리
- 첫 setup에서 Entity._T에 fixture를 저장해 LEA-2007이 났다. 제품 오류가 아니다. 즉시 Stop/재진입해 해당 핸들러를 폐기하고 Component._T fixture로 재실행했다.
- 실시간이 흐르는 두 API 사이의 0.01초 미래 회피/만료1us전은 호출 도중 경계가 지나 초기 예상과 달랐다. 제품 수치 대신 고정 맵시계 fixture로 바로 전/정확/후를 재검사하여 통과. 이 fixture를 실제 팝업으로 표시하지 않는다.
- 첫 groggy 시험은 server wait 중 client popup을 먼저 dispatch해 pause.IsPaused=true로 적용이 정당하게 거부됐다. 실제 unpaused→효과 확정→popup 순서로 다시 실행한 양성 결과만 사용했다.
- 정상 회차의 제품 runtime 오류는 관찰되지 않았다. 의도한 무효 데이터 경고와 위 setup 프로브 오류는 로그에 보존했다.

#### 사용 종료·다음 담당
- native Event 핸들러는 명시 Disconnect, 첫 잘못된 setup은 Stop으로 폐기. 모든 키/마우스는 up/tap으로 종료. 임시 프로브/수치는 Play 내부뿐이며 제품/CSV 쓰기 없음.
- 마지막 정상 재진입 [VRF][QA] restart true: SkillDataReadytrue/기본10타/WeaponAttack1/HitInterval.045/AttackInterval3/권한false·회피시각-1·slow/groggy0·rate1·guard기본.4. pHP940은 정상 AI가 이미 12피해를 반복한 관찰값이며 초기HP 변경으로 보지 않는다.
- 최종 maker_stop 성공 후 maker_get_current_map map01/edit 확인, Maker 사용 종료. 시험 후 지문 52/52 동일. 독립 reviewer에게 QA-F01과 위 NOT_RUN을 포함해 인계한다. 제품 수정/기준 완화/3단계 진행·CF-F07 종결은 수행하지 않았다.

## 리뷰 기록

### 2026-10-29 독립 리뷰 — CHANGES_REQUIRED
- 담당: /root/combat_core_reviewer_v2. coder_v4→tester_v2 실제 종료 뒤 별도 실행. Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음. 아래 런타임 근거는 해당 개발/QA 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: 52파일 Bundle SHA-256 e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49. reviewer도 manifest의 52/52 byte와 Bundle 일치를 확인했다. QA2는 같은 버전, 이전 QA는 당시 조건/무변경51파일 범위로만 유지됐다.
- 판정: **CHANGES_REQUIRED — CombatCore-REV-F01**. QA-F01 처치 상한 수정은 타당하며 해당 수치 재시험 PASS를 인정한다. 별개로 몬스터 기본 피해를 경감 전에 내림하는 기존 호출이 승인 D02/R02와 어긋나 coder 최소 수정·독립 재검증이 필요하다. 이 수정 뒤에도 V11·CF-F07 실제 연출·V12 외부 환경은 WAITING 항목이다.

#### CombatCore-REV-F01 — 몬스터 피해가 경감 전에 한 번 더 내림됨
- 요구: Plan D02/R02/V02는 기본 피해와 경감을 합성한 뒤 최종 피해를 정수 내림한다.
- 실제 소스: RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua:134에서 ResolveIncomingDamage(math.floor(self.AttackDamage), attacker)를 호출한다. RootDesk/MyDesk/Player/PlayerHealthComponent.mlua:38의 인자도 integer damage이며 :45에서 다시 math.floor(damage * result.rate)를 한다. AttackDamage는 number이고 PrepareAttack은 finite·비음수만 검증하므로 소수는 현재 허용된 입력이다.
- 재현 조건/기대·실제: 유효한 일반 또는 실패 패링 공격, AttackDamage=12.7, 가드 잔여율=.40. 승인 기대는 floor(12.7×.40)=5, 현재 코드는 floor(floor(12.7)×.40)=4. 이는 소스/산술로 확인한 결함이며 reviewer의 새 Maker 실행 결과로 표시하지 않는다. 기본12만 시험한 QA와 충돌하지 않는다.
- 최소 수정 범위: 원래 number 기본 피해를 최종 경감 소유자까지 보존하고 경감 합성 뒤 한 번만 floor한다. 위 호출자·메서드 인자 형식을 함께 맞추고 native CalcDamage 반환은 integer, HP 소유는 기존 PlayerComponent로 유지한다. 기본12·DataSet 규칙·새 스탯/치명타/피해 프레임워크를 바꾸지 않는다.
- 독립 재검증: 실제 native 몬스터 타격에서 12.7의 무가드/특수=12, 일반 가드·실패 패링 가드=5, 유효 저스트/패링=0의 HP delta/TotalDamage/Damages 합계를 대조한다. 기본12의 가드4/특수12·성공0, QA-F01의 몬스터 처치 상한·사망1회/후속 제외를 관련 회귀로 확인한다. 시험값은 Play 내부만, 수정한 두 파일/새 Bundle을 고정한 뒤 tester→reviewer로 인계한다.

#### 승인 요구·실제 경계 대조
- QA-F01 / R02: PlayerCombatComponent.CalcDamage는 보너스·실제 DEFENSE 합성/floor 뒤 남은 몬스터 HP 상한을 적용한다. native AttackComponent.CalcCritical 기본false·GetDisplayHitCount 기본1이며 이 컴포넌트는 둘을 override하지 않는다. native AttackFast→OnHit→HitEvent를 유지하고 MonsterHealth의 한 소유자만 HP를 차감한다. Health/IsAttackTarget의 DEAD 차단·사망1회 경계를 실제 코드와 QA2의 5/25/100/220/150/DEFENSE치명/0피해 및 후속0 근거로 대조했다. 숫자 화면의 가시성은 여기서 인정하지 않는다.
- R01/R02: MonsterAttack의 실행 ID·현재 쌍·패턴/영역/규칙 스냅샷, resolved 1회 확정·native resolving 범위를 확인했다. EvaluateDefense는 t-window≤start≤t와 실제 가드 상태·수락 방향을 사용하고 범위 밖 성공도 CalcDamage 밖에서 처리한다. 틀린 입력만으로 범위 밖에 추가 피해를 만들지 않는다. REV-F01 외 승인 대응표의 새 불일치는 확인되지 않았다.
- R03: GrantCounter는 현재 상대/생존/정지 여부를 확인하며 실행 중 cast와 별도 권한을 둔다. 유효 ATTACK·데이터/대상/공격력 검증 뒤 스냅샷과 예약을 만들고 소비한다. 만료 now<until·비중첩 갱신·whiff 소비·실패 보존·중간 시전 비소급은 소스와 과거 QA/QA2에 대응한다. 자동 공격 호출은 없다.
- R04/R05: MonsterStateControl은 맵 전투 시간의 slow 시작/종료 구간을 적분하고 모션·대기·공격/복귀가 같은 GetActionTime을 사용한다. 효과/그로기는 맵 시계로 만료하며 native PlayRate 저장·복원한다. STUN 진입은 ATTACK 이탈/CancelExecution으로 미실행 공격·이동을 취소하고 Health의 조건부 HIT는 STUN을 조기 종료하지 않는다. 사망 먼저 무효화/DEAD하며 이전 완료의 ID·생존/state 조건을 확인했다. QA2의 접근/실타격/복귀 양성은 유효하고 다음 대기의 정확 deadline은 정밀 PASS로 확대하지 않았다.
- R06: 신규 두 DataSet wrapper의 이름/UUID/serveronly·동명 CSV, 확정 수치(.20/.40/2/2.2/2/.5/1.5)와8패턴·기존 player.basic10타/3×1을 읽었다. CombatRuleCatalog는 전체 정상화 성공 후 캐시를 교체하고 invalid 시 임의 기본값/부분 행으로 진행하지 않는다. modifier→동일 검증→실행 복사와 OnEndPlay 캐시 정리를 확인했다. coder의 실제 CSV .30→NaN→원본복원은 독립 CSV 재편집 시험과 구분돼 있다.
- R07/R08: CombatInputController의 UI 필드/이벤트는 ClientOnly이며 현재 로컬 대결의 서버 Sync 결과만 표시한다. PlayerStateControl의 단일 수락·출처 합산·복귀 잠금, PlayerEvade의 sender 소유자·epoch/sequence/closed 경계, popup의 서버 승인·동결·홀드 시각 폐기, Manager의 유일 사용자/상대 확인·교체/사망 시 이전 실행 정리를 대조했다. 원래4버튼·이동6/복귀6·점프.5/.8과 native HP 경로를 보존한다. 이것은 실제 Run 격리/다중 접속 검증 완료가 아니다.
- 검토한 실제 소스는 위 소유자들과 Player_Attack/Player_Move/Monster_Attack/Monster_Stun, OrangeMushroomAttack, PlayerSkillEffectTable 및 native AttackComponent/HitComponent/StateComponent/HitEvent 정의다. 구조 파일은 raw JSON으로 검토/수정하지 않았으며 기존 빌더 사전 표·실제 QA 연결 결과와 byte 불변성을 보조 근거로 사용했다. 새 자원 선택·전면 모션/사망 프레임워크·수동 피해·핫바 도입은 승인 범위가 아니다.

#### CombatCore-DOC-01 — 현황·인계 링크 동기화
- DevelopmentRoadmap.md:13의 현재 자동 반격 설명, :45의 P01b 시작 예정, :103의 구현/Play/QA/리뷰 미착수·2026-10-20 재개 지점이 실제 기록과 다르다.
- ChatRoles/README.md:36의 WorkRecord 생성 예정, WorkRecords/README.md:58의 규칙 결정 대기/WorkRecord 생성 예정도 현재 Plan/WR로 연결해야 한다.
- 다음 담당은 planner. 제품 수정/재검증/리뷰 결과가 확정된 뒤 위 현황·날짜·링크만 원본 Plan/WR에 맞춘다. 규칙/검증 기준·단계 순서 변경이나 결과 전문 복제 없이 정리한다. 메인의 run도 같은 실제 담당/버전에 맞춘다.

#### 수정 후에도 남는 필수 확인·다음 행동
1. coder: REV-F01의 두 경계만 최소 수정·실제 기본 검증·새 버전/사용 종료 기록. tester: 새 버전의 소수 기본 피해와 관련 native 회귀. reviewer: 변경·QA·동일 버전 재대조. 제품을 바꾼 뒤 이번 QA2가 모든 변경 경로에 그대로 적용된다고 표시하지 않는다.
2. planner/메인: DOC-01 정리, QA-F01의 과거 FAIL과 새 수치 PASS 연결, CF-F07 수치/연출 분리·잔여 ID 추적 유지. 현재 P01b~P06은 🟡 유지가 타당하며 문서 존재나 대표 양성만으로 P06/단계 전체를 완료 처리하지 않는다.
3. 사용자 V11: 실제 PC·모바일의 예고 방향/속성·.20초 체감·저스트/패링/반격 준비·소비·적 슬로우/별 표시·피격/die·키/버튼/터치 혼합·화면 잘림·음향을 직접 확인한다. 새 수치/규칙 변경 요구가 없으면 재승인 질문은 불필요하다.
4. V12 외부 환경: 실제 두 사용자·비전투 몬스터/다른 맵이 있는 환경의 비전파는 NOT_RUN. 단일 참조/무효화 정적 검사와 현재 맵의 교체·사망 시험으로 이를 대신하지 않는다. 실제 맵 전환은 기존 CF-F03/CombatPause-F01, 기기/음향·재시작·배포·성능은 기존 후속 ID와 실행 시점을 유지한다. 이를 위해 새 Run/맵/다중 전투 체계를 만들지 않는다.
5. 현 조건의 종착점은 REV-F01와 DOC-01 처리 후 사용자/환경 WAITING 경계다. V11·CF-F07 연출·외부 필수 확인이 남은 Plan/WR/run은 보존하고 3단계를 자동 시작하지 않는다.

## 완료 시 이관할 내용

현재 기능·설정·사용자 선택·짧은 검증/미검증 범위를 Features에, 미완료 추적은 Plan에 유지한다.

## 2026-10-24 재개 인계
사용자가 "2단계 중단 시점 부터 작업 재개해줘."라고 명시 요청했다. 기존 규칙을 유지하고 P01b부터 진행한다. 제품 편집 전 실제 Maker 맵·모드와 소스/API·연결을 확인한다. 브리지 TCP 연결 성공은 Maker 도구/실제 맵 확인과 구분한다. 이전 개발·QA·리뷰 미실시를 새 결과로 변경하지 않는다.

### P01b 사전 점검 (2026-10-24 / coder)
- 실제 Maker 도구가 coder 문맥에 노출됨. maker_get_current_map: map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. maker_get_world_info: worldId=970621b29ba945369d3dc8e90c301186. MapBuilder mode=0과 일치. 아직 제품 쓰기/Play 없음.
- MonsterManager.CurrentMonster가 단일 상대 소유자. 현행 MonsterData는 castleenemy 한 행, 실제 주황버섯 모델에 DEFENSE/Stun/Attack/OrangeMotion 연결. 현재 상대·현재 사용자 1명만 허용하는 최소 fail-closed 경계를 같은 소유자에 추가하며 독립 Run 격리 완료로 보지 않는다.
- 최소 데이터: CombatRuleData 기본1행 + MonsterAttackPatternData 유효 대응×속성8행. LEFT/RIGHT는 중앙·반대 방향 영역을 타격하고 예고 방향으로 피할 수 있게 앵커 기반 범위 구성. 특수+GUARD는 거부. JumpDuration=0.5/JumpHeight=0.8과 기본 공격 행은 유지한다.
- 핵심 위험: 범위 밖 저스트가 CalcDamage를 거치지 않는 점, 슬로우 배율 변경 시 모션/예약이 점프하는 점, 기존 실제 DEFENSE의 HitEvent 후 경감으로 숫자와 HP가 어긋나는 점. 공격 실행1회 결과·적 적분 진행 시계·CalcDamage 전 경감으로 해결한다.
- StateComponent.d.mlua의 DisconnectHitEvent를 확인했다. HP는 기존 HitEvent 한 경로로 유지하며 기존 Health 소유자에서 STUN/ATTACK 보호 조건부 HIT만 처리한다. 새 수동 피해/핫바/컨트롤러/사망 연출 프레임워크는 승인 Plan 우선으로 도입하지 않는다.
- 구현 원장: 프로젝트 루트 .maplestory-skill-maker-ledger.md에 DATA/PAP/PAJ/MHP별 소유자·위치·검증 시나리오·승인 예외를 OPEN으로 생성.

### P02~P05 작성 및 통합 기본 검증 진행 (2026-10-24)
- CombatRuleCatalog 원자적 로드/검증, 기본1·8패턴 데이터, MonsterManager 단일 CurrentPlayer, 공격 실행 스냅샷/1회 판정, 수동 보너스, 적 행동 적분·그로기·서버 결과 HUD를 작성했다. Plan P01b~P05는 🟡이며 실행 완료를 뜻하지 않는다. 기존 AttackSkillData/이동 수치/점프 수치/4버튼/네이티브 타격을 유지했다.
- 16:42 Refresh→build는 오류0, 문자열 치환 다중 반환 경고1 및 기존 동적 참조 Info. normal 변환 오류0. Play에서 catalog ready rules=1 patterns=8, HUD bound=true, duel player, 이동 speed=6 return=6 확인.
- 첫 통합 회차: 유효8패턴 예고와 중복 ResolveAttack 1회 판정, 실제 HP=HitEvent 합계 normal guard4/special guard12/parry0/parry early4/wrong12 확인. 그로기 잔여는 같은 호출 중에도 프레임 진행해 1.483으로 계측되므로 1.5 정확등가 검사 대신 허용 오차로 검사한다(제품 수치 변경 아님).
- 실패: justinside 슬로우 적용에서 MonsterStateControl.ApplySlow savedPlayRate nil 산술 오류. Stop 후 수정: native 재생률은 로컬 스냅샷으로 읽고 유효 수 검증, 만료 정리와 충돌하지 않게 활성 시각을 먼저 설정한 뒤 저장값·재생률 적용. 실패 이력을 보존하고 수정1 회차에서 전체 통합 재검증 중이다. 범위 밖 비성공은 피격 대신 회피 표시로 구분했다.


## 2026-10-25 coder 재개·기본 검증 인계

### 실제 실행·변경·종료
- 담당: 독립 coder /root/combat_core_coder_v3. 기존 v2 사용량 한도 중단 뒤 현재 파일을 이어 검증했다. 사용자 재개 승인 범위는 기존 R01~R08이며 새 규칙·3단계·배포는 추가하지 않았다.
- 연결: 실제 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root id·TileMapMode=0 일치. Play context=server_main/client.
- 이번 영구 제품 수정은 MonsterManager.mlua의 model:// 접두어 제거 한 곳이다. 다중 반환 string.gsub를 단일 반환 string.sub 분기로 바꿔 DoSpawn LWA-1111 경고를 제거했다. 기존 v2의 전투 구현을 재구현하거나 기존 수치를 바꾸지 않았다.
- CombatRuleData.csv는 승인된 V09 시험 동안만 0.40→0.30→NaN→원본을 적용했다. 모든 파일 쓰기는 edit에서 수행하고 각 값마다 Refresh→build→Play를 거쳤다. 원본 복원 bytes 일치, SHA-256 fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f.
- 최종 실제 관찰(2026-10-25 11:00:32 Maker 로그 시각): 기본값 복원 Play의 build 오류0/경고0, normal 오류0. 과거 invalid 데이터 시험 경고는 보존했고 무단 clear_logs는 호출하지 않았다. 초기 경고가 잠시 과거 시각으로 남았으나 변경 뒤 Play에서 새 build 결과는 오류0/경고0이다.
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01/edit 확인. Maker 사용 종료. 시험 입력 키는 모두 up/tap 종료. 임시 컴포넌트·파일·로그 삭제는 하지 않았다. Play 내부 값/참조/시험 이벤트 연결은 Stop으로 폐기했고 별도 HitEvent 시험 핸들러도 명시 Disconnect했다. 최종 재진입의 상태가 정상임을 확인한 뒤 다시 Stop했다.

### 기본 검증 결과와 한계
아래는 coder의 실제 MCP 개발 검증이며 독립 QA나 사용자 수락이 아니다. 시각은 Maker 로그 시각이다. 일부 항목의 남은 세부 경우는 tester가 독립 보완하며, 확인한 일부만으로 V 전체를 통과 처리하지 않는다.

| 기준 | 이번 확인·양성 근거 | 남은 독립 보완·미실시 |
| --- | --- | --- |
| V01 | 10:52:22~23: 유효 8패턴의 Prepare→실제 native Resolve를 각각 강제 선택한 Play 값으로 확인. id/유형/영역 스냅샷 일치, Resolve 2회 호출에도 resolutionCount +1. 각 HP=HitEvent 12. SPECIAL+GUARD 검증 거부 | 동기화된 문구·색·다른 공격 시각의 표시 대조는 tester, 실제 읽기 편함은 V11 |
| V02 / CF-F07 | 10:52~55: 일반 가드4/특수 가드12/패링0/이른 패링 가드4/짧은 일반 가드4. actual W 시전은 10타·최종2·HP=event20. 실제 DEFENSE 진입+runtime WeaponAttack7.5+보너스2.2에서 첫 경감타6, HIT로 DEFENSE 종료 뒤 후속16×9, HP=event150. 네이티브 이벤트만 HP를 차감 | 피해 숫자의 실제 화면 가시성은 V11. tester가 최종 native 표시 인자/HP 단일 적용 및 치명 경계를 독립 대조. CF-F07 선종결 안 함 |
| V03 | health.IsInWindow의 -0.200001/-.20/-.1/0/+0.000001 결과 false/true/true/true/false. 실제 LeftArrow 서버 MOVE·LEFT epoch=bound1, A 추가 홀드에도 start37.297 유지. 범위 밖 x=-1.5에서 JUST nativeHit0·피해0·권한1회, wrong/early 피해0·권한0·자동 적피해0 | 모든 네트워크 도착 순서, 해제 후 유효 창·거부 상태·death/leave 메타데이터는 tester 추가 확인 |
| V04 | 실제 ↑/W keyboard_input과 기존 UI ButtonClickEvent 주입으로만 수동 시전. count10·factor2.2·소비1. 진행 중 성공 시 cast factor1→1 유지, 중복 DoAttack 거부에도 권한 유지. 실제 whiff 피해0·소비1, 정확한 만료 UpdateCounter는 Ready=false | 시전 데이터 실패, 만료 직전·재성공 모든 경계는 tester 보완. UI 이벤트 주입은 실제 mouse/touch 클릭이 아님 |
| V05 | ApplySlow rate=.5/renderer=.5. 실제 popup 중 적 action/map clock·monsterX·효과·보너스 잔여 불변. 닫기 후 만료에서 SlowRemaining0/ActionRate1/native rate 원래값/저장값nil. 플레이어 move/return6 보존 | 접근·복귀·대기 전 구간의 시간 적분 계측·refresh 비중첩 전수, 오디오/플레이어공격 속도는 tester/사용자 범위 구분 |
| V06 | 10:56: groggy 진입 STUN·기한1.5, 미실행 공격 activeState와 JumpActive 폐기. 타격 중 STUN/기한 유지, 종료 IDLE. 이전 state completion을 재호출해도 resolution 추가0·옛 snapshot unresolved. slow 잔여는 groggy 뒤에서도 경과 | groggy 재적용·정지 중 groggy와 모든 상태 조합은 tester 보완. 머리 별 표시 생성 로그는 있으나 가시성은 V11 |
| V07 | 실제 _UIPopup.Open→RequestPopupPause로 owner=true/paused=true. 약9초 후 clockDelta0, 회피 위치 불변. Close 후 evadeStart=-1/isEvadingfalse/pendingfalse·중앙 x0·InputBlockedfalse. 효과 시험: frozen counter1.514/slow1.389/예고.288과 monsterX/action clock이 2.3초 실시간 후 동일 | 플레이어 다중타격 중 정지·groggy 정지·응답 도착 순서 전수는 tester 보완 |
| V08 | 10:58~11:00: monster native lethal HP0/IsDeadtrue/DEAD/slow0/stunfalse/bonusfalse, 옛 return 완료로 IDLE 복구 없음. 기존 DoSpawn 교체 시 oldValidfalse/new opponent 연결. player native lethal HP5→-7=피해12, native IsDeadtrue 후 보너스/slow/현재 target 제거·옛 콜백 피해0. 실제 Stop→다음Play에서 권한false/회피-1/pendingfalse/slow·groggy0 | player native lethal 직후 state는 IDLE로 관측됨(죽음 연출 통과 주장 안 함). 실제 다른 맵 전환은 기존 후속 ID, player removal/모든 외부 상태 이탈은 tester 보완 |
| V09 | 기본 실제 DataSet rules1/patterns8. ValidateRows 무효값/빈값/NaN/inf/음수·rate·중복·누락·유형·anchor 등19/19 거부, invalid modifiers3개 거부, 기존 정상 캐시 불변. 실제 CSV .30 로드 확인, 실제 NaN Play Ready=false/empty rules·patterns/SkillReadyfalse. Ensure/GetRules 반복5회 동일 key 경고1회. 원본 .40 복원+다음Play 확인 | 실제 누락 테이블/열 asset 시험 등 남은 스키마 경계는 tester 보완. 정적 검증과 실제 CSV 초기화 결과를 구분 |
| V10 | keyboard_input 실제 Left/A/Right/Down/↑/W. endpoint LEFT+UI ButtonStateChangeEvent 홀드 합산→키해제 후 UI 홀드 유지, UI해제 즉시 RETURNING/새RIGHT거부/sequence유지. 그 후 실제Right가 서버 RIGHT epoch=bound7/pendingfalse. 마지막 정상 재진입 Left tap 뒤 IDLE/LEFT epoch=bound=closed1/x0. 최종10타·range3×1·jump.5/.8·이동복귀6 | UI 시험은 Entity:SendEvent 이벤트 주입이며 실제 mouse_input/물리 터치 아님. 기기 터치는 V11, 모든 동시 입력은 tester 추가 |
| V11 | NOT_RUN — 사용자 직접 평가 | PC/모바일 예고·성공·보너스·slow·별·피격/die·타이밍·터치/잘림/음향 |
| V12 | 현재 대결만 Resolve/수동 target. player 사망 후 GetOpponent=nil로 거부, DoSpawn 실제 교체는 옛 엔티티 폐기·새 참조 연결 | 실제 두 사용자·비전투 몬스터 환경 NOT_RUN. 독립 Run 격리 완료로 표시하지 않음 |

### 프로브 오류와 제품 오류의 구분
- 기존 v2 savedPlayRate nil/방향 RPC 순서 수정은 현재 소스에 유지했고 이번 slow/실제키 경로에서 재발하지 않았다. 이번 v3 새 제품 런타임 오류는 관측되지 않았다.
- F07 첫 프로브의 HitEvent0은 몬스터를 y=0(실제 발판 y=.581 아래)에 배치해 낙하한 시험 오류였다. Home.y=.581로 올바르게 배치한 후 native 10타20/DEFENSE150을 확인했다. 해당 첫 결과를 제품 실패 또는 PASS로 세지 않는다.
- 첫 같은 프레임 UI release/return 프로브는 중앙에서 즉시 복귀 완료가 가능한 조건이라 새 입력이 수락됐다. 실제 endpoint x=-1.5에서 다시 시험하여 RETURNING 동안 새 입력 거부를 확인했다. 제품 정책을 바꾸지 않았다.
- UI 출처 문자열을 key:A로 조회한 초기 nil은 조회 키 오기이며 실제 코드는 key. + enum이다. 실제 추가 홀드 시간 불변과 이후 UI 출처 합산 근거를 사용한다.
- invalid 데이터 시험 경고는 의도한 입력 거부 근거이며 일반 runtime 오류와 분리한다. 최종 정상 데이터 Play에는 새 경고/오류가 없다.

### 다음 담당에게
같은 버전 독립 tester가 위 미실시·부분 근거를 보완하고 R/V 전체 판정을 기록한다. 특히 MOVE metadata의 거부/빠른해제/return/popup/death/leave 도착 순서, 타이밍/보너스 실패·만료·재성공, slow 적분·groggy refresh/정지, native 숫자/DEFENSE/죽음 경계, CSV 누락열 거부를 확인한다. 제품/CSV 수정은 coder로 반환하고 시험용 값은 Play 내부만 사용한다. V11 및 실제 다중 사용자/다른맵/배포/성능은 NOT_RUN 유지. 리뷰·사용자 확인 전 단계 완료/Features 이관·기록 삭제를 하지 않는다.

### 최종 제품 버전 묶음
- 52파일 byte SHA-256 manifest. 대상은 현재 authored mLua/모델/StateSet/DataSet·CSV, Global 모델·설정·충돌그룹, map/ui. Maker 자동 .codeblock/.directory 및 문서는 포함하지 않는다. 이 표는 변경 목록이 아니라 검증 대상 전체의 지문이다.
- 묶음 계산: 아래 표 순서(경로 ASCII/JS sort)로 각 행을 경로 + TAB + sha256 + LF로 연결한 UTF-8 문자열의 SHA-256.
- Bundle SHA-256: 8be49440a9ebbda62fc38df333fb09673db66d2e60a8f873aa38012d7b505e21.
- v3 영구 제품 변경: RootDesk/MyDesk/Managers/MonsterManager.mlua (아래 지문). CSV는 위 원본 지문으로 복원됐다. v2 제품 변경 이력은 앞 절 및 현재 원장 매핑을 따른다.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | bae907a8acecd4aafe8d8c97681facdfb36ba17f36461b718d75dc0b92b142fd |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | da35d0645b2658521d9229b59bb7e4023934bb331cc1e19123dec59b433c55ff |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 9265965f9d6a30920e6675068e0e9c4d2bcafc674340268dbf0fe72c75c49af9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | c76bd5d51d9bebbed532f17c67daab28982487e243213b53c67f7be7e4e7aa3b |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 874b96b0a5af7d8be282ff53ba1162cf516cba75270bb2ab660e5c2eb09ef990 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |


## 2026-10-29 coder QA-F01 수정·기본 검증 인계

### 범위·원인·실제 변경
- 담당: 독립 coder /root/combat_core_coder_v4. 사용자 현재 재개 요청에 따라 같은 2단계 승인 범위의 CombatCore-QA-F01(R02/V02/CombatFoundation-F07)만 수정했다. 이전 독립 QA의 FAIL 기록은 보존한다. 이 절의 결과는 coder 기본 검증이며 새 독립 QA나 사용자 수락이 아니다.
- 실제 연결: maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder root id·TileMapMode=0 일치. runtime contexts server_main/client 확인.
- 제품 변경은 RootDesk/MyDesk/Player/PlayerCombatComponent.mlua의 CalcDamage 한 곳이다. 보너스·DEFENSE 합성 후 정수 내림한 피해에 현재 몬스터의 남은 정수 HP 상한을 적용해 native HitEvent 이전 최종 피해를 확정했다. 몬스터 HP를 직접 추가 차감하거나 HitEvent/Damages를 사후 수정하지 않았다. HP 단일 소유자·사망 전환·원래 개별 타격 예약은 그대로다. Maker 한정 cap 발생 [VRF] 로그를 추가했다.
- 소스 근거: AttackComponent.d.mlua의 CalcCritical 기본false, 현재 PlayerCombatComponent에는 CalcCritical override가 없다. GetDisplayHitCount 기본1인 현행 native 개별 타격 경로를 유지했다. 치명타 시스템·수동 피해/사망 프레임워크를 새로 만들지 않았다. PlayerComponent의 기존 음수 HP 사망 처리도 변경하지 않았다.
- 새 스킬/모델/맵/UI/DataSet/CSV/설정 변경 없음. 52개 기준 파일 비교에서 이 mLua 1개만 달라졌고 나머지 51개 byte 동일. 10타·범위3×1·HitInterval.045·기본Weapon1·이동/복귀6·점프.5/.8·4버튼은 보존했다.

### 실제 기본 검증 (한 통합 Play + 필수 Stop 재진입)
- edit에서 패치→maker_refresh_workspace 성공→build 오류0/경고0(동적 참조 Info79)→Play. 실제 keyboard_input W로 수동 공격을 실행했다. 각 조건의 HP/WeaponAttack/보너스·DEFENSE·배치는 Play 내부 fixture이며 제품 데이터가 아니다. 보너스 부여 자체는 GrantCounter 논리 프로브, 공격 수락은 실제 W로 구분한다.
- 로그 시각 2026-10-29 21:13~21:15. 네이티브 HitEvent.TotalDamage와 각 이벤트 Damages 합계를 실제 읽고 단일 Health의 HP delta와 대조했다. 모든 아래 타격의 IsCritical=false 관측. 화면에서 숫자가 읽히는지·die/효과가 자연스러운지는 이 계측으로 PASS 처리하지 않는다.

| 조건 | 실제 HP 감소 / TotalDamage 합계 / Damages 합계 | 추가 근거 | 기본 결과 |
| --- | --- | --- | --- |
| QA-F01 원재현 HP5·Weapon10 | 5 / 5 / 5 | cap10→5, native 1타·DeadEvent1회·DEAD, 나머지 타격 제외 | PASS |
| 후속 치명 HP25·Weapon10 | 25 / 25 / 25 | native10,10,5의3타·DeadEvent1회, 이후 제외 | PASS |
| 비치명 HP5000·Weapon10 | 100 / 100 / 100 | 원래10타·각10·사망0 | PASS |
| 비치명 보너스×2.2·Weapon10 | 220 / 220 / 220 | 10타 전부22·사망0 | PASS |
| 실제 DEFENSE·보너스·Weapon7.5 | 150 / 150 / 150 | 첫 경감6, HIT 뒤 후속16×9, 기존 전환 보존 | PASS |
| Weapon0 | 0 / 0 / 0 | native0피해10타·사망0·HP5000 유지 | PASS |
| DEFENSE 치명 HP5·보너스·Weapon7.5 | 5 / 5 / 5 | 경감 계산6→최종5, native1타·DeadEvent1회 | PASS |
| 위 사망 뒤 native 공격/예약 재호출 | 추가0 / 추가0 / 추가0 | extraHits0·HP0·deaths1·DEAD 유지 | PASS |

- fixture HitEvent/DeadEvent 핸들러를 명시 Disconnect하고 fixture 참조 해제. W는 tap/up 종료. 사용자 로그 clear 없음. 이 통합 회차 normal 오류0/경고0, Play 뒤 build 오류0/경고0을 다시 확인했다.
- actual Stop→다음 actual Play(21:16:01)에서 ready=true, WeaponAttack1, count10, HitInterval.045, range3×1, CounterReadyfalse, fixture nil, Monster AttackInterval3, Enabletrue, ActionRate1 확인. 이 재진입은 시험값/핸들러가 다음 세션에 남지 않는 양성 근거다.
- 최종 actual maker_stop 성공 뒤 maker_get_current_map=map01/edit 확인. Maker 사용 종료.

### 한계·다음 담당
- 독립 tester는 새 버전에서 QA-F01 원재현·후속 치명·DEFENSE/보너스·0피해·단일 사망/후속 제외를 재검증한다. 변경이 없는 다른 V 전체를 이번 개발 회차에서 다시 실행했다고 표시하지 않는다. 일반/특수/패링/가드의 플레이어 피해 경로는 이번에 변경하지 않았으며 이전 QA 근거와 구분해 독립 QA가 필요한 영향을 판단한다.
- 사용자 V11의 실제 PC/모바일 화면·터치·음향·피격/die 체감과 기존 NOT_RUN은 그대로 남는다. CF-F07은 수치 기본 확인만 추가됐으며 독립 QA/실제 연출 평가 전 종결하지 않는다. 스킬 원장 해당 PAJ/MHP 행은 OPEN 유지.
- 3단계·Features 완료 이관·Plan/WR/run 삭제·commit/push/배포는 하지 않았다.

### 2026-10-29 최종 제품 버전 묶음
- 이전 2026-10-25 묶음의 동일 52경로를 같은 순서로 byte SHA-256 계산했다. 문서·Maker 자동 .codeblock/.directory는 포함하지 않는다. 이는 변경 목록이 아닌 전체 검증 대상 지문이다.
- 계산법: 표 순서의 경로 + TAB + sha256 + LF를 연결한 UTF-8 문자열의 SHA-256.
- Bundle SHA-256: e8a20728629878e7ac584065a9c80b9a8a7149b6f05e8fb9a04a2d1906329a49.

| 경로 | SHA-256 |
| --- | --- |
| Global/CollisionGroupSet.collisiongroupset | c6a33dc595d425728b980c9cf72c0a80bd45083f46c551132e5b2e685a946c0c |
| Global/CustomFontGroupSet.config | 3c7e40e9602860125192282e447b4a6bc311f8eac634e8e7b8ef77f80615ccc5 |
| Global/DefaultPlayer.model | e3bc65e512b3584965b998450e1cf3d678b363d286dd2f7cc90e357396b9f31d |
| Global/WorldConfig.config | dc16d685bba16467b68dafeab8a21a1277f3c0cc5cca7d8cd723ea3bbbaf86e1 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.csv | 4d7bf5cf7d6a5482b9177c079a9b9bb807a24d097a61a62b1a1a20c358d261a7 |
| RootDesk/MyDesk/@Assist/DataSet/AssistModel.userdataset | 27953aadbc211679672a8dfc5eb9fa2f76f223aac243af95e895932af4e9cc6f |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.csv | 0b9265a2869b23de01f4edf5eebded066b6fb9f23f8643a52946f43a2bfc6983 |
| RootDesk/MyDesk/@Assist/DataSet/AttackSkillData.userdataset | e22d0b765e17c629eed9661ee9735d12ff4c7326257cc50e96037942e04adeb7 |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.csv | fa7be991121754a53d752a73912368124fc73647934d2f3072f6be0a4974363f |
| RootDesk/MyDesk/@Assist/DataSet/CombatRuleData.userdataset | 2ad214ba74aa111fba2c0975913ce7be376c004771b468c21dc3c001f75620b2 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | cd87d73d7d79cab23ced404e1ac989c5548e643a65482959d9fb97bd353ca7ed |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | bae907a8acecd4aafe8d8c97681facdfb36ba17f36461b718d75dc0b92b142fd |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | da35d0645b2658521d9229b59bb7e4023934bb331cc1e19123dec59b433c55ff |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 9265965f9d6a30920e6675068e0e9c4d2bcafc674340268dbf0fe72c75c49af9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 7b78fa679702b47f867bd5e0bf14e2b48b95baa782108468c01a32e8fa4dadbc |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeGizmo.mlua | 96d2d66ccdc13300ad879f3327cf64cc68495c63fe11384a1be39e0a19c2dc53 |
| RootDesk/MyDesk/Player/@Assist/AttackRange/AttackRangeTuner.mlua | ef5736711550c7f647d767ee08296beb8366df9cb8bce6f5cc9b5100cd544a9a |
| RootDesk/MyDesk/Player/@Assist/Skill/PlayerSkillEffectTable.mlua | 5127ff02cf93c65e92837b46716c371cd6c89f78b985165b90e1a5ca6a0f8845 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateControl.mlua | 1bf98ade664f48f2263c791520e30f03a7eb54545bf7ac7fef7ff7d60eb1de86 |
| RootDesk/MyDesk/Player/@StateControl/PlayerStateSet.stateset | 1e02d40cef0870718aaca2645f8d65e630d2f57fbca5b9970e27c0be3c83ce52 |
| RootDesk/MyDesk/Player/@StateControl/Player_Attack.mlua | a450fed1c16ebee0ca6b06cde326fe8af23ac3c05101202d2b16bae47045d772 |
| RootDesk/MyDesk/Player/@StateControl/Player_Guard.mlua | fa140dbdd70352876af80555417cbf58a849ae6a0e250d536a34875c714cf02f |
| RootDesk/MyDesk/Player/@StateControl/Player_Move.mlua | 8a4ac39d4ee33f12199be95d3663123698876ff51badbfebc5870c762063b9c0 |
| RootDesk/MyDesk/Player/PlayerCombatComponent.mlua | ebbe5f75a580523619c35729f4965ea170deef0e82b8cbc4f2443d229f90d612 |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua | ae130137842bb0b0a74020b2adc395e6750f25b4a72f736a9f08bcb72b241e50 |
| RootDesk/MyDesk/Player/PlayerGuardComponent.mlua | 297f85f1b2754bb2fe5fc28d0820f39147e7293fbda29f4c377a4a64c227596f |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 874b96b0a5af7d8be282ff53ba1162cf516cba75270bb2ab660e5c2eb09ef990 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |
