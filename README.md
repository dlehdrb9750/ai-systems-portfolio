# AI Systems Portfolio

**Designing, building, and operating AI-powered workflows**

> 실질적인 문제를 해결하기 위해 AI를 단발성 대화 도구에서 **지속 가능한 작업 시스템**으로 발전시키는 설계와 운영 경험을 소개합니다.

**Portfolio status:** Four independent public architecture references · 2026-10-11  
**Focus:** AI workflow orchestration · State and data governance · Audit & recursive improvement · Research automation · AI-assisted learning

---

## About this portfolio

저는 AI를 이용해 복잡한 일을 수행할 때 필요한 **작업 구조, 데이터 지속성, 검증, 복구, 인간의 의사결정 경계**를 설계하고 개선해 왔습니다.

관심사는 더 긴 프롬프트를 작성하는 것 자체가 아닙니다. 여러 세션과 도구를 거치는 작업이 중간에 끊기거나 상태를 잃더라도, 무엇이 검증된 결과이고 어디부터 이어가야 하는지 파악할 수 있게 만드는 것입니다.

이 저장소는 그러한 **고급 AI 활용 및 시스템 설계 역량**을 채용 담당자와 기술 검토자 모두에게 설명하기 위한 공개 포트폴리오입니다. 특정 개발 직무 또는 상용 제품 운영 경력을 주장하기 위한 것이 아닙니다.

## Core capabilities

| 역량 | 다루는 문제 | 접근법 |
| --- | --- | --- |
| **Workflow orchestration** | 복잡한 목표가 중간 작업 완료나 일시적인 오류 때문에 멈추는 문제 | 목표 → 작업 패키지 → 실행 배치, 독립 작업 지속, 명시적 완료 기준 |
| **State & data governance** | 여러 저장소·세션 사이에서 정본과 실행 상태가 혼동되는 문제 | 정본 권한, 작업 상태, 저장 위치, 복구 버퍼의 분리 |
| **Verifiable execution** | 도구가 성공했다고 해도 결과가 실제로 저장·반영되었는지 불명확한 문제 | 조건부 갱신, 결과 재조회, 충돌 인지 및 복구 |
| **Long-running research** | 반복 연구의 맥락이 회차 사이에서 단절되는 문제 | 출처 추적, 체크포인트, 미완료 작업의 지속성, 결과 수용의 분리 |
| **AI-assisted learning** | 출제·응답·평가·복습 기록이 서로 일치하지 않는 문제 | 문제와 정답의 독립 관리, 응답 이력, 세션 재개, 검증 단계 |

## Architecture portfolio

공개용 개별 아키텍처는 **내부 운영 정본의 복제본이 아니라 독립적으로 재구성한 릴리스**로 준비합니다. 아직 생성되지 않은 별도 저장소를 작동하는 프로젝트처럼 표시하지 않습니다.

| 아키텍처 | 핵심 내용 | 공개 상태 |
| --- | --- | --- |
| **AWPS — Adaptive Work Planning Standard** | 목표 중심의 장기 AI 작업 계획, 실행 단위, 오류 대응 | **[독립 공개 저장소 — AI Workflow Orchestration](https://github.com/dlehdrb9750/ai-workflow-orchestration)** |
| **DLS — Data Layer Standard** | 정본 선택, 저장 계층, 상태 복구, 검증 가능한 갱신 | **[독립 공개 저장소 — AI State Governance](https://github.com/dlehdrb9750/ai-state-governance)** |
| **AUDS + RIS — Audit & Recursive Improvement** | 근거 기반 감사, 국소 수정(R1), 반복 결함의 구조적 개선 제안(R2) | **[독립 공개 저장소 — AI Audit & Improvement](https://github.com/dlehdrb9750/ai-audit-and-improvement)** |
| **AI Research Automation & Continuity** | 다회차 연구, 증거 출처, 생산자 인계, 저장 검증 및 재개 | **[독립 공개 저장소 — AI Research Automation](https://github.com/dlehdrb9750/ai-research-automation)** |

## Selected case studies

- **[Verified state migration](case-studies/state-migration.md)** — 서로 다른 저장 환경에서 정본을 구분하고 조건부 쓰기·재조회로 실제 반영을 확인한 사례
- **[Continuity in long-running AI work](case-studies/long-running-workflows.md)** — 목표, 실행 배치, 체크포인트와 오류 복구를 분리한 설계
- **[Audit findings to improvement proposals](case-studies/audit-and-improvement.md)** — 합성 자료에 기반한 R1/R2 감사·개선 시뮬레이션과 공개 CI 테스트
- **[Research continuity across execution routes](case-studies/research-automation.md)** — 합성 연구 배치의 생산·인계·검증·재개와 공개 CI 21개 테스트
- **[AI learning workflow](case-studies/ai-learning-system.md)** — 학습 데이터·응답·평가·사용자 인터페이스를 연결하는 응용 및 검증 경계

각 사례는 **확인된 관찰, 설계 선택, 아직 검증되지 않은 범위**를 구분합니다. 비공개 연구의 내용·전략·개인 데이터는 공개하지 않습니다.

## How to navigate

| 문서 | 목적 |
| --- | --- |
| [Architecture catalog](architecture/index.md) | 아키텍처별 책임과 공개 계획 |
| [AI State Governance](https://github.com/dlehdrb9750/ai-state-governance) | 상태 게시·검증·수용을 구분하는 Python 학습용 프로토타입 |
| [AI Workflow Orchestration](https://github.com/dlehdrb9750/ai-workflow-orchestration) | 목표 중심 작업 계획·실패 국소화·복구를 다루는 Python 예제 |
| [AI Audit & Improvement](https://github.com/dlehdrb9750/ai-audit-and-improvement) | 감사 결함·R1 국소 수정·R2 개선안을 구분하는 Python 프로토타입 |
| [AI Research Automation](https://github.com/dlehdrb9750/ai-research-automation) | 여러 회차의 연구 생산자 인계와 승인 경계를 다루는 Python 예제 |
| [Case studies](case-studies/index.md) | 실제 문제와 해결 과정 |
| [Publication policy](publication-policy.md) | 비공개 운영 시스템과 공개 자료의 경계 |
| [Roadmap](roadmap.md) | 공개·검증의 다음 단계 |

## Principles

1. **Verified progress over activity counts** — 작업 횟수나 생성 파일 수보다 검증된 성과를 우선합니다.
2. **Authority is not storage** — 특정 위치에 저장되었다는 사실만으로 정본이 되지는 않습니다.
3. **Recoverability by design** — 작업을 이어갈 수 있도록 필요한 상태와 근거를 남깁니다.
4. **Human decision rights** — AI가 조사·제안·실행할 수 있는 범위와 사용자의 최종 판단 권한을 구분합니다.
5. **Honest maturity labels** — 개념, 내부 실험, 검증된 예제, 실제 운영을 혼동하지 않습니다.

## English overview

This portfolio documents practical experience designing and operating **stateful AI workflows** across research and learning tasks. The emphasis is on task orchestration, canonical-state management, reproducible verification, and recovery after interruptions—not on prompt collections or unverified claims of full autonomy.

Four independently published public educational references are available: [AI Audit & Improvement](https://github.com/dlehdrb9750/ai-audit-and-improvement) (AUDS/RIS), [AI State Governance](https://github.com/dlehdrb9750/ai-state-governance) (DLS) and [AI Workflow Orchestration](https://github.com/dlehdrb9750/ai-workflow-orchestration) (AWPS), and [AI Research Automation](https://github.com/dlehdrb9750/ai-research-automation) (multi-cycle research continuity). Each separates locally tested examples from real-world operational integration. Internal research systems and sensitive operational details are not published.

---

**Current scope:** Public portfolio documentation linked to four independently published educational architectures and synthetic prototypes. This repository does not contain private operational sources, investment strategies, sensitive research findings, or a publicly released software framework.
