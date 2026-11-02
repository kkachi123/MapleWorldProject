# Pipeline — 실행 상태와 원본 연결

## 위치와 수명

한 번의 승인된 작업 실행은 .pipeline/{run-id}/run.md로 관리한다. run-id는 짧은 소문자·숫자·하이픈 조합으로 정하고 기존 실행 경로를 덮어쓰지 않는다. 재개는 같은 run을 사용하며 다른 작업은 새 ID를 사용한다. 단순 조회에는 새 run이 필요 없다.

이 폴더는 실행 제어용 임시 자료다. 기획은 [Plans](../Docs/ProjectSkill/Engineering/Plans/README.md), 상세 실행 근거는 [WorkRecords](../Docs/ProjectSkill/Engineering/WorkRecords/README.md), 현재 결과는 [Features](../Docs/ProjectSkill/Engineering/Features/README.md)에만 둔다. 같은 명세·결과를 네 개 파일로 중복 작성하지 않는다.

## run.md 양식

```markdown
# {run-id}

- 요청·승인: {사용자의 실제 요청과 허용 범위}
- 모드: {계획 / 구현·검증 / 검증 / 재검토}
- 상태: {현재 상태}
- 갱신: {시각·갱신 주체}
- 현재 담당: {planner / coder / tester / reviewer / 사용자 / 미배정}
- 다음 행동·대기 사유:
- 환경 가이드: {WAITING_ENV일 때만 Docs/ProjectSkill/EnvGuides의 건별 가이드 경로}

## 원본 연결
- Plan: {경로·요구/검증 ID·승인된 범위}
- Feature: {있을 때만}
- WorkRecord: {경로}
- 기획 결과: {Plan의 해당 절}
- 구현 결과: {WorkRecord 개발 절}
- 테스트 결과: {WorkRecord QA 절·대상 버전}
- 리뷰 결과: {WorkRecord 리뷰 절·대상 버전}

## 실행·인계
- 대상 버전: {커밋/지문/변경 묶음 식별·미기록이면 표시}
- 실행 주체: {역할·실제 에이전트/채팅 식별·독립 실행 여부}
- Maker: {마지막 실제 관찰 모드·담당·사용 종료/양도 여부}
- 전달·완료: {요청 / 전달됨 / 실행 중 / 결과 확인을 구분}
```

경로는 실제 파일이 생긴 뒤 연결한다. 없는 산출물을 완료 링크로 만들지 않는다. 역할별 결론·로그 전문을 이 파일에 복사하지 않는다.

## 상태

| 상태 | 의미·다음 조건 |
| --- | --- |
| PLANNING | 계획/승인 범위 정리 중 |
| READY_FOR_CODE | 필요한 결정과 구현 승인이 확인됨 |
| CODING | coder가 편집·기본 검증 중 |
| TESTING | 버전 고정 후 tester 확인 중 |
| REVIEWING | reviewer가 근거·범위를 대조 중 |
| REWORK | 승인 범위의 수정과 재검증 필요 |
| WAITING_USER | 사용자 규칙/범위/직접 평가 필요 |
| WAITING_ENV | 도구·Maker·기기 등 실행 환경 대기 |
| DONE | 해당 run의 필수 확인과 결과 정리 완료 |
| STOPPED | 범위 충돌·권한 등으로 실행 중단 |

상태는 실제 결과를 확인한 메인 조율 채팅이 갱신한다. 파일 존재만으로 다음 단계에 진입하지 않는다. 판정·버전이 불명확하면 해당 대기 사유를 남긴다.

기록은 파일 잠금·메시지 전달·에이전트 실행을 자동 수행하지 않는다. 완료 후 원본 이관·추적·링크 정리가 끝나면 해당 run 폴더만 정리한다. 진행 중/사용자 확인 대기 run은 유지한다. 이 README는 삭제하지 않는다.
