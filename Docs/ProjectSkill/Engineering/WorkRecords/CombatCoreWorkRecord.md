# CombatCore — 임시 작업 기록

- 연결 Plan: [2_CombatCore](../Plans/2_CombatCore.md).
- 상태·갱신일: 2026-11-03 / 최신: 독립 리뷰 REV-F02·V11-F10·V11-F11 **WAITING**(리뷰 기록 첫 절, 5c4eda3 커밋 트리 Bundle 9208e0aa…da79 / 작업 트리 fdca556d…ee80 재계산 일치, 제품 변경 6경로, 고칠 결함 없음, H1 규칙상 정상, 사용자 V11 대기). 그 전: 독립 QA 7회차 REV-F02·V11-F10·V11-F11·H1(QA 기록 첫 절, 커밋 5c4eda3 / 작업 트리 Bundle fdca556d…ee80 54/54 전후 일치, 전부 PASS·FAIL 없음·결함 후보 없음, 육안·0.20초 손 타이밍·CSV 파일 변경 반영·실제 키 해제 타이밍 NOT_RUN, 독립 reviewer 대기). 그 전: 독립 리뷰 V11-F08·F09 **WAITING**(리뷰 기록 첫 절, a921c76 / 작업 트리 Bundle 377a5ccc…0363 재계산 일치, 수정 필요 결함 없음, 범위 밖 결함 후보 CombatCore-REV-F02 일반 사망 die 미유지는 사용자 범위 결정 대기, 사용자 V11 육안 대기). 그 전: 독립 QA 6회차 V11-F08·F09(QA 기록 첫 절, 커밋 a921c76 / Bundle 377a5ccc…0363 54/54 전후 일치, F08 세 조건 그로기 전체 hit·종료 뒤 stand·복귀 jump·그로기 중 사망 die·정리 경로, F09 9패턴 문구 없음·칸 속성색, Plan §16 필수 2칸 패턴 F02 복귀 조합 V07·V08 PASS·FAIL 없음, 육안·0.20초 손 타이밍·CSV 변경 반영·실기기·플레이어 사망 중 칸·실제 맵 이동 NOT_RUN, 범위 밖 관찰 일반 사망 stand 표시 재현, 독립 reviewer 대기). 그 전: 독립 리뷰 V11-F01~F06 **WAITING**(리뷰 기록 첫 절, b89de46 / Bundle b985aa4b…74dbf 54/54 재계산 일치, 새 결함 없음, 사용자 V11·CF-F07 연출·V12 대기). 그 전: 독립 QA 5회차 V11-F01~F06(QA 기록 첫 절, Bundle b985aa4b…74dbf 54/54 전후 일치, F06 수치·로그 PASS·FAIL 없음·육안/창 0.20 손 타이밍/CSV 변경/F04 클립 재계측 NOT_RUN, 독립 reviewer F01~F06 일괄 리뷰 대기). 그 전: coder V11-F06 구현·기본 검증 인계(맨 아래 절, 새 Bundle b985aa4b…74dbf 54경로). 그 전(2026-11-02): 독립 QA 4회차 V11-F01~F05(QA 기록 첫 절, Bundle d2b57802…0fbb 54/54 전후 일치, 수치·로그 PASS·육안 일부 NOT_RUN, 독립 reviewer 대기). 그 전: coder V11-F01~F05 구현·기본 검증 인계(맨 아래 절, 새 Bundle d2b57802…0fbb 54경로). 아래는 그 이전 상태 — coder REV-F01 수정·기본 검증(커밋 6614b20 / Bundle 1ac324e6…9de4), 독립 tester 3회차 수치 PASS, 독립 리뷰 WAITING. 사용자 V11 대기. 2026-10-29 QA2·리뷰와 그 이전 기록은 이전 버전 근거.
- 실행: [20261020-combat-core](../../../../.pipeline/20261020-combat-core/run.md).
- 삭제 조건: 승인된 범위 구현·필수 확인·결과/미완료 추적 이관·링크 정리 완료 후 삭제. 사용자 직접 확인이 남으면 유지한다.

## 현재 재개 지점

2026-11-04(회차 A Plan 뒤) 기준: 2026-11-03 사용자 V11에서 §17의 F10 4패턴과 F11 "가드 불가" 문구는 통과했다. REV-F02는 die가 반복 재생된다는 보고로, 범위 밖 저스트는 "너무 쉬움" 보고와 Pos2 규칙 확정으로 이어진다. planner가 [Plan §19](../Plans/2_CombatCore.md)에 CombatCore-V11-F12(die 1회 재생 후 마지막 프레임 정지)와 V11-F13(JUST·PARRY 성공은 입력 시작 위치 Pos2 칸 ±0.75, 공격 영역 Pos2 포함 조건)을 정리했고, 2026-11-04 사용자 "A 회차 시작"으로 구현 승인 상태다. 다음은 msw-coder 한 회차(기준 5c4eda3, 이 기록 맨 아래에 새 개발절) → 같은 버전 msw-tester(QA 8회차) → msw-reviewer → 사용자 V11이다. 회귀로 다시 볼 기존 근거는 QA 7회차 REV-F02 사망 경로·E1 계열, QA 5회차 K3b·ANY 끝 칸 저스트(기대가 JUST 아님으로 바뀜)다(Plan §19 "다시 확인할 기존 근거"). 회차 B(플레이어 기본 능력치 DataSet·V11-F07)와 Plan §18(회차 C)은 그 뒤다. P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-03, 5c4eda3 리뷰 뒤): Plan §17 회차(REV-F02·V11-F10·V11-F11)는 msw-coder 구현·기본 검증(로컬 커밋 5c4eda3, 맨 아래 2026-11-03 개발절) → 별도 msw-tester 독립 QA 7회차(작업 트리 Bundle fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80, 54/54 전후 일치, H1 포함 전부 PASS) → 별도 msw-reviewer 독립 리뷰 **WAITING**(결함 없음, 5c4eda3 커밋 트리 Bundle 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79 / 작업 트리 fdca556d…ee80 재계산 일치, QA7 근거가 커밋 트리에도 적용)까지 마쳤다(각각 QA 기록·리뷰 기록 첫 절). 현재 AI 담당 작업은 없고 다음은 사용자 V11 확인이다. 확인 항목 5개는 리뷰 기록 첫 절 "사용자 V11 확인 항목"에 있고 [Plan §17 끝 "사용자 V11 확인 항목"](../Plans/2_CombatCore.md)에 연결했다. 그 뒤 Plan §18(머쉬맘 전환, MM-01·MM-02)은 사용자 재개 지시와 §18 질문 답을 받은 다음 시작한다. 남은 필수: V11, CF-F07 실제 연출 평가, V12 외부 환경과 기존 외부 후속 ID. P01b~P06은 🟡 유지, 3단계 미시작.

이전 재개 지점(2026-11-03, b89de46 기준): msw-coder가 V11-F06을 구현·기본 검증했고(커밋 b89de46 / 54경로 Bundle b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf, 맨 아래 2026-11-03 개발절), 별도 msw-tester가 같은 Bundle에서 독립 QA 5회차(커밋 a43b1b5, F01~F06 수치·로그 PASS·FAIL 없음, 육안·창 0.20 손 타이밍·CSV 변경 반영·F04 클립 재계측 NOT_RUN), 별도 msw-reviewer가 F01~F06 일괄 리뷰 **WAITING**(커밋 2dbaa07, 새 결함 없음)을 판정했다(각각 QA 기록·리뷰 기록 첫 절). 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다. 확인 항목 7개는 리뷰 기록 첫 절 "다음 행동" 4번에, 비차단 재확인 공백(2칸 패턴 패링 → 복귀 중 팝업 정지·재개, 복귀 중 Stop → 재Play 기본값)은 같은 절 "같은 버전 확인"에 있으며, 둘 다 [Plan §15 끝 "사용자 V11 확인 항목"](../Plans/2_CombatCore.md)에 연결했다. 남은 필수: V11, CF-F07 실제 연출 평가(수치 근거만 확보), V12 외부 환경과 기존 외부 후속 ID. V11에서 새 요구나 실기기 재현 결함이 나오면 해당 ID만 다시 돈다. P01b~P06은 🟡 유지, 3단계 미시작. 범위 밖 관찰인 플레이어 사망 직후 HP 문자 음수 표시 가능성은 V11 확인 항목 7번에 포함됐다(처리 여부는 3단계 계획 후보).

이전 재개 지점(2026-11-02, 6614b20 기준): 2026-11-02 사용자 재개 명령에 따라 msw-coder가 REV-F01을 최소 수정·기본 검증했고(커밋 6614b20 / 52파일 Bundle 1ac324e6…9de4, 아래 2026-11-02 개발절), 별도 msw-tester가 같은 Bundle에서 독립 QA 3회차 수치 PASS, 별도 msw-reviewer가 WAITING을 판정했다(각각 QA 기록·리뷰 기록 첫 절). 최종 map01/edit·Maker 사용 종료·제품 지문 전후 동일 확인. DOC-01 현황·링크 동기화는 2026-11-02 planner가 정리했다. 현재 AI 담당 작업은 없고 다음은 사용자 V11 직접 확인이다. 남은 필수: V11, CF-F07 실제 연출 평가(수치 근거만 확보), V12 외부 환경과 기존 외부 후속 ID. 결함 경과: QA-F01은 QA1 FAIL→QA2 수치 PASS, REV-F01은 2026-10-29 리뷰 지적→QA3 수치 PASS·리뷰 해소. 과거 FAIL과 이전 버전 QA/리뷰는 당시 근거로 보존한다. P01b~P06은 🟡 유지, 3단계 미시작. V11 때 함께 볼 범위 밖 관찰: 플레이어 사망 직후 HP 문자 음수 표시 가능성(새 규칙 아님, 처리 여부는 3단계 계획 후보).

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

### 2026-11-04 독립 QA 8회차 — 회차 A(V11-F12·V11-F13) — 중단(사용자 일시정지)
- 상태: **중단(사용자 일시정지)**. 사용자 요청("작업 일시 정지")으로 진행 중이던 위치 기록 삭제 단계(D1)만 마무리하고 새 시험은 시작하지 않았다. 아래에 실제 실행한 기준만 결과를 적고 나머지는 NOT_RUN이다. FAIL·결함 없음. 독립 reviewer 대기가 아니라 **재개 뒤 남은 NOT_RUN 실행이 먼저**다.
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 `[TQ8S]`·`[TQ9S]`·`[TQ10S]`·`[TQ11S]`·`[TQ12S]`·`[TQ13R]`·`[TQ13D]`(서버)·`[TQ8C]`(클라이언트) 표지와 시각으로 파일에 저장해 걸러 읽음). 시험이 만든 반복 타이머는 없다(`wait` 루프만 사용, 클라이언트 모니터는 마지막에 빈 스크립트로 중단). LEA-3051 없음.
- 대상 버전: coder 커밋 7f2d0b4 / 작업 트리 54경로 Bundle SHA-256 **b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f**(= 커밋 + 미커밋 Maker 재저장 3경로 AssistModel·AttackSkillData userdataset·주황버섯 모델, 건드리지 않음). 경로는 coder 절(V11-F06 표) 54경로를 이름으로 모아 ASCII 정렬, 각 줄 `경로\t해시\n`의 SHA-256. **시험 시작과 끝 모두 같은 값**(54개 경로별 해시 목록 diff 일치). 같은 방법으로 7f2d0b4 **커밋 트리** 값은 `7f32ae45d37aa6613db2c8de1c56ede5e0915fb5d0e0c34abb12a63340ce21e3`이다(Maker 재저장 3경로가 커밋과 달라 작업 트리 값과 다름이 정상). 시작·끝 git status는 Maker 재저장 3경로(M)와 메인·planner 문서뿐.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 다시 읽지 않았다. Refresh 하지 않음(파일 무변경). build 로그 81건 모두 Info(오류 0·경고 0, coder와 같은 건수). **Play 1회 연속**(약 18분, 14:13~14:32), Stop 1회. Warning 로그 2건은 모두 내 프로브가 만들었다: `[CombatRuleCatalog] pattern model missing: x`(첫 정보 프로브의 지역 변수 오류), `[Monster_Attack] Battle position missing`(S9에서 죽은 몬스터에 일부러 ChangeState("ATTACK")를 호출한 프로브). 제품 경로의 Error·Warning 없음. 최종 Stop 뒤 map01 / edit.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트에서 한 번에 스크립트 하나만 돈다). 서버·클라이언트가 같은 `_UtilLogic.ServerElapsedSeconds` 시계를 써 같은 시간축이다. 클라이언트 모니터는 몬스터 엔티티의 `SpriteAnimPlayerChangeFrameEvent` 프레임 번호와 렌더러 `SpriteRUID`/`StartFrameIndex`/`EndFrameIndex`/상태를 기록했고, 서버 프로브는 같은 값을 0.02초 폴링했다. 사망은 서버 `MonsterHealthComponent:ApplyDamage(999)`(제품 사망 확정 경로 그 자체)로 일으켰다. (B) 실제 키 입력 = maker_keyboard_input DownArrow 홀드·LeftArrow/RightArrow 탭(2.5~4.5초)·UpArrow 탭. 도구 왕복이 수 초라 판정 창을 손으로 맞출 수 없어 **시작 위치·시각을 강제한 사례는 "프로브 근거", 실제 키 사례는 판정 창을 넓힌 "시험값"**으로 구분했다. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(320,165)~(420,225)의 평균 절대 RGB 차이/최대값(Pillow). (D) 팝업 = 실제 `_UIPopup:Open`과 취소 핸들러 `OnClickCancel` 호출(마우스 클릭이 아님).
- 시험 한정 값(모두 Play 내부, Stop으로 폐기): 몬스터 `AttackInterval` 9999, 패턴 목록 단일 행 교체(`TelegraphLeadSec` 1.0~8.0, 속성·유형·대상 칸 지정), `math.random` 일시 교체(RANDOM 칸 고정, 호출 후 즉시 복원), 플레이어 HP 보충, 강제 시작 위치·시각(`SetEvading`/`ChangeState("GUARD")` 뒤 `_T.evadeStartX`/`guardStartX`·시각 덮어쓰기), 판정 창 **ParryWindowSec 40(R1 실제 ↓ 홀드 시험)·JustWindowSec 3.0·CounterWindowSec 8.0(K1b~K3 실제 ←/→ 시험, 이유: 실제 키로 0.20초 창에 맞출 수 없고 접근 점프 0.5초 때문에 선행 시간이 0.5초 이상)**, K4부터 JustWindowSec 0.2·ParryWindowSec 0.2·CounterWindowSec 2.0으로 복원(로그로 확인), F12 참조 화면용 렌더러 강제(프레임 고정·PlayRate 0), 서버 MOVE 순번 재정렬(아래 시험 오류). 모두 Stop으로 폐기. **Stop 뒤 다음 Play 기본값 재확인은 하지 못했다(NOT_RUN).**

#### V11-F12 — die 1회 재생 후 마지막 프레임 정지
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 8개 사망 경로(S1 IDLE, S2 ATTACK 시작 직후, S3 점프 중, S4 착지 대기(예고 4초 중 1.6초), S5 복귀 점프 중(판정 뒤 0.2초), S6 HIT, S7 슬로우 중(PlayRate 0.5), S8 그로기(STUN) 25초 중)의 서버 렌더러 | A | 모두 사망 +0.05~0.09초에 `65a2bf…\|0/2147483647\|DEAD`(die 첫 프레임부터), +0.40~0.49초에 `65a2bf…\|2/2\|DEAD`로 정지. 서버 로그 `MonsterDie start frames=3 total=0.660 freezeAfter=0.360`→`MonsterDie freeze frame=2`(전투 시계 차 0.36~0.37초). 관찰창 7.5초 동안 서버 렌더러 변화 0건, END 시점 `s/e=2/2`·상태 DEAD·hp 0. S7은 사망 직전 PlayRate 0.5가 사망 후 첫 폴링에서 1.0(복원)이었다 | PASS |
| 같은 8경로의 소유 클라이언트 프레임 시계열 | A | 사망 시점 기준 die 프레임 0@+0.06~0.08 → 1@+0.21~0.27 → 2@+0.38~0.44초가 한 번(지연 0.18·0.18초와 일치), 정지 시 프레임 2 이벤트가 한 번 더 나온 뒤 **1초 이후 프레임 이벤트·렌더러 변화 0건**(경로별 7.5초 창 전부). 클라이언트 렌더러 값은 마지막에 `65a2bf…\|2/2\|DEAD`. 슬로우(S7)도 기본 속도 간격(0.18/0.19초)으로 한 번 | PASS |
| 정지 뒤 서로 다른 세 시점 이상 스크린샷 | C | 살아 있는 stand 화면과 정지 뒤 4장(사망 후 약 5초 두 장(0.07초 간격)·약 19초·약 33초)의 몬스터 영역: 정지 4장끼리 평균 0.000·최대 0(완전 동일), 살아 있는 stand와는 29.8/255. 읽은 장면은 눌린 die 마지막 모습(HP 0/100) | PASS |
| 재생 중과 다른 화면(참고) | C(렌더러 강제 참조) | 재생 중 장면은 0.36초라 캡처하지 못했고(팝업이 가림), 살아 있는 몬스터에 die RUID·PlayRate 0으로 **프레임 0**을 붙잡은 화면은 정지 화면과 23.2/255 다름. 프레임 1을 붙잡은 화면(StartFrameIndex=EndFrameIndex=1)은 정지 화면(프레임 2)과 0.000/0으로 **같다**(die 클립의 프레임 1·2는 같은 모습). 따라서 화면 픽셀로 구별되는 것은 첫 프레임 0.18초뿐이고, 재생·정지 증명은 프레임 이벤트·렌더러 값이 근거다 | PASS(근거 한계 있음, 관찰 3번) |
| 실제 UIPopup — die 재생 도중 열고 닫기 | A+D | 사망 +0.087초에 팝업 요청, 서버 전투 시계 424.468(die 시작 424.415)에서 정지, 약 12초 뒤 닫자 서버 정지 해제(시계 424.468 그대로) → 클라이언트 프레임 1@+0.16초·2@+0.17초 뒤 이어서 재생(**프레임 0 이벤트 없음, 처음부터 다시 시작하지 않음**), 서버 정지 전투 시계 424.788(= die 시작 0.373초)에 프레임 2 고정 | PASS |
| 실제 UIPopup — 정지 뒤 열고 닫기 | A+C+D | 사망 +0.36초 정지 뒤 +6.07초에 팝업(서버 정지 485.467), 19초 뒤 닫음: 렌더러 `2/2` 유지, 프레임 이벤트·렌더러 변화 0건, 닫은 뒤 스크린샷 두 장은 앞서 찍은 정지 화면과 0.000/0 | PASS |
| 추가 관찰(우연히 만든 조합): 팝업으로 정지된 상태에서 사망 | A | 내 모니터 오류로 팝업이 먼저 열린 상태에서 몬스터가 생성·사망(`MonsterHealth lethal state=DEAD enabled=false`). die 시작 시계 346.296에서 정지 중 시계가 흐르지 않았고, 닫은 뒤 프레임 1·2가 한 번 재생되고 시계 346.671에 고정 | PASS(참고) |
| 늦은 경로 — 사망 +0.155초와 +2.1~3.0초(S9, 프로브가 직접 호출) | A | +0.155초에 `SetVisualClip("die")`·`("stand")`·`("jump")`·`("stun")` 연속 호출, +2.1초에 `SetStunned(false)`·`ClearCombatEffects`·`CancelPendingAttack`·`ApplyGroggy(2)`·`ApplySlow(5,0.5)`·`CancelMotion`, +3.0초에 `JumpActive` 강제 뒤 `CompleteMotion`·`SetVisualClip("stand")`·`ApplyDamage(5)`: 서버·클라이언트 렌더러 `65a2bf…\|2/2` 그대로, 클라이언트 프레임 이벤트는 정상 한 번(0·1·2)뿐이고 추가 이벤트 0건. S2~S8은 제품 경로 자체(그로기 종료 `SetStunned(false)`→die 재호출(S8), 슬로우 복원(S7), 공격 취소·점프 완료·복귀 완료(S2~S5), HIT 복귀(S6))를 그대로 거쳤고 정지를 풀지 않았다 | PASS |
| DEAD·DeadEvent 1회·HP=HitEvent=숫자(F12 항목) | - | DeadEvent 횟수와 HitEvent 합계는 이번에 읽지 않았다. DEAD 상태·HP 0·IsDead true만 확인 | NOT_RUN(DEAD만 확인) |
| 사망 후 새 상대 stand 시작·Stop 뒤 다음 Play stand·정지 설정 잔존 없음 | - | 살아 있는 새 몬스터(DoSpawn)의 시작 렌더러는 `96e955…\|0/0\|IDLE`이고 클라이언트에서 stand가 프레임 0↔1로 정상 반복 재생(첫 맵 배치 몬스터는 `0/2147483647`). 이전 사망의 정지 값이 새 몬스터에 남은 사례 없음(8번 교체). **Stop 뒤 다음 Play는 확인하지 못했다** | PASS(DoSpawn 교체)·NOT_RUN(Stop 뒤 다음 Play) |
| 회귀: 살아 있는 동안 stand·jump 재생, 그로기 hit(F08), 2칸 중간 착지(F06), 복귀 뒤 그로기(F02) | A | stand 0↔1 반복, ATTACK 점프 클립(`94bbe2`)·stand 복귀를 클라이언트 모니터에서 확인. F13 PARRY 사례 10건(프로브 7·실제 ↓ 3) 모두 `sawStun=true`로 복귀 뒤 그로기 진입(F02). hit 클립 표시와 2칸 중간 착지 위치(x=±0.75)는 직접 측정하지 않았다 | PASS(stand·jump·F02 진입 대표)·NOT_RUN(F08 hit 표시·F06 착지 위치 측정) |

#### V11-F13 — JUST·PARRY 성공은 Pos2 시작 + 영역 Pos2 포함
기본 실행 x는 Pos1 -1.5·Pos2 0·Pos3 1.5, 패딩 0.5, 칸 경계 ±0.75. 사례마다 `[VRF] PlayerHealth evade/guard eval x=… cellOk=… areaOk=…`와 `[VRF] CombatCore defense` 로그를 같이 확인했다.
| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| 회피 20사례(프로브 근거: 시작 위치·시각·방향을 서버가 강제, 플레이어는 x=0에 서 있음, 창 0.20 안에서 판정 직전 입력) | A | E01 parry.left LEFT·E02 parry.right RIGHT·E03/E04 parry.any 최근접(Pos2) 좌/우·E05/E05b special.random 칸 2 좌/우 → **JUST**·피해 0·반격 권한 true·슬로우 true. E06 special.random 칸 1(영역 -2.0~-1.0)에서 멀어지는 방향·E07 칸 3·E17 패링 속성 1칸 칸 1·E19 입력 없음 칸 1 → **JUST 아님**, 영역 밖이라 네이티브 피격 없음 → 피드백 EVADE·피해 0·반격/슬로우 없음(QA5 K3b·QA7 E1 계열 기대가 JUST에서 바뀜). E08 시작 x +0.75·E09 -0.75 → JUST(경계 포함). E10 +0.76·E11 -0.76·E12 +0.80(parry.left)·E13 -0.80(parry.right) → JUST 아님, 영역 안이라 **HIT**·피해 12. E14 틀린 방향·E15 창보다 0.6초 일찍 시작·E16 시작 위치 기록 없음·E18 입력 없음 → HIT 12. 20건 모두 기대와 일치 | PASS(프로브 근거) |
| 가드 20사례(프로브 근거: 서버 `ChangeState("GUARD")`로 시작 기록 뒤 위치·시각 덮어쓰기) | A | G01 parry.left·G02 parry.right·G03 parry.any·G05 패링 속성 1칸 칸 2 → **PARRY**·피해 0·반격 권한·복귀 뒤 그로기 예약. G04/G04b 패링 속성 1칸 칸 1/3(영역이 Pos2 불포함) → PARRY 아님(결과 종류 GUARD), 영역 밖이라 피드백 EVADE·피해 0·그로기 없음. G06 x=+0.80·G07 -0.80·G09 +0.76·G09b -0.76 → **GUARD** 12×0.40=4.8→4. G08 +0.75·G08b -0.75 → PARRY(경계 포함). G10 special.random 칸 2 → **UNGUARDABLE**·원래 피해 12, G10b 칸 1(영역 밖) → 피드백 EVADE 0. 시험 데이터(가드형 3칸, Pos2 포함): G11 NORMAL → GUARD 4, G12 PARRY 속성 → PARRY, G13 같은 행 x=+0.80 → GUARD 4. G14 가드 시작 0.5초 전(창 밖)·G15 시작 위치 기록 없음 → GUARD 4. G16 일반 속성 ANY → GUARD 4. 20건 모두 일치. PARRY 7건 모두 복귀 뒤 `sawStun=true` | PASS(프로브 근거, 가드형 3칸은 시험 데이터 근거) |
| 실제 DownArrow 홀드(시험값 ParryWindowSec 40, 서버 GUARD 상태·시작 x=0.000 기록) 6사례 | B+A | R1a parry.left·R1b parry.right·R1c parry.any → **PARRY**·피해 0·반격·그로기. R1d 패링 속성 1칸 칸 1 → 결과 GUARD, 피드백 EVADE 0·그로기 없음. R1e special.random 칸 2 → **UNGUARDABLE** 12. R1f 가드형 일반 3칸 → GUARD 4. 6건 일치 | PASS(시험값) |
| 실제 LeftArrow/RightArrow(시험값 JustWindowSec 3.0) JUST | B+A | K1b LeftArrow + parry.left·K2 RightArrow + parry.right → **JUST**·피해 0·반격 권한·슬로우(K1b `manual cast … factor=2.2`: 곧바로 **실제 UpArrow**로 반격 1회 소비 확인, count=10) . 판정 순간 플레이어는 이미 x=∓1.5(영역 밖, nativeHit nil)였고 시작 기록 x=0.000으로 성공 | PASS(시험값) |
| 실제 키: 끝 칸 홀드 겹침(H1) 및 창 밖 시작·홀드 해제 | B+A | K3 LeftArrow 홀드 + special.random 칸 1(영역 -2.0~-1.0, 판정 때 플레이어 -1.5): `areaOk=false` → **HIT**·피해 12. K4(기본 창 0.20, 선행 2.5초) LeftArrow + special.random 칸 3: 창보다 일찍 시작, 판정 때 영역 밖 → JUST 아님·**EVADE 0**. K5 LeftArrow 홀드 후 실제 키 해제(2.5초), 선행 5.0초, 칸 1: 판정 때 x=0.000(복귀) → EVADE 0 | PASS(K3은 시험값 창 3.0, K4는 기본 창 0.20, K5는 기본 창 0.20 상태로 실행) |
| 서버 기록 시작 x 대 클라이언트 segment.startX | B+A | 실제 LeftArrow/RightArrow 6건(K1 첫 실행·K1b·K2·K3·K4·K5)의 클라이언트 `MovementInput phase=OUTBOUND x=0.0`과 서버 `PlayerEvade start x=0.000` **차이 0.000**. DownArrow 1회 홀드(R1 6사례가 같은 홀드) 서버 `PlayerGuard start x=0.000`(클라이언트 이동 구간 없음). 서버가 MOVE를 감지한 뒤 0.1초 시점에 서버가 읽은 플레이어 x는 -0.59~-0.91로 이미 움직였지만 서버가 시작 기록을 남긴 순간은 0.000이었다. 정상 입력이 위치 때문에 거부된 사례 0건 | PASS(시료 6건, 단일 접속) |
| 위치 기록 삭제 — 팝업 닫기 | A+D | 예고(선행 8.0초) 중 회피 시작 x=0.12·시각, 가드 시작 x=0.34·시각을 심은 뒤 실제 UIPopup 열기: 정지 중 예고 남은 시간 6.127→(닫음)5.973(정지 중 보존), 정지 중 x 값 0.120/0.340 유지. 닫은 직후 `evX=nil evT=-1.0 gdX=nil gdT=-1.0`. 이어진 판정은 JUST·PARRY가 아닌 **HIT 12**(이전 시작 기록이 쓰이지 않음) | PASS |
| 위치 기록 삭제 — 플레이어 사망, Stop 뒤 | - | 실행하지 않음 | NOT_RUN |
| 회귀: 일반 가드 ×0.40, 특수 가드 UNGUARDABLE, 무가드 범위 안 HIT, 영역 밖 EVADE 0, 반격 소비·슬로우 | A+B | 위 가드·회피 사례 그대로(GUARD 4=12×0.40 내림, UNGUARDABLE 12, HIT 12, EVADE 0, 반격 ×2.2 소비 1회, 슬로우 true). 피해 숫자는 `hpDelta`가 기대값(12·4·0)과 일치한 것으로만 확인(HitEvent 합계는 읽지 않음) | PASS(대표) |
| 회귀: 예고 중 팝업(정지·재개), 패링 뒤 그로기 대표 | A+D | 위 팝업 사례에서 예고 정지·재개 확인. 그로기는 복귀 뒤 진입 10건 확인 | PASS(대표) |
| 회귀: HP=HitEvent=숫자 직접 비교, parry.any Pos1·Pos3 홀드 끝 칸, Stop 뒤 다음 Play 기본값 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 결함: **없음**. FAIL·NEEDS_DECISION 없음. 새 결함 ID 없음.
- 시험 오류(제품 오류 아님): (1) **K1 첫 실행은 MISMATCH였으나 시험 오염**이다. 내 강제 시험이 `SetEvading(true)`를 약 40번 호출해 서버 `PlayerEvadeComponent._T.moveEpoch`가 19까지 올랐고 소유 클라이언트의 실제 MOVE 순번은 1이어서 `ConfirmDirection`이 방향 순번 불일치로 거부됐다(`dir=` 빈 값, 두 값을 읽어 확인: 서버 19/클라이언트 1). 서버 순번을 클라이언트에 맞춰 1로 되돌린 뒤 같은 사례를 K1b로 다시 실행해 JUST가 나왔다. K1 첫 결과는 과거 시험 오류로 남긴다(제품 코드 변경 경로 아님, 이번 버전이 바꾼 영역도 아님). 이후 사례(K1b~K5)의 `[VRF] PlayerHealth evade eval … dir=LEFT/RIGHT`로 방향 확정 확인. (2) 첫 팝업 시험에서 클라이언트 모니터가 이전 사망 몬스터를 보고 먼저 팝업을 열어 의도한 "사망 +0.03초 팝업"이 아니라 "정지 상태에서 사망" 조합이 됐고, 감시 대상을 새 몬스터로 바꿔 다시 실행했다(위 두 행). (3) 첫 정보 프로브의 지역 변수 범위 오류로 `pattern model missing: x` 경고가 한 건 났다. (4) 프로브의 "재생 중 화면" 참조는 StartFrameIndex=EndFrameIndex=0이 "전체 클립"과 같은 기본값이라 프레임 0을 고정하지 못했고(루프 재생), PlayRate 0 방식으로 다시 찍었다.
- 관찰(바꾸지 않음, 판정은 reviewer): (1) 맵 배치 몬스터의 시작 렌더러는 `0/2147483647`, DoSpawn 몬스터는 `0/0`이다(coder 관찰과 같은 기존 현상, stand는 0↔1 정상 재생, 사망 때 PlayDieOnce가 `0/2147483647`로 정리). (2) die 클립의 프레임 1과 2가 화면상 같아서 화면 픽셀로는 "재생 중"을 거의 구별할 수 없다(프레임 0 0.18초만 다름). (3) 죽은 몬스터에 프로브가 `StateComponent:ChangeState("IDLE"/"HIT"/"ATTACK")`을 직접 호출하면 엔진이 전환을 허용해 상태가 IDLE로 바뀌었다(제품 코드는 모든 경로에서 IsDead를 확인해 이 호출을 하지 않음, 이번 변경 밖). 그때도 렌더러는 die 2/2 그대로였고 프레임 이벤트가 새로 생기지 않았다. (4) 시료 크기: 실제 키 위치 차이 6건(단일 접속)·강제 사례 40건.
- 한계: 판정 창을 넓힌 시험값(위)으로 방향·유형·결과 종류를 확인했고 0.20초 손 타이밍은 K4(기본 창, 창 밖 시작) 한 사례뿐이다. 재생 중(0.36초) die 화면의 캡처와 사람 육안 평가 없음. 팝업 닫기는 취소 핸들러 호출. 클라이언트가 실제로 그리는 클립을 읽는 API가 없어 렌더러 값·프레임 이벤트·스크린샷이 근거다. 단일 접속·Maker 환경. 서버 지연이 큰 환경에서의 위치 기록 오차는 미확인.

#### NOT_RUN(재개 뒤 실행할 것)
1. F12: 사망 경로별 팝업(재생 중·정지 뒤)은 IDLE 경로 한 건만 실행(나머지 경로 조합 NOT_RUN), 실제 UpArrow로 그로기 중 처치, DeadEvent 1회·HP=HitEvent 합계 직접 비교, **Stop 뒤 다음 Play에서 stand 시작과 정지 설정 잔존 없음**, F08 hit 표시·F06 2칸 중간 착지 위치 측정.
2. F13: **플레이어 사망 뒤 위치 기록 삭제**, **Stop 뒤 위치 기록·시험값 기본 복원**, parry.any Pos1·Pos3 홀드 끝 칸 실제 키, HP=HitEvent 합계 직접 비교, 사람 손 0.20초 타이밍.
3. 사용자 V11: die 한 번 재생·끝 모습 정지의 육안(그로기 중 처치·팝업 뒤·모바일), Pos2에서 가운데 칸 공격에만 저스트·패링이 나는 체감과 끝 칸 1칸 공격(특수 무작위) 무보상 난이도. 그 밖의 기존 V11 미확인 항목(모바일·터치·음향·반격 체감·CF-F07).
- 사용 종료: maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 시작·끝 54/54 동일 Bundle b321d71c…040f, 제품 파일 무수정. Maker 사용 종료. commit·push 하지 않음.

### 2026-11-03 독립 QA 7회차 — REV-F02·V11-F10·V11-F11·H1
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA와 coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·`[QA7S]`(서버)·`[QA7C]`(클라이언트)·`[QA7V]`(검증 프로브)·`[QA7W]`(선택 경계)·`[QA7M]`/`[QA7U]`/`[QA7H]`/`[QA7R]`/`[QA7G]` 표지로 파일에 저장해 걸러 읽음). 시험 스크립트는 `_TimerService` 타이머를 만들지 않고 `wait` 루프만 써 `LEA-3051`이 나지 않았다.
- 대상: coder 커밋 5c4eda3(기준 a921c76) / 작업 트리 54경로 Bundle SHA-256 fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80(= 커밋 + 미커밋 Maker 재저장 3경로, 건드리지 않음). 계산법은 coder 절 manifest의 54경로(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결). 경로 행은 표를 **이름으로 모아** 계산했고(coder 절이 늘어 줄 번호가 밀림) 시험 시작과 끝에 같은 값이며 두 계산의 54개 경로별 해시 목록도 `diff` 일치다. 시작과 끝 git status는 Maker 재저장 3경로(M)와 메인·planner 문서뿐이다.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. Refresh는 하지 않았다(파일 무변경, Maker 재저장 방지). build 로그 81건 모두 Info, 오류 0·경고 0(시험 전·후 같음). Play 4회(최초 Play 1회, Stop 뒤 재Play 3회), Stop 4회. 최종 Stop 뒤 map01 / edit. Maker 로그 시각 19:45~20:03. Error·Warning 레벨 로그는 시험 시간대에 [QA7V] 검증 프로브가 일부러 만든 CombatRuleCatalog 경고 13건뿐이다(14건 중 baseline 제외 13항목 각 1건). 19:36~19:40의 경고·LEA-3051 1건은 coder의 이전 Play 로그다.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client, 각 컨텍스트에서 한 번에 스크립트 하나만 돈다 — 새 스크립트가 이전 것을 멈춰 병렬 모니터는 서버/클라이언트로 나눴다). 서버는 `_UtilLogic.ServerElapsedSeconds`로, 클라이언트도 같은 시계로 기록해 시간축이 같다. 시험 헬퍼는 서버 `_CombatRuleCatalog._T.QA`와 클라이언트 `_CombatInputController._T.QA`에 두었고 Stop으로 폐기됐다(재Play에서 nil 확인). (B) 실제 키 입력 = maker_keyboard_input(DownArrow 가드·LeftArrow/RightArrow 이동·UpArrow 공격). 도구 왕복이 수 초라 판정 창 안에 손을 맞출 수 없어, **키 입력으로 시작·유지하는 시험은 서버 프로브가 플레이어 상태(GUARD/MOVE)를 감지한 직후 예고를 시작하는 방식**으로 했고 창 값은 시험 값으로 넓혔다. 타이밍이 중요한 해제(H1 홀드 떼기)는 실제 키 `down` 홀드 뒤 클라이언트가 입력 수락 지점 `PlayerStateControl:ReleaseHeldState`(키 해제 핸들러가 부르는 같은 함수)를 `TelegraphRemaining` 기준으로 호출했다 — 논리 경로 검사다. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(330,165)~(400,222)의 평균 절대 RGB 차이와 사람이 읽은 장면.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 마지막 재Play에서 기본값 확인: JustWindowSec 0.2·ParryWindowSec 0.2·CounterWindowSec 2.0·GuardDamageRate 0.4·AttackInterval 3.0·패턴 4행·Weight 2·2·2·1): `_CombatRuleCatalog.rules["default"]`의 Just·Parry 창 3.0(B·B2·C2·D·E·H1·PL·PR 실제 키 시험을 위해, LG는 Parry 0.1), CounterWindowSec 8(반격 소비 시험 한정), 단일 행 패턴 목록과 `TelegraphLeadSec`(0.6~6.0, 시험 행), `math.random` 일시 교체(한 번 호출 동안 고정 단위로 무작위 칸 고정, 즉시 복원), 몬스터 AttackInterval 9999·HP 5·`ApplyGroggy(25)`·`ApplySlow(8, 0.5)`·`ApplyDamage(999)`, 플레이어 HP 보충. CSV·제품 파일은 바꾸지 않았다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| REV-F02 IDLE 사망(실제 UpArrow) | A+B | HP 5, 서버 IDLE→실제 ↑ 공격(`manual cast`)→DEAD. 사망 +0.00·+0.2·+1.2·+2.5초 서버 SpriteRUID=ActionSheet die, 상태 DEAD, IsDead true, HP 0, paused false. (참고: 이 실행에서 클라이언트 프로브가 이전 몬스터의 사망을 보고 먼저 UIPopup을 열어 첫 ↑ 입력은 팝업 입력 차단으로 무시됐고, 팝업을 닫은 뒤 입력으로 처치했다. 순서 실수이며 입력 차단은 기대 동작) | PASS |
| REV-F02 ATTACK 시작 직후·점프 중·착지 대기·복귀 점프·HIT·슬로우+점프(S2·S3·S3b·S4·S5·S6, 서버 `ApplyDamage(999)`) | A | 모두 사망 시점(+0.00)부터 +0.2·+1.2·+2.5초까지 서버 clip=die, DEAD. 점프 중 사망은 몸이 y만 0.58로 낙하하고 x 고정. S6은 사망 때 PlayRate 0.5→1.0 복원, die 유지. 클라이언트 SpriteRUID·상태는 같은 몬스터에 대해 `DEAD\|die`로 한 번 바뀐 뒤 stand·jump·hit로 바뀐 줄이 없다(변경만 기록) | PASS |
| REV-F02 그로기 중 사망(실제 UpArrow, S7) | A+B | `ApplyGroggy(25)`로 STUN\|hit 유지 중 실제 ↑ → 클라이언트 STUN→HIT\|hit(타격 이벤트 1회)→DEAD\|die. 서버 +0.00부터 +8.0초까지 die, isStunned false | PASS |
| REV-F02 실제 UIPopup 열고 닫기 중·후 사망 표시 | A+C | S7 사망 +3.4초에 `_UIPopup:Open`(실제 코드, 서버 paused=true 승인) → 열린 동안 사망 +4.0·+6.0 서버 clip die·paused true → `OnClickCancel`(취소 버튼 핸들러) → `popup closed`, +8.0초 paused false·die 유지. 열린 스크린샷은 팝업이 몬스터를 가려 근거가 안 되고, 닫은 뒤 스크린샷은 눌린 die 프레임으로 읽힘(몬스터 영역 차이: die 기준 22.6, stand 기준 44.3. S1 처치 뒤 팝업 닫은 장면과 같은 값) | PASS(팝업 클릭은 마우스가 아니라 취소 핸들러 호출) |
| REV-F02 Stop 뒤 재Play stand 시작 | A+C | 사망(서버 DEAD\|die 확인) 뒤 Stop → Play: 서버 t=1.36초 IDLE\|stand·IsDead false·HP 100, 클라이언트 t=2.92초 IDLE\|stand, 재Play 스크린샷은 stand 계열(stand 기준 20.8·die 기준 44.5). 시험 값(규칙·창·AttackInterval·패턴 4행)도 기본으로 돌아옴 | PASS |
| V11-F10 로드(4행·AreaTarget) | A+파일 읽기 | CSV는 4행(`AreaTarget` 열 추가), normal.*·special.left·special.right·special.any 없음. 매 Play `[VRF] CombatCore catalog ready rules=1 patterns=4`. 런타임 행 id·ResponseType·속성·앵커·Weight 2·2·2·1·AreaTarget FIXED·FIXED·NEAREST·RANDOM | PASS |
| V11-F10 검증 거부(V09) | A | 실제 DataSet 행을 복사해 한 항목씩 변경한 ValidateRows 호출을 같은 입력 두 번씩: baseline ok/ok, AreaTarget 빈 값·BOGUS·nil, ANY+FIXED, LEFT+NEAREST, RIGHT+RANDOM, RANDOM 앵커 1/1, NEAREST 앵커 0/2, FIXED 앵커 0/0, FIXED 앵커 3/2, SPECIAL+GUARD, Weight 0, Weight abc, 선행 시간 < 창이 모두 REJECT/REJECT, 항목마다 경고 1건(두 번째 호출은 늘지 않음). 필수 열 누락(`ReadRows`에 없는 열 요구)은 nil(전체 거부). 거부 뒤 카탈로그 Ready true·4행 유지. CSV 파일 자체를 바꾼 열 누락 시험은 하지 않음 | PASS(CSV 파일 변경 NOT_RUN) |
| V11-F10 패턴 선택·무작위 칸 경계 | A | 합 7: 단위 0·1.999/7→parry.left, 2/7·3.999/7→parry.right, 4/7·5.999/7→parry.any, 6/7·0.9999999999→special.random(누적 [0,2)·[2,4)·[4,6)·[6,7), CSV 행 순서). 700표본 199/192/198/111. SelectRandomCell: 0·0.3·0.3333→1, 1/3·0.34·0.6666→2, 2/3·0.67·0.9999999999→3, 600표본 197/201/202 | PASS |
| V11-F10 RANDOM 칸·플레이어 위치 무관·예고 뒤 불변 | A | 플레이어 Pos2(x=0.0)일 때 난수 고정 0.1/0.5/0.9: 칸 1→영역 -2.0~-1.0·cells 100·유효방향 R, 칸 2→-0.5~0.5·010·LR, 칸 3→1.0~2.0·001·L, TelegraphAttribute SPECIAL. 예고 뒤 플레이어가 중앙→Pos3으로 움직이는 동안에도(E1) 판정 영역은 예고 때 값 -2.0~-1.0·cells 100 그대로. 예고 중 UIPopup(PU2: 칸 3, 영역 1.0~2.0)도 영역·cells 불변, 클라이언트 칸 표시 `3:[SPECIAL]`(1·2번 칸은 꺼짐), 팝업 중 남은 예고 시간 4.441→4.352(정지), 닫은 뒤 2.028로 재개 | PASS |
| V11-F10 special.random 판정(실제 키 입력 포함) | A+B | 무대응 범위 안(A·A2·플레이어 Pos2): HIT, 피해 12=HitEvent 12, HUD "피격". 범위 밖(C·C3: 칸 1·3, 플레이어 중앙): nativeHit nil, HP 0, HUD "회피". 실제 DownArrow 가드(창 3.0 시험값, 가드 시작이 판정 1.03초 전) 범위 안(B): UNGUARDABLE·rate 1, HP -12=HitEvent 12, 패링·슬로우·반격 권한·그로기 없음 → **↓ 패링 불성공**. 같은 시험값에서 PARRY 속성(B2, parry.any)은 실제 ↓로 PARRY·피해 0·반격 권한·그로기 → 시험값이 실제로 패링을 허용하는 상태였음(대조) | PASS(창 3.0은 시험값) |
| V11-F10 RANDOM 저스트·슬로우·반격 권한 | A+B | 실제 LeftArrow(칸 2, 범위 안 출발 E2): JUST·rate 0, 슬로우 2.0초 ×0.5(`slow applied duration=2.0 rate=0.5`), 반격 권한 ×2.2, HUD "저스트 회피 성공"+"반격 준비"+"상대 슬로우". 실제 RightArrow(칸 1, 범위 밖 중앙에서 출발 E1·E1b·E1c·E1d·E1e): JUST·rate 0, nativeHit nil, 같은 결과. 반격 소비(E1e): 반격 권한 부여 뒤 입력 수락 지점의 ATTACK 요청(논리 경로, 지연 때문에 실제 ↑ 3번은 창 안에 못 맞춤)이 `manual cast ... factor=2.2` | PASS(반격 소비는 논리 경로) |
| V11-F10 고정 칸 쪽 방향·중앙 복귀는 저스트 아님 | A+B | 칸 1에서 LeftArrow(고정 칸 쪽): evDir=LEFT, 결과 HIT(영역 안에 머무름)·JUST 아님(H1a·H1b). 칸 3에서 RightArrow도 HIT. 중앙 복귀는 홀드 뒤 떼기(H1e)에서 EVADE 0, JUST 아님 | PASS |
| V11-F10 parry.any 회귀(Pos1·Pos2·Pos3) | A+B | 실제 LeftArrow 홀드 Pos1에서 parry.any: 대상 칸 1·영역 -2.0~-1.0·유효방향 R(H1d). Pos2(B2): 칸 2·010·LR, 실제 ↓로 PARRY. 실제 RightArrow 홀드 Pos3(H1f-R): 칸 3·001·L, HIT 12=HitEvent 12 | PASS |
| V11-F10 parry.left·parry.right 회귀 | A+B+C | parry.left(실제 ↓ 가드로 PARRY): 클라이언트 관측 ATTACK\|jump(x 2.92)→착지 ATTACK\|stand x=0.75(영역 -0.5~2.0의 중앙)→판정(PARRY·피해 0)→복귀 ATTACK\|jump→**x=3.00 처음 위치에서** STUN\|hit 1.5초→IDLE\|stand. parry.right: 착지 x=-0.75(영역 -2.0~0.5의 중앙), 같은 흐름. F02 복귀 뒤 그로기·F08 그로기 hit·2칸 중간 착지 유지(parry.left 첫 실행 PL은 서버 모니터가 멈춰 판정 로그만 있고, PL2·PR을 클라이언트 모니터로 판정에 사용) | PASS |
| V11-F10 일반(NORMAL)·가드형(GUARD) 유형(시험 데이터 근거) | A+B | NORMAL 시험 행(parry.any 복사, 속성만 NORMAL, D): 실제 ↓ 가드 → GUARD·rate 0.4, 피해 4=HitEvent 4(12×0.4=4.8→4), HUD "가드 · 피해 경감". GUARD 유형 시험 행(속성 NORMAL, 앵커 1~3, FIXED): cells 111·영역 -2.0~2.0·유효방향 없음, 실제 ↓ 가드 → GUARD·0.4, HP -4. 실제 데이터에는 없음 | PASS(시험 데이터 근거) |
| V11-F11 가드 중 범위 안 "가드 불가" | A+B | 위 B: 실제 ↓ 가드 중 special.random 범위 안: `[VRF] defense kind=UNGUARDABLE rate=1`, nativeHit true, HP -12=HitEvent 12, 클라이언트 defenseText "가드 불가" 색 (1.00, 0.43, 0.36), 456.078→457.076초 약 1.0초 뒤 비워짐. 슬로우·반격·그로기 없음 | PASS |
| V11-F11 가드 중 범위 밖 "회피"·무가드 "피격"·일반 가드 문구 | A+B | 가드 중 범위 밖(C2, 칸 1): UNGUARDABLE이나 nativeHit nil → RecordDefense가 EVADE로 대체, HP 0, HUD "회피"(0.65, 0.83, 1.00). 무가드 범위 안(A2): HUD "피격"(1.00, 0.43, 0.36). 일반 가드(D): "가드 · 피해 경감"(0.65, 0.83, 1.00)·40%. 패링 속성 늦은 가드(LG, 창 0.1·가드 시작이 판정 2.05초 전): GUARD·0.4·HP -4. 패링 성공(B2·PL·PR): "패링 성공"(0.88, 0.65, 1.00)·피해 0. 예고 문구(telegraphText)는 모든 실행에서 빈 문자열 | PASS |
| HP = HitEvent = 숫자(V02 대표) | A | A·A2 12=12, B 12=12, D 4=4, LG 4=4, GUARD 유형 4, H1a·H1d·H1f 12=12, 범위 밖·저스트·패링은 0=0 | PASS(대표) |
| H1 끝 칸 홀드 중 special.random이 그 칸일 때(홀드 유지) | A+B | 실제 LeftArrow 홀드 Pos1(x=-1.50, 콜라이더 -1.75~-1.25), 칸 1(영역 -2.0~-1.0) 두 번(H1a·H1b-4 등): 판정 순간 콜라이더가 영역과 겹침(overlap true), nativeHit true, HIT, HP -12=HitEvent 12. RightArrow·Pos3 대칭(H1c-R: 콜라이더 1.25~1.75, 영역 1.0~2.0): HIT 12. parry.any 끝 칸(Pos1 H1d-1·H1d-2, Pos3 H1f-R): HIT 12 | PASS(규칙상 정상, 겹침) |
| H1 홀드를 떼어 중앙 복귀하는 서로 다른 시점 | A+B(홀드 시작)+논리 경로(해제) | 실제 키 홀드 Pos1 후 클라이언트가 `TelegraphRemaining`≤θ에서 해제. θ 0.289초(H1b-1): 복귀 중, 판정 뒤 읽은 위치 x=-0.79(콜라이더 -1.04~-0.54, 영역 -2.0~-1.0과 겹침, 여유 0.04) → nativeHit true, HIT 12. θ 0.170·0.087·0.020초(H1b-2·3·4): 해제 효과가 판정 뒤(x=-1.50 홀드 중) → HIT 12. θ 0.535(H1e-1)·0.448(H1e-2)·0.372(H1e-3)초: 판정 때 x=0.00(콜라이더 -0.25~0.25, 겹침 false), nativeHit nil, EVADE·HP 0·HUD "회피". Pos3(RightArrow) θ 0.443(H1e-4): x=0.00, EVADE 0. **겹치는데 피해 없음 또는 안 겹치는데 피해는 한 건도 없었다** → 결함 후보 없음 | PASS(실제 키 해제 타이밍은 NOT_RUN) |
| 기존 기능 대표 회귀(V06·V10·V01) | A+B | 실제 UpArrow 공격 반복(`manual cast count=10`, 처치·그로기 중 타격·팝업 입력 차단), 실제 DownArrow 가드·LeftArrow/RightArrow 이동·복귀, 패링→반격 권한(0.88,0.65,1 문구)→그로기 흐름, 팝업 열기·닫기 승인(`CombatPause paused=true/false`·`popup closed`). 예고 문구 없음·칸 속성색(특수 칸 `[SPECIAL]`) | PASS(대표) |
| 사람 육안(die 모습·가드 불가 문구 느낌·난이도·구별)·0.20초 손 타이밍·Weight 체감 | - | 실행하지 않음. 스크린샷은 내가 읽은 장면과 픽셀 차이만 | NOT_RUN(V11 사용자) |
| CSV 파일을 바꿔 열 누락·값 변경을 Refresh로 반영하는 시험(V09) | - | 하지 않음(제품 파일 무수정 원칙). CSV 새 열 적용은 Refresh 뒤 런타임이 4행·AreaTarget을 읽는 것으로만 확인 | NOT_RUN |
| 실제 마우스·터치로 UIPopup 버튼 클릭, 실기기·모바일, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 제품 결함 후보 없음. 새 결함 ID 없음. FAIL·NEEDS_DECISION 없음.
- 시험 오류(제품 오류 아님): (1) S1 첫 실행에서 클라이언트 프로브가 서버가 새 몬스터를 만들기 전(약 3초 도구 지연) 이전 몬스터의 사망을 보고 팝업을 열어, 새 몬스터 처치 입력이 막혔다. 같은 시나리오를 팝업을 닫은 뒤 다시 처치해 판정했다. (2) 서버 모니터 스크립트가 다음 서버 스크립트 디스패치에 멈춰 PL 첫 실행은 위치 시계열이 없었다. 클라이언트 모니터로 PL2·PR을 다시 실행해 판정했다. (3) 반격 소비 실제 ↑ 3번은 도구 지연으로 반격 창 2.0초(첫 시도)·8초(두 번째)를 넘겨 소비되지 않았다. 입력 수락 지점 호출(E1e)로 소비를 확인했다. (4) 첫 번째 재Play 관찰(t=7.1초)은 몬스터가 자연 공격(AttackInterval 3.0) 중이라 stand 시작 근거가 되지 않아, 세 번째 재Play(t=1.36초)를 판정에 썼다. (5) 한 번 Stop 직전 시험 스크립트가 끝나기 전에 Stop해 `second pre-Stop` 줄이 없다(판정에 쓰지 않음).
- 관찰: (1) H1b-1의 겹침 여유는 0.04 단위로 작다. 판정 뒤 읽은 위치라 정확한 판정 순간 값이 아니며, 엔진 nativeHit true와 계산 겹침이 일치한다. (2) 팝업이 열려 있는 동안 클라이언트 `wait`는 시간 배율 0 때문에 재개되지 않는다(시험 스크립트 한정). (3) 사망 몬스터 영역에서 클라이언트 `DEAD|die`의 첫 프레임은 시험 스크립트가 사망 후 약 0.03초 뒤에 기록했다. (4) UNGUARDABLE은 범위 밖 가드에서 `[VRF] defense` 로그에는 UNGUARDABLE로 남고 HUD·RecordDefense는 EVADE로 대체된다(Plan 기대와 같음). (5) die 프레임과 die 기준 영상의 픽셀 차이가 22.6으로 stand와의 차이(44.3)보다 작지만 0은 아니다. die 클립이 정지가 아니라 시간에 따라 변하는 동안 찍어서로 보이며, 사람이 읽은 장면은 눌린 몬스터(얼굴 없음)다. 육안 평가는 사용자 몫이다.
- 한계: 실제 키 입력으로 0.20초 창을 맞출 수 없어 창을 넓힌 시험 값으로 방향·유형·결과 종류를 검증했다(창 경계 0.20 자체는 이번 변경 경로 밖이며 재시험 안 함). 실제 키 해제 시점 시험은 입력 도구 지연 때문에 논리 경로(`ReleaseHeldState`)로 했다. 클라이언트 렌더러 실제 클립 이름 API가 없어 표시는 SpriteRUID와 스크린샷으로만 확인했다. 육안·실기기·터치 미실시.

#### 판정 요약
- REV-F02(7개 사망 경로 서버·클라이언트 die 유지, 실제 UIPopup 열고 닫기, Stop 뒤 재Play stand), V11-F10(로드·검증·선택·RANDOM 칸·판정·RANDOM 저스트·↓ 패링 불성공·반격·슬로우·parry.any/left/right 회귀·시험 데이터 유형), V11-F11("가드 불가"·"회피"·"피격"·일반 가드·패링 늦은 가드), H1(홀드 유지·해제·Pos3·parry.any 끝 칸), HP=HitEvent=숫자 대표 모두 **PASS**. FAIL·NEEDS_DECISION 없음.
- NOT_RUN: 사람 육안 평가, 0.20초 손 타이밍과 실제 키 해제 타이밍, CSV 파일을 바꾼 반영 시험, 실제 마우스·터치 클릭·실기기, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit. 시험 전·후 54/54 동일 Bundle fdca556d…ee80, 제품 파일 무수정. Maker 사용 종료.
- 다음은 독립 reviewer: H1이 겹침 규칙대로임, 시험 값(창 3.0·반격 8초)이 Play 안에서만 쓰였음, 사용자 V11 확인(die 모습, 가드 불가 문구, 난이도·구별, 범위 밖에서 시작한 저스트 인정 체감)을 정리한다.

### 2026-11-03 독립 QA 6회차 — V11-F08·F09
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA 1~5회차와 coder 개발절의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·`[QA6S]`(서버)·`[QA6C]`(클라이언트)·`[QA6M]`(칸·문구)·`[QA6P]` 표지로 구분해 파일로 걸러 읽음).
- 대상: coder 커밋 a921c76 / 작업 트리 54경로 Bundle SHA-256 377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363(= 커밋 + 미커밋 Maker 재저장 3경로, 건드리지 않음). coder 절 "2026-11-03 최종 제품 버전 묶음"의 경로 집합(V11-F06 표 54경로)·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)을 node 스크립트로 **시험 시작과 끝 모두 재계산해 같은 값**이었고 두 계산의 54개 경로별 해시 목록이 완전히 같았다. 시험 끝 git status도 시작과 같은 3경로(M)뿐이다. 참고: WorkRecord에 이 절이 추가돼 coder 절 표의 줄 번호가 밀렸으므로 다음 계산은 표 행(`| 경로 | 해시 |`)을 이름으로 모아야 한다.
- 환경: 시작 시 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. build 로그 81건 모두 Info(오류·경고 0, coder와 같은 건수). Play 3회(최초 통합 Play 1회, Stop 뒤 재Play 2회), Stop 3회. Maker 로그 시각 14:49~15:03. Error·Warning 레벨 로그는 시험 시간대(14:49~) 0건이다(14:38대 LEA-2007은 coder의 이전 프로브). 최종 Stop 뒤 map01 / edit, worldId 일치.
- 실행 방식 구분: (A) 서버·클라이언트 프로브 = maker_execute_script(server_main·client). 서버 상태·SpriteRUID·isStunned·GroggyRemaining·PlayRate·HP를 0.02초 폴링으로, 클라이언트 StateComponent·SpriteRUID·PlayRate·AnimationClipEvent·StateChangeEvent를 같은 방식으로 기록했다. 두 쪽 모두 `_UtilLogic.ServerElapsedSeconds`(같은 서버 시계)를 써 같은 시간축이다(로그 시각이 두 쪽에서 0.02초 안으로 일치). 시작 트리거(패턴 단일 행 교체, 몬스터 `ChangeState("ATTACK")`, 플레이어 `ChangeState("GUARD")`로 패링 창 안 가드, 그로기 연장 `ApplyGroggy`, `ApplySlow`, `ApplyDamage`)는 프로브가 맡았고 판정·피해·그로기 진입·복귀·표시 클립은 제품 경로다(논리 경로 검사). (B) 실제 입력 = maker_keyboard_input UpArrow 탭·LeftArrow 홀드. (C) 화면 근거 = maker_screenshot(558×314) 몬스터 영역(335,160)~(425,228)의 평균 절대 RGB 차이. 기준 영상: stand(애니메이션이 있어 stand끼리도 0~41.5 차이), hit(IDLE 몬스터에 서버가 hit 클립을 직접 쓴 정지 프레임), die(IDLE 몬스터에 die 클립 쓰기). 분류 기준은 hit 기준과의 차이 작음(≤ 약 17, 공격 이펙트가 겹치지 않을 때 0~7)이면 hit, stand 기준과 0~41.5이면 stand, 둘 다 80 이상이면 jump 등 다른 프레임이다. 스크린샷 파일 시각(ms)을 로그 시각(초)과 맞추려고 서버 로그의 초 경계가 바뀌는 지점으로 시계 오프셋을 보정해(구간 폭 0.02~0.46초) 각 스크린샷의 서버 시각을 구했다. 정렬 불확실성 약 ±0.15초.
- 시험 한정 값(모두 Play 내부, Stop으로 폐기, 재Play에서 기본값 확인): AttackInterval 9999, 패턴 목록 단일 행 교체(예고 선행 0.5~60초), 그로기 연장 25초(`ApplyGroggy`), 슬로우 8초 ×0.5, 몬스터 HP 5, 시험용 ApplyDamage 999, TelegraphAttribute 직접 변경("SPECIAL"·"PARRY"·"XYZ"). CSV·제품 파일은 바꾸지 않았다. 참고: `_CombatRuleCatalog:GetRules({}).GroggyDurationSec` 쓰기는 반영되지 않아(복사본) 연장은 `ApplyGroggy`로 했다. 자연 1.5초 구간은 그로기 값을 바꾸지 않은 실행(NA3·NB·NC)이다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| V11-F08 조건 (a) 피격 없음, 자연 1.5초(NA3, parry.any) | A+C | 서버·클라이언트 시계열: ATTACK\|jump(접근) → ATTACK\|stand(착지 대기) → ATTACK\|jump(복귀, 0.5초) → 317.35 STUN\|hit/stun(서버·클라이언트 SpriteRUID 모두 hit) 1.50초 → 318.86 IDLE\|stand. 스크린샷 20장(≈0.18초 간격) 서버 시각 정렬: 복귀 구간 프레임은 vsStand 80~117·vsHit 92~121(jump, stand도 hit도 아님), **STUN 구간 317.38~318.68 프레임 모두 vsHit 0.0~6.7·vsStand 73~78(hit 유지)**, STUN 종료 318.86 이후 vsStand 0.0 또는 41.5(stand 프레임 계열) | PASS |
| V11-F08 조건 (b) 그로기 중 실제 ↑ 공격 | B+A+C | (b1) 연장 그로기 25초 중 UpArrow 3회: 서버 상태 STUN 유지·SpriteRUID hit/stun 유지, 클라이언트 STUN→HIT(ACE clip=hit 1회) 뒤에도 SpriteRUID hit/stun 유지, 서버 GroggyRemaining 감소(조기 해제 없음), 몬스터 HP 100→70(수동 공격 10타×3회, 1/타). 스크린샷 vsHit 3.1~8.8·vsStand 75~77(그로기 3.4초·16초·22초·24초 시점). 그로기 만료 직후 스크린샷 vsStand 0.0. (b2) 자연 1.5초 중 UpArrow(반격 ×2.2): 서버 STUN 유지 grog 0.85→0.47, HP 70→50(2/타 ×10), 클라이언트 STUN→HIT 후 SpriteRUID hit/stun 유지. 공격 이펙트·숫자가 겹친 프레임은 vsStand 74~144, **그로기 안에서 stand 프레임(vsStand ≤ 41)은 종료 시점 전까지 없음**, 종료 336.33 뒤 stand | PASS(이펙트 겹침으로 hit 정지 프레임과의 정확한 일치는 일부 프레임만) |
| V11-F08 조건 (c) 슬로우 겹침(NC, ApplySlow 8초 ×0.5, 자연 1.5초) | A+C | STUN 진입 직후 서버 PlayRate 0.5·클라이언트 rate=0.5, SpriteRUID hit/stun 유지 353.74~355.25, 그로기 1.50초 동안 서버 시간 진행 정상. 스크린샷 353.92~355.21 모두 vsHit 0.0~3.9·vsStand 73~76(hit 유지), 종료 355.39 이후 vsStand 0.0/41.5 | PASS |
| V11-F08 종료 뒤 stand | A+C | 위 (a)(b)(c) 모두 STUN→IDLE 시 서버 SpriteRUID stand·클라이언트 ACE clip=stand, 이후 스크린샷 stand 계열. 연장 그로기 종료 뒤 스크린샷 vsStand 0.0(145239) | PASS |
| V11-F08 복귀 중 jump 유지(그로기 시작에만 hit) | A+C | 복귀 jump 구간(서버 ATTACK\|jump, 약 0.5초) 스크린샷은 hit 아님(vsHit 92~121). 그로기 시작 시점 서버·클라이언트 SpriteRUID가 jump→hit로 바뀜(NA3 317.35, ND 396.6, E1 446.19 등). 2칸 패턴(parry.left·parry.right)도 같음 | PASS |
| V11-F08 그로기 중 사망 die | A+B+C | 그로기 중 HP 5 → 실제 UpArrow(반격) → 서버 STUN→DEAD, SpriteRUID die, isStunned false, 클라이언트 ACE clip=die·SCE HIT→DEAD, 스크린샷은 die 클립 재생(고통 얼굴 없음)과 die 마지막 포즈 정지(vsDie 0.0·7.0, vsStand 88~92). 10초 이상 뒤 스크린샷 두 장이 같은 die 마지막 프레임(vsStand 67.7) | PASS |
| V11-F08 정리 경로 — 상대 교체·소유자 이탈(ClearOpponentExecution) | A+C | 그로기 중 `mgr:ClearOpponentExecution()`: 직전 STUN·hit·stunned true·grog 23.5 → 직후 IDLE·stand·stunned false·grog 0, 클라이언트 SCE STUN→IDLE·ACE stand. `mgr:DoSpawn()`(그로기 중 새 상대 생성): 이전 몬스터 무효(isvalid false), 새 몬스터 IDLE·stand RUID·stunned false, 이후 스크린샷 stand 계열(생성 직후 0.3초 프레임 2장은 vsStand 80~106의 생성 연출 프레임). DoSpawn·ClearOpponentExecution 호출은 프로브가 시작한 논리 경로 검사 | PASS(논리 경로) |
| V11-F08 정리 경로 — 맵 이탈(MonsterStunComponent:OnMapLeave 서버 분기) | A+C | 그로기 중 `stun:OnMapLeave(map)` 직접 호출: 직전 STUN·hit/stun·stunned true → 직후 SpriteRUID stand·stunned false·grog 0(상태는 STUN으로 남음: 직접 호출 때문이며 실제 이탈은 몬스터가 맵과 함께 정리됨), 스크린샷 vsStand 0.03(stand). 실제 다른 맵 이동은 하지 않았다(맵이 1개) | PASS(논리 경로)·실제 맵 이동 NOT_RUN |
| V11-F08 정리 경로 — Stop | A+C | (1) 연장 그로기 18초 남은 시점 maker_stop → 재Play: 서버 IDLE·stand·stunned false·grog 0·cells ''·AttackInterval 3.0·패턴 9행·그로기 규칙 1.5·몬스터 HP 100, 스크린샷 vsStand 0.03. (2) 아래 V08 2칸 복귀 중 Stop 재Play도 같음 | PASS |
| V11-F09 9패턴 예고 문구 없음·서버 영역 칸 속성색 | A(클라이언트 칸 컴포넌트 `_T.attribute`·UI 텍스트 폴링)+C | 9패턴을 제품 경로로 1회씩 실행(플레이어 무대응): normal.left 011→`-NN`, special.left 011→`-SS`, parry.left 011→`-PP`, normal.right 110→`NN-`, special.right `SS-`, parry.right `PP-`, normal.any 010→`-N-`, special.any `-S-`, parry.any `-P-`. 모든 실행에서 telegraphText.Text는 빈 문자열(예고 시작~판정~종료 내내 길이 0). 결과 문구(def=피격 등)는 이전처럼 표시, 판정 뒤 칸은 1~2프레임 안에 꺼짐. 칸 변화는 서버 TelegraphCells 뒤 1프레임 이내 | PASS |
| V11-F09 칸 색값(픽셀 근거) | C(스크린샷, 알파 0.45 역산) | 예고 60초 단일 행(normal.left 011, 가드형이 아님·값은 속성 직접 지정)에서 칸 영역 중앙값 역산 색: NORMAL (1.00,0.84,0.40), SPECIAL (1.00,0.43,0.36), PARRY (0.88,0.65,1.00)(기대 노랑 1,0.85,0.4 / 적색 1,0.43,0.36 / 보라 0.88,0.65,1). 같은 칸에서 속성을 서버가 NORMAL→SPECIAL→PARRY→"XYZ"→NORMAL로 바꾸는 동안 칸이 켜진 채 `-NN`→`-SS`→`-PP`→`---`→`-NN`으로 새 색을 반영했고 "XYZ"는 칸 픽셀이 배경과 같아져(변화 0/176) 숨김, 0.25초 뒤 `[VRF] AttackAreaMark unknown attribute` 로그가 칸 2·3에 1회씩, NORMAL 복귀 시 다시 노랑 | PASS(속성 값 직접 변경은 시험값, 칸 색 자체는 제품 경로) |
| V11-F09 속성 미상 숨김·결과·상태 문구 유지 | A | 속성 "XYZ" 숨김(위). 결과 문구 `def`(피격·회피)와 counter·effect 텍스트 경로는 그대로 표시(9패턴 실행의 피격 문구, 실제 LeftArrow 홀드 회피의 회피 문구 길이 6바이트). 반격 준비·상대 그로기·슬로우 문구는 이번에 새로 확인하지 않음(변경 없는 경로) | PASS(대표) |
| V11-F09 팝업 중 칸 유지·재개 | A | 예고 60초(NORMAL 011) 중 실제 `_UIPopup:Open`: server paused true, 칸 `-NN`·cells 011 유지(복원 전까지 칸 변화 없음), 7초 뒤 Close: paused false, 이어서 정리 호출 뒤 칸 꺼짐. 팝업이 화면을 덮어 칸 색은 로그 근거만 | PASS |
| V11-F09 사망·Stop 경계 | A | 예고 중 몬스터 사망(ApplyDamage 999): cells '' 즉시, 칸 `---`(1프레임 이내). 재Play 뒤 칸 `---`·텍스트 빈 값·팝업 닫힘. 플레이어 사망 중 칸 정리는 이번에 새로 실행하지 않음(변경 경로 밖, 이전 QA5 V08 근거) | PASS(몬스터 사망·Stop) / 플레이어 사망 NOT_RUN |
| Plan §16 필수: 2칸 패턴 패링 → 복귀 중 팝업 정지·재개(V07) | A+C | parry.left(착지 x=+0.75): 복귀 점프 0.2초 뒤 팝업 Open(x=1.74): 서버 paused true, ATTACK\|jump 그대로 x 1.98에 **7.6초 이상 정지**(0.5초 간격 로그 전부 x=1.98, 전투 시계 646.322 고정), Close 후 paused false로 x 2.21→3.00 이어서 이동 → STUN\|hit/stun(grog 1.48 시작, 정지 시간이 그로기에 섞이지 않음) 1.5초 → IDLE\|stand. 스크린샷(재개 뒤 15장): STUN 구간 vsHit 0.0~3.6(hit 유지), 종료 뒤 stand 계열 | PASS |
| Plan §16 필수: 2칸 패턴 복귀 중 Stop → 재Play 기본값(V08) | A+C | parry.right(착지 x=-0.75) 복귀 점프 중 팝업 정지(x=1.19, paused true) 상태에서 maker_stop(CombatPause abort·popup closed 로그) → 재Play: IDLE·stand·stunned false·grog 0·ParryEffect (0,0,0)·cells ''·paused false·AttackInterval 3.0·패턴 9행·그로기 규칙 1.5·몬스터 HP 100, 클라이언트 IDLE·stand·칸 `---`·텍스트 빈 값·popupOpen false, 스크린샷 stand 계열(재Play 직후 플레이어 HP 964는 AttackInterval 3.0 자연 공격 3회 12씩 — 프로브가 늦은 것) | PASS |
| HP = HitEvent = 숫자(V02 대표) | A(제품 경로) | normal.any 무대응 HIT hpDelta 12 = HitEvent 12, normal.any 가드 GUARD 4 = 4(12×0.4=4.8→4), special.any 무대응 12=12, parry.any 가드(창 안) PARRY 0=0 + 그로기·반격, 그로기 중 수동 공격 HP 감소 = 수동 공격 숫자(10타 합계 20=2×10, 반격 ×2.2·1 타당 2) | PASS(대표) |
| V03(저스트·패링 판정 대표)·V04 반격 | A | 패링(창 안 가드 PARRY 0, `counter granted factor=2.2`, 그로기 1.5초) 반복 10여 회 정상, 반격 ×2.2 수동 공격 로그(`manual cast ... factor=2.2`). 저스트 회피 시각 경계(0.20)는 이번 변경 경로 밖이라 재시험하지 않았다 | PASS(대표) |
| V10 대표(실제 입력) | B+A | 실제 LeftArrow 홀드(예고 5초 중 2초): 칸 `-N-` 예고, 판정 시 EVADE HUD 문구(6바이트 "회피"), hpDelta 0·HitEvent 0, 예고 문구 길이 0. UpArrow 탭 5회(수동 공격 로그 `manual cast count=10`) 모두 동작 | PASS(대표) |
| V01·V06 기존 기능 대표 회귀 | A | 9패턴 칸·유형 대응(위), 패링→복귀→그로기→IDLE 흐름(위), 사망(위) | PASS(대표) |
| 육안(스크린샷 대신 사람의 눈) 그로기 hit 모션 가독성·별·접촉 파티클·칸 색 가독성·색약 접근성 | - | 사람 평가는 하지 않았다. 스크린샷 픽셀 근거만 | NOT_RUN(V11 사용자) |
| 0.20초 창 손 타이밍·CSV 변경 반영(V09)·UI 좌·우 버튼 실기기·플레이어 사망 중 칸·실제 다른 맵 이동 | - | 실행하지 않음 | NOT_RUN |
| V11(사용자)·V12 외부·CF-F07 연출 평가 | - | 실행하지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 범위 밖 관찰(coder 인계 사항 재현, 판정은 reviewer): **일반 사망의 표시.** (1) IDLE 상태 몬스터에 `ApplyDamage(999)`: 서버 DEAD·SpriteRUID **stand**(3초 뒤도 stand), 스크린샷 stand 계열(vsStand 41.5). (2) 공격(ATTACK) 중 사망도 같음(DEAD\|stand, HP 0/100 표시 화면에서 웃는 stand 얼굴). 이벤트(ACE clip=die)는 1번 나오지만 서버 SpriteRUID는 stand로 남는다. 반대로 **그로기 중 사망은 die가 고정**돼 표시가 다르다. 이번 변경(그로기 중 사망만 die 고정)의 결과로 두 경우가 달라 보이는 것이며, 일반 사망 die 유지는 결함 후보·사용자 판단(새 ID는 붙이지 않음).
- 관찰: (1) 그로기 hit 프레임은 시간이 지나면서 vsHit가 0.0에서 6.7까지 서서히 변한다(hit 클립 마지막 부분의 미세한 움직임으로 보이며 stand와는 항상 70 이상 떨어져 있다). (2) 그로기 만료 순간에 실제 공격 타격이 겹치면 서버가 STUN→IDLE→HIT로 지나가 0.5초 HIT(stand 표시)가 보인 뒤 IDLE로 돌아간다(연장 그로기 b1 마지막, 221.37~221.88). 기존 HIT 규칙대로이며 새 변경과 무관. (3) 새로 생성된 몬스터(DoSpawn)는 0.3초 동안 생성 연출 프레임(vsStand 80~106)이 보인다. (4) 클라이언트 화면 표시 클립을 직접 읽는 API가 없어 스크린샷 픽셀이 근거이며, 스크린샷은 약 5~16장/초이고 공격 이펙트·숫자 겹침 프레임은 hit 정지 프레임과 정확히 일치하지 않는다.
- 시험 오류(제품 오류 아님): (1) 초기 시험의 sleep 간격 도구 지연(1~3초)으로 첫 연장 그로기 실행의 일부 스크린샷이 그로기 밖(stand)이었다. 그 실행은 판정에 쓰지 않고 `ApplyGroggy` 연장·자연 구간 장수 확대로 다시 실행한 결과만 썼다. (2) `GetRules` 복사본 쓰기는 반영되지 않았다(위). (3) 실행 G에서 프로브의 패턴 복원 타이머가 정지 중 서버에서 먼저 돌아 `RUN G NO-STUN restore` 로그가 찍혔으나 이미 판정이 끝난 뒤라 영향 없음. (4) 몬스터 사망 뒤 `mgr:DoSpawn()`으로 새 상대를 만들었다(시험용 호출). (5) LEA-3051 MemoryLeak은 시험 타이머를 모두 정리해 이번 시간대에는 관측되지 않았다.
- 한계: 육안 평가 불가, 클라이언트 렌더러 실제 클립 이름 API 없음(픽셀 대체), 그로기 1.5초 구간은 스크린샷 약 8장(0.18초 간격)으로만 덮음, 정렬 불확실성 ±0.15초, 실기기·터치·실제 맵 이동·0.20초 손 타이밍 미실시.

#### 판정 요약
- 기준: V11-F08(세 조건 그로기 전체 hit, 종료 뒤 stand, 복귀 중 jump, 그로기 중 사망 die, 상대 교체·Stop·맵 이탈 정리 뒤 잔존 없음), V11-F09(9패턴 문구 없음·서버 영역 칸 속성색·같은 칸 속성 연속 변경·속성 미상 숨김·결과 문구 유지·팝업/몬스터 사망/Stop 경계), Plan §16 필수 2칸 패턴 F02 복귀 조합(V07·V08), HP=HitEvent=숫자 대표, V10·V01·V06 대표 회귀 모두 **PASS**. FAIL·NEEDS_DECISION 없음. NOT_RUN: 사람 육안 평가, 0.20초 손 타이밍, V09 CSV 변경 반영, 실기기·터치, 플레이어 사망 중 칸, 실제 맵 이동, V12, CF-F07 연출. 이번 회차의 새 결함 ID 없음.
- 사용 종료: 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, worldId 970621b29ba945369d3dc8e90c301186. 시험 전·후 54/54 동일 Bundle 377a5ccc…0363, 제품 파일 무수정, git status 시작·끝 동일(M 3경로: Maker 재저장 userdataset 2·주황버섯 모델). Maker 사용 종료.
- 다음은 독립 reviewer: 범위 밖 관찰(일반 사망 stand 표시)의 결함 여부와 사용자 V11 확인 항목(그로기 hit 모션 육안, 속성색 칸 가독성)을 정리한다.

### 2026-11-03 독립 QA 5회차 — V11-F01~F06
- 담당: Claude Code msw-tester(coder와 별도 실행). 제품·모델·맵·UI·DataSet·CSV·.codeblock 수정 없음. commit·push 없음. 이전 QA 1~4회차의 PASS는 이번 실행으로 세지 않았다. **maker_clear_logs는 한 번도 호출하지 않았다**(Maker 로그는 시각·[VRF-QA5] 표지로 구분해 읽음, QA4 계약 위반 재발 없음).
- 대상: coder 커밋 b89de46 / 54경로 Bundle SHA-256 b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf. coder 절 "최종 제품 버전 묶음"의 경로 목록·계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF 연결의 SHA-256)을 node 스크립트로 시험 전·후 재계산해 둘 다 54/54 개별 해시 일치·Bundle 동일, 시험 후 git status 변경 없음.
- 환경: maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId 970621b29ba945369d3dc8e90c301186 시작·중간 반복 확인. TileMapMode는 기존 기록(0 MapleTile)을 따르며 이번에 MapBuilder를 다시 읽지 않았다. build 로그 80건 모두 Info(오류·경고 0, coder와 같은 건수). Play 5회(시험 중 Stop 4회 포함), Maker 로그 시각 10:22~10:37. 최종 Stop 뒤 map01 / edit.
- 실행 방식 구분: (B) 실제 입력 = maker_keyboard_input의 Left/Right/Down/UpArrow 실제 키 이벤트, maker_mouse_input의 UI 뒤 버튼 홀드·공격 버튼 클릭. (A) 서버 프로브 = maker_execute_script(server_main)로 `_CombatRuleCatalog.patterns["castleenemy"]`를 시험 행 1개로 교체하고 몬스터를 `ChangeState("ATTACK")`로 시작시킨 뒤 회피 방향·시작 시각 필드(`EvadeDirection`·`evadeStartTime`)나 서버 GUARD 상태를 정해진 시점에 부여. 방어 판정(EvaluateDefense)·영역·피해(CalcDamage→ResolveIncomingDamage)·네이티브 AttackFast/HitEvent·HP는 제품 경로이며 프로브는 시작 트리거와 관찰만 맡았다(논리 경로 검사). (C) 순수 함수 호출 = SelectPattern·FindNearestCell·ValidateRows(시험 행). 시험 한정 값(모두 Play 내부, Stop으로 폐기): AttackInterval 9999, 패턴 목록 1행 교체, 예고 선행 1~8초, 일부 실제 키 시험의 JustWindowSec·ParryWindowSec 8.0(손 타이밍으로 0.20초 창을 맞출 수 없어 창만 확대), 가드형 시험 행(Play 내부 메모리 행). CSV는 시험용으로도 바꾸지 않았다.

| 기준 | 방식 | 실제 결과 | 판정 |
| --- | --- | --- | --- |
| V01·V09 로드 | 로그 | `catalog ready rules=1 patterns=9`(매 Play), 9행 id·유형·속성·앵커 0-0/2-3/1-2·Weight 문자열 "1", 가드형 0행 | PASS |
| V01 주황버섯 9행 판정 대응(LEFT·RIGHT·ANY × 일반·특수·패링) | A | 모든 행이 예고 문구·칸·영역·판정과 일치(아래 행들). 일반 가드 12×0.4=4.8→4(=HitEvent 4), 특수 가드 12, 패링 창 안 가드 PARRY 0, 창 밖 가드 4 | PASS |
| V01 ANY Pos2(x=0) 조준 | A | tgt=2 cells=010 영역 -0.5~0.5 dirs=LR 착지 x=0.0. 무대응 HIT 12=HitEvent 12. 일반·특수·패링 모두 LEFT·RIGHT 저스트 JUST·피해 0·슬로우 1.72(≈2.0 시작)·반격 true | PASS |
| V01·V03 ANY Pos1 조준(실제 LeftArrow 홀드, x=-1.5) | B+A | tgt=1 cells=100 영역 -2.0~-1.0 dirs=R 착지 x=-1.5. 무대응 HIT 12, RIGHT 저스트 JUST(특수 포함), 조준 칸 쪽 LEFT는 HIT 12(저스트 아님), 창 밖 RIGHT HIT 12 | PASS |
| V01·V03 ANY Pos3 조준(실제 RightArrow 홀드, x=+1.5) | B+A | tgt=3 cells=001 영역 1.0~2.0 dirs=L 착지 x=+1.5. LEFT 저스트 JUST 0(특수), 조준 칸 쪽 RIGHT HIT 12, 창 밖 LEFT HIT 12, 무대응 HIT 12 | PASS |
| V03 최근접·동률 경계 | C | anchors -1.5/0/1.5: -9→1, -1.5→1, -1.0→1, -0.76→1, -0.75→2(동률 중앙), -0.74→2, 0→2, 0.74→2, 0.75→2(동률 중앙), 0.76→3, 1.0→3, 1.5→3, 9→3. 같은 입력은 같은 칸 | PASS(PrepareAttack에 플레이어를 -0.75 등에 세운 통합 시험은 안 함, 함수 단위) |
| V03 저스트 시각 경계(ANY, 서버 부여) | A | 판정시각-시작시각 0.013 JUST, 0.115·0.158 JUST, 0.198 JUST, 0.222 HIT, 0.241 HIT, 판정 뒤 시작(-0.032·-0.122) HIT, 빈 방향 HIT. 정확히 0.200 등호값은 타이머 간격(0.02) 때문에 재현하지 못함 | PASS(근사 경계, 등호 경계 NOT_RUN) |
| V03 예고 뒤 이동해도 조준 불변 | B | 실제 RightArrow(K2: Pos2 조준, 판정 때 x=+1.5)·키 이동 중 telegraph 칸·영역·방향 집합이 판정까지 tgt=2 cells=010 영역 -0.5~0.5 불변 | PASS |
| V03 조준 칸 쪽·중앙 복귀는 저스트 아님, 탈출 | B | K1b: Pos1 LeftArrow 홀드 뒤 예고 중 키 해제 → 판정 x=0.0(영역 -2~-1 밖) → 피해 0·HitEvent 없음·kind HIT/native nil(HUD EVADE)·JUST 아님. K3: Pos3 홀드→Right 해제→(복귀 중 Left 눌림은 무시됨, 입력 예약 없음)→ x=0.0 EVADE·JUST 아님. 자연 공격 id=45(Pos2 조준, 예고 중 실제 RightArrow로 영역 이탈): HUD EVADE, 피해 0 | PASS |
| V03 끝 칸 조준에서 중앙 복귀 뒤 중앙 쪽 방향 회피 저스트 | B(시험 한정 창 8.0) | K3b: Pos3 조준(dirs=L) → Right 해제 → 중앙 복귀 후 실제 LeftArrow → JUST, 판정 x=-1.5, evDir=LEFT 실제 입력으로 기록, 피해 0, HUD JUST | PASS(창은 시험 값) |
| V03·V10 Pos2 조준에서 실제 RightArrow | B(창 8.0) | K2: JUST, evDir=RIGHT 실제 기록, 판정 x=1.5, 슬로우·반격 true, HUD JUST | PASS(창은 시험 값) |
| 가드형 시험 데이터(V01 "시험 데이터 근거") | A(Play 내부 메모리 행 2개, 제품 CSV 아님) | 영역 -2~2 cells=111 dirs 빈 집합 착지 x=0.0. 일반+GUARD: 무대응 HIT 12, 가드 GUARD 4, 회피 방향 부여해도 HIT 12. 패링+GUARD: 창 안 가드 PARRY 0·반격 true, 창 밖 가드 GUARD 4 | PASS(시험 데이터 근거) |
| V01·V09 잘못된 ANY 영역·유형 조합 거부 | C(ValidateRows 시험 행) | ANY 1/1·ANY 0/2는 `ANY area must be 0/0`, LEFT 0/0·RIGHT 1/4는 `invalid anchor`, 역전 3/2 `invalid pattern area`, SPECIAL+GUARD `SPECIAL cannot request GUARD`, 잘못된 유형 `invalid response`, 선행 0.1 `invalid pattern area or lead`, AreaHeight 0, 중복 id `invalid or duplicate pattern`, 빈 목록 `patterns missing` — 모두 REJECT, 경고 정확히 1회씩. 허용 케이스(GUARD 일반 1/3, Weight 0.5, 전체 2.5)는 ACCEPT. 거부 뒤 live 카탈로그 ready=true rows=9 | PASS |
| V09 Weight 거부 | C | 누락(nil)·빈 값·abc·nan·inf·1e999는 `invalid pattern number`, 0·-1은 `invalid weight`. 모두 REJECT·경고 1회(카탈로그 전체 거부). 열 자체 누락(`NoSuchColumn`)은 ReadRows nil | PASS |
| V09 Weight 가중치 선택 | C | 9행 균등 중간값 (i-0.5)/9 → 1~9행 순서대로. 경계 u=0·1/9-1e-9→normal.left, 1/9+1e-9→special.left, 2/9+1e-9→parry.left, 8/9-1e-9→special.any, 8/9+1e-9·1-1e-12·1.0·1.5→마지막 parry.any. 가중치 1,2,3 행: u=0·0.1666→a, 0.17·0.49→b, 0.5·0.9999·1.0→c(마지막 행). math.random 900회: 9행 각 82~118회(전부 선택), 가중 600회 a87/b204/c309(≈1:2:3) | PASS |
| V09 CSV 파일 변경→Refresh→Play 반영 | - | 지시상 CSV·제품 파일을 바꾸지 않아 실행하지 않았다(ValidateRows 시험 행으로 대체) | NOT_RUN |
| V01 2칸 중앙 착지·판정 일치 | A | normal.left 착지 x=+0.750, normal.right -0.750(두 칸 중간), ANY 고정 칸 x(0.0/-1.5/+1.5), 가드형 시험 0.0. 판정 시각 hitDt≈0.47(예고 후 점프 0.5초 고정), 영역 min/max·피해 12=HitEvent 12 이전과 동일 | PASS(서버 위치 근거) |
| V01·F01 빨간 칸(클라이언트 마크) | A+로그 | 클라이언트 TelegraphCells·marks: ANY Pos2 010→marks 010, ANY Pos1 100→100, ANY Pos3 001→001, normal.left 011→011, parry.right 110→110, 가드형 시험 111. 판정 뒤·종료 뒤 000(≈0.03초 지연). ANY에서 고정 1칸만 켜짐 | PASS |
| V01 예고 문구 | 로그 | ANY: "일반 · 방향 무관 회피 [좌·우] / 가드", "특수 · 방향 무관 회피 [좌·우] · 가드 불가", "패링 · 방향 무관 회피 [좌·우] / 정확히 가드"(Pos1·Pos2·Pos3 동일). LEFT "일반 · 뒤 회피 [왼쪽] / 가드", RIGHT "패링 · 앞 회피 [오른쪽] / 정확히 가드" | PASS |
| 육안(스크린샷 800×450) | B | 예고 중 상단 문구와 빨간 칸이 플레이어 위치에 보임(2회 캡처). 몬스터 착지 모양·색·가독성·1칸 공격 난이도·2칸 중간 착지 모션 모양은 판단하지 않음 | 일부 NOT_RUN(V11 사용자) |
| 실제 입력 창 0.20초 안 손 타이밍의 저스트·패링 성공 | - | 재현하지 않음(실제 키 성공은 시험 한정 창 8.0, 창 0.2 안 성공은 서버 프로브 A) | NOT_RUN |
| V02 회귀 | A+B | 모든 케이스에서 HP 감소=HitEvent 합계: 무가드 12/12, 가드 4/4, 저스트·패링·범위 밖 0/0 | PASS |
| V04 회귀 | B | ANY JUST 직후 실제 UpArrow: `manual cast id=32 count=10 factor=2.2`, 반격 즉시 소비(counter false). 성공 전 UpArrow는 factor=1 | PASS(대표) |
| V05 회귀 | A | ANY 저스트 슬로우 시작 값 ≈2.0(1.71~1.73 측정), 예고·복귀 진행 정상 | PASS(대표, 전 구간 재시험 아님) |
| V06·F02·F04 회귀 | B | ANY 패링(K4b, 실제 DownArrow, 시험 한정 창 8.0): PARRY 0, 판정 후 몬스터 ATTACK(복귀 중) → x=3.0에서 STUN → 그로기 약 1.5초 → IDLE, 반격 true 유지 후 만료. `parry effect serial=5 x=0.0`(F03 접촉 파티클 로그 1회). F04 hit 클립 RUID는 이번에 재계측하지 않음 | PASS(대표) / F04 클립 NOT_RUN |
| V07 회귀 | A | ANY 예고(선행 8초) 중 실제 `_UIPopup:Open`: 전투 시계 501.670 고정 5초, rem 7.176·cells 010 불변. Close 뒤 같은 실행이 이어져 판정 시계 508.852(=501.670+7.176+0.006), HIT 12=HitEvent 12 | PASS |
| V08 회귀 | A+B | 몬스터 사망(예고 2.35초 남음): 즉시 DEAD, cells·resp 비움, snapshot nil, 판정(res) 변화 없음, 클라이언트 마크 000, 이후 3초 유지. 플레이어 사망(HitComponent:OnHit 5000): 몬스터 IDLE로 복귀, cells 비움, 판정 없음, plState DEAD 유지. 예고 도중 실제 Stop → 다음 Play: interval 3.0·dmg 12·rows 9·cells ''·seq 새로 시작·규칙 .2/.2/.4/2.0×2.2/2.0×0.5/1.5·evDir ''·반격 false·몬스터 HP 100·마크 000 | PASS |
| V10 회귀 | B | 실제 Left/Right/Down/UpArrow 키, UI 뒤 버튼 마우스 홀드(예고 선행 5초 동안 홀드 → 판정 x=-1.5, EVADE, 피해 0), UI 공격 버튼 클릭 2회(`manual cast factor=1` 2건) | PASS(대표) |
| F05 회귀 | B+A | 실제 LeftArrow 홀드 Pos1: 뒤 회피형 3패턴 EVADE 피해 0/HitEvent 0, 앞 회피형 3패턴 HIT 12/12, ANY(tgt=1) HIT 12/12. 실제 RightArrow 홀드 Pos3(대칭): 앞 회피형 2패턴 EVADE 0/0, 뒤 회피형 2패턴 HIT 12/12, ANY(tgt=3) HIT 12/12 | PASS |
| F01·F02·F03 나머지, F04 클립·별 크기·접촉 파티클 육안 | - | QA4 범위 중 이번에 새로 재실행하지 않은 항목(복귀 중 팝업·피격·슬로우 조합, 그로기 중 피격 클립 재생, 별·파티클 가시성)은 F06 변경 경로(영역 전달·착지·선택)와 겹치지 않아 재실행하지 않았다 | NOT_RUN(V11 사용자) |
| V11(사용자 직접)·V12 외부 환경·CF-F07 연출 | - | 실행하지 않음. V12 단일 참조 없음/폐기 경로는 위 사망·Stop 시험이 일부 겹치나 V12 전체로 세지 않음 | NOT_RUN |

#### 관찰·시험 오류 분리
- 시험 오류(제품 오류 아님): (1) 첫 harness는 몬스터가 자연 공격 중(ATTACK)일 때 `ChangeState("ATTACK")`가 무시돼 아무 케이스도 기록되지 않았다. Stop→재Play 후 "IDLE이 된 뒤 시작"하도록 고쳐 다시 실행했고 그 이후 결과만 사용했다. (2) K4 첫 시도는 직전 시험의 RightArrow를 해제하지 않아 플레이어가 MOVE 중이라 DownArrow가 수락되지 않았다(kind HIT, 무효). 키를 해제하고 K4b로 다시 실행한 결과만 썼다. (3) K1b는 직전 harness가 `EvadeDirection`을 초기화해 실제 LeftArrow 홀드의 방향 기록은 남지 않았다(탈출 결과·조준은 확인, 방향 불일치 판정은 Pos1 서버 부여 시험이 근거). (4) 한 harness 시작 직후 키 이동과 겹쳐 id=45 공격이 harness 케이스 로그 없이 지나갔다(위 EVADE 근거로만 사용).
- 시험 스크립트 한계: maker_execute_script는 한 번에 약 900회 반복 이상은 완료되지 않았다(900회 선택 시험을 나눠 실행). LEA-3051 MemoryLeak 3건(10:25:09, 10:34:48 두 건)은 모두 `MakerScript`의 시험 타이머이며 제품 오류가 아니다. 제품 runtime 오류는 관측되지 않았고 Warning은 V09 시험 행의 의도한 경고(1회씩)뿐이다.
- 관찰: (1) ANY 끝 칸(Pos1·Pos3) 조준에서도 예고 문구는 "[좌·우]" 일반형이라 실제 유효 방향(한쪽)과 다르게 읽힐 수 있다. Plan §15가 허용한 표현이며 칸 표시가 조준 칸을 알린다. 체감은 V11에서 판단. (2) 끝 칸에 홀드 중인 플레이어는 새 회피를 시작할 수 없고(홀드 해제 → 중앙 복귀), 복귀 중 들어온 반대 방향 입력은 무시된다(입력 예약 없음). Plan 설계대로이며 난이도는 사용자 V11. (3) `TelegraphAttribute`는 공격 종료 뒤에도 마지막 값이 남는다(Response가 비어 HUD에는 안 보임, 이전 버전부터의 동작). (4) 접촉 파티클 serial·판정 로그 근거만 있고 화면 가시성은 미확인.

#### 판정 요약
- 기준: F06(ANY 3칸 조준·최근접·동률, 유효 방향 저스트, 조준 칸 쪽·복귀 비저스트, 탈출, 2칸 중앙 착지·판정 일치, Weight 선택·거부, 가드형 시험 데이터, F01 1칸 표시, 예고 문구) **PASS**. 회귀 F01·F02·F05·V02·V04~V08·V10 대표 **PASS**. 실제 입력의 창 안 성공은 시험 한정 창 확대(K2·K3b·K4b)이며 창 0.20 안 손 타이밍, CSV 파일 변경→Refresh→Play, F04 클립 재계측, 육안·V11·V12는 NOT_RUN. FAIL·NEEDS_DECISION 없음.
- 사용 종료: 모든 키·마우스 up. 마지막 maker_stop 성공 뒤 maker_get_current_map map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, Maker 사용 종료. 시험 전·후 54/54 동일 Bundle b985aa4b…74dbf, git status 변경 없음.
- 다음은 독립 reviewer(F01~F06 일괄): 위 실행 방식 구분과 한계를 같은 Bundle에서 대조한다. 사용자 V11에서 1칸 공격 구별·난이도, 2칸 중간 착지 모션, F01~F04 체감, 별·접촉 파티클 가시성, 좌·우 UI 버튼 전체 면적을 확인한다.

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

### 2026-11-03 독립 리뷰 — REV-F02·V11-F10·F11 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절(REV-F02·V11-F10·V11-F11)과 QA7의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git diff·소스 대조(Grep 포함)와 작업 디렉터리 밖 임시 node 스크립트의 지문 재계산뿐이다.
- 검토 버전: coder 로컬 커밋 5c4eda3(기준 a921c76, push 전). QA7은 미커밋 작업 트리(WR QA 절·Plan §17 상태). V11-F06 절 manifest 54행을 같은 계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)으로 재계산했다. a921c76 커밋 트리 = 38e7aa22…0ba53(이전 리뷰 값과 일치), **5c4eda3 커밋 트리 = 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79**(새 값), 작업 트리 = **fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80**(coder·QA7 기재와 일치). a921c76→5c4eda3 차이 경로는 제품 6개뿐이고 개별 해시가 coder 절 값과 모두 같다. 5c4eda3→작업 트리 차이는 Maker 재저장 3경로뿐이며 해시(주황버섯 모델 d8f79eb5…, AssistModel a933d30a…, AttackSkillData c6b692fd…)가 지난 리뷰(43c5c63)에서 의미 차이 없음을 확인한 바이트와 같다. 따라서 QA7 근거는 커밋 트리에도 그대로 적용된다. 전체 저장소 diff a921c76..5c4eda3의 RootDesk·map·ui·Global 변경은 위 6경로뿐이고 .codeblock·.directory·.userdataset·.map·.ui 변경과 추적 안 된 파일은 없다. CSV는 BOM·CRLF 유지(머리말+4행, 줄마다 CR).
- 판정: **WAITING**. 고칠 결함 없음(CHANGES_REQUIRED 없음). 세 요구의 AI 측 근거(소스 대조·coder 실측·QA7 서버/클라이언트 시계열·스크린샷 픽셀·실제 키 입력)는 Plan §17 완료 기준을 충족한다. 남은 필수는 사용자 V11 직접 확인이다. 이 판정은 2단계 완료·3단계 진행·push 승인이 아니다.

#### 사용자 결정 → Plan §17 → 변경 대조
| 사용자 결정(run 2026-11-03 절) | Plan §17 | 실제 변경 | 판단 |
| --- | --- | --- | --- |
| "1. 너 의견대로": 사망 시 die 고정만, fade·스테이지 전환은 4단계 | REV-F02, fade·처치 연출 제외 | MonsterHealthComponent.ApplyDamage 사망 확정 경로에 기존 MonsterAttackMotion:SetVisualClip("die") 한 번(4줄). fade·전환·새 연출 없음 | 일치·최소 |
| "안 2 보라+특수 1칸", 특수 "약 1/7", 대상 "랜덤으로" | F10 4행·Weight 2·2·2·1·AreaTarget FIXED/NEAREST/RANDOM | CSV 4행, Catalog 검증 3줄+필수 열 1개, MonsterAttackComponent RANDOM 분기와 SelectRandomCell | 일치. 보라 셋의 2:2:2는 planner 기본안(Plan에 그렇게 적힘) |
| 특수=가드·패링 불가 유지 + "가드 불가" 문구, 범위 밖 회피 0 유지 | F11 UNGUARDABLE rate 1, RecordDefense EVADE 대체 유지 | PlayerHealthComponent else 분기 3줄, CombatInputController 문구 1줄 | 일치·최소 |
| 끝 칸 홀드 + 1칸 특수 가설은 tester 확인만 | H1 | 코드 변경 없음, QA7 확인 | 일치 |

#### REV-F02 대조
- 위치·역할 분리: 공통 층(MonsterHealthComponent)에서 모든 HP 0 경로가 지나는 ApplyDamage 한 곳에 넣었고, 주황버섯 전용 OrangeMushroomAttack에는 넣지 않았다(Plan 지시대로). 새 RUID·Sync 값·모델 변경 없이 ActionSheet["die"]를 읽는다.
- 순서: IsDead=true → CancelPendingAttack(실행 무효화, CancelMotion은 stand를 쓰지 않음) → ClearCombatEffects → SetStunned(false)(그로기였다면 IsDead를 보고 die, 아니면 무동작) → SetVisualClip("die") → ChangeState("DEAD")(DEAD 잠금). 늦은 stand 쓰기 후보를 소스로 확인했다: OrangeMushroomAttack.CompleteMotion은 JumpActive일 때만 stand를 쓰는데 OnUpdate가 ATTACK이 아니면 CancelMotion만 하고, 활성 실행은 CancelExecution으로 무효화된다. MonsterStunComponent는 사망 시 die를 남긴다. HandleHitEvent는 IsDead면 반환한다. 추가 차단이 필요 없다는 coder 판단과 맞다.
- QA7 근거: 7경로(IDLE 실제 ↑·ATTACK 시작/점프/착지 대기/복귀·HIT·슬로우+점프·그로기 실제 ↑) 서버 +2.5초(그로기 +8초)까지 die, 클라이언트 `DEAD|die` 뒤 변경 없음, 실제 UIPopup 열기(_UIPopup:Open)·닫기(취소 핸들러) 중·후 die, Stop 뒤 재Play stand. Plan 완료 기준 항목을 모두 덮는다. 팝업 버튼 마우스 클릭은 핸들러 호출로 대체했다(입력 경로는 이번 변경 밖이라 판정에 영향 없음).

#### V11-F10 대조
- 데이터 주도: 대상 칸 방식이 CSV 열(AreaTarget)이고 공통 층에 modelId 분기·주황버섯 규칙이 없다. 주황버섯 착지(영역 중앙)는 기존 OrangeMushroomAttack 그대로라 고정 칸에 착지한다. 칸 수 3은 기존 BattlePos 3앵커 전제와 같다.
- 검증: 세 값 외(빈 값·알 수 없는 값·nil) 거부, `(ANY)==(FIXED)` 한 줄로 ANY+FIXED와 비ANY+NEAREST/RANDOM을 함께 거부, 앵커는 기존 검사(ANY 0/0, 그 밖 1~3 정수·From≤To)로 거부. 열 누락은 ReadRows 필수 열로 전체 거부. 부분 행·기본값 대체 없음. Plan 검증 목록과 같다.
- 무작위 칸: `SelectRandomCell(unit)`은 결정적 단위 함수라 경계 프로브가 가능하고, 결과는 기존 ANY 경로(영역·cells·유효 방향·탈출 검증·스냅샷 고정)를 그대로 지난다. 예고 중 재선택이 없다(PrepareAttack 1회). QA7 경계값·600/700표본 분포·플레이어 위치 무관·예고 뒤 이동/팝업에도 영역 불변 PASS.
- 판정 회귀: NEAREST·FIXED 경로 코드 불변. QA7 parry.any(Pos1·2·3)·parry.left/right(2칸 중간 착지·복귀 뒤 그로기·hit) PASS. NORMAL·GUARD 유형은 실제 데이터에 없어 시험 데이터 근거로만 확인(Plan 허용).

#### V11-F11 대조
- 가드+SPECIAL만 새 종류 UNGUARDABLE(rate 1, success false)로 갈린다. 결과 종류를 읽는 곳을 Grep으로 다시 확인했다: ResolveAttack의 RecordDefense(성공 아님·nativeHit 없음이면 EVADE)·JUST·PARRY 분기, Monster_Attack의 PARRY 분기, 로그, HUD. UNGUARDABLE은 슬로우·반격·그로기 어느 분기에도 걸리지 않고 범위 밖이면 "회피"로 대체된다. 피해 계산(ResolveIncomingDamage = floor(damage×rate))은 바뀌지 않아 원래 피해다. 문구 색은 기존 피격 색, 지속은 SetSignal 기존 규칙. .ui 무변경.
- QA7: 범위 안 "가드 불가" 12=HitEvent 12·약 1.0초, 범위 밖 "회피" 0, 무가드 "피격", 일반 가드 40%, 패링 늦은 가드 40%, 패링 성공 문구 유지 PASS.

#### 범위 밖 변경 없음
- 규칙·수치: CombatRuleData·AttackSkillData·MonsterData CSV, IsInWindow·창 0.20·×0.40·반격·슬로우·그로기·AttackDamage·AttackInterval·점프 값 불변(diff에 없음). 기존 행의 패딩·높이·오프셋·선행 시간 유지, Weight만 사용자 결정대로 2로.
- .ui·.map·.model·.codeblock·.userdataset 변경 없음. 3단계·V11-F07(수치 DataSet화)·§18(머쉬맘 리소스·이름 변경, 모델·OrangeMushroomAttack·modelId castleenemy 그대로) 착수 없음. §18은 Plan에 후보 등록만 있고 구현 승인 전 상태로 적혀 있다.

#### QA7 시험값 한계가 판정에 미치는 영향
- 창 3.0(실제 키 시험)·반격 8초: Play 내부 rules 캐시만 바꿨고 재Play에서 기본값 복귀를 확인했다. 이번 diff는 IsInWindow와 창 값을 건드리지 않았으므로 넓힌 창은 결과 종류·방향·속성 분기 검증에 충분하다. 0.20초 경계 자체는 이번 변경 경로 밖이라 재시험이 필요 없고, 손 타이밍 체감만 사용자 V11로 남는다.
- H1 해제 시점을 `ReleaseHeldState`(키 해제 핸들러가 부르는 같은 함수) 호출로 대체: 결과는 판정 순간 콜라이더와 영역의 겹침(서버 네이티브 판정)으로 정해지므로 규칙 판정에는 충분하다. 실제 손으로 떼는 시점의 난이도만 사용자 몫이다.
- 반격 소비는 입력 수락 지점 호출(논리 경로)로 확인했다. 반격 소비 코드는 이번 변경 밖이다.
- 시험 행의 TelegraphLeadSec(0.6~6.0)은 Play 내부 값이다. 실제 데이터 0.5에서의 반응 여유는 사용자 V11이다.

#### H1 결론
- 규칙대로 동작한다. 판정 순간 겹치면 HIT·원래 피해, 안 겹치면 EVADE·0이며, 겹치지 않는데 피해가 난 사례가 없다. R02 결함 아님. 사용자 결정(범위 밖 회피 0 유지)과 맞고 코드·입력 규칙은 바꿀 필요가 없다.
- 체감 참고(사용자 V11 평가 대상, 결함 아님): QA7 측정상 끝 칸 홀드 중 special.random이 그 칸에 오면 예고 남은 시간 약 0.37초 이상에서 떼야 피하고 약 0.29초 이하이면 맞는다(H1b-1 겹침 여유 0.04). 실제 선행 0.5초에서는 떼는 반응 여유가 짧다. 1/7 × 1/3 확률로만 생기는 경우다.

#### clear_logs 확인
- coder 절과 QA7 절 모두 maker_clear_logs 미호출을 적었고 run 235·238도 같다. QA7이 coder 시각대(19:36~19:40) 경고·LEA-3051을 그대로 읽어 구분한 기록은 로그가 지워지지 않았다는 정황과 맞다. reviewer는 Maker 로그를 직접 보지 않았다.

#### 미커밋 문서 대조
- GameDesign §4.2·§5·§8 미커밋 diff: 현재 상대=1번 마을(헤네시스) Stage 10 최종보스 머쉬맘, 현재 구현은 주황버섯 리소스, 리소스 교체·이름 변경은 §18 다음 회차, 일반 몬스터 주황버섯·초록버섯은 §5대로 남음, 마을 표기 "1번 마을(헤네시스)", 중간보스 미정. run "2026-11-03 일시정지"·"재개" 절의 사용자 말과 일치한다. 규칙·수치 변경 없음.
- 로드맵 미커밋 diff: 같은 내용과 §18 후보·6단계 일반 몬스터 질문 절차. 일치한다.
- 비차단 메모: (1) GameDesign §4.2 "보라 세 가지가 나머지를 같게 나눈다"는 planner 기본안(Plan §17·run 220)인데 "사용자 결정" 문장 안에 있다. 이 문장은 이번 diff 이전부터 있던 것이며 사용자 V11 때 확인하면 된다. (2) 로드맵 "다음 재개 지점"과 Plan §17 상태 칸이 "reviewer 대기"로 남아 있다. 회차 종료 정리 때 planner·메인이 맞춘다. (3) run 232는 planner 문서를 coder 로컬 커밋에 묶는다고 적었지만 5c4eda3에는 Plan·WR만 들어 있고 GameDesign·로드맵은 아직 미커밋이다. 회차 종료 커밋에 넣어야 한다.

#### NOT_RUN (PASS로 세지 않음)
- 사람 육안(die 모습·"가드 불가" 문구·특수 칸 구별), 0.20초 손 타이밍·실제 키 해제 타이밍, CSV 파일을 바꿔 Refresh로 반영하는 시험, 실제 마우스·터치 팝업 클릭·실기기, V12 외부, 플레이어 사망·실제 맵 이동, CF-F07 연출.

#### 다음 행동
1. 메인: run 대상 버전에 5c4eda3 커밋 트리 9208e0aa…da79 / 작업 트리 fdca556d…ee80과 이 판정 WAITING을 적는다. CLAUDE.md 회차 단위 기준에 따라 회차 종료 커밋에 QA7 절·이 리뷰 절·Plan §17 상태·미커밋 GameDesign·로드맵을 넣고, Maker 재저장 3경로는 넣지 않고 사용자에게 알린다. push 전 비밀값·개인정보 검사는 메인 몫이다.
2. 사용자 V11 확인(아래).
3. planner(문서만, 비차단): Plan §17 상태 칸·WR 머리·로드맵 재개 지점을 리뷰 WAITING과 사용자 V11 대기로 맞춘다. 규칙·수치·기준은 바꾸지 않는다.
4. coder/tester: 지금 할 일 없음. §18은 사용자 재개 지시와 §18 질문 답 뒤에 시작한다.

#### 사용자 V11 확인 항목
- HP 0 뒤 die 모습이 사망 경로와 관계없이 유지되는지(팝업 열고 닫은 뒤 포함).
- 보라 중심 4패턴과 특수 1칸 무작위의 난이도·구별, 특수 비중 약 1/7과 보라 셋 2:2:2 비중의 체감.
- 특수 가드 때 "가드 불가" 문구가 보이고 이해되는지.
- 범위 밖에서 시작한 저스트 인정 체감: 특수 칸이 다른 칸일 때 그 칸에서 멀어지는 방향으로 움직이면 위험 없이 저스트(슬로우·반격 ×2.2)가 된다. planner 해석이며 너무 쉬운지 판단이 필요하다.
- 끝 칸 홀드 중 그 칸 특수가 오면 짧은 반응 시간 안에 떼야 피하는 점(H1 체감).

### 2026-11-03 독립 리뷰 — V11-F08·F09 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 아래 런타임 근거는 coder 개발절(2026-11-03 V11-F08·F09)과 QA6의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다. reviewer가 직접 한 것은 git diff·소스 대조, node 스크립트(작업 디렉터리 밖 임시 스크립트)의 지문 재계산, ModelBuilder 읽기와 userdataset JSON 비교뿐이다.
- 검토 버전: coder 커밋 a921c76(기준 b89de46), QA 커밋 5a6ec07. V11-F06 절 manifest 54행을 같은 계산법(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)으로 재계산했다. b89de46 = b985aa4b…4dbf(표 54행 개별 해시 0건 불일치), 작업 트리 = **377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363**(coder·QA6 기재와 일치, coder가 적은 변경 6경로 개별 해시도 일치). 커밋 트리 자체(a921c76 = 5a6ec07 = HEAD)는 38e7aa22e05a0a71cc90ca6680278f4352315788cedbfabc7256e4d44dd0ba53이다. b89de46→a921c76 제품 변경은 mlua 3개(AttackAreaMarkComponent·MonsterStunComponent·CombatInputController)뿐이고, a921c76→작업 트리 차이는 미커밋 Maker 재저장 3경로뿐이다. a921c76..HEAD는 run·Plan·WR 문서만 바뀌었다(QA6 제품 무수정). .codeblock·.ui·.map·.model·CSV 변경 없음. 검토 시 git status는 그 3경로(M)뿐.
- 판정: **WAITING**. 새로 고칠 결함 없음(CHANGES_REQUIRED 없음). F08·F09의 AI 측 근거(코드 대조·coder 실측·QA6 서버/클라이언트 SpriteRUID 시계열·스크린샷 픽셀)는 Plan §16 완료 기준을 충족한다. 남은 필수는 사용자 V11 육안 확인이다. 이 판정은 2단계 완료·3단계 진행 승인이 아니다.

#### 미커밋 Maker 재저장 3경로 — 의미 차이 없음, 커밋 제외 타당
- AssistModel·AttackSkillData userdataset: JSON 전체 비교에서 차이는 `CoreVersion` 26.7.0.0 → 26.10.0.0 한 값뿐이다.
- 주황버섯 모델(ModelBuilder.read, HEAD 대 작업 트리): 컴포넌트 14개 목록 동일, properties·children·이름·id 동일, ActionSheet 6키(move·stand·jump·hit·die·stun, stun=hit RUID aec950…) 동일. 값 차이는 (1) HitComponent.ColliderOffset x 0.045 → 0.0449999869(float32 표기, 같은 값), (2) 스크립트 컴포넌트 값 17개 새 직렬화 — MonsterStateControl·MonsterAttackComponent·MonsterDefenseComponent·MonsterStunComponent·OrangeMushroomAttack의 Enable=true와 attackTimer 0·isDefending false·isStunned false·stunDeadline -1·scheduledId 0·executionId 0·Home (0,0)·HomeCaptured false·JumpActive false·JumpStartX/TargetX/StartTime 0. 모두 해당 .mlua 선언 기본값과 같다(Grep 대조). (3) 값은 같고 형식 버전 문자열만 바뀐 항목 7개. 런타임 의미 차이 없음.
- 판단: coder가 이 파일들을 쓰지 않았고(F08은 .mlua로 해결) 사용자 V11 중 Maker 저장으로 보이므로, 제품 커밋에 섞지 않은 처리는 CLAUDE.md "사용자가 직접 바꾼 파일은 범위가 아니면 섞지 않고 알린다"에 맞다. QA6는 이 3경로가 포함된 작업 트리를 시험했지만 의미 차이가 없어 근거가 커밋 트리(38e7aa22…)에도 그대로 적용된다. 이 리뷰의 [review] 커밋에도 넣지 않는다. 처리(별도 커밋 또는 유지)는 사용자에게 알리고 사용자가 정한다. 참고: 스크립트 기본값이 모델에 고정됐으므로 이후 해당 .mlua 기본값을 바꾸면(예: V11-F07 DataSet화) 모델 값이 우선한다. 지금 값은 모두 기본값과 같아 영향 없음.

#### V11-F08 대조 (MonsterStunComponent.SetStunned)
- 원인 근거와 수정의 일치: coder 실측은 "ActionSheet stun 키·RUID는 정상이고 ACE clip=stun도 오지만 hit가 비반복 클립이라 한 번 재생 뒤 렌더러 기본 표시(SpriteRUID=stand, 복귀 완료 CompleteMotion이 씀)로 돌아간다"이다. 수정은 그로기 동안 서버 SpriteRUID를 ActionSheet "stun"(=hit RUID)으로 고정하는 것이라 원인과 직접 맞는다. 이미 있던 MonsterAttackMotion.SetVisualClip(ActionSheet 값 재사용)만 써서 새 RUID·Sync 값·모델 변경이 없다. 변경은 SetStunned 한 메서드 12줄이다. 최소 범위로 판단한다.
- 서버 상태·HIT·수치 불변: Monster_Stun·MonsterHealthComponent·MonsterManager·HitComponent 경로 byte 불변. SetStunned는 isStunned 쓰기 순서를 그대로 두고 표시 클립만 덧붙였다. ApplyGroggy·BeginStunTimer·OnUpdate 만료·HandleHitEvent의 HIT 진입 조건(STUN 제외)은 diff에 없다. QA6에서 STUN 유지·GroggyRemaining 감소·HP=HitEvent=숫자 대표 PASS.
- 정리 경로 잔존: 호출처 5곳을 확인했다. (1) Monster_Stun.OnEnter → stun, (2) OnExit(자연 만료·ClearOpponentExecution의 IDLE 전환) → stand, (3) ApplyDamage 사망: IsDead=true 뒤 SetStunned(false) → die, 이어지는 DEAD 전환의 OnExit는 wasHeld=false라 아무것도 쓰지 않아 die를 덮지 않는다, (4) MonsterManager.ClearOpponentExecution → stand(사망이면 die), (5) MonsterStunComponent.OnMapLeave/OnEndPlay 서버 분기 → stand. 그로기가 아니던 SetStunned(false)는 즉시 반환해 공격 취소·정리 때 jump/stand를 덮지 않는다. 그로기 중 ApplyGroggy 재호출은 같은 RUID를 다시 쓴다(QA6 연장 그로기에서 hit 유지 확인). QA6가 상대 교체·DoSpawn·OnMapLeave 직접 호출·Stop 두 경로를 실행했고 잔존 없음(맵 이탈은 논리 경로, 실제 맵 이동 NOT_RUN).
- QA6 근거 수준: 세 조건 모두 서버·클라이언트 SpriteRUID 시계열과 스크린샷 픽셀(그로기 구간 vsHit 0~8.8, vsStand 73 이상)로 판정했고 이벤트 로그만으로 PASS하지 않았다. Plan §16 완료 기준("실제로 보이는 표시")과 맞다. 한계(클라이언트 실제 클립 이름 API 없음, 스크린샷 약 0.18초 간격, 정렬 ±0.15초, 사람 육안 아님)는 QA6에 그대로 적혀 있다.

#### V11-F09 대조
- 문구: CombatInputController에서 예고 문구 계산 블록만 지우고 telegraphText에 항상 빈 문자열을 쓴다. .ui 엔티티·바인딩 유지(.ui 무변경). defenseText(저스트 회피 성공·패링 성공·가드·피해 경감·회피·피격)·counterText(반격 준비)·effectText(상대 그로기·슬로우)의 문구·색·지속 코드는 byte 불변. 사용자 결정 "결과·상태 문구는 그냥 두는 걸로"와 맞다.
- 색·알파: NORMAL (1, 0.85, 0.4) / SPECIAL (1, 0.43, 0.36) / PARRY (0.88, 0.65, 1), 알파 CellAlpha 0.45 — Plan 표·이전 문구 색과 같다. 기존 빨강(1, 0.12, 0.12)은 남지 않았고 투명 기본색만 (1,1,1,0)으로 바뀌었다(알파 0이라 화면 차이 없음).
- 켜고 끄는 시점: 켜짐 판단은 그대로 서버 TelegraphCells의 칸 문자이고, 숨김 경로(대결 없음·상대 없음·OnMapLeave)는 기존 호출에 속성 인자만 더했다. TelegraphAttribute는 PrepareAttack에서 TelegraphCells 바로 앞에 같은 실행으로 설정된다(MonsterAttackComponent 140·142행), MonsterAttackComponent 무변경 조건 충족.
- 속성 미상 숨김: 세 값이 아니면 칸을 숨기고 0.25초를 넘기면 `[VRF]` 한 번(Maker Play만). 캐시는 켜짐과 속성을 함께 비교한다. QA6 "XYZ" 숨김·같은 칸 NORMAL→SPECIAL→PARRY 갱신 PASS.
- 가드형: 주황버섯 데이터에 없고 GUARD 처리는 바뀌지 않았다. 색은 속성만으로 정해지므로 가드형도 속성색이다. QA6 색값 픽셀 근거는 normal.left 단일 행에 속성을 직접 바꾼 시험값이며, Plan이 말한 "가드형(111) 시험 행"은 coder 기본 검증에서만 실행됐다. 색 결정 코드가 칸 집합·대응 유형을 보지 않으므로 같은 근거로 본다(공백 아님).
- 잔여 위험(비차단, 결함 아님): 공격 종료 뒤 TelegraphAttribute가 이전 값으로 남는다(기존 동작). 다음 공격에서 칸 동기가 속성 동기보다 먼저 클라이언트에 닿으면 이전 속성색이 1프레임 보일 수 있다. 서버는 속성을 먼저 쓰고 QA6에서 관측되지 않았다. 사용자 V11에서 색 깜빡임이 보이면 공격 종료 시 속성 초기화를 후보로 둔다.

#### 범위 대조
- 규칙·수치(창 0.20, 가드 ×0.40, 반격 ×2.2, 슬로우, 그로기 1.5, AttackDamage 12 등)·9패턴·Weight·CSV·.ui·.map·.model 변경 없음. 3단계·V11-F07(몬스터 수치 DataSet화) 착수 없음. 요구가 Plan §16에서 빠지거나 늘어난 곳은 없다.
- Plan §16 NOT_RUN 공백(2칸 패턴 복귀 중 팝업 V07·Stop 재Play V08)은 QA6에서 parry.left·parry.right로 메워졌다. 2026-11-03 F01~F06 리뷰가 남긴 비차단 공백은 해소로 본다.

#### tester 관찰 분류
- **일반 사망(IDLE·공격 중) 화면 stand 유지 → CombatCore-REV-F02로 추적(결함 후보, 이번 변경 범위 밖, 사용자 범위 결정 필요, 비차단).** 근거: coder 기준선(b89de46)과 QA6 재현 모두 DEAD에서 서버 SpriteRUID가 stand로 남고 ACE clip=die는 한 번만 나온다. 원인은 F08과 같은 구조(die도 비반복 클립이라 한 번 재생 뒤 렌더러 기본 표시로 돌아감)로 보이며, 몬스터 재생성 경로가 없어 HP 0 상태의 몬스터가 stand로 계속 보인다. a921c76이 만든 회귀가 아니라 이전부터의 동작이지만, 이번 변경으로 그로기 중 사망만 die가 고정돼 두 경우의 표시가 갈라졌다. Plan §7 V06 "기존 hit/die 가시성 보존"·V11 "die 구별"·CF-F07 피격/die 연출과 직접 닿으므로 V11 주관 평가로만 두지 않고 ID로 추적한다. 다만 수정은 §16 승인 범위(그로기 표시) 밖이고 Plan §16 "바꾸지 않는 것"의 DEAD 흐름 근처를 건드리므로 사용자가 (a) 2단계 V11 회차에 포함(예상 범위: DEAD 진입 시 기존 SetVisualClip("die")로 표시 고정, 서버 상태 흐름·수치 불변, .mlua만) 또는 (b) CF-F07·이후 몬스터 모션 단계로 미룸을 정한다. planner가 사용자 답을 받아 Plan에 기록한다.
- 그로기 만료와 타격이 겹칠 때 0.5초 HIT(stand 표시): 서버가 STUN→IDLE→HIT로 기존 HIT 규칙대로 지나간 결과다. F08 완료 기준(그로기 구간 hit)과 충돌하지 않는다. HIT 클립도 같은 비반복 구조라 짧게만 보이는 것은 REV-F02와 같은 표시 계열이므로 REV-F02 결정 때 함께 볼 수 있다. 별도 ID 없음.
- 생성 직후 0.3초 연출 프레임: DoSpawn 직후 네이티브 생성 표시로 보이며 이번 변경과 무관. 결함 아님.
- TelegraphAttribute 잔존: 이전 리뷰 분류 유지(판정이 읽지 않음). 이번 F09로 칸 색이 이 값을 읽게 됐지만 칸이 꺼진 동안은 보이지 않는다. 위 잔여 위험 1프레임만 남는다.

#### clear_logs 확인
- QA6 절과 run 198행 모두 maker_clear_logs 미호출을 적었다. coder 절도 미호출을 적었다. reviewer는 Maker 로그를 직접 볼 수 없으므로 담당 기록과 메인 확인을 근거로 한다. QA6가 coder 시각대 로그(14:38 LEA-2007)를 그대로 읽어 구분한 기록은 로그가 지워지지 않았다는 정황과 맞다.

#### NOT_RUN (PASS로 세지 않음)
- 사람 육안: 그로기 hit 모션, 노랑·적색·보라 칸 가독성과 색만으로의 속성 구별, 색약 접근성, 별·접촉 파티클.
- 0.20초 창 손 타이밍, V09 CSV 변경 반영, 실기기·터치(좌·우 버튼 전체 면적), 플레이어 사망 중 칸 정리, 실제 다른 맵 이동, V12 외부, CF-F07 연출.

#### 다음 행동
1. 메인: run 대상 버전을 a921c76(커밋 트리 38e7aa22…, 작업 트리 377a5ccc…)과 이 판정 WAITING으로 갱신하고 이 절만 `[CombatCore][review] WAITING`으로 커밋한다. 미커밋 Maker 재저장 3경로는 넣지 않고 사용자에게 알린다.
2. 사용자 결정: CombatCore-REV-F02(일반 사망 die 미유지)를 V11 회차에 포함할지 미룰지.
3. planner(문서만, 비차단): Plan §16 상태 칸 "reviewer 대기" → 리뷰 WAITING, REV-F02 추적 위치, WR 머리 "현재 재개 지점"(b89de46 기준으로 남음)과 로드맵 "다음 재개 지점"(F08·F09 미반영) 동기화. 규칙·수치·검증 기준은 바꾸지 않는다.
4. coder/tester: 지금 할 일 없음. 사용자가 REV-F02 포함을 정하면 그 ID만 coder→tester→reviewer로 돈다.
5. 사용자 V11(PC·모바일 직접): 그로기 동안 hit 모션이 실제로 보이는지(피격 없음·그로기 중 공격·슬로우 겹침), 예고 문구 없이 칸 위치·색만으로 방향·속성(일반 노랑·특수 적색·패링 보라)을 구별할 수 있는지와 가독성, 공격 사이 칸 색 깜빡임 여부, 결과·상태 문구 유지 확인, 일반 사망 때 몬스터 표시(REV-F02). 이전 리뷰의 V11 항목 중 (1)·(3)의 문구·빨간 칸 평가는 Plan §16대로 이것으로 대체되고 나머지는 유지된다.

### 2026-11-03 독립 리뷰 — V11-F01~F06 WAITING
- 담당: Claude Code msw-reviewer(coder·tester와 별도 실행). Maker 제어/Play·제품·Plan 요구·QA 판정 수정 없음, commit·push 없음. 1447ff8 대상 이전 reviewer 호출은 기록 없이 중단돼 F01~F05 몫까지 이번에 한 번에 판정했다. 아래 런타임 근거는 coder 개발절(2026-11-02 V11, 2026-11-03 F06)과 QA4·QA5의 실행을 대조한 것이며 reviewer가 다시 실행한 결과가 아니다.
- 검토 버전: coder 커밋 b89de46 / 54경로 Bundle b985aa4b901dfd0602303de3504aa0372acc4d54ed9ccaa6a7d1c4fb56d74dbf. reviewer가 F06 절 manifest 54행을 node 스크립트(경로 ASCII 정렬, 경로+TAB+sha256+LF의 SHA-256)로 작업 트리·b89de46·a43b1b5(QA5)·HEAD에서 재계산해 54/54·Bundle 동일을 확인했다. 같은 manifest로 1447ff8·f7b3244(QA4)는 d2b57802…0fbb, a289eb7·6614b20은 1ac324e6…9de4가 재현된다. 1447ff8..b89de46에서 바뀐 manifest 경로는 coder 기재대로 10개다. 검토 시 git status 깨끗.
- 판정: **WAITING**. 새 결함 ID 없음. F01~F06의 AI 측 근거(코드 대조·QA4/QA5 수치·로그)는 승인 범위를 충족한다. 남은 필수는 사용자 V11 직접 확인, CF-F07 실제 연출, V12 외부 환경이다. 이 판정은 2단계 완료·3단계 진행 승인이 아니다.

#### 같은 버전 확인 — F01~F05 근거가 F06 변경 뒤에도 유효한가
- QA5(b89de46)에서 다시 확인됨: F01 칸 표시(1칸·2칸·ANY 고정 칸), F02 대표(ANY 패링→복귀→Home x=3.0 STUN→약 1.5초→IDLE), F03 접촉 파티클 로그 1회, F05 전체, V02·V04~V08·V10 대표.
- QA4(1447ff8)에서만 확인되고 이월된 것과 이월 근거:
  - F04 STUN hit 클립·사망 die 우선: 주황버섯 model·Monster_Stun·MonsterStunComponent 해시가 두 manifest에서 같고, 아래 구조 비교에서 model 의미 차이도 0이다. 이월 타당.
  - F03 별 크기·높이, 파티클 재생 경로: MonsterStunComponent byte 불변. 이월 타당(육안은 원래 NOT_RUN).
  - F02 복귀 중 팝업·피격·슬로우·사망·Stop 조합: **재확인 공백(차단 아님)**. Monster_Attack은 모션 호출 1줄만 바뀌었고 OrangeMushroomAttack의 복귀(PerformReturnMotion→Home)·CompleteMotion·CancelMotion·OnUpdate는 byte 불변이다. 다만 2칸 패턴의 복귀 출발점이 착지 x(±0.75)로 바뀌었고 QA5의 복귀 대표는 ANY(1칸) 1건이다. 같은 시계·같은 상태 경로라 위험은 낮다고 판단하며 필수 재시험으로 두지 않는다. tester를 다시 부를 일이 생기면 함께 볼 조건: 2칸 패턴 패링→복귀 중 팝업 정지·재개, 복귀 중 Stop→재Play 기본값.
- .codeblock: 1447ff8..b89de46에 변경 없음. MonsterAttackMotion·OrangeMushroomAttack .codeblock에는 메서드 이름이 들어 있지 않아(Grep 0건) PerformAttackMotion 서명 변경과 무관하다. QA5 build 로그 80건 오류·경고 0.

#### 구조 파일 의미 비교 (ModelBuilder/MapBuilder 읽기, node)
- 주황버섯 model a289eb7→b89de46: 차이 2개뿐. ActionSheet에 `stun` = aec9504d5dc24aceb5646b79d30abad4(hit와 같은 RUID) 추가, 그 값의 ValueType 형식 버전 문자열 26.7.0.0→26.10.0.0. 1447ff8→b89de46 차이 0. 줄 끝 CRLF→LF는 의미 차이 아님. F04 의도 범위 안이다.
- map01 a289eb7→1447ff8: BattlePosMark1~3 엔티티 3개 추가뿐(modelId attackareamark, x -1.5/0/1.5, y 0.98, Scale 25×25×1, PixelRenderer, AttackAreaMarkComponent CellIndex 1/2/3). 기존 엔티티 의미 차이 0. 1447ff8→b89de46(Maker 재저장): 같은 세 엔티티의 Transform에서 Scale `$type` 표기 제거와 기본값 Rotation (0,0,0)·ZRotation 0 명시뿐. 값 변화 없음.
- AttackAreaMark model은 1447ff8에서 새로 생겼다(a289eb7에 없음). 1447ff8→b89de46 의미 차이 0. Components는 Transform·PixelRenderer·script.AttackAreaMarkComponent, Values는 Scale 하나.
- MapObjects.directory도 1447ff8에서 새로 생겼고 b89de46에서는 StudioVersion "" → "0.1.0.0" 한 줄만 바뀌었다.
- 결론: 구조 파일 변경은 F01·F04 의도 범위와 Maker 재저장 표기 차이뿐이다. raw JSON 편집이나 수정은 하지 않았다.

#### F06 승인 범위 대조 (Plan §15·사용자 결정 1~4)
- ANY 조준: PrepareAttack에서 FindNearestCell로 예고 시작 순간 최근접 칸을 한 번 고정한다(동률 순서 2→1→3, epsilon 1e-6, 추적 없음). 유효 방향은 Pos2 좌·우, Pos1 오른쪽, Pos3 왼쪽(targetCell ≥2 → LEFT, ≤2 → RIGHT)이다. 기존 LEFT/RIGHT 탈출 검증은 그대로이고, ANY는 각 유효 방향 도착 x ± (|offset| + halfWidth)가 [minX, maxX] 밖인지 따로 검사한다. ResolveAttack은 snapshot.validDirs를 EvaluateDefense에 넘기고, 회피 분기는 `validDirs[EvadeDirection] == true`와 창 안 시작일 때만 JUST다. 가드 분기는 byte 불변이다. QA5의 Pos1/2/3·동률·경계·이동 뒤 조준 불변·중앙 복귀 비저스트 근거와 일치한다.
- 2칸 중앙 착지: OrangeMushroomAttack.PerformAttackMotion(cells, minX, maxX)만 영역 중앙 `(minX+maxX)/2`를 부모 로컬 x로 바꿔 JumpToLocalX한다(NaN·역순이면 -1). 공통 층의 Monster_Attack·MonsterAttackMotion 기본 구현은 칸 문자열과 x 범위만 전달·반환 0이다. 착지 위치 규칙은 주황버섯 모션에 한정되고, 이후 보스 모션이 같은 인자로 다른 착지를 정할 수 있다. 공통 snapshot의 landing 필드와 CSV LandingAnchor는 제거됐다.
- Weight: CSV 필수 열, 로더가 ≤0·비수치를 거부(전체 카탈로그 거부·경고 1회). SelectPattern은 r = unit × 합계를 CSV 행 순서로 누적 비교하고 마지막 행을 끝값 처리한다. 9행 모두 1이라 균등이다. QA5의 거부 시험과 900회 선택 분포와 일치한다.
- 가드형 제외: CSV에서 normal.guard·parry.guard 2행이 빠졌고 GUARD 처리 코드는 남아 있다. QA5의 가드형 확인은 Play 내부 메모리 시험 행으로 "시험 데이터 근거"라고 표시돼 있어, 실제 데이터 PASS로 섞이지 않았다.
- 바뀌지 않아야 할 것: CombatRuleData·AttackSkillData CSV는 a289eb7..b89de46 변경 없음(CSV 변경은 MonsterAttackPatternData뿐). 패턴 CSV의 padding 0.5·height 1·offset 0.4·lead 0.5, 기존 LEFT 2-3·RIGHT 1-2 앵커는 그대로다. JumpHeight 0.8·JumpDuration 0.5와 공격 수치·창 0.20·가드 0.40·반격·슬로우·그로기 수치를 바꾸는 diff는 없다. F06 변경은 승인된 1~4 범위를 넘지 않는다. .ui·.model·.map 변경은 Maker 재저장 3개 파일뿐이다.

#### QA 관찰 분류 (모두 결함 아님, 새 ID 없음)
- ANY 끝 칸 문구 "[좌·우]"와 실제 한 방향 차이: Plan §15가 허용한 일반형 표현이고, 칸 표시가 조준 칸을 알린다. 사용자 V11의 가독성 판단 대상. 바꾸려면 planner 문구 결정이 필요하다.
- 끝 칸 홀드 중 새 저스트 불가, 복귀 중 반대 입력 무시: §15 설계와 기존 이동·복귀 잠금(입력 예약 없음) 그대로다. 난이도는 V11 판단.
- TelegraphAttribute 잔존: 공격 종료 뒤 마지막 값이 남지만 Response가 비어 HUD에 나오지 않는다. 이전 버전부터의 동작이며 판정이 이 값을 읽지 않는다. 정리 여부는 후속 선택 사항.
- UI 뒤·앞 버튼이 시뮬레이터에서 가장자리(x=805/1115)에서만 눌림(QA4): 제품 결함인지 시뮬레이터 좌표 재매핑인지 근거가 없다. F06은 .ui·버튼 코드를 바꾸지 않았다. 사용자 실기기 V11에서 전체 면적을 확인한다. 실기기에서도 재현되면 그때 결함으로 등록한다.
- 복귀·그로기 중 피격 시 클라이언트 로컬 HIT·hit 클립(QA4): 서버 상태(ATTACK/STUN)와 규칙은 정상이다. 이번 변경 이전부터 있는 클라이언트 표시 구조이고, 그로기 중에는 RUID가 같아 화면이 같다. 복귀 중 jump→hit 전환이 거슬리는지는 V11·CF-F07 연출 판단 대상.
- 플레이어 사망 직후 HP 문자 음수 가능성: 2026-11-02 리뷰 분류 유지(결함 아님, 3단계 계획 후보, V11에서 함께 확인).

#### QA4 계약 위반 기록
- QA4 tester가 시작 직후와 회차 사이에 maker_clear_logs를 호출해 이전 Play의 normal 로그 36건을 보존 확인 없이 지웠다(build 로그는 유지, QA4 절 시험 오류 (4)(5)·run 144행). 사용자 로그 무단 삭제 금지 위반이다. 메인이 사용자에게 보고했고 QA5 지시에 금지를 명시했으며, QA5는 미호출을 기록했다(QA5 절·run 167행).
- 판정 영향: 지워진 것은 이전 Play 로그이고, QA4 판정에 쓴 근거는 지운 뒤 새로 실행한 회차의 로그다. 결과를 잃은 J2는 새 몬스터로 다시 실행한 결과만 썼다. QA4 PASS는 무효로 보지 않는다. 다만 지워진 36건의 내용은 복구·확인할 수 없다.

#### NOT_RUN (PASS로 세지 않음)
- 실제 입력으로 0.20초 창 안 손 타이밍 저스트·패링 성공(실제 키 성공은 시험 한정 창 8.0/0.9, 창 0.2 안은 서버 프로브), 0.200 등호 경계.
- V09 CSV 파일 변경→Refresh→Play 반영(시험 행 ValidateRows로 대체).
- F04 클립 재계측(QA5), 그로기 중 hit 클립 재생 재시작 여부(QA4).
- 육안 전체: 별 크기·가시성, 접촉 파티클, 1칸 공격 구별, 2칸 중간 착지 모션, 칸 색·가독성.
- 위 F02 복귀 중 조합의 2칸 패턴 재확인.
- V11 사용자 직접, CF-F07 실제 연출, V12 외부(두 사용자·비전투 몬스터·다른 맵).

#### 다음 행동
1. 메인: run 상태·대상 버전을 b89de46 / b985aa4b…74dbf와 이 리뷰 판정 WAITING으로 갱신한다. 이 절을 `[CombatCore][review] WAITING`으로 커밋한다.
2. planner(문서만, 차단 아님): 이 WR 머리 "현재 재개 지점"(6614b20 기준으로 남음)과 Plan 머리·§15 끝의 "다음 흐름"을 리뷰 완료·사용자 V11 대기로 맞춘다. 규칙·수치·검증 기준은 바꾸지 않는다.
3. coder/tester: 지금 할 일 없음. V11에서 새 요구나 실기기 재현 결함이 나오면 해당 ID만 다시 돈다.
4. 사용자 V11(PC·모바일 직접):
   - 1칸(ANY) 공격이 칸 표시로 구별되는지, "[좌·우]" 문구가 끝 칸에서 헷갈리지 않는지, 끝 칸 홀드 중 대응 불가 난이도.
   - 2칸 공격의 두 칸 중간 착지 모션 모양.
   - F01 빨간 칸 표시의 색·가독성, F02 복귀 후 그로기 흐름, F03 별 크기·높이와 패링 접촉 파티클, F04 그로기 hit 모션.
   - 복귀 중 피격 시 jump→hit 클립 전환이 거슬리는지.
   - 좌·우 UI 버튼 전체 면적이 눌리는지(실기기·터치).
   - 0.20초 창 손 타이밍 체감, 패턴 선택(Weight 균등) 체감.
   - 플레이어 사망 직후 HP 문자 표시.
5. 외부 대기: V12, CF-F07 연출, 기존 외부 후속 ID는 기존 추적 유지. P01b~P06 🟡 유지, 3단계 자동 시작 없음.

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

## 2026-11-03 coder V11-F08·F09 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §16의 CombatCore-V11-F08(그로기 중 hit 모션 실제 표시)·V11-F09(예고 문구 제거·칸 속성색)뿐이다. 규칙·수치(0.20, ×0.40, 반격, 슬로우 2.0·×0.5, 그로기 1.5, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8), CSV·DataSet, 9패턴·Weight, D01~D04, 서버 상태 흐름(IDLE/HIT/ATTACK/STUN/DEAD)과 HitComponent·MonsterHealthComponent의 HIT 진입 조건, 주황버섯 ActionSheet 값, 결과·상태 문구(defenseText·counterText·effectText), .ui·.map·모델, V11-F07, 3단계는 바꾸지 않았다. 새 클립·자원은 쓰지 않았다(기존 hit 클립 RUID aec950… = ActionSheet "stun"·"hit").
- 기준 버전: 커밋 b89de46. 같은 방법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)으로 b89de46의 54경로를 git show로 재계산해 b985aa4b…4dbf 일치를 확인했다. 시작 시 작업트리 Bundle은 b0019098…f5b0이었고 차이는 Maker 재저장 미커밋 3파일(아래)뿐이다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록; 이번에는 구조 파일을 바꾸지 않아 MapBuilder를 다시 읽지 않았다). Maker 로그 시각 14:29~14:43. **maker_clear_logs는 한 번도 호출하지 않았다.** 로그는 시각·`[VRF8]`(이번 회차 임시 계측 표지)·`[VRF]` 표지로 파일에 저장해 걸러 읽었다.
- 미커밋 Maker 재저장 3파일(AssistModel.userdataset·AttackSkillData.userdataset의 CoreVersion 한 줄, 주황버섯 모델의 형식 버전·부동소수 표기·스크립트 기본값 직렬화)은 되돌리거나 건드리지 않았다. **주황버섯 모델을 빌더로 다시 쓰지 않았다**(F08은 .mlua로 해결, 모델 무수정). 따라서 이 세 파일은 이번 변경이 아니며 지문에는 포함된다.

### V11-F08 원인 확정 (실측)
- 방법: 패링(가드 시작이 타격 0.12초 전, 패턴 단일 행 교체) → 복귀 → 그로기 → IDLE을 서버 프로브(상태·SpriteRUID·isStunned·GroggyRemaining)와 소유 클라이언트 프로브(StateComponent.CurrentStateName·SpriteRendererComponent.SpriteRUID·PlayRate·AnimationClipEvent·StateChangeEvent)로 같은 시간축(ServerElapsedSeconds)에 기록했다. 클라이언트에서 "화면에 실제로 보이는 값"을 읽는 API는 없다(SpriteRendererComponent.ClipName은 deprecated로 항상 빈 문자열, SpriteRUID는 서버 쓰기만 따라가고 AnimationClipEvent는 속성을 바꾸지 않는다). 그래서 실제 표시는 play 카메라 스크린샷(maker_screenshot)에서 몬스터 영역 픽셀을 IDLE(stand) 기준 영상과 비교해 판정했다(같은 위치·정지 프레임이면 차이 평균 0, 고통 얼굴 hit 끝 프레임은 차이 ≈78~80, 중간 프레임은 ≈50, 확대 그림과 눈으로 대조).
- 관측 1 (이벤트 vs 속성): IDLE에서 서버 ChangeState("HIT")만 해도 클라이언트에 ACE clip=hit가 오지만 SpriteRUID는 stand로 그대로다(IDLE→HIT 0.5초 사이 stand 유지). 그로기 진입도 같다: ACE clip=stun(=hit RUID) 직후 클라이언트 SpriteRUID는 stand(복귀 완료 CompleteMotion이 쓴 값)였다.
- 관측 2 (화면): ApplyGroggy(30)을 IDLE에서 바로 준 경우(SpriteRUID 변화 없음) 직후 스크린샷은 hit 중간 프레임(차이 49.8)이고, 같은 방식의 그로기 중 플레이어 실제 ↑ 공격 뒤(약 2초 후) 스크린샷은 stand(차이 4.25)였다. 실제 패링 흐름(복귀→그로기, 그로기 연장 30초)의 그로기 중 스크린샷도 stand(차이 0.85)였다. 서버가 SpriteRUID에 hit 클립을 직접 쓴 경우(IDLE 시험)는 직후 0, 이후 세 장 모두 78.57 고정(고통 얼굴 끝 프레임을 유지)이었다.
- 관측 3 (피격 중 클라이언트 상태): 그로기 중 플레이어 ↑ 공격에서 서버 상태는 STUN을 유지하지만 클라이언트 로컬 상태가 STUN→HIT로 바뀌고 ACE clip=hit가 한 번 나온 뒤 서버 그로기 종료(ACE stand, HIT→IDLE)까지 HIT로 남았다(자동 IDLE 복귀 없음, 화면은 이미 stand).
- 확정: 원인은 Plan 후보 3·4의 변형이다. ActionSheet "stun" 키·RUID는 정상(stun=aec950…, 그로기 진입마다 ACE clip=stun)이지만 hit는 짧은 비반복 클립이라 상태 이벤트로는 한 번 재생된 뒤 렌더러 기본 표시(SpriteRUID=stand)로 돌아간다. 그로기 1.5초 동안 hit 모습이 남지 않으며, 복귀 완료 직전 서버가 stand를 써 두는 것도 같은 결과로 이어진다. 후보 2(클라이언트 로컬 HIT)는 관측됐지만 stand 복귀 원인이 아니라(자동 IDLE 없음) 결과를 바꾸지 않는다. 후보 1(동기값 덮어쓰기 순서)은 단독으로 분리해 확인하지 않았다(위 설명만으로 모든 관측이 설명된다).

### V11-F08 수정 (최소 범위, .mlua 한 곳)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Monster/MonsterStunComponent.mlua | SetStunned(boolean)에서 그로기가 켜지면 기존 MonsterAttackMotion.SetVisualClip("stun")으로 서버 표시 클립을 ActionSheet "stun"(=hit RUID)로 고정하고, 실제로 그로기였다가 꺼질 때 stand로 되돌린다(사망으로 끝나면 "die"를 남긴다, health.IsDead는 ApplyDamage가 상태 변경 전에 먼저 true로 둔다). 그로기가 아니던 SetStunned(false) 호출(공격 취소·정리)은 아무것도 쓰지 않는다. 복귀 중 jump(JumpToLocalX)·CompleteMotion의 stand 쓰기는 그대로라 그로기 시작 시점에만 hit로 바뀐다. 상태 규칙·타이머·서버 HIT 진입 조건·ActionSheet 값·모델은 무변경. |
- 모션 클래스가 없거나 유효하지 않으면 아무것도 하지 않는다. 새 Sync 값·새 RUID 없음.

### V11-F08 수정 후 확인 (Play 내부, 서버·클라이언트 동시 기록)
| 조건 | 결과 |
| --- | --- |
| (a) 피격 없는 실제 흐름(자연 1.5초) | 서버 상태 ATTACK(jump)→STUN 14.04에 SpriteRUID hit(stun) + 클라이언트 같은 시각 ACE clip=stun, 클라이언트 SpriteRUID hit(stun) 유지 → 그로기 1.5초 뒤 서버 IDLE\|stand, 클라이언트 ACE clip=stand·IDLE\|stand. 복귀 중에는 jump 유지(ATTACK\|jump), 그로기 시작 시점에만 hit. 스크린샷(그로기 연장 중): 고통 얼굴 hit 프레임 유지 |
| (b) 그로기 중 실제 ↑ 공격 | 클라이언트 STUN→HIT(ACE clip=hit 1회) 뒤에도 SpriteRUID hit(stun) 유지, 공격 이펙트·피해 숫자와 함께 스크린샷 모두 hit 프레임. 그로기 종료 뒤 스크린샷 stand. 서버 상태 STUN 유지·GroggyRemaining 감소(조기 해제 없음)·몬스터 HP는 HitEvent 경로(수동 공격 10타씩) 그대로 |
| (c) 슬로우 겹침(ApplySlow 8초×0.5) | PlayRate 0.5가 되었으나 SpriteRUID hit(stun) 유지, 스크린샷 hit. 서버 그로기 기한은 전투 시간 기준 그대로 |
| 그로기 중 사망(ApplyDamage 999) | 서버 STUN→DEAD, isStunned false, SpriteRUID die. 클라이언트 ACE clip=die·SCE HIT→DEAD, 스크린샷은 die 프레임이 고정(HP 0). die가 hit보다 우선한다 |
| 2칸 패턴(parry.left) 복귀 중 팝업(V06·V07) | 판정 PARRY 직후 x=0.75에서 팝업 → 서버 paused 5초 동안 ATTACK\|jump 유지·위치 고정 → 닫은 뒤 복귀가 이어져 STUN 진입 시 hit(stun)로 바뀌고 1.5초 뒤 IDLE\|stand |
| Stop 뒤 재Play(V08) | (1) 그로기(30초) 중 maker_stop → 재Play: 몬스터 IDLE·SpriteRUID stand·isStunned false·GroggyRemaining 0·ParryEffect (0,0,0)·칸 표시 없음·패턴 9행·AttackInterval 기준값. (2) 2칸 패턴(parry.right) 복귀 중 팝업 정지(x=-0.75)에서 maker_stop → 재Play: paused false·칸·응답·반격 false·패턴 9행·플레이어 IDLE, 팝업 닫힘, 클라이언트 IDLE·stand·칸 표시 없음. 런타임 오류 로그 없음 |
- HP=HitEvent=숫자(V02 대표, 제품 경로): 일반 무대응 HIT 12/12, 저스트 JUST 0/0, 가드 GUARD 4/4(12×0.4=4.8→4), 패링 PARRY 0/0 후 그로기 진입(V03 대표 경계). 이번 변경은 이 경로에 관여하지 않는다.

### V11-F09 변경
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/UI/CombatInputController.mlua | 공격 예고 문구(telegraphText) 계산 블록을 삭제하고 항상 빈 문자열("", 흰색)로 둔다. .ui 엔티티·바인딩은 그대로(.ui 무변경). defenseText·counterText·effectText(저스트 회피 성공·패링 성공·가드·피격·회피·반격 준비·상대 그로기·슬로우)는 문구·색·지속 그대로 |
| RootDesk/MyDesk/Combat/AttackAreaMarkComponent.mlua | 칸 색을 서버 동기 MonsterAttackComponent.TelegraphAttribute로 정한다: NORMAL (1, 0.85, 0.4) / SPECIAL (1, 0.43, 0.36) / PARRY (0.88, 0.65, 1), 알파는 기존 CellAlpha 0.45. 표시 캐시는 켜짐 여부와 속성을 함께 비교해(같은 칸에 속성이 바뀐 연속 공격도 새 색 반영) 속성 값이 달라질 때만 FillColor한다. 켜져야 하는데 속성이 세 값이 아니면(빈 값·동기화 순서 차이 포함) 그 칸을 숨기고, 0.25초를 넘겨 계속되면 `[VRF] AttackAreaMark unknown attribute` 한 번만 남긴다. 기존 단일 빨강(1, 0.12, 0.12)은 더 쓰지 않으며 투명 기본색은 (1,1,1,0). 칸 선택(TelegraphCells)·켜는 시점·끄는 조건은 F01과 같다(MonsterAttackComponent 무변경 — 같은 실행의 속성 동기값이 칸 정보와 함께 PrepareAttack에서 설정됨을 확인) |
- 확인(Play 내부): (1) 9패턴 각각을 제품 경로로 한 번씩 실행(패턴 단일 행 교체): 클라이언트 칸 속성 표시 normal.left -NN / special.left -SS / parry.left -PP / normal.right NN- / special.right SS- / parry.right PP- / normal.any -N- / special.any -S- / parry.any -P-(서버 TelegraphCells 011·110·010과 일치), 모든 구간에서 telegraphText.Text는 빈 문자열, 판정 뒤 칸이 꺼졌고 결과 문구(피격)는 이전처럼 표시됐다. (2) 가드형 시험 데이터(Play 내부 단일 행, 칸 111·예고 40초): NORMAL·SPECIAL·PARRY 순으로 켜 스크린샷의 칸 픽셀을 배경(칸 없는 같은 프레임)과 알파 0.45로 역산해 색을 확인했다 — 노랑 (1, 0.85, 0.4)·적색 (1, 0.43, 0.36)·보라 (0.88, 0.65, 1)가 세 칸 모두에서 오차 ±0.01로 일치("시험 데이터 근거"). 같은 칸 연속 공격에서 속성이 NORMAL→SPECIAL→PARRY로 바뀌면 칸이 계속 켜진 채 새 색으로 갱신됐다. (3) 속성 미상: 서버에서 TelegraphAttribute를 "XYZ"로 바꾸자 칸 픽셀이 배경과 같아져(숨김) 확인했다. (4) 2칸 패턴 복귀 중 팝업·Stop·재Play 뒤 칸 표시 없음(위 표).

### 실제 기본 검증 요약
- 빌드: Refresh 후 build 로그 81건 모두 Info(LIA 동적 참조 노이즈, 앞 회차와 같은 유형), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음.
- Play 5회(최초 통합 계측·수정 전 원인 실측 / 수정 후 통합 확인 / 9패턴·팝업·Stop 회귀 / Stop 뒤 재Play 기본값 2회). 모든 Play는 maker_stop으로 닫았고 시험값(AttackInterval 9999, 패턴 단일 행 교체, 그로기 연장 6~60초, 슬로우 8초, 예고 40초, 플레이어 HP 보충, 속성 "XYZ")은 Play 내부에만 두었다. 재Play에서 패턴 9행·AttackInterval 기준값·규칙값 정상.

### 프로브 오류와 제품 오류의 구분, 관찰
- 시험 스크립트 문제: (1) 이전 몬스터를 폴링하던 클라이언트 프로브가 DoSpawn(교체) 뒤에도 돌아 `LEA-2007 nil StateComponent`를 약 370건 냈다(14:38:38~52, 제품 오류 아님). (2) Stop 때 남은 클라이언트 프로브 타이머로 `LEA-3051 MemoryLeak(MakerScript)` 1건(14:42:06). (3) Stop과 같은 순간에 찍은 서버 로그 한 줄(T2)은 Play 정리가 시작돼 상태가 흔들려 읽혔다 — 같은 조작을 Stop 없이 다시 실행해 정상 값(그로기 켜짐 시 SpriteRUID hit)을 확인했다. 제품 runtime 오류·경고는 관측되지 않았다.
- 관찰(이번 범위 밖, 바꾸지 않음): 수정 전 기준선에서 IDLE의 몬스터가 사망하면(DEAD) 화면이 die가 아니라 stand 프레임으로 보였다(die 클립도 비반복이라 끝난 뒤 기본 표시 stand로 돌아가는 것으로 보이며, 스크린샷 차이 0·HP 0/100). 이번 변경 이후 그로기 중 사망은 die가 고정되어 표시가 다르다. 일반 사망의 die 유지 여부는 사용자 확인(V11) 또는 별도 결함 후보로 판단한다.
- 클라이언트 로컬 HIT: 그로기 중 피격 시 클라이언트가 STUN→HIT로 보이는 구조는 그대로다(서버 상태는 STUN). 화면은 hit 고정이라 문제 없다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 문구 없이 칸 위치·색만으로 방향·속성 구별과 노랑·적색·보라 칸 가독성, 그로기 hit 모션이 실제 눈에 어떻게 보이는지(여기서는 스크린샷 픽셀·프레임 대조), 별·접촉 파티클, 좌·우 UI 버튼 전체 면적(실기기·터치), 사람 손 0.20초 창 타이밍, Weight 체감. V12 외부 환경, V09 CSV 파일 변경 반영, 플레이어 사망·다른 맵 전환, 모바일 화면, 속성색의 색약 접근성은 미실시.
- 스크린샷 해상도(558×314)와 간격 한계: hit 프레임 유지는 연속 스크린샷 3~4장과 클라이언트 SpriteRUID·이벤트 시계열로 확인했다. 1.5초 전체를 연속 프레임으로 녹화한 것은 아니다. 짧은 자연 그로기(1.5초)의 육안 확인은 도구 왕복 시간 때문에 연장 그로기(시험값)로 대신했고, 자연 1.5초는 클라이언트 SpriteRUID 시계열로만 확인했다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F08 세 조건(피격 없음·그로기 중 실제 ↑ 공격·슬로우 겹침)에서 그로기 전체 구간 hit 표시, 종료 뒤 stand, 복귀 중 jump, 사망 시 die — 클라이언트 SpriteRUID 시계열(상태·ACE와 같은 시간축)과 스크린샷 두 방식을 함께 쓰고 기존 이벤트 근거만으로 PASS 하지 않는다. (2) F09 9패턴 칸 색·예고 문구 없음·결과 문구 유지·속성 미상 숨김·가드형 시험 데이터, 팝업 중 유지·사망·Stop 뒤 잔존 없음. (3) 회귀 V02·V03 대표, V06(복귀 중 jump 유지)·V07·V08(2칸 패턴 복귀 중 팝업·Stop 포함), V10 대표. 주의: maker_clear_logs를 호출하지 말고 시각·표지로 구분해 읽는다(로그가 매우 커서 파일로 저장된 분량을 걸러 읽는 것이 편하다). SetStunned 변경이 그로기 정리 경로(ClearOpponentExecution·OnMapLeave·OnEndPlay·사망)에서도 stand/die를 쓰므로 이 경로들(상대 교체·Stop·맵 이탈)의 표시 잔존 여부를 함께 본다. 육안·V11·V12는 사용자 몫이다.

### 2026-11-03 최종 제품 버전 묶음 (V11-F08·F09)
- 이전 묶음(b985aa4b…4dbf, 54경로)과 같은 경로 집합·계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)이다. b89de46을 같은 방법으로 재계산해 b985aa4b…4dbf 일치를 확인한 뒤 작업트리를 계산했다. b89de46 대비 변경된 경로는 6개로, 이번 변경 3개(AttackAreaMarkComponent.mlua·MonsterStunComponent.mlua·CombatInputController.mlua)와 Maker 재저장 3개(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번에 수정하지 않음)다. 나머지 48개는 b89de46과 같다. .codeblock·.directory는 대상 외다.
- Bundle SHA-256: 377a5ccc5f42de649117004aad7520cff9a73eae80c9e1096bb3e3bf3f780363.
- 변경 경로 SHA-256: Combat/AttackAreaMarkComponent.mlua 09df43555df7528ef68043d44c4927183401c878f09aa63cedaf6695fa8b495f · Monster/MonsterStunComponent.mlua 165d8b5ec9bff3bbbb2b0feda73cfb42a53141f55657a5772b97efafac27cd34 · UI/CombatInputController.mlua 5e42865cdf8b15813aa2a5a8a47bd26b3587fa1387152735ae76a4e1a7bec21d · Models/Monsters/주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · @Assist/DataSet/AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 48경로 해시는 이전 묶음(V11-F06) 표와 같다.

## 2026-11-03 coder REV-F02·V11-F10·V11-F11 구현·기본 검증 인계

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §17의 CombatCore-REV-F02(모든 사망 경로 die 고정)·V11-F10(주황버섯 패턴 4행 재구성, CSV `AreaTarget` 열, RANDOM 대상 칸)·V11-F11(특수 가드 "가드 불가" 문구)뿐이다. §18(머쉬맘 전환)은 하지 않았다(이름·리소스·모델 무변경). 규칙·수치(0.20, ×0.40, ×2.2, 2.0초, ×0.5, 1.5초, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8), D01~D04, 입력 규칙, .ui·.map·몬스터 모델, 새 자원, 3단계, V11-F07은 바꾸지 않았다.
- 기준 버전: a921c76. 같은 방법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256, F06 절 manifest 54경로)으로 a921c76 커밋 트리를 재계산해 리뷰가 기록한 38e7aa22…0ba53과 일치함을 확인했다.
- 실제 연결: 시작 시 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록; 구조 파일 무변경). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 파일로 저장해 시각·`[VRF9*]` 표지로 걸러 읽었다.
- 미커밋 Maker 재저장 3파일(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델)은 되돌리거나 건드리지 않았다. MonsterAttackPatternData.userdataset은 CSV 변경·Refresh·Play·Stop 뒤에도 Maker가 바꾸지 않았다(SHA-256 59bba898…e888 그대로, git status에도 안 뜸).

### 변경 파일 (6개, .codeblock·.directory·.userdataset·모델·맵·.ui 변경 없음)
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/@Assist/DataSet/MonsterAttackPatternData.csv | 9행을 4행으로 교체하고 마지막에 `AreaTarget` 열 추가(BOM·CRLF 유지). parry.left(LEFT·PARRY·2~3·Weight 2·FIXED), parry.right(RIGHT·PARRY·1~2·Weight 2·FIXED), parry.any(ANY·PARRY·0/0·Weight 2·NEAREST), special.random(ANY·SPECIAL·0/0·Weight 1·RANDOM). modelId castleenemy·AreaPaddingX 0.5·AreaHeight 1·AreaOffsetY 0.4·TelegraphLeadSec 0.5는 기존 값. normal.* 3행·special.left·special.right·special.any 제거 |
| RootDesk/MyDesk/Combat/CombatRuleCatalog.mlua | 필수 열에 AreaTarget 추가(열 누락은 기존 ReadRows 규칙으로 전체 거부). ValidateRows에 AreaTarget 검증: FIXED·NEAREST·RANDOM 외(빈 값·알 수 없는 값·누락) 거부, ANY↔FIXED·ANY가 아닌 유형↔NEAREST/RANDOM 불일치 거부. 방식과 맞지 않는 앵커는 기존 검사(ANY는 0/0만, 그 밖은 1~3 정수·From≤To)로 거부. 기존 SPECIAL+GUARD·Weight 양수·TelegraphLeadSec 검사 유지 |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | 공통 층에 `SelectRandomCell(unit)`(0 이상 1 미만 → max(1,min(3,floor(unit×3)+1))) 추가. PrepareAttack의 ANY 분기가 `AreaTarget == "RANDOM"`이면 `SelectRandomCell(math.random())`으로, 아니면 기존 FindNearestCell로 고정 칸을 정한다. 고정 칸·영역·cells·유효 방향은 기존대로 실행 스냅샷에 한 번 고정(예고 중 재선택 없음). modelId 분기·주황버섯 전용 규칙 없음 |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | EvaluateDefense의 가드 분기에서 SPECIAL이면 `{ kind = "UNGUARDABLE", rate = 1, success = false }`를 반환(F11). 피해는 원래대로 |
| RootDesk/MyDesk/UI/CombatInputController.mlua | UNGUARDABLE의 HUD 문구 "가드 불가"(색 1, 0.43, 0.36, 기존 1초 규칙) 추가. 다른 문구·색·지속 무변경, .ui 무변경 |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | ApplyDamage 사망 확정 경로에서 기존 MonsterAttackMotion.SetVisualClip("die")를 재사용해 서버 표시 클립을 die로 고정(REV-F02). 공통 층이라 OrangeMushroomAttack에는 넣지 않았다. 사망 뒤 늦은 stand 쓰기 경로(공격 취소·점프 완료·슬로우 복원·그로기 종료)는 기존 가드(IsDead 조건·CancelPendingAttack·DEAD 잠금)로 막혀 있음을 소스와 시험으로 확인해 추가 차단은 하지 않았다 |
- RecordDefense의 EVADE 대체 규칙은 그대로다. 결과 종류를 읽는 곳(ResolveAttack의 JUST·PARRY 분기, Monster_Attack의 PARRY 분기, RecordDefense, HUD)을 grep으로 확인했고 UNGUARDABLE이 어느 분기에도 걸리지 않는다(슬로우·반격 권한·그로기 없음).

### 실제 기본 검증 (Play 1회, Maker MCP + 서버/클라이언트 프로브. 시험 설정은 Play 내부에만 두고 Stop으로 정리)
- 빌드: Refresh 뒤 build 로그 81건 전부 Info(LIA 동적 참조 노이즈), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음.
- 로드(V09): `[VRF] CombatCore catalog ready rules=1 patterns=4`, 4행 id·유형·속성·앵커·Weight 2·2·2·1·AreaTarget FIXED·FIXED·NEAREST·RANDOM이 Refresh 뒤 런타임에서 읽힘. normal.*·2칸 특수 행 없음.
- 검증(ValidateRows 프로브, 실제 DataSet 행을 복사해 한 항목씩 변경, 같은 입력 두 번 호출): baseline ok/ok. 빈 값·알 수 없는 값(BOGUS)·필드 누락(nil)·ANY+FIXED·LEFT+NEAREST·RIGHT+RANDOM·RANDOM 앵커 1/1·NEAREST 앵커 0/2·FIXED 앵커 0/0·FIXED 앵커 3/2·SPECIAL+GUARD·Weight 0·Weight abc가 전부 REJECT/REJECT이며 경고는 항목마다 정확히 1건(두 번째 호출은 경고 없음, 경고 13건 = 거부 13항목). 열 누락: 실제 DataSet에 없는 열 이름을 요구한 ReadRows가 nil(전체 거부). CSV 파일 자체를 시험용으로 바꾸는 열 누락 시험(Stop·Refresh·재Play)은 하지 않았다(NOT_RUN).
- 패턴 선택(합 7): 경계 난수 0→parry.left, 1.999/7→parry.left, 2/7→parry.right, 2.001/7→parry.right, 3.999/7→parry.right, 4.001/7→parry.any, 5.999/7→parry.any, 6/7→special.random, 6.001/7→special.random, 0.9999999999→special.random. 누적 구간 [0,2)·[2,4)·[4,6)·[6,7)와 CSV 행 순서, 4행 모두 선택 가능.
- RANDOM 칸: SelectRandomCell 단위 0·0.3·0.3333→1, 1/3·0.34·0.6666→2, 2/3·0.67·0.9999999999→3. PrepareAttack를 플레이어 Pos2(x=0.0)에서 90회 호출한 분포 Pos1 32·Pos2 31·Pos3 27(위치 무관). 난수 고정(math.random 임시 교체, 시험 뒤 복원) 0.1/0.5/0.9: 칸 1→영역 -2.0~-1.0·cells 100·방향 R, 칸 2→-0.5~0.5·010·LR, 칸 3→1.0~2.0·001·L, 예고 TelegraphAttribute SPECIAL·cells 동기. 제품 경로에서도 special.random이 target 3(방향 L)로 선택된 예고가 1건 관측됨. 예고 중 영역·칸은 스냅샷 고정(PrepareAttack 한 번뿐). NEAREST 회귀: 플레이어 x=0에서 칸 2, FindNearestCell -1.4→1, ±0.75·±0.7→2, 1.4→3(F06과 같음).
- F10 판정(special.random, 제품 ATTACK 경로, 난수 고정, 시험 설정은 Play 내부): (플레이어 Pos2) 칸 2 무가드 kind HIT·rate 1·nativeHit true·HP 12 감소=HitEvent 12·HUD HIT. 칸 1(범위 밖) 무가드 nativeHit nil·HP 0·HUD EVADE. (실제 DownArrow 홀드, 플레이어 GUARD 상태) 칸 2 가드 kind UNGUARDABLE·rate 1·nativeHit true·HP 12=HitEvent 12·HUD UNGUARDABLE, 칸 1 가드(범위 밖) kind UNGUARDABLE이나 nativeHit nil·HP 0·HUD EVADE. 시험 데이터 근거로 NORMAL 속성 test.normal 행(칸 2)·가드: kind GUARD·rate 0.4·HP 4=HitEvent 4(12×0.4=4.8→4)·HUD GUARD. 패링·저스트 방향 판정 규칙은 이번 변경이 건드리지 않았고(validDirs 로직 무변경) 이번 회차에 다시 시험하지 않았다(NOT_RUN: RANDOM 저스트·패링 불성공 키 입력).
- F11 HUD(클라이언트 defenseText 폴링): 가드 홀드 중 UNGUARDABLE 판정 때 defenseText.Text가 "가드 불가"(색 1.00, 0.43, 0.36)로 바뀌고 약 1.0초(264.56→265.55) 뒤 비워짐. 무가드 피격은 "피격", [VRF] defense kind=UNGUARDABLE·HUD feedback=UNGUARDABLE 로그로 구분. 가드·회피 문구는 기존대로(시험 행에서 feedback GUARD 확인).
- REV-F02(서버 SpriteRUID 시계열 + 소유 클라이언트 SpriteRUID·상태 시계열, 각 시나리오마다 새 몬스터 DoSpawn 뒤 ApplyDamage(999)로 사망): 사망 시점(+0.0)부터 +0.2·+1.2·+2.5초까지 서버 SpriteRUID=ActionSheet die, 상태 DEAD, IsDead true, HP 0. 소유 클라이언트도 상태 DEAD와 같은 시각에 SpriteRUID die. 경로: 그로기 중(S7, STUN·hit에서 die), 슬로우 PlayRate 0.5+ATTACK 점프 중(S6, 사망 때 PlayRate 1.0 복원, die 유지), HIT 상태(S5), ATTACK 복귀 구간(S4, 판정 직후 점프 중), ATTACK 점프 중간(S3), ATTACK 시작 직후(S2), IDLE(S1). 공중 사망은 몸이 y만 0.58까지 떨어지고 x는 고정, 사망 뒤 stand·jump·hit로 덮인 시점은 없음. S1은 사망 뒤 서버 일시정지(SetServerPaused) 시험을 했으나 컨트롤러가 약 1초 안에 paused를 false로 되돌려 팝업 정지 1초 이상 유지는 확인하지 못했고(paused-on 스냅샷 true 동안은 die 유지) 실제 UIPopup 열기·닫기 경로는 NOT_RUN. 스크린샷 1장(그로기 몬스터 사망 뒤)에서도 몬스터가 눌린 die 프레임으로 보임(육안 평가는 사용자 몫). Stop 뒤 재Play에서의 stand 시작은 이번에 재측정하지 않았다(NOT_RUN, 모델 무변경).
- H1(끝 칸 홀드 특수 피격, 참고 관찰): 실제 LeftArrow 홀드로 Pos1 유지(x=-1.50, 콜라이더 오프셋 0·폭 0.5), special.random 대상 Pos1(영역 -2.0~-1.0)을 난수 고정으로 두 번 연속 실행: 두 번 모두 홀드 유지 상태(MOVE)에서 nativeHit true·kind HIT·HP 12=HitEvent 12(규칙상 정상). 중간에 홀드를 떼 중앙으로 복귀하는 경우는 키 해제 타이밍이 두 번째 공격 이후라 관찰하지 못했다. RightArrow·Pos3 대칭, parry.any 끝 칸 대표는 하지 않았다. 나머지 H1은 tester 몫이다.
- 정리·로그: Play 안에서 만든 시험 스크립트 타이머(클라이언트 상태 폴링)가 Stop 때 `LEA-3051 MemoryLeak(MakerScript)` 1건을 냈다(시험 스크립트가 원인, 제품 오류 아님). 그 밖의 runtime 오류·경고는 없었다(경고는 ValidateRows 프로브가 일부러 만든 CombatRuleCatalog 13건뿐). 마지막 maker_stop 성공, 시험값(AttackInterval 9999, math.random·패턴 목록 임시 교체, 플레이어 HP 보충, 서버 일시정지)은 Play 내부에만 있었고 복원 로그를 확인했다.

### 최종 제품 버전 묶음 (REV-F02·V11-F10·V11-F11)
- F06 절 manifest의 54경로 그대로(경로 수 변경 없음), 같은 계산법(경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256). a921c76 커밋 트리를 먼저 재계산해 38e7aa22e05a0a71cc90ca6680278f4352315788cedbfabc7256e4d44dd0ba53 일치를 확인한 뒤 작업 트리를 계산했다.
- Bundle SHA-256(작업 트리): fdca556d1e14533c143c6a07e40b3971b5ebfa8d4e885bded1fb24be2940ee80. a921c76 대비 변경된 경로는 9개로, 이번 변경 6개와 Maker 재저장 3개(이번에 수정하지 않음)다.
- 변경 경로 SHA-256: MonsterAttackPatternData.csv 809d1bdfa2f1ba143cc702ee5a2aac93f3441260b37e950be5a57a7c95733f45 · Combat/CombatRuleCatalog.mlua a1a1cb32438843dfb24cbbd5dcc0a3f81782cad6ebe629c11151e8220b444e0b · Monster/MonsterAttackComponent.mlua b0053ff01366f971254ab034c0e3dd94275790363f955a0e049eefa0ab72c780 · Monster/MonsterHealthComponent.mlua e3d28e7321257aad7077acfc7559181d1e4b17f844be536fe2bf54f787f1c013 · Player/PlayerHealthComponent.mlua 2939d7f8144afbfea463b979da926be8e2ec8b722244f67e0a16928fb9560481 · UI/CombatInputController.mlua a062fed645e021e7b22fb967c9ec7b1ce1c6173123e4b7644274a233b728a10a · (Maker 재저장, 이번 변경 아님) 주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 45경로 해시는 이전 묶음(a921c76) 값과 같다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 보라 중심 구성과 특수 1칸 무작위의 난이도·구별, 범위 밖에서 시작한 저스트 인정 체감, "가드 불가" 문구의 눈에 보이는 느낌, HP 0 뒤 die 유지의 육안.
- NOT_RUN: 실제 UIPopup 열기·닫기 중 사망 뒤 die 유지(서버 일시정지는 1초 미만 유지), Stop 뒤 재Play에서 stand 시작 재측정, RANDOM 저스트·↓ 패링 불성공의 실제 키 입력과 반격 권한·슬로우, CSV 파일을 바꿔 열 누락을 일으키는 시험, 끝 칸 홀드를 떼 중앙으로 복귀하는 H1 경우·RightArrow/Pos3·parry.any 끝 칸(tester), V12 외부 환경, 사람 손 0.20초 타이밍, 실기기·터치, 플레이어 사망·실제 맵 전환.
- 판단 메모: 사망 경로의 die 고정은 서버 표시 클립 쓰기가 전부다. 사망 뒤 서버가 stand를 쓰는 경로는 소스상(IsCurrent·CancelMotion·DEAD 잠금·SetStunned 조건)과 시험(7개 경로)에서 확인되지 않았다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map=map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인. Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) REV-F02: 7경로 사망 뒤 서버·클라이언트 SpriteRUID가 die로 유지되는지(실제 표시는 스크린샷 픽셀도 병행, 실제 UIPopup 열고 닫기·Stop 뒤 재Play 포함). (2) F10: 4행 로드, 경계 난수의 누적 구간·칸, RANDOM 저스트(범위 안·밖 출발)·반격·슬로우와 고정 칸 쪽 방향·중앙 복귀·↓ 패링 불성공, 예고 뒤 이동에도 영역 불변, parry.any 회귀(Pos1·Pos2·Pos3), parry.left·right 2칸 중간 착지·F02 복귀 후 그로기·F08 그로기 hit, NORMAL·GUARD 유형은 시험 데이터 근거. (3) F11: 가드 홀드 중 special.random 범위 안 "가드 불가"·원래 피해, 범위 밖 "회피", 무가드 "피격", 일반 가드 "가드 · 피해 경감"·40%. (4) H1: 끝 칸 홀드 유지·해제(예고 중 서로 다른 두 시점 이상) 정밀 확인과 RightArrow·Pos3, parry.any 끝 칸. 주의: maker_clear_logs를 호출하지 말고 큰 로그는 파일로 저장한 뒤 시각·표지로 거를 것. 시험 스크립트가 만든 타이머는 Stop 때 LEA-3051을 낼 수 있으니 ClearTimer로 정리할 것.

## 2026-11-04 coder V11-F12·V11-F13 구현·기본 검증 인계 (회차 A)

### 범위·연결
- 담당: Claude Code msw-coder(독립 실행). 승인 범위는 Plan §19 회차 A의 CombatCore-V11-F12(몬스터 die 1회 재생 뒤 마지막 프레임 정지)·V11-F13(JUST·PARRY 성공에 입력 시작 위치 Pos2 칸 ±0.75와 공격 영역의 Pos2 포함 조건 추가)뿐이다. 수치(JustWindowSec 0.20, GuardDamageRate 0.40, 반격 2.0초·×2.2, 슬로우 2.0초·×0.5, 그로기 1.5초, AttackDamage 12, AttackInterval 3.0, JumpDuration 0.5·JumpHeight 0.8, 패턴 4행·Weight·영역·패딩·선행 시간, 이동·복귀 속도 6), CSV·DataSet, D01~D04, 입력 규칙, LEFT/RIGHT/ANY 영역·대상 칸 방식·ANY 탈출 검증, 몬스터 모델·.ui·.map, 새 RUID·자원, 회차 B(플레이어 기본 능력치·V11-F07), §18 머쉬맘 전환, fade·스테이지 전환(4단계), 3단계는 바꾸지 않았다.
- 기준 버전: 커밋 5c4eda3. 같은 방법(54경로 manifest, 경로 ASCII 정렬, 경로 + TAB + sha256 + LF 연결의 SHA-256)으로 5c4eda3 커밋 트리를 재계산해 리뷰 기록 9208e0aa…da79와 일치함을 확인했다. 시작 시 작업 트리는 5c4eda3 + Maker 재저장 미커밋 3파일(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번 변경 아님·되돌리지 않음)뿐이었고 그 밖의 예상 못한 제품 변경은 없었다.
- 실제 연결: 시작 시 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit, maker_get_world_info worldId=970621b29ba945369d3dc8e90c301186. 맵 TileMapMode=0(MapleTile, 앞 회차 기록, 구조 파일을 바꾸지 않아 다시 읽지 않았다). **maker_clear_logs는 호출하지 않았다.** 큰 로그는 파일로 저장돼 시각·`[VRF…]` 표지로 걸러 읽었다.

### V11-F12 — 현재 재생 실측(수정 전, 5c4eda3 그대로)
- 방법: 서버 프로브(상태·SpriteRUID·PlayRate·Start/EndFrameIndex)와 소유 클라이언트 프로브(몬스터 엔티티의 SpriteAnimPlayerChangeFrameEvent 프레임 번호 + 같은 ServerElapsedSeconds 시계)를 같은 시간축에 기록했다. IDLE 몬스터에 ApplyDamage(999) 뒤 die 클립(ActionSheet die=65a2bf…, 프레임 3장, 지연 0.18·0.18·0.30초, 합 0.66초)이 프레임 0→1→2→0→1→2…로 약 0.66초 주기로 **끝없이 반복**됨을 확인했다(사망 뒤 약 47초 관측, 서버 SpriteRUID=die·상태 DEAD 유지). 사용자 보고와 일치한다. 서버가 쓴 SpriteRUID 값은 클라이언트에 같은 시각(시차 0.00초)에 반영되고 클라이언트 프레임 0이 곧바로 시작됐다.

### V11-F12 — 구현 방식과 이유
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Monster/MonsterAttackMotion.mlua | 공통 사망 표시 층. `SetVisualClip`이 (a) 사망 표시가 시작된 뒤(`_T.dieStarted`)에는 모든 키를 무시해 어떤 늦은 경로도 클립을 바꾸거나 die를 다시 시작하지 못하게 하고, (b) 키가 "die"이면 새 `PlayDieOnce()`로 간다. `PlayDieOnce()`는 die RUID의 AnimationClip을 `_ResourceService:LoadAnimationClipAndWait`로 읽어 프레임 수·지연 합·PlayRate로 "마지막 프레임 시작까지의 시간(=(합-마지막 지연)/재생 배율)"을 맵 전투 시계(CombatPauseComponent.GetCombatTime) 기준 기한으로 기록하고, StartFrameIndex=0·EndFrameIndex=2147483647로 정리한 뒤 SpriteRUID=die를 쓴다. `TickDie()`가 기한이 되면 StartFrameIndex=EndFrameIndex=마지막 프레임 번호로 쓴다(마지막 프레임 고정). 클립을 읽지 못하면(프레임 0) 종전처럼 die RUID만 쓴다(`[VRF] MonsterDie start without freeze`). |
| RootDesk/MyDesk/Monster/MonsterHealthComponent.mlua | `OnUpdate`를 추가해 사망 후 `MonsterAttackMotion:TickDie()`만 호출(OrangeMushroomAttack.OnUpdate는 `__base`를 부르지 않아 거기에는 둘 수 없었다). 사망 확정 경로의 기존 `SetVisualClip("die")` 호출은 그대로(주석만 수정). |
- 고른 이유: 렌더러 PlayRate 0 방식은 슬로우 PlayRate 복원(`ClearCombatEffects`)과 순서가 엇갈리고 정지 프레임이 부정확하다. Start/EndFrameIndex 방식은 PlayRate와 무관하다. 기한은 서버 `_TimerService`가 아니라 **맵 전투 시계**로 재서 팝업 정지(클라이언트 SetClientTimeScale 0 + 서버 전투 시계 정지) 동안 남은 재생이 보존된다. "마지막 프레임 시작 시점"에 고정해 서버 쓰기가 클라이언트에 도착하기 전에 한 바퀴가 끝나 프레임 0으로 돌아가는 위험(여유 0.30초)을 없앴다. 새 Sync·RUID·모델·DataSet·자원 변경 없음(die 클립 반복 메타데이터도 그대로).
- 서버에서 쓴 렌더러 값이 클라이언트에 보이는지: 위 클라이언트 프레임 이벤트가 서버 쓰기 직후 frame 0(0.00초)·1(0.18~0.19초)·2(0.34~0.38초)를 순서대로 냈고 그 뒤 프레임 이벤트가 없었다. 클라이언트 렌더러 값 SpriteRUID=die·StartFrameIndex/EndFrameIndex=2/2를 시계열 끝에서 직접 읽어 확인했다(`SE=2/2`).

### V11-F12 — 수정 뒤 확인 (Play 1회 연속, 서버·클라이언트 동시 기록)
| 사망 경로(각 시나리오마다 DoSpawn으로 새 상대) | 서버 SpriteRUID/Start/End/상태 | 소유 클라이언트 die 프레임 이벤트(사망 시점 기준 초) |
| --- | --- | --- |
| S1 IDLE | 사망 +0.2 die 0/MAX → +0.6 이후 2/2 고정 → +4.0 2/2 | 0@0.00 1@0.19 2@0.38, 이후 이벤트 0건(정지) |
| S2 ATTACK 시작 직후 | 같음, pre=jump | 0@0.00 1@0.19 2@0.34, 이후 0건 |
| S3 ATTACK 점프 중 | 같음 | 0@0.00 1@0.18 2@0.36, 이후 0건 |
| S4 ATTACK 착지 대기(예고 3초) | 같음, pre=stand | 0@0.00 1@0.19 2@0.36, 이후 0건 |
| S5 ATTACK 복귀 중 | 같음 | 0@0.00 1@0.19 2@0.36, 이후 0건 |
| S6 HIT | 같음, pre=state HIT | 0@0.00 1@0.19 2@0.37, 이후 0건 |
| S7 슬로우 중(PlayRate 0.5) | pre rate=0.5 → 사망 때 1.0 복원 후 die 한 번 | 0@0.00 1@0.19 2@0.36, 이후 0건(frame 0 이벤트가 한 번 더 온 기록이 있으나 재생은 한 번) |
| S8 그로기(STUN) 중 | pre=stun hit RUID → die | 0@0.00 1@0.19 2@0.37, 이후 0건 |
- 서버 `[VRF] MonsterDie start frames=3 total=0.660 freezeAfter=0.360`, 이어 `MonsterDie freeze frame=2`(시계 차 0.36~0.37초). 모든 경로에서 상태 DEAD·HP 0·IsDead true, die 아닌 클립으로의 변경 0건(`nonDieAfter=0`), 정지 뒤 프레임 이벤트(1초 뒤) 0건.
- 팝업(실제 UIPopup 코드 경로, `_UIPopup:Open`/`OnClickCancel`): (1) die 재생 도중 열고 닫기 — 사망 후 약 0.07초에 서버 일시정지(전투 시계 127.994에서 정지), 1.8초 열어 둔 뒤 닫자 클라이언트 프레임이 1@2.15 2@2.32로 **이어서** 재생(처음부터 다시 시작 없음)되고 서버는 전투 시계 128.303(남은 0.31초 경과)에 고정. (2) 정지 뒤(고정 후) 열고 닫기 — 서버 paused true→false, 프레임 이벤트·SpriteRUID 변화 없음. 정지 중 서버 Start/End는 0/MAX로 유지돼 일시정지 동안 기한이 흐르지 않음.
- 화면: 정지 뒤 서로 다른 시점의 maker_screenshot(558×314) 몬스터 영역(320,165,420,225) 픽셀 차이 — 13:58:59·13:59:05 두 장(6초 간격)·13:59:59(팝업 닫은 뒤)·14:00:14(정지 뒤 팝업 열고 닫은 뒤, 다른 몬스터 개체)가 모두 평균 차이 0.000·최대 0(완전 동일). 같은 영역을 새 살아 있는 몬스터(stand) 화면(14:01:09)과 비교하면 평균 32.4·최대 255(다른 화면). 눌린 die 마지막 프레임이 정지해 있음을 화면에서 읽었다. 재생 중 화면은 팝업이 몬스터를 가려 캡처하지 못했고 재생 중은 클라이언트 프레임 이벤트(0→1→2)로 대신했다(육안 평가는 사용자 몫).
- 늦은 경로: 그로기 종료 `SetVisualClip("die")` 재호출·`SetStunned(false)`(사망 경로 S8)·슬로우 PlayRate 복원(S7)·공격 취소·점프 완료·복귀 완료(S2~S5의 `CancelPendingAttack`·`CancelMotion`)·HIT 복귀(S6)가 정지를 풀거나 재생을 다시 시작하지 않았다(`SetVisualClip` 가드 + 시계열 0건).
- 회귀: 살아 있는 몬스터의 stand·jump·그로기 hit 클립은 사망 전 값 그대로(pre 열: stand 96e955·jump 94bbe2·hit/stun aec950). Stop 뒤 재Play에서 첫 몬스터는 stand를 0↔1 프레임으로 정상 반복 재생하고 Start/End=0/2147483647(정지 설정 잔존 없음). DeadEvent 1회, HP 70=100−HitEvent 합 30(수동 공격 실제 ↑ 두 번, V02 대표), 사망 뒤 예고 칸 비어 있음, 추가 피해·공격 없음.

### V11-F13 — 구현
| 파일 | 변경 |
| --- | --- |
| RootDesk/MyDesk/Player/PlayerEvadeComponent.mlua · PlayerGuardComponent.mlua | 서버 상태 진입(SetEvading(true)/SetGuarding(true))에서 시작 시각을 기록하는 같은 지점에 **그 순간 서버가 보는 플레이어 WorldPosition.x**를 `_T.evadeStartX`/`_T.guardStartX`로 함께 기록(`[VRF] PlayerEvade/PlayerGuard start x=… t=…`). `ClearStart()`(시각 −1·위치 nil)과 `GetStartX()`를 추가하고 OnMapLeave의 시각 삭제를 `ClearStart()`로 바꿨다. 클라이언트가 보낸 위치·성공 값은 쓰지 않는다. |
| RootDesk/MyDesk/Combat/CombatPauseComponent.mlua · Player/PlayerHealthComponent.mlua | 팝업 닫기(RequestPopupPause 해제)와 플레이어 사망(HandleStateChangeEvent DEAD)의 시각 −1 삭제 두 곳씩을 `ClearStart()` 호출로 교체(위치 기록도 함께 폐기). |
| RootDesk/MyDesk/Monster/MonsterAttackComponent.mlua | PrepareAttack이 실행 스냅샷에 `pos2Cell = { minX=(앵커1+앵커2)/2, maxX=(앵커2+앵커3)/2, areaIncludes = (앵커2 x ∈ [영역 minX, maxX]) }`를 한 번 고정(Pos2 칸 경계 = 앵커 중점, 지금 간격 1.5에서 ±0.75, 새 DataSet 열 없음). ResolveAttack이 이를 EvaluateDefense 6번째 인자로 넘긴다(호출자는 ResolveAttack 하나, grep 확인). 영역·유효 방향·ANY 탈출 검증은 그대로. |
| RootDesk/MyDesk/Player/PlayerHealthComponent.mlua | `IsStartInPos2Cell(startX, pos2Cell)`(기록 없음 → 불성립, 경계 포함 ±1e-6 허용)을 추가. EvaluateDefense는 JUST와 PARRY 성공에 기존 조건(창·방향·속성·가드 홀드)과 **그리고** (a) 시작 위치가 Pos2 칸 안, (b) 스냅샷 영역이 Pos2 앵커 포함을 요구한다. 불성립이면 성공만 빠지고 가드 경감(GUARD ×0.40)·가드 불가(UNGUARDABLE)·영역 밖 0(RecordDefense "회피")·영역 안 원래 피해(HIT)는 그대로. 판정 로그 `[VRF] PlayerHealth guard/evade eval x=… cellOk=… areaOk=…`. 새 결과 종류·문구·.ui 변경 없음(CombatInputController 무변경). |

### V11-F13 — 확인 (Play 내부, 서버 프로브 + 실제 키 입력)
- 방법: 패턴 단일 행 교체(Play 내부 `_CombatRuleCatalog.patterns`, 예고 3초/60초)와 math.random 임시 교체(RANDOM 칸), 시작 시각·위치·방향 강제("프로브 근거")로 제품 ATTACK 경로(PrepareAttack→ResolveAttack→EvaluateDefense→네이티브 AttackFast→CalcDamage)를 돌렸다. 판정 시각 직전 0.05초에 시작을 기록하고(창 0.20 안) 판정을 앞당겨 실행. 가드는 **실제 DownArrow 키 홀드**(서버 GUARD 상태·isGuarding true)에서 시작 위치·시각만 덮어썼다. 결과는 feedback 문자열(RecordDefense), HP 변화, 반격 권한, 슬로우, 패링 뒤 그로기 예약(`groggyAfterReturn`)으로 확인했다.
- E 단계(회피, 플레이어 Pos2 x=0, 17건, 전부 기대와 일치):
  - E01 parry.left·E02 parry.right·E03/E04 parry.any(Pos2 조준, 좌·우 양방향)·E05 special.random 칸 2(좌) → JUST·피해 0·반격 권한 true·슬로우 true.
  - E06 special.random 칸 1(영역 −2.0~−1.0, 유효 방향 R)·E07 칸 3(영역 1.0~2.0, 유효 방향 L)·E17 패링 속성 1칸 칸 1 → JUST 아님, 영역 밖이라 네이티브 피격 없음 → "EVADE" 피해 0·반격 없음·슬로우 없음(QA5 K3b·QA7 E1 계열 기대가 JUST에서 바뀜).
  - E08 x=+0.75·E09 x=−0.75(경계 포함) → JUST. E10 x=+0.76·E11 −0.76·E12 +0.80·E13 −0.80 → JUST 아님, 영역 안이라 HIT·피해 12. E14 틀린 방향 HIT 12(기존). E15 창보다 일찍 시작(0.6초 전) HIT 12(기존). E16 시작 위치 기록 없음 → HIT 12.
- G 단계(가드, 실제 DownArrow 홀드, 15건, 전부 일치): G01 parry.left·G02 parry.right·G03 parry.any·G05 패링 속성 1칸 칸 2 → PARRY·피해 0·그로기 예약 true·반격 true. G04 패링 속성 1칸 칸 1(영역이 Pos2 불포함) → PARRY 아님, 영역 밖이라 "EVADE"·그로기 없음. G06 x=+0.80·G07 −0.80·G09 +0.76 → GUARD, 피해 12×0.40=4.8→4(그로기·반격 없음). G08 x=+0.75 PARRY(경계 포함). G10 special.random 칸 2 → UNGUARDABLE·원래 피해 12. 시험 데이터 근거(GUARD 유형 3칸, Pos2 포함): G11 NORMAL → GUARD 4, G12 PARRY 속성 → PARRY, G13 같은 행 x=+0.80 → GUARD 4. G14 가드 시작 0.5초 전(창 밖) → GUARD 4(기존). G15 시작 위치 기록 없음 → GUARD 4.
- 실제 키 입력(K, 판정 시각 앞당김, 창 0.20은 시험값 30초로 넓힘 — 입력 시각을 못 맞춰서): K1 parry.left + LeftArrow 탭 → JUST·피해 0·반격·슬로우. K2 parry.right + RightArrow 탭 → JUST. K4 parry.left + LeftArrow(2번째) → JUST. K5 parry.right + RightArrow(2번째) → JUST. K3 special.random 칸 1(영역 Pos1) + LeftArrow 홀드(플레이어 Pos1에서 판정, 시작 때 x=0) → `areaOk=false`로 JUST 아님, 영역 안이라 HIT·피해 12("끝 칸 쪽 회피 → HIT"; H1 겹침 =HIT). DownArrow 홀드는 G 단계 전체가 실제 키.
- **위치 정확도(서버 시작 기록 x 대 클라이언트 segment.startX)**: LeftArrow/RightArrow 실제 키 입력 5건(K1·K2·K3·K4·K5) 모두 클라이언트 `MovementInput phase=OUTBOUND … x=0.0`, 서버 `PlayerEvade start x=0.000`으로 **차이 0.000**이다. 서버 기록 시각은 클라이언트 시작 시계보다 0.085~0.095초 늦었지만 그 시점 서버가 본 위치는 아직 0.000이어서 Pos2 칸(±0.75, 속도 6에서 약 0.125초) 안이었다. 정상 입력이 위치 때문에 거부된 사례 0건(DownArrow 실제 입력도 `PlayerGuard start x=0.000`). 한계: 입력 지연이 0.125초를 넘으면 서버 기록 위치가 칸을 벗어날 수 있으나 이번 시료에는 없었다(5건, 단일 접속 Maker 환경).
- 위치 기록 삭제: (1) 실제 UIPopup 열기→닫기 직전에 evade/guard 시작 x=0.5·시각을 심자 닫은 뒤 `evadeX=nil evadeT=-1.0 guardX=nil guardT=-1.0`. (2) 예고 중 팝업(예고 6초, 팝업 +1.0초부터 약 1.5초): 시작 기록 후 팝업 중 예고 남은 시간 5.71→4.50(정지 중 보존), 닫은 뒤 `evadeX=nil`, 이후 판정은 JUST가 아닌 HIT 12(이전 회피 시각 폐기 규칙 유지). (3) 플레이어 사망(서버 ChangeState DEAD): `evadeX=nil·guardX=nil`, 시각 −1. (4) Stop → 재Play: evade/guard x=nil·시각 −1.0·창 규칙 0.2/0.2(시험값 30초 복원)·패턴 4행·AttackInterval 기본.
- 회귀: 일반 가드 ×0.40(G11), 특수 가드 UNGUARDABLE 12(G10), 무가드 범위 안 HIT 12(E10~E16), 반격 소비·슬로우 대표(JUST 직후 실제 ↑ 한 번 → 반격 권한 소비, 10타 ×2.2 내림 2×10=20 vs 일반 10, 슬로우 true), HP=HitEvent 합 대표(위 30), 예고 중 팝업(위), Stop 뒤 다음 Play 기본값(위).

### 빌드·로그
- Refresh 뒤 build 로그 81건 전부 Info(LIA 1114/1115 동적 참조 노이즈, 앞 회차와 같은 유형), 오류 0·경고 0. 새 .mlua가 없어 .codeblock 변경 없음(git status에도 .codeblock·.directory·.userdataset 추가 변화 없음).
- Play 2회(통합 1회 약 6분 + Stop 뒤 재Play 1회). 마지막 Stop 정상. 두 Play 모든 로그가 Info 뿐이다(Warning·Error·LEA·LWA 0건). 시험 스크립트가 만든 반복 타이머는 Stop 전에 ClearTimer로 정리해 LEA-3051은 나오지 않았다.

### 프로브 오류와 제품 오류의 구분, 관찰
- 시험 문제: 팝업 감시 프로브의 첫 시도가 이전 사망 몬스터(IsDead)를 감지해 시나리오보다 먼저 팝업을 열었다(제품 오류 아님, 감시 대상을 새 몬스터로 바꿔 재시험). 그 첫 시도에서 우연히 "팝업 정지 중 사망·SpriteRUID 쓰기" 조합이 만들어졌는데 정지 중 서버 기한이 흐르지 않고 닫은 뒤 0.37초에 고정, 클라이언트 프레임은 1@0.00 2@0.19(첫 프레임 이벤트는 프로브 타이머가 정지돼 놓침) 순서로 한 번만 재생되고 고정됐다.
- 관찰(바꾸지 않음): (1) 새로 스폰한 직후 몬스터의 렌더러 Start/End가 0/0으로 읽힌 시점이 있었다(S1·S6 pre, 스폰 1초 이내, 다른 시나리오는 0/MAX). 사망 때 PlayDieOnce가 0/MAX로 정리하므로 영향 없고 stand 재생은 0↔1 정상이다. (2) 플레이어 HP가 시험 도중 큰 값(988)으로 읽혔다(기준 모델 값이 아니며 시험 스크립트가 MaxHp로 채움). (3) 슬로우(S7)에서 클라이언트 frame 0 이벤트가 두 번 온 기록이 있으나 재생은 한 번이다.

### 실패/미확인/미실시 (PASS로 세지 않음)
- 사용자 직접 평가(V11): 사망 뒤 die 1회 재생과 끝 모습 정지의 육안(그로기 중 처치·팝업 뒤 포함, 모바일), Pos2에서 가운데 칸 공격에서만 저스트·패링이 나는 체감과 끝 칸 1칸 공격(특수 무작위) 무보상 난이도. 사람 손의 0.20초 창 타이밍, 실기기·터치·모바일.
- 재생 중(0.36초) die 화면의 스크린샷 캡처(팝업이 가림, 프레임 이벤트로 대신), 파일 CSV 변경 반영, 실제 UIPopup 도중 플레이어 사망, 실제 다른 맵 전환, V12 외부 환경, 다중 접속 지연에서의 위치 기록 오차(시료 5건은 단일 접속).
- 시험값(창 30초, 패턴 단일 행 교체, 예고 3~60초, 판정 앞당김, 시작 시각·위치·방향 강제, math.random 임시 교체, 플레이어 HP 보충, 서버 직접 ChangeState)은 Play 내부에만 두었고 Stop·재Play로 기본값 복귀를 확인했다.

### 사용 종료·다음 담당
- 마지막 maker_stop 성공 뒤 maker_get_current_map = map01 / 0a0972ef-ad23-4e24-af63-afbd53120c1d / edit 확인(Stop 직후 한 번 "play"로 보였다가 다음 조회에서 edit, 전환 중이던 값). Maker 사용 종료. commit·push는 하지 않았다.
- tester가 확인할 것: (1) F12: 사망 경로(IDLE·ATTACK 예고·점프·착지 대기·복귀·HIT·슬로우·그로기)별로 서버 SpriteRUID/Start/End와 소유 클라이언트 프레임 이벤트·SpriteRUID 시계열, 정지 뒤 5초 이상 변화 없음, 서로 다른 세 시점 이상의 스크린샷 몬스터 영역 동일(재생 중과 다름), 실제 UIPopup 재생 도중·정지 뒤 열고 닫기, 늦은 경로(그로기 종료 die 재호출·슬로우 복원·공격 취소), Stop 뒤 재Play stand. (2) F13: parry.left/right·parry.any·special.random 강제 칸 1/2/3, 가드형 시험 데이터, 실제 Left/Right/DownArrow, 시작 위치 ±0.75/±0.76/±0.80 프로브, 위치 기록 삭제(팝업 닫기·플레이어 사망·Stop), 서버 기록 x와 클라이언트 segment.startX 차이 기록(이번 5건 0.000). 주의: maker_clear_logs를 호출하지 말고 큰 로그는 파일로 저장된 것을 `[VRF`·`VRF12`·`VRF13` 표지와 시각으로 거른다. 시험 스크립트의 반복 타이머는 ClearTimer로 정리하고, 기존 QA5 K3b·QA7 E1 계열 기대(JUST)는 JUST 아님으로 바뀌었다.

### 2026-11-04 최종 제품 버전 묶음 (V11-F12·F13)
- 54경로 manifest 그대로(경로 수 변경 없음), 같은 계산법(경로 ASCII 정렬 `LC_ALL=C sort`, 경로 + TAB + sha256 + LF 연결의 SHA-256). 5c4eda3 커밋 트리를 먼저 재계산해 9208e0aa066893298fe425d7c72f0e43d5fcc8c57b1553c1951f95c0a0e3da79 일치를 확인한 뒤 작업 트리를 계산했다.
- Bundle SHA-256(작업 트리): b321d71c506c993747785757c04677c5aef39058e06f17f61334cf48e3a4040f. 5c4eda3 대비 바뀐 manifest 경로는 10개로, 이번 변경 7개와 Maker 재저장 미커밋 3개(AssistModel.userdataset·AttackSkillData.userdataset·주황버섯 모델, 이번에 수정하지 않음, 직전 회차 작업 트리와 같은 값)다.
- 변경 경로 SHA-256: Combat/CombatPauseComponent.mlua 92e0b0800b9c71ecc377c720854599dbf406120ab51d8cdba29d3ce9e0c525dd · Monster/MonsterAttackComponent.mlua 5c6a7896bd04a1835de517522da49de187a3fb8e560b975f50a76877fd800fe0 · Monster/MonsterAttackMotion.mlua 349d3e8a699d58b2779c5a61adde812802135cbcbf8807bddab70c9351a24a0a · Monster/MonsterHealthComponent.mlua 38d5379fb523dda28cb60e4887ae30b2b88b6f6b8be99103e4ab52ab52936a00 · Player/PlayerEvadeComponent.mlua 679dc069fa8108d7839d61b8d748fbb037141b3e41a84e16b37cac1231753547 · Player/PlayerGuardComponent.mlua f8d0bd7052f8992630532b96ef30887a5227042978d62c3a5801bdb0102ace73 · Player/PlayerHealthComponent.mlua 9cf53db223aaaa130389c63e58b3a4854a8a1edeeb348e0abe570380e10883a2 · (Maker 재저장, 이번 변경 아님) 주황버섯 모델 d8f79eb5991229e9699edf7206725e767797b3630215c171278c08173e3eb732 · AssistModel.userdataset a933d30aa5042bac273f904dd56058ff506a4db62b8af33490dfa41bdc915665 · AttackSkillData.userdataset c6b692fdd73e8ed144b2b32255dc95fe531e9bfb7d09591f8672841c441aeedd. 나머지 45경로 해시는 이전 묶음(5c4eda3) 값과 같다.
