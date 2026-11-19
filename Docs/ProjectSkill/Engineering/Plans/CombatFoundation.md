# CombatFoundation — 전투 기반 후속 확인 계획

## 목표·상태

2026-10-19 기준 7건 중 F06은 AI 확인 완료, 나머지 6건은 미실시다(2026-11-19 기준: F06·F07 완료(F07은 사용자 결정, PC Maker 기준), F04 사용자 확인 대기, F01·F02·F03·F05 미실시). 종결된 리팩토링을 재개하는 계획이 아니다. [재개용 임시 기록](../WorkRecords/CombatFoundationWorkRecord.md)의 기존 계약을 참고하되 실제 확인 기준은 아래 표를 따른다.

승인 없는 배포·Maker 재시작·새 맵 생성·기획 기능 추가는 범위가 아니다. 과거 성능 개선율을 소급 산출하지 않는다.

## 남은 확인

| ID | 상태 | 실행 시점·확인 기준 |
| --- | --- | --- |
| CombatFoundation-F01 | 미실시 | 다음 본인 Maker 재시작·Refresh 때 DamageSkinSetting 중복 LWA-4013 재발 여부 확인. 재발 시 조사 항목 분리 |
| F02 | 미실시 | 본인 승인 배포 환경에서 Tuner 요청 거부·범위 불변·Gizmo 미실행 확인 |
| F03 | 미실시 | 4단계 실제 다른 맵/방 전환 마련 후 공격·복귀·홀드·팝업 중 전환. 이전 실행 정리, 새 맵 위치/Manager·HUD·Gizmo 재연결 확인. 훅 직접 호출로 대체하지 않음 |
| F04 | 본인 확인 대기 | PC·모바일에서 버튼 누름/해제·키/터치 혼합·팝업 차단/순서·채팅·화면 잘림·체감 확인 |
| F05 | 미실시 | 최적화 전후 같은 기기·장면·엔티티 수·구간·반복 횟수의 CPU/메모리 실측 비교. 전후 자료 없는 과거 성과 주장 금지 |
| F06 | AI 확인 완료 | 2026-10-19 실제 StateComponent 비활성 조건에서 진입·완료 실패와 복구 확인. 기존 CombatFoundation-V19, 짧은 근거는 [후속 확인용 임시 기록](../WorkRecords/CombatFoundationWorkRecord.md) |
| F07 | 완료(2026-11-19 사용자 결정, PC Maker 기준) | 2단계 최종 일반/가드/패링/회피/치명 HP·숫자·연출 일치 확인. 몬스터 DEFENSE 연결 시 해당 경감도 확인. **수치(AI)**: PASS(CombatCore-V02). QA1 FAIL(QA-F01, 치명 피해 숫자 불일치)을 수정한 뒤 QA2(2026-10-29)·QA3(2026-11-02)에서 일반·가드·저스트·패링·치명·보너스·DEFENSE 150의 HP 감소 = HitEvent 합 = 피해 숫자([2단계 Feature V02](../Features/2_CombatCore.md#반영-결과확인-범위), 상세 [WorkRecord QA 기록](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md#qa-기록)). **연출(사용자)**: 회차 C V11 8번(모바일·터치·사운드·CF-F07)에 "이상 없음"(2026-11-06), 회차 D·D2 PC 수락("점프음 확인 완료", 2026-11-16), 회차 E PC 수락("다른 건 다 좋음", Maker 26.11, 2026-11-19)([2단계 Feature 본인 결정](../Features/2_CombatCore.md#본인-결정플레이-피드백)). **결정**: 2026-11-19 사용자 "기존 수락으로 닫기"로 위 수락을 F07 실제 연출 평가(피해 숫자 가시성·피격·die 연출) 완료로 인정했다. **단서**: PC Maker 기준이다. 모바일·실기기 연출은 F07을 다시 열지 않고 [CombatCore-V11(모바일·실기기 부분)](CombatCore.md) NOT_RUN으로 추적한다 |

표의 F02~F07은 모두 CombatFoundation 접두사를 갖는 기존 추적 ID다. [이동 V08](../Features/1_MovementInput.md)은 2026-10-20 사용자 확인 완료지만, F04와 [정지 F02](CombatPause.md)의 전체 환경 결과를 대신하지 않는다. F04의 확인 대기와 나머지 미실시 상태, F06의 기존 완료는 유지한다. F07은 [2단계 CombatCore-V02](https://github.com/kkachi123/MapleWorldProject/blob/5efe005d4bd5bf45453e52f6ff692780b3b63135/Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md)에서 같은 버전의 실제 근거를 확보한 뒤 갱신한다. → 2026-11-19 2단계 완료 정리에서 근거를 붙여 사용자 확인 대기로 바꿨고, 같은 날 사용자 "기존 수락으로 닫기"로 F07을 완료했다(PC Maker 기준, 결과 요약 [2단계 Feature](../Features/2_CombatCore.md), 모바일 추적 [2단계 후속 계획](CombatCore.md)). 2단계 완료 결정은 모바일·다중 환경을 하지 않은 채 내려졌으므로 F04의 확인 대기도 그대로다. F07 완료는 F04·[정지 F02](CombatPause.md)의 PC·모바일 전체 확인을 대신하지 않는다.

## 진행·종료

AI 실행 내역은 위 임시 기록에 이어서 작성하고 본인 관찰은 직접 답변만 남긴다. 완료 결과는 관련 단계의 Features에 짧게 반영한다. 후속 확인 계획 자체를 별도 영구 기능 문서로 만들지 않는다.

미완료 항목은 유지한다. 모두 확인하거나 사용자 승인으로 처리한 뒤 결과·링크를 정리하고 계획·임시 기록을 삭제한다.
