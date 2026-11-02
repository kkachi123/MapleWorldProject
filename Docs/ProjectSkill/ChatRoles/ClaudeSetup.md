# Claude Code — 프로젝트 실행 준비

- 설정 확인일: 2026-11-02. 게임 개발은 사용자 요청에 따라 일시정지 중이다. 이 설정 작업은 개발 재개 승인이 아니다.
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
현재는 2단계 REV-F01 수정 대기 상태에서 사용자가 일시정지했다.
일부 로드맵/run의 옛 진행 표시보다 최신 리뷰와 일시정지 요청을 우선해줘.
지금은 조회만 하고 파일 수정·Play·서브에이전트 실행은 하지 마.
```

개발 재개는 사용자의 별도 명령 뒤에만 한다. 다음 후보는 [CombatCore Plan](../Engineering/Plans/2_CombatCore.md)의 REV-F01이며, 근거는 [WorkRecord 리뷰](../Engineering/WorkRecords/CombatCoreWorkRecord.md#리뷰-기록)에 있다. 3단계는 시작하지 않았다.
