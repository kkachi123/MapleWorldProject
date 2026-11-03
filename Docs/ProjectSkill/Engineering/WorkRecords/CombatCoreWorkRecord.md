# CombatCore — 임시 작업 기록

- 연결 Plan: [2_CombatCore](../Plans/2_CombatCore.md).
- 상태·갱신일: 2026-11-03 / 최신: coder V11-F06 구현·기본 검증 인계(맨 아래 절, 새 Bundle b985aa4b…74dbf 54경로, 독립 tester QA5·reviewer 대기). 그 전(2026-11-02): 독립 QA 4회차 V11-F01~F05(QA 기록 첫 절, Bundle d2b57802…0fbb 54/54 전후 일치, 수치·로그 PASS·육안 일부 NOT_RUN, 독립 reviewer 대기). 그 전: coder V11-F01~F05 구현·기본 검증 인계(맨 아래 절, 새 Bundle d2b57802…0fbb 54경로). 아래는 그 이전 상태 — coder REV-F01 수정·기본 검증(커밋 6614b20 / Bundle 1ac324e6…9de4), 독립 tester 3회차 수치 PASS, 독립 리뷰 WAITING. 사용자 V11 대기. 2026-10-29 QA2·리뷰와 그 이전 기록은 이전 버전 근거.
- 실행: [20261020-combat-core](../../../../.pipeline/20261020-combat-core/run.md).
- 삭제 조건: 승인된 범위 구현·필수 확인·결과/미완료 추적 이관·링크 정리 완료 후 삭제. 사용자 직접 확인이 남으면 유지한다.

## 현재 재개 지점

2026-11-02 사용자 재개 명령에 따라 msw-coder가 REV-F01을 최소 수정·기본 검증했고(커밋 6614b20 / 52파일 Bundle 1ac324e6…9de4, 아래 2026-11-02 개발절), 별도 msw-tester가 같은 Bundle에서 독립 QA 3회차 수치 PASS, 별도 msw-reviewer가 WAITING을 판정했다(각각 QA 기록·리뷰 기록 첫 절). 최종 map01/edit·Maker 사용 종료·제품 지문 전후 동일 확인. DOC-01 현황·링크 동기화는 2026-11-02 planner가 정리했다. 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다. 남은 필수: V11, CF-F07 실제 연출 평가(수치 근거만 확보), V12 외부 환경과 기존 외부 후속 ID. 결함 경과: QA-F01은 QA1 FAIL→QA2 수치 PASS, REV-F01은 2026-10-29 리뷰 지적→QA3 수치 PASS·리뷰 해소. 과거 FAIL과 이전 버전 QA/리뷰는 당시 근거로 보존한다. P01b~P06은 🟡 유지, 3단계 미시작. V11 때 함께 볼 범위 밖 관찰: 플레이어 사망 직후 HP 문자 음수 표시 가능성(새 규칙 아님, 처리 여부는 3단계 계획 후보).

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

### 2026-11-02 독립 QA 4회차 — V11-F01~F05
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA/QA2/QA3의 PASS는 이번 실행으로 세지 않았다.
- 대상: coder 커밋 1447ff8 / 54경로 Bundle SHA-256 d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb. 시험 전·후 54/54 byte 일치(Bundle 재계산 동일, git status 제품 변경 없음). 계산은 coder 절의 manifest·방법을 그대로 썼다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. 기준 build 로그 80건 모두 Info(오류·경고 0). Play context server_main/client. Maker 로그 시각 23:09~23:22. TileMapMode는 기존 기록(0)을 따르며 이번에 MapBuilder를 다시 읽지 않았다.
- 실행 방식 구분: (B) 실제 입력 = maker_keyboard_input(LeftArrow/RightArrow/DownArrow/UpArrow 실제 키 이벤트), maker_mouse_input(UI 버튼 누름·홀드). (A) 서버 프로브 = maker_execute_script로 패턴 목록을 단일 행으로 교체해 `StateComponent:ChangeState("ATTACK")`로 공격 시작, 플레이어 GUARD는 서버 `ChangeState("GUARD")`(패링 창 안 시점 맞춤), 저스트 회피는 `PlayerEvadeComponent:SetEvading`+`EvadeDirection`, 피격·사망은 `HitComponent:OnHit`(네이티브 HitEvent 경로), 팝업은 클라이언트 `_UIPopup:Open/Close`, 슬로우는 `MonsterStateControl:ApplySlow`. 판정(EvaluateDefense)·피해·그로기 진입·복귀·클립 전환·칸 표시는 모두 제품 경로이며 프로브는 시작 트리거와 관찰만 맡았다. 클라이언트에서는 AnimationClipEvent(clip 이름과 ActionSheet RUID), 칸 컴포넌트(AttackAreaMarkComponent._T.shown), TelegraphCells 동기값, 로컬 플레이어 상태를 폴링해 기록했다.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 다음 Play 기준값 확인): AttackInterval 9999, 패링 창 0.9(DownArrow 실제 홀드 패링), 반격 창 6초·그로기 4초/9초, 슬로우 0.02배·60초(칸·팝업 화면 확인용), 몬스터 HP·시험용 즉사 피해 999. 중간 복원 후 사용했다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| F05 뒤 회피형 (normal/special/parry.left) Pos1(x=-1.50) 실제 LeftArrow 홀드, 서버 상태 MOVE | B+A | 3패턴 모두 판정 순간 plx=-1.50 / pst=MOVE, 네이티브 피격 없음, HUD feedback=EVADE, HP 감소 0 / HitEvent 합계 0 | PASS |
| F05 앞 회피형 (normal/special/parry.right) 같은 조건 | B+A | 3패턴 모두 네이티브 피격 있음, kind HIT, HP 감소 12 / HitEvent 12 | PASS(기대 HIT) |
| F05 가드형 (normal.guard, parry.guard) 같은 조건 | B+A | 두 패턴 HIT, HP 감소 12 / 12(가드 없음) | PASS(기대 HIT) |
| F05 예고 시작 뒤 방향 전환 | B(실제 RightArrow·LeftArrow, 서버가 MOVE 수락 순간 정확히 시작) | normal.right+RightArrow → 판정 시 x=+1.50, EVADE, HP 0 / 0. normal.left+LeftArrow → x=-1.50, EVADE, HP 0 / 0. 플레이어 Scale.x는 모든 이동에서 1.0 그대로라 시작 시 Scale 기준 검증과 판정 콜라이더가 어긋날 여지가 관측되지 않았다 | PASS |
| F05 UI 버튼 경로 | B(실제 mouse 홀드) | 뒤 버튼 누름(ButtonState Pressed)→클라이언트 MOVE→normal.left 판정 시 x=-1.50, EVADE, HP 0 / 0. 앞 버튼 누름은 x=1.50 MOVE·복귀 확인. 가드 버튼 누름은 GUARD 진입·해제 확인 | PASS(아래 좌표 관찰 별도) |
| F05 입력→서버 수락 지연(키·UI 공통) | B | 클라이언트 MOVE 진입 시각 대비 서버 MOVE 관측 시각 차 0.065~0.079초(키 3회, UI 1회, 서로 다른 시계라 지시용 값, 샘플 타이머 0.01초 포함). 수백 ms 단위 지연은 관측되지 않음 | PASS(지시 수준) |
| F02 패링 → 복귀 → 그로기 1.5초 → IDLE | B(실제 DownArrow 홀드 + 패링 창 0.9) | 시작 x=3.00 → 판정 PARRY 피해 0, 판정 순간 x≈0.0~0.1 → 복귀 중 상태 ATTACK(isStunned false, 별 표시 없음, jump=true) → 복귀 완료 시점에 x=3.00 STUN, GroggyRemaining 1.50, stun 진입 로그 FinishAttack 호출 → 1.5초 뒤 IDLE. 그로기 길이는 전투 시계 1.50/1.51초. 접촉 시 추가 타격 없음 | PASS |
| F02 반격 창 | B+A | 성공 시점(clock 344.493)부터 until 346.493 = 2.0초. 복귀 시간만큼 그로기 구간이 줄고 창 종료 시 CounterReady false | PASS |
| F02 다음 공격 Home 시작 | A | 그로기 종료 IDLE 위치 x=3.00(Home)이고, 이후 시작한 모든 공격이 x=3.00에서 시작(x=2.90 점프 시작) | PASS |
| F02 복귀 중 슬로우 | A | 복귀 중 슬로우(2초 ×0.5) 적용 → STUN 진입이 판정 후 +0.90초(0.1초 정상 + 나머지 0.4 가 두 배)로 늘어남. 그로기 deadline은 진입+1.5로 슬로우와 무관(맵 전투 시간), IDLE까지 1.51초 | PASS |
| F02 복귀 중 팝업 | A(실제 _UIPopup) | 복귀 중 x=1.23에서 정지, 약 11초 동안 clock·x 불변(server paused=true). Close 뒤 복귀를 이어 가 x=3.00 STUN(deadline=재개 후 복귀 완료+1.5), 반격 창은 전투 시간만 흘렀다 | PASS |
| F02 복귀 중 피격 | A(OnHit 5) | 서버 상태 ATTACK 유지(HIT 아님), HP 100→95, 복귀 계속 후 STUN 진입. 클라이언트에는 HIT 클립 이벤트가 한 번 나온다(아래 관찰) | PASS(서버 규칙) / 관찰 있음 |
| F02 복귀 중 사망 | A(OnHit 999) | 즉시 DEAD, STUN·그로기 진입 없음(isStunned false, stunDeadline -1), 별·칸 없음, 이후 2.5초 resolutionCount 변화 없음 | PASS |
| F02 복귀 중 Stop | B(실제 maker_stop) | 팝업으로 정지된 복귀 중(x=1.25) Stop → 다음 Play에서 몬스터 IDLE, stunned false, GroggyRemaining 0, ParryEffect (0,0,0), pause false, counter false, 칸 000, 규칙 기본값 | PASS |
| F04 STUN 동안 hit 클립 | A(제품 STUN 진입 경로) | STUN 진입 순간 클라이언트 AnimationClipEvent clip=stun ruid=aec950…(주황버섯 ActionSheet hit와 같은 RUID)를 패링 시험 매 회(9회) 관측. 복귀 중에는 stun 클립이 나오지 않았다(clip=jump는 서버 SetVisualClip 경로, 이벤트 없음) | PASS |
| F04 종료 후 stand | A | 그로기 만료 IDLE에서 clip=stand ruid=96e955…를 매 회 관측 | PASS |
| F04 그로기 중 피격 | B(실제 UpArrow)+A | 실제 UpArrow 공격 10타(반격 factor 2.2) 중 서버 상태 STUN 유지·GroggyRemaining 계속 감소·deadline 만료 시 IDLE, HP 100→80. 클라이언트는 로컬 상태 HIT가 되며 clip=hit ruid=aec950…(stun RUID와 동일)가 한 번 발생. RUID가 같아 화면 클립 변화는 없으나 같은 클립이 다시 재생(처음부터)되는지는 로그로 구분 못 함 | PASS(RUID 근거) / 재생 재시작 NOT_RUN |
| F04 사망 시 die 우선 | A | 예고 중·복귀 중·그로기 중 사망 모두 clip=hit 직후 같은 프레임에 clip=die ruid=65a2bf…, 최종 DEAD, isStunned false(별 제거) | PASS |
| F01 8패턴 칸 = 서버 영역 | A+자연 공격 | TelegraphCells(서버)·클라이언트 칸 표시 일치: left 3패턴 011, right 3패턴 110, guard 2패턴 111(서버 영역 left -0.5~2.0, right -2.0~0.5, guard -2.0~2.0). 처음 자연 공격 13회(칸·영역 로그)에서도 동일. 칸은 동기값 수신 1프레임(≈0.03초) 뒤 켜짐 | PASS |
| F01 예고~판정 사이 유지, 판정 뒤 꺼짐 | A+B | 각 공격에서 TelegraphCells 설정과 같은 프레임대에 칸 on, 판정 직후 sync 비워지면 칸 off(0.03초 이내) | PASS |
| F01 슬로우 | A | 슬로우 0.02배로 예고가 25초로 늘어나도 칸 011이 계속 켜짐, 슬로우 0.5배에서 예고 0.5→1.0초 | PASS |
| F01 팝업 | A(실제 _UIPopup) | 예고 중 팝업: TelegraphRemaining 1.51→1.458(정지 반영 직전 값), 3초 동안 변화 없음·칸 011 유지·몬스터 위치 불변. Close 뒤 같은 실행이 이어져 칸 유지(rem 0.21) | PASS |
| F01 사망 | A | 예고 0.23초 시점 사망: 서버 TelegraphCells·Response 비움, snapshot nil, 판정(Resolve) 없음, 클라이언트 칸 011→000(0.03초), 상태 DEAD | PASS |
| F01 Stop | B | 복귀 정지 중 Stop 뒤 새 Play에서 칸 표시 000(클라이언트 _T.shown 3칸 false) | PASS(예고 중 Stop 단독 시험은 없음, 복귀·정지 중 Stop과 Stop→재Play 기준값으로 확인) |
| F01 스크린샷 칸 위치·색 | B | 예고 중(slow 시험값) 558×314 캡처에서 normal.left(011) 때 BattlePos2·3 위치에 반투명 빨강/주황 사각이 보이고 BattlePos1에는 없음. 몬스터 높이대와 맞음. 마크 3개 컴포넌트 값 pos x=-1.5/0/1.5, y=0.98, scale 25(1.0×1.0), MapLayer0 order 1 확인 | PASS(저해상도, 색·가독성 평가는 V11) |
| F03 패링 성공에만 접촉 파티클 1회 | A+B | PARRY 판정마다 `parry effect serial=N x=0.0 y=0.981` 한 번씩(패링 9회: serial 1,3,5,7,9,11,13,14,18, 별 serial과 짝 번호) 관측. GUARD(HP 4), 저스트 JUST, 일반 HIT(8패턴 포함)에서는 parry effect 로그와 그로기가 없었다 | PASS |
| F03 별 크기·높이 표시 | B | 그로기 9초 시험 중 캡처에서 몬스터 위쪽에 작은 청색 점/스파크가 희미하게만 보임(높이는 머리 위로 넉넉). 크기·가시성은 이 해상도에서 판정 불가 | NOT_RUN(육안 판정은 V11 사용자) |
| F03 접촉 파티클 육안 | - | 순간 효과라 도구 왕복 시간 안에 캡처하지 못함. 로그(재생 serial)만 근거 | NOT_RUN(육안은 V11) |
| F03 팝업·사망·Stop 뒤 잔존 | A+B | 그로기 중 사망 시 isStunned false(별 제거 경로), 복귀 중 팝업 뒤 Stop → 재Play 기준 ParryEffect (0,0,0)·별 없음. 시각 잔존은 로그·상태값 근거, 화면 확인 없음 | PASS(상태·로그 근거) |
| 회귀 V01 | A+B | 8패턴 예고↔영역 일치(F01 행), HUD feedback 문구 EVADE/HIT/GUARD/PARRY/JUST가 판정과 일치 | PASS(대표) |
| 회귀 V02 | A+B | HP 감소=HitEvent 합계: 무가드 12/12(앞 회피·가드형 12회), 가드 4/4, 패링·저스트·뒤 회피 0/0. 가드 12×0.4=4.8→4 | PASS |
| 회귀 V03 | A+B | 패링 창 0.2 안(판정 0.086~0.10초 전 가드 시작) PARRY, 창 밖(1.0초 전 홀드) GUARD, 저스트 RIGHT 0.09초 전 SetEvading JUST(슬로우 1회), 다른 방향·전부 범위 밖 EVADE 0피해 | PASS(대표 경계, 전체 경계 열 재실행 아님) |
| 회귀 V04 | B | 패링 뒤 실제 UpArrow: manual cast count=10 factor=2.2, 즉시 CounterReady false(소비), HP 100→80. 창이 끝난 뒤 UpArrow는 factor=1 | PASS(대표) |
| 회귀 V05 | A | 슬로우 시 예고 0.5→1.0초, 복귀 +0.9초, 그로기는 맵 전투 시간 1.5초. 슬로우 만료 후 IDLE 정상 | PASS(대표) |
| 회귀 V06 | B+A | 그로기 중 피격에서 서버 STUN 유지·조기 해제 없음·deadline 만료로 IDLE | PASS(대표) |
| 회귀 V07 | A | 예고 중·복귀 중 팝업 정지·재개 | PASS(대표) |
| 회귀 V08 | A+B | 예고·복귀·그로기 중 사망, 복귀 중 Stop→재Play 기준 확인. 플레이어 사망·다른 맵 전환은 실행하지 않음 | PASS(대표) |
| 회귀 V09 | - | 이번 Play마다 `catalog ready rules=1 patterns=8` 로드, CSV 변경 시험 없음 | PASS(로드만) / CSV 변경 NOT_RUN |
| 회귀 V10 | B | 실제 Left/Right/Down/Up 키, 실제 mouse로 뒤·앞·가드·공격 버튼 | PASS(대표) |
| V11(사용자 직접) / V12 외부 / CF-F07 연출 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- UI 버튼 좌표 관찰: 뒤·앞 버튼은 시뮬레이터에서 UI 좌표상 중심(790/1130, y 110~180 및 x=760~790 구간 반복 시도)에서 ButtonStateChange(Pressed)가 오지 않았고 x=805·1115, y=170에서만 Pressed가 왔다. 가드(960,180)·공격(960,340)은 중심에서 정상이다. 앞서 QA1도 첫 버튼 가장자리 무반응을 좌표 조건으로 기록했다. 제품 결함인지 시뮬레이터 좌표 재매핑 때문인지 이번 근거로 구분하지 못했다. 사용자 실기기(V11)에서 좌·우 버튼 전체 면적이 눌리는지 확인이 필요하다. 이것으로 F05 UI 경로 PASS를 취소하지 않았다(누름이 입력되면 판정까지 정상).
- 클라이언트 HIT 신호: 복귀 중·그로기 중 피격에서 서버 상태는 ATTACK/STUN을 유지하지만 클라이언트 로컬 상태가 HIT가 되고 clip=hit가 발생한다. 그로기 중에는 hit와 stun RUID가 같아 화면이 같고 복귀 중에는 jump 클립이 hit 클립으로 바뀔 수 있다(이 변경 이전부터 있는 구조, 이번 변경으로 새로 생긴 것으로 판단하지 않음). 화면 확인은 하지 않았으며 reviewer·사용자 판단 대상이다.
- 시험 오류(제품 오류 아님): (1) 첫 G 회차는 이전 snapshot 잔존으로 트리거 시각이 어긋나 무효, 같은 조건을 snapshot 시퀀스 확인으로 고쳐 G2로 다시 실행한 결과만 사용했다. (2) V4 첫 회차는 서버 GUARD 상태 중 UpArrow가 입력돼 거부되어(factor 로그 없음) 무효, 그로기 구간에 맞춰 V4b로 재실행했다. (3) 첫 저스트 프로브는 EvadeDirection을 SetEvading 앞에 줘서 방향이 초기화돼 HIT, 순서를 고쳐 JU2에서 JUST를 확인했다. (4) J2(예고 중 사망) 첫 결과는 로그를 읽기 전에 clear_logs를 호출해 잃었고, 새 몬스터로 같은 조건을 A 회차로 다시 실행한 결과만 사용했다. (5) 시험 시작 시 clear_logs를 호출해 이전 Play의 normal 로그 36건이 지워졌고(사용자 로그 보존 대상 확인 없이 호출함) 이후 회차 사이에도 호출했다. build 로그는 지우지 않았다.
- 제품 runtime 오류·경고 로그는 관측되지 않았다.
- 사망 직후 반격 권한(CounterReady)은 사망 직후 로그에 true였다가 2.0초 창이 끝난 뒤 false였다. 사망 시점에 즉시 소멸하는지는 이번에 구분하지 못했다(사망은 PlayerCombatComponent.ClearCounter 호출 경로가 RefreshDuelPlayer에 있어 소스상 소멸 예정, 로그로는 미확인).

#### 사용 종료
- 모든 키·마우스 up. 서버·클라이언트 프로브 타이머는 완료 시 해제, 나머지는 Stop으로 폐기. 시험값(AttackInterval, 패턴 목록, 규칙 창, 슬로우, HP)은 Play 내부뿐이며 Stop→재Play에서 기준값(interval 3.0, dmg 12, patterns 8, 규칙 .2/.4/2.0/2.2/1.5/2.0×0.5, HP 100, pause false)을 확인했다. 최종 maker_stop 성공, maker_get_current_map map01 / edit, Maker 사용 종료. 시험 후 54/54 동일 Bundle d2b57802…0fbb.
- 다음은 독립 reviewer: 위 PASS/NOT_RUN과 실행 방식 구분(A 서버 프로브 vs B 실제 입력)·한계를 같은 Bundle에서 대조한다. 사용자 V11에서 F01~F04 체감, 별·접촉 파티클 가시성, 좌·우 UI 버튼 전체 면적, 복귀 중 피격 화면을 확인한다.

### 2026-11-02 독립 QA 3회차 — REV-F01
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA/QA2의 PASS를 이번 실행으로 세지 않았다.
- 대상: coder 커밋 6614b20 / 52파일 Bundle SHA-256 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4. 시험 전·후 manifest 52/52 byte 일치(Bundle 재계산 동일, git status 제품 변경 없음). 이전 e8a20728…a49 대비 변경은 MonsterAttackComponent.mlua:134, PlayerHealthComponent.mlua:38이며 두 파일을 소스로도 읽어 확인했다.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록 0(MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. 재개 전 build 로그는 coder 갱신본(Info 79, 오류·경고 0)을 그대로 사용했고 이 회차에서 refresh하지 않았다. Play context server_main/client. Maker 로그 시각 19:11~19:20, 오류/경고 로그 0(normal 전체 Info만).
- 실행 방식 구분: (A) 서버 프로브 = 지정 패턴 1행 임시 교체(`_CombatRuleCatalog.patterns`), 몬스터 AttackInterval 일시 상향, 몬스터 `StateComponent:ChangeState("ATTACK")`로 공격 시작, 플레이어 가드는 서버 `ChangeState("GUARD")`, 저스트는 `PlayerEvadeComponent:SetEvading`+`EvadeDirection` 부여. 판정(EvaluateDefense)·피해(CalcDamage→ResolveIncomingDamage)·native AttackFast/HitEvent·HP는 제품 경로이며 HitEvent는 플레이어 엔티티 핸들러로 TotalDamage와 Damages 합계를 읽었다. (B) 실제 입력 = maker_keyboard_input의 DownArrow/RightArrow/LeftArrow/W 실제 키 이벤트가 클라이언트 PlayerInputComponent→PlayerStateControl→서버 상태 진입까지 이어진 경로. 서버 스크립트는 "방어 입력이 서버에서 수락된 순간"에 몬스터 ATTACK을 시작시키는 시험 트리거만 맡았고 방어 상태·시작시각은 실제 입력이 만들었다. 모든 시험값(AttackDamage, 패턴, 간격, WeaponAttack, 몬스터/플레이어 HP, 패링·저스트 창)은 Play 내부에서만 바꿨고 Stop→다음 Play 기준값(dmg12/interval3/rows8/가드.4/패링·저스트 .2/Weapon1) 확인으로 폐기를 확인했다.

| ID·조건 | 방식 | 실제 결과 (HP delta / HitEvent.TotalDamage / Damages 합계) | 판정 |
| --- | --- | --- | --- |
| REV-F01 무가드 일반 (12.7) | A | 12 / 12 / 12, kind HIT | PASS |
| REV-F01 특수 무가드 (12.7) | A | 12 / 12 / 12 | PASS |
| REV-F01 특수+가드 홀드 (12.7) | A(서버 가드) + B(DownArrow 실제 홀드, special.left) | A 12/12/12, B 12/12/12 (kind HIT) | PASS |
| REV-F01 일반 가드 (12.7) | A(normal.guard·normal.left) + B(DownArrow, normal.guard) | 모두 5/5/5, kind GUARD rate .4 (구 코드 기대 4와 구별) | PASS |
| REV-F01 패링 공격 실패 가드 (12.7) | A 가드 시작 hit-1.13s·hit-0.254s(창 밖) + B DownArrow, 가드 시작 hit-.52s·기본 창 .2 | 모두 5/5/5, kind GUARD | PASS |
| REV-F01 유효 패링 성공 (12.7) | A 가드 시작 hit-.103s + B DownArrow, 시험 한정 ParryWindowSec .9(손 타이밍으로 .2 창 불가) | A·B 모두 0/0/0, kind PARRY, native 이벤트 1건 0피해 | PASS (B의 창 폭은 시험 값) |
| REV-F01 유효 저스트 회피 (12.7) | A SetEvading RIGHT(텔레그래프 잔여 .12s 이하에서 부여, 시작시각 직접 미계측, native 이벤트 1건) + B RightArrow 실제, 시험 한정 JustWindowSec .9 | A 0/0/0 kind JUST. B kind JUST, 플레이어가 x=1.5로 이동해 범위 밖이므로 native HitEvent 없음, HP delta 0 | PASS (B는 범위 밖 회피, 창 폭 시험 값) |
| 저스트 방향 불일치 (12.7, 보조) | A SetEvading LEFT + B LeftArrow 실제(RIGHT 예고) | A 12/12/12 HIT. B 플레이어 x=-1.5, native HitEvent 1건 12/12/12 | PASS (보조, 방향 일치 필수 경계 불변) |
| 다른 소수 보조 | A | 7.5 가드 3/3/3(구 선내림 2), 12.99 가드 5/5/5·무가드 12/12/12, 13.99 특수+가드 13/13/13, 0.9 무가드·가드 0/0/0(native 이벤트 1건 0피해) | PASS |
| 기본12 회귀 | A | 무가드 12, 가드 4(12*.4=4.8 내림), 특수+가드 12, 패링 0, 저스트 0 (각 HP=TotalDamage=Damages) | PASS |
| QA-F01 회귀 몬스터 처치 상한 (HP5, Weapon10) | B 실제 W (몬스터·플레이어 HitEvent 핸들러, Weapon10은 Play 내부) | 몬스터 HP 5→0 감소 5, HitEvent 1건 TotalDamage 5, Damages 5, IsCritical 0, DEAD 전이 1회 | PASS(수치) |
| QA-F01 후속 치명·후속 제외 (HP25, Weapon10) | B 실제 W | HP 감소 25, HitEvent 3건 합계 25(10,10,5), Damages 25, DEAD 1회. 10타 예약 중 사망 후 추가 이벤트 없음 | PASS(수치) |
| 플레이어 사망 경계 (HP5, D12.7, 무가드) | A 몬스터 ATTACK | 5→-7, delta 12, 이벤트 1건 12/12, IsDead true, DEAD 전이 1회 (플레이어 쪽 HP 하한 없음은 기존 범위 밖 관찰과 동일) | PASS (경계만, 별도 표시) |

#### 판정 요약
- 기준 1 (소수 12.7 HP delta=TotalDamage=Damages 합계: 무가드·특수/가드홀드=12, 일반·패링실패 가드=5, 유효 저스트/패링=0): PASS. 대표 경우(DownArrow 가드, RightArrow/LeftArrow 회피)는 실제 키 입력 경로로 독립 확인했다. 패링 성공과 저스트 성공의 실제 입력은 .2초 창을 손 타이밍으로 맞출 수 없어 시험 한정으로 창만 .9로 넓혔다(창 경계 자체는 이번 변경과 무관, 기존 QA 근거 범위). 창 .2 안에서 맞춘 성공은 서버 프로브(A)로 확인했다.
- 기준 2 (기본12 가드4/특수12/성공0): PASS (서버 프로브).
- 기준 3 (QA-F01 처치 상한·사망 1회·후속 제외): PASS(수치, 실제 W).
- 기준 4 (플레이어 사망 경계): PASS(경계만). 그 외 슬로우/그로기/팝업/DataSet 로드·V01~V12의 나머지 회귀는 이번 변경(두 파일 각 1줄)과 무관해 재실행하지 않았다. 새 전수 실행으로 세지 않는다.
- NOT_RUN / 미완료: V11(사용자 직접 PC/모바일 가독성·체감·음향·피격/die), CF-F07 연출, V12 외부(실제 두 사용자·비전투 몬스터·다른 맵), 실제 mouse/touch 입력, 창 .2 안의 손 입력 패링/저스트 성공, 가드 시작이 타격 이후인 경우의 별도 관찰(그 경우는 가드 상태가 아니라 HIT로 처리됨).

#### 시험 오류·불확실성 분리
- A 회차에서 서버 `SetEvading`을 직접 호출하면 서버 MOVE epoch가 올라가 클라이언트 epoch와 어긋난다. 그 직후 같은 Play에서 시도한 첫 RightArrow 저스트(kind HIT, EvadeDirection 빈 값)는 이 시험 상태 오염이 원인이라 제품 결과로 세지 않고, Stop→새 Play에서 A 호출 없이 다시 실행한 결과(kind JUST, evadeDir RIGHT)만 사용했다. 제품 오류로 보지 않는다.
- QA-F01 두 번째 시험 첫 스크립트가 몬스터 사망 뒤 재생성(DoSpawn) 전에 시작해 죽은 개체에 Hp를 세팅했다. 해당 시도의 결과는 사용하지 않고 `MonsterManager:DoSpawn()` 후 새 개체에서 다시 실행한 결과만 사용했다. 몬스터 사망 뒤 자동 재생성이 없는 것은 기존 동작(DoSpawn은 OnBeginPlay에서만 호출)이다.
- 서버 프로브 중 몬스터 자연 공격은 AttackInterval 상향으로 막았고, 각 회차의 hit 시각·snapshot kind로 판정 로그를 분리했다.

#### 사용 종료
- 모든 키 up. HitEvent/StateChangeEvent 핸들러 명시 Disconnect, 임시 패턴/창/AttackInterval/WeaponAttack는 Stop으로 폐기. Stop→다음 Play(19:20) baseline: dmg12.0/interval3.0/rows8/가드.4/패링·저스트.2/Weapon1/몬스터 HP100 확인, 이후 maker_stop. maker_get_current_map map01 / edit 확인(전이 중 play 응답 1회 뒤 재확인), Maker 사용 종료. 시험 후 52/52 동일 Bundle 1ac324e6…9de4.
- 다음은 독립 reviewer: 위 REV-F01 수치 PASS와 실행 방식 구분(서버 프로브 vs 실제 키)·한계를 같은 Bundle에서 대조한다.

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

### 2026-11-02 독립 리뷰 — WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절과 tester QA3의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: coder 커밋 6614b20 / 52파일 Bundle 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4. reviewer가 2026-11-02 manifest 52행을 작업 트리·6614b20·13fe548 각각에서 byte SHA-256으로 재계산해 52/52 일치·Bundle 동일을 확인했다. 6614b20~1(eedeefb)에서는 두 파일만 달라 이전 Bundle e8a20728…a49가 재현된다. eedeefb..HEAD 제품 변경은 아래 두 .mlua뿐이고 나머지는 run/Plan/WR/EnvGuides 문서다. 두 .codeblock은 내용 변경 없음(Refresh 시각만 갱신).
- 판정: **WAITING**. CombatCore-REV-F01은 해소됐다(코드·QA3 근거 충족). 현재 승인 범위의 AI 측 필수 근거는 충족됐으나 사용자 직접 확인 V11과 CF-F07 실제 연출 평가, V12 외부 환경이 필수로 남는다. DOC-01은 planner 문서 정리로 남는다(제품·재검증 불요). 이 판정은 단계 완료·3단계 진행 승인이 아니다.

#### CombatCore-REV-F01 — 해소 확인
- 실제 소스: MonsterAttackComponent.mlua:134 `ResolveIncomingDamage(self.AttackDamage, attacker)`로 number 원값을 넘기고, PlayerHealthComponent.mlua:38 인자가 `number damage`, :45 `math.max(0, math.floor(damage * result.rate))`가 유일한 내림이다. D02 "합성 뒤 정수 내림·음수 0 제한"과 일치한다. 호출자는 :134 하나(Grep), 반환 integer·@ExecSpace("ServerOnly")·native CalcDamage 서명(@ExecSpace 없음) 유지, AttackDamage는 PrepareAttack에서 finite·비음수 검증 그대로다.
- 범위 밖 변경 없음: diff는 두 파일 각 1줄이며 EvaluateDefense/IsInWindow·PlayerCombatComponent.CalcDamage(QA-F01 상한)·MonsterHealth·DataSet·기본 AttackDamage=12는 byte 불변이다.
- QA3 대응(2026-10-29 리뷰의 독립 재검증 항목): 12.7 무가드=12·특수 무가드=12·특수+가드 홀드=12, 일반 가드=5·실패 패링 가드=5(창 밖 두 시점+실제 DownArrow), 유효 패링=0·유효 저스트=0, 기본12 무가드12/가드4/특수+가드12/패링0/저스트0, QA-F01 HP5·Weapon10 처치 5/5/5·DEAD 1회, HP25 10·10·5 합25·후속 제외를 같은 Bundle의 native AttackFast→CalcDamage→HitEvent·HP에서 HP delta=TotalDamage=Damages 합계로 확인했다. 항목 누락 없음.
- 실제 입력 범위의 충분성: 이번 결함은 방어 판정 결과(rate) 뒤 합성·내림 위치뿐이며, 성공 rate=0은 창 폭과 무관하게 0으로 내림된다. .2초 창 경계 코드(IsInWindow)는 byte 불변이고 경계 직전/정확/안/공격시점/직후는 QA1 V03(당시 동일 함수 내용)의 근거 범위다. QA3는 (A) 서버 프로브로 .2창 안 시작(hit-.103s 패링, 잔여 .12s 이하 저스트)의 PARRY/JUST 0피해를, (B) 실제 DownArrow/RightArrow/LeftArrow로 입력→상태→판정→피해 경로를 확인했고 (B)의 성공 창 .9는 Play 내부 시험 값으로 명시·Stop 폐기·기준값 재확인됐다. REV-F01 수락에는 충분하다. 손 타이밍 .2초 성공의 체감·가독성은 AI로 대신하지 않으며 V11에 남는다. 실제 입력 저스트 성공은 범위 밖 이동이라 native 이벤트 없음(HP 0)이고 범위 안 JUST 0피해는 (A)가 덮는다.

#### 플레이어 쪽 남은 HP 상한 부재 — 결함 아님(범위 밖 관찰)
- 관찰: 플레이어 HP5에 12.7 무가드 → Hp 5→-7, delta 12, HitEvent 12, Damages 12, DEAD 1회(QA3). QA1 V08 특수12 HP5→-7도 같은 동작이다.
- 분류 근거: V02/R02의 문자 기준은 "최종 HP 감소=HitEvent 합계=피해 숫자, 네이티브 HP 한 번 적용"이며 플레이어 쪽은 PlayerComponent.Hp가 0에서 clamp되지 않아 세 값이 12로 일치한다. QA-F01은 MonsterHealth가 이벤트 뒤 0으로 clamp해 감소5≠이벤트10이 된 경우라 성격이 다르다. D02는 "합성 뒤 내림·음수 0"만 정하고 남은 HP 상한 규칙을 두지 않는다. 따라서 승인 요구상 결함이 아니고 새 ID를 만들지 않는다. 상한을 추가하면 새 규칙이 되어 승인 범위 밖이다.
- 남는 점(현재 진행 차단 아님): CombatHpBarController.mlua:26이 `tostring(math.floor(current))`라 사망 직후 플레이어 HP 문자가 "-7 / 최대"로 보일 수 있다(막대 비율은 :24에서 0 clamp). 실제 화면 관찰은 이번 근거에 없다. 표시를 0으로 맞출지·피해를 남은 HP로 상한할지는 사용자/planner 판단 사항이며, GameDesign §4의 "플레이어 HP 0이면 한 판 종료"·승패는 3단계 범위다. V11 평가 때 사용자가 확인하거나 3단계 계획에서 다룬다.

#### 이전 근거·미실시 표시 대조
- QA2(e8a20728…a49)·2026-10-29 리뷰·QA1(8be49440…e21)은 Plan §13·WR 머리·QA3에서 이전 버전 근거로만 표시돼 있고 이번 PASS로 다시 세지 않았다. QA3의 "나머지 V01~V12 회귀 재실행 안 함"은 두 파일 외 byte 불변을 근거로 명시돼 있다.
- 미실시가 PASS로 위장되지 않음: V11, CF-F07 연출, V12 외부(두 사용자·비전투 몬스터·다른 맵), 실제 mouse/touch, 손 입력 .2창 성공은 coder·QA3·Plan §13에 NOT_RUN/미완료로 남아 있다. 플레이어 사망 경계는 "경계만"으로 별도 표시됐다.
- 문서 불일치(DOC-01에 포함): Plan 머리 3행("갱신 2026-10-29… 독립 리뷰 남음")과 §8 167행("다음 담당 reviewer, QA2"), WR "현재 재개 지점" 10행(e8a20728 기준 reviewer 대기)이 현재 상태와 다르다. 2026-10-29 리뷰가 든 DevelopmentRoadmap.md:13·:45·:103, WorkRecords/README.md:58, ChatRoles/README.md:37(당시 :36) "WorkRecord 생성 예정"도 그대로다. run.md 15·18~21행(리뷰 결과 없음·대상 버전 e8a20728)은 메인 담당이다.

#### 다음 행동
1. planner(msw-planner): CombatCore-DOC-01 — 위 현황·날짜·버전·링크만 Plan/WR 원본에 맞춘다. QA-F01 과거 FAIL→QA2 PASS, REV-F01→QA3 PASS 연결, CF-F07 수치/연출 분리, P01b~P06 🟡 유지. 규칙·검증 기준·단계 순서 변경과 결과 전문 복제 없음. 제품·Maker 변경이 없으므로 coder/tester 재실행은 필요 없다.
2. 메인: run 상태·대상 버전 줄을 6614b20/1ac324e6…9de4와 이 리뷰 판정으로 갱신.
3. 사용자 V11: PC·모바일에서 예고 방향/속성·.20초 체감·저스트/패링/반격 준비·소비·슬로우/어지러움·피격/die·키/버튼/터치 혼합·화면 잘림·음향을 직접 평가. 이때 플레이어 사망 직후 HP 문자 표시도 보면 된다. 새 규칙·수치 요구가 생기면 관련 D/R/V만 planner로 재검토한다.
4. 외부 대기: V12 실제 두 사용자·비전투 몬스터·다른 맵 환경, CF-F03/CombatPause-F01 실제 맵 전환, 기기/음향·재시작·배포·성능 후속 ID는 기존 추적 유지. Plan/WR/run 보존, 3단계 자동 시작 없음.

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


## 2026-11-02 coder REV-F01 수정·기본 검증 인계

### 범위·원인·실제 변경
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 CombatCore-REV-F01(R02/V02/D02)뿐이다. 새 규칙·수치·기본 AttackDamage=12·DataSet·EvaluateDefense 대응표·PlayerCombatComponent.CalcDamage(QA-F01 처치 상한)·native HP 단일 소유는 바꾸지 않았다. 기준 저장소 커밋 eedeefb, 기준 Bundle e8a20728…a49.
- 원인: 몬스터 기본 피해가 경감 전에 한 번 내림(MonsterAttackComponent)되고 PlayerHealthComponent에서 경감 뒤 다시 내림되어, 소수 AttackDamage에서 D02 "합성 뒤 한 번 내림"과 어긋났다(12.7 가드: 4).
- 실제 변경(제품 mLua 2파일, 각 1줄):
  - RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua:134 — `ResolveIncomingDamage(math.floor(self.AttackDamage), attacker)` → `ResolveIncomingDamage(self.AttackDamage, attacker)`. CalcDamage 서명·integer 반환 유지(override이므로 @ExecSpace 미추가).
  - RootDesk/MyDesk/Player/PlayerHealthComponent.mlua:38 — `ResolveIncomingDamage(integer damage, Entity attacker)` → `ResolveIncomingDamage(number damage, Entity attacker)`. 반환 integer·@ExecSpace("ServerOnly") 유지, :45 `math.max(0, math.floor(damage * result.rate))`가 유일한 최종 내림. 호출자는 MonsterAttackComponent:134 하나(Grep 확인).
- 플레이어 쪽 HP 상한(남은 HP 대비 overkill) 부재는 이번 범위 밖 관찰이며 건드리지 않았다.

### 실제 기본 검증 (한 통합 Play)
- 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186 일치. MapBuilder는 사용하지 않았고 기존 기록의 TileMapMode=0(MapleTile)을 따른다. 맵·모델·UI 파일 변경 없음.
- 순서: edit에서 패치 → maker_refresh_workspace(ok) → build 로그 오류0/경고0(Info 79, 기존 동적 참조 Info만) → Play → server_main maker_execute_script 한 회차 → Stop. Play 후 normal 로그에 Info 이외 로그 없음(오류/경고0). 제품 [VRF] 추가 없음(기존 CombatCore defense 로그 사용).
- 시험 방식: Play 내부 server_main 프로브가 몬스터 AttackInterval을 일시 크게 올려 자연 공격을 막고, 기존 패턴 행에서 지정 id 1행만 해당 회차에 사용하도록 `_CombatRuleCatalog.patterns`를 임시 교체한 뒤, 실제 `StateComponent:ChangeState("ATTACK")`→PrepareAttack→시전 대기→ResolveAttack→native AttackFast/HitEvent 경로를 실행했다. 가드는 플레이어 `ChangeState("GUARD")`(PlayerGuardComponent.guardStartTime 서버 기록), 저스트는 PlayerEvadeComponent.SetEvading+EvadeDirection 설정으로 부여했다. 이 방어 입력은 키보드 입력이 아니라 서버 프로브이며 판정(EvaluateDefense)·피해(CalcDamage→ResolveIncomingDamage)·HitEvent·HP는 제품 경로다. HP delta는 PlayerComponent.Hp 전후, TotalDamage·Damages 합계는 플레이어 엔티티 HitEvent 핸들러로 읽었다.
- 로그 시각 2026-11-02 19:06:17~19:06:34 (Maker 로그). 시험값(AttackDamage 12.7, AttackInterval, patterns 임시 교체)은 프로브 종료 시 즉시 복원: rows=8, interval=3.0, dmg=12.0 확인. HitEvent 핸들러는 Disconnect.

| 조건 | AttackDamage | 판정 kind / rate | HP delta | HitEvent.TotalDamage | Damages 합계 | 결과 |
| --- | --- | --- | --- | --- | --- | --- |
| T1 무가드 일반 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T2 특수 무가드 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T3 특수+가드 | 12.7 | HIT / 1 | 12 | 12 | 12 | PASS (기대 12) |
| T4 일반 가드 | 12.7 | GUARD / .4 | 5 | 5 | 5 | PASS (기대 5, 구 코드 4) |
| T5 패링 실패 가드(가드 .5초 전 시작) | 12.7 | GUARD / .4 | 5 | 5 | 5 | PASS (기대 5) |
| T6 유효 패링(가드 시작이 타격 .089초 전) | 12.7 | PARRY / 0 | 0 | 0 | 0 | PASS (기대 0, native 이벤트1·0피해) |
| T7 유효 저스트(회피 시작이 타격 .102초 전, RIGHT) | 12.7 | JUST / 0 | 0 | 0 | 0 | PASS (기대 0) |
| R1 무가드 | 12 | HIT / 1 | 12 | 12 | 12 | PASS 회귀 |
| R2 일반 가드 | 12 | GUARD / .4 | 4 | 4 | 4 | PASS 회귀 (기대 4) |
| R3 특수+가드 | 12 | HIT / 1 | 12 | 12 | 12 | PASS 회귀 |
| R4 유효 패링 | 12 | PARRY / 0 | 0 | 0 | 0 | PASS 회귀 |
| R5 유효 저스트 | 12 | JUST / 0 | 0 | 0 | 0 | PASS 회귀 |

- 각 회차 resolved=true·nativeHit=true·native 이벤트 1건. PlayerHealthComponent의 마지막 확정 피해(lastResolved)도 HP delta와 일치.
- 이번에 실행하지 않은 것: 실제 keyboard_input/mouse_input 방어 입력, QA-F01 몬스터 처치 상한·사망1회/후속 제외 회귀(PlayerCombatComponent·MonsterHealth 변경 없음, 소스 무변경으로 독립 QA가 확인 필요), 플레이어 사망 경계, 슬로우/그로기/팝업/DataSet 로드 회귀, 두 파일 외 경로의 전수 재실행, V11 화면 가시성·체감. 이 항목은 새 전수 실행으로 표시하지 않는다.
- 시험 오류·한계: 프로브 중 몬스터 자연 공격(시험 전 약 4초 간격)이 프로브 전후에 몇 번 있었으나 회차 판정 로그와 분리되어 측정에 섞이지 않았다(회차마다 snapshot id·pattern·hit 시각 기록). 제품 오류는 관측되지 않았다.

### 사용 종료·다음 담당
- 최종 maker_stop 성공 후 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. 사용자 로그 clear·파일/CSV 추가 변경 없음. commit·push는 하지 않았다.
- 다음은 독립 tester: 새 Bundle에서 소수 기본 피해(12.7)의 무가드/특수=12, 일반·패링실패 가드=5, 유효 저스트/패링=0를 실제 입력 경로로 재확인하고 기본12 회귀와 QA-F01 처치 상한·사망1회/후속 제외를 관련 회귀로 확인한다. 이전 QA2를 이 변경 경로에 그대로 적용된다고 표시하지 않는다. V11·CF-F07 연출·V12 외부 환경은 NOT_RUN/WAITING 유지, 단계 완료·3단계 진행·Features 이관 아님.

### 2026-11-02 최종 제품 버전 묶음
- 이전 2026-10-29 묶음과 같은 52경로·순서. byte SHA-256을 다시 계산해 변경 파일은 아래 두 개뿐임을 확인했다(나머지 50개는 기존과 동일). 계산법: 표 순서의 경로 + TAB + sha256 + LF를 연결한 UTF-8 문자열의 SHA-256.
- 직전 Bundle(e8a20728…a49) 재계산도 일치. 변경 전 지문: MonsterAttackComponent eb0ee88a85fb08f87c02de448c2c4f1b89992a7117496464bbf1798233061e7d, PlayerHealthComponent 1e1396015176a5284d4553ae816294933ebd6079f16ade8ff78064a85abf86e8.
- Bundle SHA-256: 1ac324e61f5668a43fb5d0232399aa75299322bbb59143c8cb70080f080d9de4.

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
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 13d0db06277f2d1f215dbd9df73f348181b00ac53a7e5aa0ebaffe0cb6d69eed |
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
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1ee406d747b8a3edece94fc7b4f74500f94c65e6fb3d398df531332f284f5d79 |
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


## 2026-11-02 coder V11-F01~F05 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §14의 CombatCore-V11-F01~F05뿐이다. 모든 수치(0.20, ×0.40, 반격 2.0·×2.2, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0)·CSV 3종·D01~D03 판정 규칙·8패턴 영역·LandingAnchor·피해 합성/내림·플레이어 애니메이션·.ui는 바꾸지 않았다. 기준은 커밋 a289eb7(제품은 6614b20과 동일) / Bundle 1ac324e6…9de4(52경로)이며 시작 전 같은 방법으로 재계산해 일치를 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder TileMapMode=0(MapleTile). Maker 로그 시각 22:48~23:03.
- 시험값(AttackInterval 일시 상향, 패턴 목록 단일 행 교체, 그로기 6초 시험값)은 모두 Play 내부 서버 프로브이며 Stop으로 폐기했다. 반영한 영구 변경은 아래 제품 변경뿐이다.

### F05 원인 판정 — 규칙상 정상, 제품 무수정 (변경 전 기준 버전에서 실행)
- 방법: 실제 `maker_keyboard_input`으로 LeftArrow를 홀드해 Pos1(x=-1.5)에 머문 채(서버 상태 MOVE 유지) 서버 프로브로 8패턴을 한 번씩 강제 공격시키고, 패턴 ID·판정 순간 플레이어 x·서버 상태·kind·HP·HitEvent 합계를 기록했다. 패턴 행만 단일 행으로 교체했고 판정·영역은 제품 경로 그대로다.

| 대응형 | 패턴 | 서버 영역 | 판정 순간 x / 서버 상태 | 네이티브 피격 | HP 감소 / HitEvent 합계 | 결과 |
| --- | --- | --- | --- | --- | --- | --- |
| 뒤 회피형(LEFT) | normal/special/parry.left | -0.5~2.0 | -1.5 / MOVE | 없음 | 0 / 0 | 피해 없음, HUD 회피(EVADE) |
| 앞 회피형(RIGHT) | normal/special/parry.right | -2.0~0.5 | -1.5 / MOVE | 있음 | 12 / 12 | HIT |
| 가드형(GUARD) | normal/parry.guard | -2.0~2.0 | -1.5 / MOVE | 있음 | 12 / 12 | HIT(가드 없음) |

- 판정: 뒤 회피형은 Pos1에서 기대대로 EVADE·피해 0이다. 앞 회피형·가드형이 Pos1에서 맞는 것은 D01의 정상 동작이다(영역이 Pos1을 포함한다). 사용자 사례의 패턴은 미상이므로 앞 회피형·가드형이었다면 정상이고, 뒤 회피형에서 맞는 재현은 나오지 않았다(결함 아님).
- 입력 지연 점검(키보드): 같은 키 이벤트의 클라이언트 시각 78.363에 클라이언트 상태 IDLE→MOVE가 같은 프레임에 일어났고, 서버 상태 IDLE→MOVE는 서버 시계 77.890이다. 같은 프로브의 MOVE→IDLE 복귀(클라이언트 82.244 / 서버 81.755)에서 시계 차 ≈0.49초가 나와 진입 시 차 0.473초와 같다. 따라서 서버 수락 지연은 약 1프레임 이내로 본다. 홀드 중에는 RETURNING으로 넘어가지 않았고 해제 뒤에만 복귀했다(OUTBOUND 0.243초 도착→HOLD, 해제 뒤 RETURNING 0.24초). 미실시: UI 버튼 누름 경로의 수락 지연 측정(Entity 이벤트 주입이 실제 터치가 아님), 예고 시작 뒤 플레이어 방향 전환이 시작 시 Scale 기준 검증과 어긋나는지 시험.

### 항목별 실제 변경
| ID | 변경 파일 | 요약 |
| --- | --- | --- |
| F02 | RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua, RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 패링 성공 판정(PARRY) 시 ResolveAttack은 더 이상 즉시 ApplyGroggy를 호출하지 않는다. Monster_Attack이 ResolveAttack 직후 결과가 PARRY면 groggyAfterReturn(지속시간은 스냅샷 규칙값)을 기록하고 기존 복귀 모션을 그대로 수행한다. 복귀 완료(OnReturnComplete) 또는 복귀 모션 거부 시 FinishAttack이 ApplyGroggy를 호출해 STUN으로 가고, 거부되면 IDLE로 간다. 반격 창은 기존 GrantCounter(성공 시점)를 그대로 쓴다. 취소(CancelExecution) 때 플래그를 초기화한다. |
| F04 | RootDesk/MyDesk/Models/Monsters/주황버섯.model(ModelBuilder) | 방식 (a). StateAnimationComponent.ActionSheet에 "stun" 키 하나를 추가하고 기존 hit RUID(aec9504d5dc24aceb5646b79d30abad4)를 연결했다. move·stand·jump·hit·die 다섯 키의 값은 그대로다. .mlua 변경 없음. 새 클립·자원 검색·제작 없음. |
| F01 | RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua(신규, Maker가 .codeblock 생성), RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model(ModelBuilder 신규), map/map01.map(MapBuilder: BattlePosMark1~3 3개 배치), MonsterAttackComponent.mlua, Monster_Attack.mlua | MonsterAttackComponent에 @Sync TelegraphCells("111" 형식, 칸1~3 중 앵커 x가 서버 영역 min~max 안에 있으면 "1")를 추가해 PrepareAttack에서 TelegraphResponse와 함께 설정하고 ResolveAttack·CancelPendingAttack·Monster_Attack.CancelExecution에서 같이 비운다. 맵에 3개 표시 엔티티(model AttackAreaMark: TransformComponent·네이티브 PixelRendererComponent·AttackAreaMarkComponent, 위치 x=-1.5/0/1.5, y=0.98, z=0, Scale 25 = 4×4 논리 픽셀 → 1.0×1.0 월드 단위)를 두고, 소유 클라이언트가 MonsterManager의 현재 몬스터·대결 플레이어를 확인한 뒤 자기 CellIndex 칸만 반투명 빨강(알파 0.45)으로 칠한다. 새 RUID·.ui 없음. 표시는 서버 동기 값만 읽으며 판정·피해에는 관여하지 않는다. |
| F03 | RootDesk/MyDesk/Monster/MonsterStunComponent.mlua, MonsterAttackComponent.mlua | 별 StarVortex 부착 파티클을 크기 0.2→0.5, 부착 높이 0.65→0.9로 키웠다. 서버 확정 PARRY에서만 MonsterAttackComponent가 stun:NotifyParry(접촉 지점 x=(플레이어 x+몬스터 x)/2, y=몬스터 y+패턴 AreaOffsetY)를 호출하고, MonsterStunComponent의 @Sync ParryEffect(Vector3, z는 같은 위치 반복에도 동기화되도록 한 순번)가 바뀌면 소유 클라이언트가 네이티브 BasicParticleType.SparkRadialExplosion(크기 1.5, 1회)을 재생한다. 저스트·가드·패링 실패에는 호출하지 않는다. 맵 이탈·종료 시 파티클을 제거한다. HUD 문구·.ui 무변경. |
| F05 | 없음 | 위 판정대로 무수정. |

- 건드리지 않은 것: CombatRuleData·MonsterAttackPatternData·AttackSkillData CSV, 주황버섯 ActionSheet의 기존 다섯 키, HitComponent·MonsterHealthComponent의 HIT 진입 조건, PlayerStateControl 등 플레이어 쪽, CombatInputController(HUD 문구 포함).
- Maker 부산물: Models/MapObjects.directory, Combat/AttackAreaMarkComponent.codeblock이 refresh로 생겼다. 이 둘은 지문 대상 외(이전 묶음 정의 유지)다. 빌더가 주황버섯.model을 다시 쓰며 줄 끝이 CRLF→LF로 바뀌고 변경한 ActionSheet 값의 형식 버전 문자열이 26.7.0.0→26.10.0.0이 됐다. 의미 비교(JSON)에서 이외의 차이는 없음을 확인했다(stun 키 제거 후 형식 버전 문자열 1곳만 다름).

### 실제 기본 검증 (Maker MCP, 같은 Bundle 기준 통합 Play를 여러 회차로 수행)
- 빌드: Refresh 후 build 로그 80건, 모두 Info(LIA 1114/1115, 기존 동적 참조 노이즈 유형 — 새 NotifyParry 항목 포함). 오류 0·경고 0. 별도 normal 로그의 제품 오류 없음.
- F02 패링 흐름(서버 프로브, 제품 경로 판정): 패턴 parry.guard, 가드 시작이 타격 0.10초 전. 결과 PARRY·피해 0, 타임라인(전투 시계 기준): 0.00 시작 x=3.00(Home 3.00)→0.55 판정 PARRY·반격 가능→0.55~1.07 ATTACK 상태로 복귀(그로기 아님, 별 표시 없음)→1.07 STUN x=3.00(GroggyRemaining 1.48)→2.53 잔여 0.02→2.57 IDLE. 그로기 길이 ≈1.50초(복귀 완료부터), 반격 창은 성공 시점 0.55부터 약 2.0초(2.55에 CounterReady false). 다음 공격(case2)은 x=3.00(Home)에서 시작해 착지 x=0.10으로 점프했다. 그로기 진입 로그는 Monster_Attack.FinishAttack 호출이다.
- F02 대조: 가드 0.45초 전(패링 창 밖) → GUARD·HP -4(12×0.4 내림)·그로기 없음·접촉 파티클 없음. 저스트(RIGHT 회피 시작 0.12초 전) → JUST·슬로우 적용·그로기 없음·접촉 파티클 없음(case3 요약 줄은 clear_logs로 잃었지만 같은 구간 로그에 slow applied·defense JUST가 있고 groggy applied·parry effect 로그는 없었다).
- F03: PARRY 판정마다 `parry effect serial=N x=0.0 y=0.981`이 한 번만 나왔고(소유 클라이언트), GUARD·JUST에는 없었다. 육안 확인은 아래 한계.
- F04: 클라이언트 AnimationClipEvent 추적: HIT→clip=hit, IDLE→clip=stand, STUN→clip=stun(ActionSheet "stun"=hit RUID), 종료 IDLE→clip=stand. 실제 패링 흐름에서도 STUN 진입에서 clip=stun, 그로기 종료에서 clip=stand를 확인했다. 복귀 중에는 stun 클립이 나오지 않았다(복귀 중 기존 모션 유지). SpriteRUID 속성 읽기는 클립 파이프라인이 속성을 바꾸지 않아 근거로 쓰지 않았다.
- F01: 8패턴 서버 영역→TelegraphCells: normal.left/special.left/parry.left(-0.5~2.0)=011, normal.right/special.right/parry.right(-2.0~0.5)=110, normal.guard/parry.guard(-2.0~2.0)=111. 같은 프로브의 클라이언트 표시 판정 로그가 각 패턴의 칸과 일치하게 켜졌고 판정 직후 모두 꺼졌다(제품 로그 `area mark cell=…` — 이후 로그 소음을 줄이려 제거). 예고 중 슬로우·팝업·사망·Stop에서 칸이 유지·제거되는 경로는 별도 시험하지 않았다(표시는 서버 동기 TelegraphCells 값에만 묶여 있고, 복귀 중 정지 뒤 Stop→재Play에서 칸이 모두 꺼져 있음은 V08에서 확인). 스크린샷에서 칸 1·3이 반투명 빨강(배경과 섞여 주황빛)으로 보이고 몬스터 판정 높이(몬스터 y+0.4 중심, 높이 1.0)와 맞는 위치임을 확인했다.
- V02: 중앙(x=0)에서 8패턴 모두 HIT, HP 감소=HitEvent 합계=12. 가드 4.8→4(경감 뒤 한 번 내림) 일치.
- V03: 패링 창 경계 대표 두 점(0.10초 전 PARRY, 0.45초 전 GUARD)과 F05 8패턴(범위 밖 EVADE 포함)을 확인했다. 전체 경계 열(정확히 0.20·직후 등)은 이번에 다시 하지 않았다.
- V04: 패링 성공 뒤 실제 ↑ 입력으로 수동 공격 `manual cast count=10 factor=2.2`, 이후 CounterReady false(소비). 반격 보너스 규칙 전체 경계는 재시험하지 않았다.
- V06: (1) 패링→복귀→그로기(2.57 IDLE). (2) 그로기(시험 6초) 중 실제 ↑ 공격: 서버 상태 STUN 유지, 몬스터 HP 100→80(10타), GroggyRemaining이 계속 감소해 시작 +6.0초(전투 시계 7.05)에 IDLE, 조기 해제·연장 없음. 클라이언트에서 같은 피격으로 로컬 상태가 HIT로 보인 순간에 hit 클립 이벤트가 한 번 관측됐으나 서버 상태는 STUN이고 hit RUID가 stun RUID와 같아 화면 변화는 없다(기존 구조의 클라이언트 쪽 HIT 신호로 보이며 이번에 바꾸지 않음, tester가 화면 확인).
- V07: 패링 뒤 복귀 중 popup 열기(x≈0.31에서 정지, 전투 시계 12.87 고정, 약 24초 정지). 닫은 뒤 전투 시계가 이어져 x가 0.31→0.41…→3.00으로 복귀하고 STUN 진입(GroggyRemaining 시험값 6.00)했다. 정지 중 위치·그로기 값 불변. 닫기는 팝업 실시간이 아니라 프로브가 `_UIPopup:Close()`를 직접 호출했다(client TimerService가 정지해 타이머로 닫을 수 없었음, 제품 문제 아님). 슬로우·예고 중 팝업의 칸 유지·재개는 이번에 다시 하지 않았다.
- V08: (1) 복귀 중(x=0.10) 몬스터 치명 피해(MonsterHealthComponent.ApplyDamage): 0.04초 뒤 DEAD, STUN·그로기 진입 없음(isStunned false, GroggyRemaining 0), 3초 동안 변화 없음. (2) 팝업 정지 중 복귀(패링 직후)에서 실제 maker_stop → 새 Play: 몬스터 IDLE x=3.00, isStunned false, GroggyRemaining 0, 칸 표시 없음(서버 cells='', 클라이언트 3칸 모두 false), 슬로우 0·배율 1, pause false, 반격 false, ParryEffect 순번 0, popup 닫힘, 첫 자연 공격 정상. 플레이어 사망·다른 맵 전환은 이번에 하지 않았다.
- V10: 실제 키 입력으로 Right(MOVE→복귀→IDLE, x 0→1.5→0), Down 2초 홀드(GUARD, isGuarding true, 서버 GUARD→IDLE), ↑ 탭(ATTACK 10타 factor 1, 반격 없음 시 ×1)과 Left 홀드(F05)를 확인했다. UI 버튼 경로·동시 입력 전 조합은 재시험하지 않았다.
- 미실시: V05 슬로우 전 구간 적분 재확인, V09 CSV 변경 시험(CSV 무변경, 로드 `rules=1 patterns=8` 확인만), V12.

### 화면 근거와 한계(F03 값 제안)
- 해상도 558×314 스크린샷으로 확인한 것: BattlePos 칸의 위치·크기·반투명 빨강(F01), 부착 파티클의 로컬 좌표·스케일이 부모(몬스터 Scale 2)에 곱해진다는 사실(attached Nova local y=1.5가 몬스터 발 기준 약 3.0~3.2 위에 중심). 별 스파크·접촉 폭발은 이 해상도·캡처 타이밍에서 형태를 확정할 수 없었다(작은 스파크가 희미하게만 보임).
- 제안값(사용자 V11에서 판단): 별 크기 0.5, 높이 0.9(몬스터 월드 기준 머리 위 약 0.7). 접촉 효과는 SparkRadialExplosion 크기 1.5, 위치는 패링 판정 순간 플레이어·몬스터 x의 중간, 높이는 몬스터 y+0.4(공격 영역 중심). 더 눈에 띄는 형태·색을 원하면 사용자가 선택한다(자원 검색·제작은 하지 않았다).
- F01 칸 알파는 0.40으로 화면을 확인한 뒤 0.45로 올렸고 최종 값의 화면 재확인은 하지 않았다.

### 프로브 오류와 제품 오류의 구분
- 보정용 프로브에서 `Dictionary()` 생성자 사용 오류(LEA-2011 3건)와 Stop 시 남은 프로브 타이머의 LEA-3051 MemoryLeak 1건이 났다. 모두 시험 스크립트 문제이며 제품 오류는 관측되지 않았다.
- 칸·파티클·클립 확인은 로그 중심이고 육안 확인은 위 한계가 있다. V11(체감)·CF-F07 연출·V12 외부 환경은 이번에도 미실시다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F05를 같은 조건(실제 LeftArrow 홀드 Pos1)에서 8패턴 독립 재확인하고 UI 버튼·방향 전환 시나리오 추가. (2) F02: 패링→복귀→그로기 순서·1.5초·다음 공격 Home 시작·복귀 중 슬로우/팝업/피격/사망/Stop. (3) F04: 그로기 중 hit 클립(복귀 중에는 아님)·종료 후 stand·그로기 중 피격 시 클라이언트 HIT 신호가 화면을 바꾸지 않는지. (4) F01: 8패턴 칸과 예고 중 슬로우·팝업·사망·Stop 제거를 육안으로. (5) F03: 패링에만 접촉 파티클, 별 크기·높이의 가시성. (6) 회귀 V01·V02·V03·V06~V08·V10과 관련 경로의 V04·V05·V09. 사용자 V11 재확인과 V12 외부 환경은 AI 결과로 대신하지 않는다.

### 2026-11-02 최종 제품 버전 묶음 (V11-F01~F05)
- 이전 묶음(1ac324e6…9de4, 52경로)의 경로 표에 신규 2경로(Combat/AttackAreaMarkComponent.mlua, Models/MapObjects/AttackAreaMark.model)를 더한 54경로. 계산법은 이전과 같다(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256). 이전 묶음을 HEAD(a289eb7)에서 같은 방법으로 재계산해 1ac324e6…9de4와 일치함을 확인했다. 변경·추가 파일은 7개: AttackAreaMarkComponent.mlua(신규), AttackAreaMark.model(신규), 주황버섯.model, Monster_Attack.mlua, MonsterAttackComponent.mlua, MonsterStunComponent.mlua, map/map01.map. 나머지 47개는 이전과 같다.
- Bundle SHA-256: d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb.

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
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 9c0e9b5bbc2ba588e021aeca0ac9f9dcaacdc6223ddae17ea955dcf2c8544907 |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 3c592e5296af804136a372900abe87267ae7027ce6f4c737ebda17c92cb8bfbe |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model | 954a3ef24d26150150de52b5fe6a738276561b18da0129c762e3899e72a1466b |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | 1b7686acda7c84412676a7157681156cbef5f693e4b3c0872d609c5cf61c3b9d |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 578acaa625570909d0eebf2a46332d7f429b3aed351c0b098c7fc6f3d6a60db8 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | a1735e7f50fc694a08133bfd2a012b2438051fe7b0fa45e55e7bc123b9d9a164 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | a7a4508fd600b47548fe2a9182d371ab2dc06cbd3941070e5774228fa716993b |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 69ad2f52be603d7fedde3223678094968d859cd209f9771895ab1175ce29e3c9 |
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
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | 1ee406d747b8a3edece94fc7b4f74500f94c65e6fb3d398df531332f284f5d79 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 16b323c5e3c9d3cb0290e78dc3cc7b0e840c6709e42d08ceb40ebeed835c7288 |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 1e9dbe01ec2139a7da3a2129399620b187592559856a5d4959b537b72d11fa65 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |

## 2026-11-03 coder V11-F06 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §15 CombatCore-V11-F06뿐이다. JustWindowSec 0.20, GuardDamageRate 0.40, 반격 2.0·×2.2, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8, 기존 패딩 0.5·높이 1·오프셋 0.4·선행 0.5, CombatRuleData·AttackSkillData CSV, D02~D04, 입력 규칙, LEFT/RIGHT 영역, GUARD 판정 규칙·코드, F01~F05 동작, .ui, 주황버섯 모델, 몬스터 수치 DataSet화(F07)·3단계는 바꾸지 않았다.
- 기준 버전: coder 커밋 1447ff8(54경로 Bundle d2b57802…0fbb). 시작 전 같은 방법(아래 계산법)으로 1447ff8의 54경로를 재계산해 d2b578021b563a54a2a2d5ff4370a7a6b1cb79bf3fa1718b36f8bc5b332c0fbb와 일치함을 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. MapBuilder 읽기 TileMapMode=0(MapleTile). Maker 로그 시각 10:05~10:17. maker_clear_logs는 한 번도 호출하지 않았다.

### 미커밋 Maker 재저장 3파일의 의미 비교 (제품 수정 전, 빌더 읽기)
- 방법: git show로 1447ff8 판을 임시 경로에 꺼내 MapBuilder.read(...).build()/ModelBuilder.read(...).build()로 읽고, 문자열로 직렬화된 jsonString을 풀어 키 순서·숫자 표기(1↔1.0)·줄 끝을 무시한 깊은 비교를 했다(StudioVersion은 별도 보고).
- map/map01.map: 엔티티 13개 동일. 차이는 BattlePosMark1~3(Entities[10~12]) TransformComponent 3곳에서 (a) Scale의 형식 메타 `$type`(MOD.Core.MODVector3) 제거, (b) 기본값 Rotation(0,0,0)·ZRotation 0 명시 추가뿐이다. Position(-1.5/0/1.5, 0.98, 0)·Scale(25,25,1)·QuaternionRotation·Enable·컴포넌트 목록·path/id 등 값은 동일하다. 의도하지 않은 의미 차이 없음 → Maker 재저장 형식 차이로 판정, 그대로 둔다.
- RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model: 차이 0건(의미 동일).
- RootDesk/MyDesk/Models/MapObjects.directory: StudioVersion `""` → `"0.1.0.0"` 한 곳뿐(나머지 동일).
- 세 파일은 되돌리거나 직접 수정하지 않았다. map·model은 54경로 Bundle 대상이라 지문이 1447ff8과 달라졌다.

### 결정 사항 (Plan이 coder에게 맡긴 항목)
- 동률 칸 선택(ANY): 플레이어 WorldPosition.x와 BattlePos 3칸 x의 거리가 가장 작은 칸. 거리가 같으면(차이 1e-6 이하) 중앙(2)→왼쪽(1)→오른쪽(3) 순서로 먼저 본 칸을 유지한다. 같은 입력은 항상 같은 칸이다. 실제 간격(-1.5/0/1.5)의 중간점에서 -0.750→2, -0.760→1, -0.740→2, 0.750→2, 0.760→3.
- ANY 영역 표현: CSV AreaFromAnchor=AreaToAnchor=0. 로더는 ANY에서만 0/0을 허용하고, ANY의 0이 아닌 값과 LEFT/RIGHT/GUARD의 0 또는 범위 밖·역전 값은 전체 거부한다.
- LandingAnchor: 열을 CSV에서 제거하고 로더 필수 열·검증에서도 제거했다(무시가 아니라 제거). 착지는 데이터가 아니라 모션이 영역에서 도출하므로 데이터와 모션이 어긋날 수 없다. 다른 코드의 참조는 PrepareAttack의 `landing` 하나뿐이었고 함께 제거했다.
- Weight: 필수 열, 유한한 양수만 허용(누락·빈 값·숫자 아님·0·음수·NaN/무한대는 카탈로그 전체 거부·1회 경고). 선택은 MonsterAttackComponent.SelectPattern(rows, unit): r=unit×가중치 합, CSV 행 순서 누적, r<누적합인 첫 행, 끝까지 못 고르면 마지막 행. unit은 PrepareAttack에서 math.random()을 넘긴다(프로브가 경계 난수를 직접 넣을 수 있도록 분리). 판정 규칙·수치가 아니라 선택 방식만 바뀌었다.
- 저스트 방향 집합: 실행 스냅샷에 validDirs({LEFT=true}/{RIGHT=true}/ANY는 고정 칸에서 멀어지는 방향/GUARD는 빈 집합)를 고정하고 PlayerHealthComponent.EvaluateDefense(5번째 인자)가 `validDirs[evade.EvadeDirection]`과 0.20초 창으로 JUST를 판정한다. LEFT/RIGHT도 같은 집합을 쓰도록 통일해 가드 분기와 창 경계는 byte 불변이다. ANY: Pos2 조준 {LEFT,RIGHT}, Pos1 {RIGHT}, Pos3 {LEFT}.
- ANY 탈출 검증: 유효 방향마다 도착 칸(LEFT=조준 칸-1, RIGHT=조준 칸+1)에 선 플레이어 콜라이더(오프셋 절댓값+반폭, 좌우 반전 대비)가 고정 칸 영역 [x-0.5, x+0.5]을 완전히 벗어나는지 확인하고 실패하면 시작하지 않고 1회 경고한다. 현재 간격·패딩(반폭 0.25, 오프셋 0)에서는 모두 통과한다(중단 조건 아님).
- 공통 계층과 모션의 역할: MonsterAttackComponent는 스냅샷 area={cells("010" 형식), minX, maxX}만 만들고 Monster_Attack이 PerformAttackMotion(string cells, number minX, number maxX)로 모션 담당에 넘긴다. 영역 중앙 착지((minX+maxX)/2)는 OrangeMushroomAttack 안에만 있다. 로더·MonsterAttackComponent에는 착지점 규칙이 없다. 보스용 다중 이펙트는 이 cells를 쓰는 별도 모션이 맡는다(떨어진 칸·칸별 다중 타격 형식은 구현하지 않음).
- 예고 문구(.ui 무변경, CombatInputController): ANY는 "방향 무관 회피 [좌·우]"로 표시하고 속성 접두·접미는 기존과 같다(예: 일반 · 방향 무관 회피 [좌·우] / 가드, 특수 · … · 가드 불가, 패링 · … / 정확히 가드). 끝 칸 조준 시 실제 유효 방향은 한쪽뿐이지만 문구는 일반형으로 두고 칸 표시(F01)가 조준 칸을 알린다. 아이콘 등 .ui 요소는 필요하지 않다고 판단했다.

### 변경 파일
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | 8행→9행(가드형 2행 제거, ANY 3행 추가), LandingAnchor 열 제거, Weight 열 추가(모두 1). BOM·CRLF 유지. .userdataset 무변경 |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | ANY 응답 허용, 앵커 0/0 규칙, Weight 검증, LandingAnchor 제거 |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | SelectPattern·FindNearestCell 추가, ANY 칸 고정·영역·유효 방향·탈출 검증, 스냅샷 area/validDirs/targetCell, landing 제거, 텔레그래프 [VRF]에 target·dirs 추가 |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | EvaluateDefense에 validDirs 인자 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 모션 호출을 영역 전달로 변경 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | PerformAttackMotion 시그니처(cells, minX, maxX) |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 영역 중앙 착지(주황버섯 한정) |
| RootDesk/MyDesk/UI/CombatInputController.mlua | ANY 예고 문구 |
| map/map01.map, RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model, RootDesk/MyDesk/Models/MapObjects.directory | 이번 회차에 수정하지 않음. Maker 재저장 형식 차이만(위 비교). Bundle에는 map·model이 들어 있어 지문만 달라짐 |

### 실제 기본 검증 (Maker MCP, Play 2회: 최초 Play 통합 + 예고 도중 Stop 뒤 재Play)
- 빌드: Refresh 2회. 첫 build 로그에 Monster_Attack의 `LEA-1102 number PerformAttackMotion(Entity target)`(시그니처 변경 직후 낡은 결과)가 있었고, 호출 파일에 주석만 고쳐 다시 Refresh하자 사라졌다. 이후 build 로그 80건 모두 Info(LIA 1114/1115 동적 참조 노이즈), 오류 0·경고 0.
- 방법: 모든 판정 경로는 Play 내부 server_main 프로브가 제품 경로(PrepareAttack→Monster_Attack→ResolveAttack→EvaluateDefense→네이티브 AttackFast→HitEvent)를 그대로 실행하게 했다. 패턴 목록을 단일 행으로 교체하고 몬스터 상태를 ATTACK으로 보냈으며, 저스트/패링 입력은 회피 방향·시작 시각, 가드 시작 시각 필드를 판정 전에 기록했다. 가드·좌우 홀드는 클라이언트 PlayerStateControl.RequestChangeState("…","probe.…")로 실제 입력 수락 지점을 거쳐 걸었다(키보드 이벤트가 아님). 대표 실제 키 입력은 maker_keyboard_input LeftArrow 1회(아래 K1b). 시험값(AttackInterval 9999, 단일 행 교체, K1b의 JustWindowSec 4.0, 선행 4~6초)은 모두 Play 내부이며 Stop으로 폐기했다. CSV는 시험용으로 바꾸지 않아 원복할 것이 없다.

| 항목 | 결과 |
| --- | --- |
| 로드(V01·V09) | `catalog ready rules=1 patterns=9`, 9행 id·유형·속성·앵커·Weight=1 확인, 가드형 0행, LandingAnchor 값 nil. 재Play에서도 동일 |
| 검증 거부(V09, ValidateRows 시험 행 19건) | 허용 4건(LEFT, ANY 0/0, GUARD 일반, GUARD 패링)은 통과. Weight 누락·빈 값·abc·0·-1·nan·inf·1e999, ANY 1/1, ANY 0/2, LEFT 0/0, 역전 3/2, SPECIAL+GUARD, 잘못된 유형, 선행 시간 부족, 중복 id는 모두 거부되고 거부마다 경고 정확히 1회. 열 누락(`NoSuchColumn`)은 ReadRows nil, 실제 CSV의 Weight 열은 9행 읽힘 |
| Weight 선택(V09) | 9행 균등 가운데값 (i-0.5)/9 → 1~9행 순서대로 선택. 경계 u=0·1/9-1e-9→normal.left, 1/9+1e-9→special.left, 2/9+1e-9→parry.left, 1-1e-12·1.0·1.5→마지막 행(parry.any). 가중치 1,2,3 행: u=0·0.1666→w1, 0.17·0.49→w2, 0.5·0.9999→w3, 1.0→마지막 w3. math.random 900회: 9행 각 82~118회(전부 선택됨), 200회 16~30회 |
| 동률 규칙 | anchors -1.5/0/1.5: -1.5→1, 1.5→3, 0→2, -0.750→2(동률), 0.750→2(동률), -0.760→1, -0.740→2, 0.760→3, ±9→끝 칸 |
| 2칸 착지(V01) | normal/special/parry.left 착지 x=0.75, .right는 -0.75(두 칸 중간). 판정 시각 hitDt≈0.50~0.52초, JumpDuration 0.5, 피해 12=HitEvent 합계 12 |
| ANY Pos2 조준(플레이어 x=0) | tgt=2 cells=010 영역 -0.5~0.5 dirs=LR 착지 x=0.0. 무대응 HIT 피해 12(=HitEvent 12). 일반 LEFT/RIGHT 저스트 각각 JUST·피해 0·슬로우 ≈2.0초·반격 true. 창 밖 이른 입력(0.45초 전)은 HIT 12. 특수·패링 속성도 JUST |
| ANY Pos1 조준(LEFT 홀드, x=-1.5) | tgt=1 cells=100 영역 -2.0~-1.0 dirs=R 착지 x=-1.5. 무대응 HIT 12, RIGHT 저스트 JUST 0(특수도), 조준 칸 쪽 LEFT는 HIT 12(저스트 아님), 패링 속성 무대응 HIT 12 |
| ANY Pos3 조준(RIGHT 홀드, x=1.5) | tgt=3 cells=001 영역 1.0~2.0 dirs=L 착지 x=1.5. 무대응 HIT 12, LEFT 저스트 JUST 0(패링 속성도), 조준 칸 쪽 RIGHT는 HIT 12 |
| 가드 분기(ANY, 아래 홀드) | 일반+가드=GUARD 피해 4(12×0.4 내림, =HitEvent 4), 특수+가드=HIT 12(가드 불가), 패링+창 안 가드=PARRY 0·반격 true·그로기 진입(2.5초 뒤 IDLE, 판정 0.5+복귀 0.5+그로기 1.5), 패링+창 밖 가드=GUARD 4 |
| 가드형 시험 데이터(V01 "시험 데이터 근거", 제품 CSV 밖의 Play 내부 단일 행) | 영역 -2~2 cells=111 착지 x=0.0, dirs 빈 집합. 일반+가드=GUARD 4, 패링+창 안 가드=PARRY 0·그로기, 패링+창 밖=GUARD 4. 기존 판정과 같음 |
| LEFT/RIGHT 회귀 | 올바른 방향 회피 JUST 0, 반대 방향(RIGHT 행에 LEFT 회피)은 HIT 12, 무대응 HIT 12 |
| 실제 키 입력 + 예고 뒤 이동(V03, K1b) | ANY(선행 4.0초, 시험 한정 창 4.0)를 Pos2에 조준한 뒤 maker_keyboard_input LeftArrow 홀드: tgt=2 cells=010 영역 -0.5~0.5가 판정 때까지 불변, 플레이어는 판정 순간 x=-1.5로 이동해 영역 밖 → 피해 0·HitEvent 없음, kind=JUST·슬로우 1.967·반격 true. 창을 확대하지 않은 첫 시도(K1)는 입력이 사례 시작 직후(창 밖)라 kind=HIT(저스트 아님)·피해 0(영역 밖)·같은 칸 고정이었다 |
| 탈출 검증 실패(V01) | 시험 행 AreaPaddingX=2.0의 ANY: 시작 거부, `telegraph escape area invalid: normal.any` 경고 1회, AttackSequence 불변, 몬스터 IDLE 유지, 칸 표시 없음 |
| 팝업 중 ANY 예고(V07) | 선행 6.0초 예고 중 팝업을 열어 전투 시계 346.829가 고정(샘플 3회), cells=010·resp=ANY·remaining 5.262 불변. 닫은 뒤 이어서 진행해 hitDt=6.003, HIT 12=HitEvent 12 |
| 예고 도중 Stop→재Play(V08) | 재Play 직후 TelegraphCells='' · Response='' · remaining 0 · pause false · AttackInterval 3.0 · 패턴 9행 · JustWindow 0.2 · evade '' · 반격 false · AttackSequence가 새로 시작(이전 값 비계승, 자연 공격 4회 뒤 4). 클라이언트 BattlePosMark 1~3은 ANY 예고 중 2번만 켜짐(cells=010), 판정 뒤·종료 뒤 모두 꺼짐 |
| 자연 공격 | 최초 Play에서 선택된 7회 가운데 ANY·LEFT/RIGHT가 섞여 나오고 모두 정상 판정·HUD 피드백이 났다 |

### 실패/미확인/미실시
- 프로브 오류와 제품 오류의 구분: 예고 도중 Stop한 프로브의 폴링 타이머 때문에 `LEA-3051 MemoryLeak`(MakerScript 라인) 1건이 났다. 시험 스크립트 문제이며 제품 오류는 관측되지 않았다. 팝업 시험에서 클라이언트 타이머가 팝업 정지로 멈춰 첫 시도가 무산돼 직접 호출로 닫았다(제품 문제 아님).
- 사람 손 타이밍의 0.20초 창 성공은 AI로 재현하지 않았다(저스트 입력은 시험 한정 창 확대 또는 필드 기록). 체감·가독성은 V11 몫이다.
- V04(ANY 성공의 반격 권한 부여는 확인, 소비·만료 경계는 기존 QA 근거 범위), V05(슬로우 ≈2.0초 부여는 확인, 전 구간 적분 재시험 안 함), V06(패링 그로기 진입·종료는 확인, 복귀 중 피격·팝업 조합은 재시험 안 함), V08(플레이어/몬스터 사망·다른 맵 전환 미실시), V10(UI 버튼 전 조합·동시 입력 미실시), 모바일 화면, 화면 육안(칸·예고 문구 색, 2칸 중간 착지 모션 모양)은 미실시다. V12 외부 환경은 NOT_RUN 유지.
- 끝 칸 ANY 난이도(방향 홀드 중에는 중앙 복귀로만 피함 → 저스트 보상 없음)는 Plan §15 설명대로 구현했고 체감 평가는 사용자 V11이다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) 로드·검증 거부·Weight 선택(경계 난수, 필요하면 임시 CSV 시험 후 원복), (2) ANY Pos1·Pos2·Pos3 조준과 유효 방향 집합·범위 밖 EVADE·무대응 HIT, 실제 키 입력, 예고 뒤 이동 불변, (3) 가드·패링·그로기 분기와 새 착지점에서의 복귀, 슬로우·반격 권한, (4) 2칸 착지 중간 위치, 가드형 시험 데이터, (5) 팝업·Stop 회귀와 F01 칸 표시, F02~F05 회귀(공유 경로). 사용자 V11 재확인(1칸 공격 구별·난이도, 2칸 중간 착지 모션, F01~F04)과 V12는 AI 결과로 대신하지 않는다.

### 2026-11-03 최종 제품 버전 묶음 (V11-F06)
- 이전 묶음(d2b57802…0fbb, 54경로)과 같은 경로 집합·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)이다. 1447ff8을 같은 방법으로 재계산해 d2b57802…0fbb 일치를 확인한 뒤 작업트리를 계산했다. 변경된 경로는 10개: MonsterAttackPatternData.csv, CombatRuleCatalog.mlua, AttackAreaMark.model·map/map01.map(Maker 재저장 형식 차이, 위 비교), Monster_Attack.mlua, MonsterAttackComponent.mlua, MonsterAttackMotion.mlua, OrangeMushroomAttack.mlua, PlayerHealthComponent.mlua, CombatInputController.mlua. 나머지 44개는 이전과 같다. .codeblock·.directory는 대상 외다.
- Bundle SHA-256: b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf.

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
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | fd557b85435ee92bd2616db605d5ce88a27c1a16e79e058eb9af7fa15cf49cd5 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.userdataset | 59bba89881cc2815cf9a1e47767d9c124c1a535f562459cd3335131eb35ce888 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.csv | db655856dcbdbe8dc9eab9ae9dca93cb573b4a44c9088ad9563be6efc50c7c81 |
| RootDesk/MyDesk/@Assist/DataSet/MonsterData.userdataset | b10bd13cc602f12bd50ed1ea92c8ecce07a29e9734b7899e76b9e3e30fd798b1 |
| RootDesk/MyDesk/@Assist/RangeGizmo/AttackRangeGizmo.model | 84c9e6ab606a1a54edf7490124de4a308d678efccfb6ad53c748de5c621b234e |
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 9c0e9b5bbc2ba588e021aeca0ac9f9dcaacdc6223ddae17ea955dcf2c8544907 |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua | 6a20d8c1a1b46fd50bc0a62695900fac3decc2def68b69124082eef8e2bf5f8b |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | bf287ec4e51466a827b9093d58e052c7e0eb6fe5bd22e43fcd8aa00b286c7020 |
| RootDesk/MyDesk/Managers/MonsterManager.mlua | 6cea8d7f99f55b50dc4dd0a96a0973c12cc7a934151b9d8d3a50dc7ab6bb2aab |
| RootDesk/MyDesk/Models/MapObjects/AttackAreaMark.model | 965f107350f59e76497a1b0a3b16cad58c11bdeaf594157e76e5b480f3f3fa29 |
| RootDesk/MyDesk/Models/Monsters/주황버섯.model | 1b7686acda7c84412676a7157681156cbef5f693e4b3c0872d609c5cf61c3b9d |
| RootDesk/MyDesk/Monster/@StateControl/MonsterStateControl.mlua | 3346a2b1c0a35752e32978bed6d34ce5b7295d9545639d9dc90e95eb8a27c395 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Attack.mlua | 9c04d255fd0af81b42eb798c1e39af2b3e3de7241621504d8490d7783d06fb62 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Defense.mlua | 3443b93e831d12eaf978a10260bd869c06754efd3cb7f41648526639a4e269d1 |
| RootDesk/MyDesk/Monster/@StateControl/Monster_Stun.mlua | 7ab182ba9ea1326190c178e7f1ee95ed33533a7699fac33f8d08ab061b9acbaf |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 9ef869fadce5fe12a111df55d4bf6a78812dcc5e74cc9a18567a4a523c252574 |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | e54d144379d8b30f9510295754388faca43c124d1d52590e9257feb46e4b4691 |
| RootDesk/MyDesk/Monster/MonsterDefenseComponent.mlua | d1ba0a0c5cb80dc54b93f75ed9103b705609519d7c49c06251a9125be81321da |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | 86ccd4916ab7b0c67ee0b71d4e02a1a48e4df8011038dbdcc94a833981455379 |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | 69ad2f52be603d7fedde3223678094968d859cd209f9771895ab1175ce29e3c9 |
| RootDesk/MyDesk/Monster/OrangeMushroom/OrangeMushroomAttack.mlua | 88a738ebc9f5aa7b4b78d74e4164a4f103cfff690fc7e1ccbb2ce2bde5035518 |
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
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | ede3e85448ba374cd288332c1727ff9f34fdcb995767de150d888845b230bc71 |
| RootDesk/MyDesk/Player/PlayerInputComponent.mlua | 3268e06bd6726009b2dc9b8fa2e8d00072dee5662eb1f195cdc3085fa8103705 |
| RootDesk/MyDesk/Player/PlayerMoveComponent.mlua | c794253d08b222280a563675b7dd778dc6802b765faa68cf34153d10136f10fd |
| RootDesk/MyDesk/UI/CombatHpBarController.mlua | 8a908f5bac7f723ae6326a836932c8959d0a2d846f7654e21f6acf5da841e36e |
| RootDesk/MyDesk/UI/CombatInputController.mlua | c66b26266b3a57ebcaae08d481b4bd296183f6c5e1f1e455eeaa83b7c3a6dded |
| RootDesk/MyDesk/UIPopup.mlua | 97e1d7f3b5f3eeb525e5805b1126962dca1d33ac9cd6e40516630599854c6fed |
| RootDesk/MyDesk/UIToast.mlua | baa498d9bb1745186cc098e45294dfe29db27f4fbafb98179d5fbb76064ec7e2 |
| map/map01.map | 02e41f3c81c09e95c49e0eb69c05e0d80d1f04845112be62d78cdda638250125 |
| ui/CombatScreen.ui | f0b37dd5142332caeb33e77cb10b32fc48f669e4db5aa868b58c24b78444ffe6 |
| ui/DefaultGroup.ui | 673cacd1d4717088dc75f576f35dd6147ace94a9c362ae3b73e0c54328bdef07 |
| ui/PopupGroup.ui | 7e405a3c6de93e25dd0d6b858d172c15579c52df1e811c862df48896073c23a4 |
| ui/ToastGroup.ui | 9c29998895c5fecc54bacbbdf0a8ca2c472d95fadbc5cb30fe46bed7c7fc444f |
