# README-template.md

Ln 구조 프로젝트의 README.md 템플릿.

## 목적

README.md는 프로젝트의 외부 진입점이다.
사람이든 에이전트든, 이 프로젝트가 무엇이고 어떻게 쓰는지를 가장 먼저 파악하는 문서.
`for-agent-*` 문서 체계는 내부 탐색용이지만, README는 그 이전 단계 -- 이 프로젝트를 열었을 때 첫 화면에서 맥락을 잡기 위한 것이다.

## 필수 섹션

### Overview
프로젝트 목적 1-2문장. 무엇을 하는 시스템인지.

### Quick Use
설치/설정 + 최소 실행 코드. 복사해서 바로 돌릴 수 있는 수준.

### About Layer Structure
Ln 레이어 구성과 각 레이어의 역할 요약. 전체 구조를 한눈에 파악.
반드시 다음 내용을 포함해야 한다:

> 이 프로젝트는 AI 코딩 에이전트가 코드베이스를 효율적으로 탐색하고 수정할 수 있도록 설계된 Ln 레이어 구조를 따른다. 의존 방향이 단방향으로 고정되고, 레이어/모듈 경계가 명확하여 에이전트가 변경 범위를 한정하고 영향도를 예측할 수 있다.

### Info Document Description
3단계 해상도 문서 체계 안내. 코드베이스 탐색 방법 설명.

## 형식

```markdown
# project-name (pkg)

프로젝트 목적 1-2문장.

## Quick Use

(설정 + 최소 실행 코드)

## About Layer Structure

(레이어 구조 요약)

## Info Document Description

(3단계 문서 체계 테이블)
```
