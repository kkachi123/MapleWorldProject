# Claude Code — 프로젝트 실행 준비

- 설정 확인일: 2026-11-02. 설정 당시 게임 개발은 사용자 요청으로 일시정지 중이었고 이 설정 작업은 재개 승인이 아니었다. 같은 날 사용자가 일시정지 해제·REV-F01 수정 회차 재개를 별도로 승인했다. 현재 상태는 [CombatCore Plan](../Engineering/Plans/2_CombatCore.md)·[WorkRecord](../Engineering/WorkRecords/CombatCoreWorkRecord.md)를 따른다(2026-11-02 리뷰 WAITING, 사용자 V11 대기).
- 프로젝트: E:/MapleWorldProject. 기존 CLAUDE.md → @AGENTS.md 연결과 MCP/후크 설정을 유지한다.
- 설치 확인: Claude Code 2.1.228, Node.js v24.15.0, Git 2.54.0.windows.1. claude doctor 설치 진단 통과.
- 등록: 비어 있던 .claude/skills/ship에 공용 SKILL.md와 역할 references를 등록했다. 공용 15개 스킬의 파일 누락·내용 차이 없음.
- 백업: [.handoff-backups/2026-11-02-claude-setup-before/project](../../../.handoff-backups/2026-11-02-claude-setup-before/project). 3,696파일 SHA-256 일치. manifest.json과 setup-report.json은 project 폴더의 상위에 있다. 백업 사본은 개발·수정 대상에서 제외한다.

## 시작

PowerShell에서 다음을 실행한다. 계정 인증은 사용자가 직접 완료한다.

```powershell
Set-Location "E:/MapleWorldProject"
claude auth login
claude
```

새 세션에서 /ship 등록과 /mcp의 두 MSW 서버 상태를 확인한다. 이번 설정 작업에서 Claude 모델 세션·로그인·Maker 조회·Play는 실행하지 않았다.

첫 메시지:

```text
/ship 프로젝트 인계 상태를 조회해줘.
CLAUDE.md와 AGENTS.md를 적용하고 필요한 Foundation 스킬·참조를 로드해줘.
Docs/ProjectSkill/Engineering/Plans/2_CombatCore.md와
Docs/ProjectSkill/Engineering/WorkRecords/CombatCoreWorkRecord.md의 최신 리뷰를 확인해줘.
현재는 2단계 REV-F01 수정·독립 QA·리뷰(WAITING)를 마치고 사용자 V11 확인 대기다.
옛 진행 표시보다 최신 리뷰와 Plan 상태를 우선해줘.
지금은 조회만 하고 파일 수정·Play·서브에이전트 실행은 하지 마.
```

2026-11-02 사용자 명령으로 개발을 재개해 [CombatCore Plan](../Engineering/Plans/2_CombatCore.md)의 REV-F01 수정 회차를 마쳤다. 다음은 사용자 V11 직접 확인이며 근거는 [WorkRecord 리뷰](../Engineering/WorkRecords/CombatCoreWorkRecord.md#리뷰-기록)에 있다. 다음 작업은 사용자 명령 뒤에만 진행하며 3단계는 시작하지 않았다.
