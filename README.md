# ff_coding_agent_protocol_md

AI 코딩 에이전트를 위한 프로젝트 구조 및 코딩 프로토콜 정의.
새 프로젝트 시작 시 `.claude/` 디렉토리에 복사하여 에이전트 지침으로 사용한다.

## Quick Use

1. 프로젝트 루트에 `.claude/` 디렉토리 생성
2. 필요한 프로토콜 파일을 `.claude/`에 복사
3. `CLAUDE-template.md`를 프로젝트 루트에 `CLAUDE.md`로 복사 후 프로젝트 정보 작성

```
project/
  CLAUDE.md                                    # CLAUDE-template.md 기반
  .claude/
    for-agent-codingprotocol-ln-structure.md    # Ln 구조 규칙
    for-agent-codingprotocol-python.md          # Python 코딩 규칙
    for-agent-layerinfo-template.md             # 저해상도 문서 템플릿
    for-agent-layerinfo-ln-template.md          # 중해상도 문서 템플릿
    for-agent-moduleinfo-template.md            # 고해상도 문서 템플릿
```

## About Layer Structure

이 프로젝트는 AI 코딩 에이전트가 코드베이스를 효율적으로 탐색하고 수정할 수 있도록 설계된 Ln 레이어 구조를 따른다. 의존 방향이 단방향으로 고정되고, 레이어/모듈 경계가 명확하여 에이전트가 변경 범위를 한정하고 영향도를 예측할 수 있다.

Ln 구조는 의존 방향이 단방향인 계층 기반 아키텍처다.

- **l0**: 외부 의존 없는 코어 (데이터 타입, 상수)
- **l1**: 단위 기능 (외부 API 래퍼, 단일 책임 모듈)
- **l2**: l1 조합 서비스
- **l3+**: 상위 파사드, 오케스트레이션

상위 레이어는 하위를 참조할 수 있지만, 같은 레이어 간/하위에서 상위 참조는 금지.
모든 모듈은 `ln/modulename/` 폴더 구조를 사용하며, `__init__.py`로 export를 관리한다.

상세 규칙: `for-agent-codingprotocol-ln-structure.md` 참조.

## Info Document Description

3단계 해상도 문서 체계로 에이전트가 필요한 깊이만큼만 탐색할 수 있다.

| 해상도 | 파일 | 위치 | 내용 |
|--------|------|------|------|
| 저 | `for-agent-layerinfo.md` | `src/pkg/` | 전체 레이어별 모듈 목록 |
| 중 | `for-agent-layerinfo-ln.md` | `src/pkg/ln/` | 레이어 내 모든 공개 메서드 시그니처 |
| 고 | `for-agent-moduleinfo.md` | `src/pkg/ln/module/` | 모듈 상세 (동작, 예외, 설계 이유) |

탐색 흐름: 저해상도에서 모듈 위치 파악 -> 중해상도에서 메서드 확인 -> 필요시 고해상도로 상세 확인.

각 템플릿 파일:
- `for-agent-layerinfo-template.md` -- 저해상도 작성 예시
- `for-agent-layerinfo-ln-template.md` -- 중해상도 작성 예시
- `for-agent-moduleinfo-template.md` -- 고해상도 작성 예시
