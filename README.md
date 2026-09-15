# ff_coding_agent_protocol_md

AI 에이전트용 연구 프로토콜 문서.

코딩 프로토콜(ln-structure, Python 규칙, 문서 템플릿, Claude Code 훅)은 2026-09-15 부로
[ff-lntools](https://github.com/gatesplan/ff-lntools) 의 `src/lntools/protocol/` 로 옮겨져 거기서 관리한다.
프로젝트 세팅은 `pip install git+https://github.com/gatesplan/ff-lntools` 후 `lnt init`.

## 파일

- `for-agent-research.md` - 실험 폴더, 스크립트, 결과, 실험.md 양식
- `for-agent-experiment-template.md` - 실험 기록 템플릿
- `for-agent-papernotes-template.md` - 논문 노트 템플릿
- `CLAUDE-template.md` - 연구 프로젝트용 CLAUDE.md 템플릿 (사실관리 태그, 조사 기록 규칙)
- `for-agent-codingprotocol-backend.md` - 레거시. ln-structure 이전의 5계층 구조. 배포하지 않음

## 사용

필요한 파일을 프로젝트 `.claude/` 에 복사하고 `CLAUDE.md` 에서 참조한다.
