# Architecture Catalog

> 공개 포트폴리오용 아키텍처 지도입니다. 내부 운영 시스템의 정본이나 실시간 설정 문서가 아닙니다.

## Architecture map

| System | Fundamental question | Public release status |
| --- | --- | --- |
| **AWPS — Adaptive Work Planning Standard** | AI가 복잡한 목표를 어떻게 분해하고, 중단 이후에도 목적을 잃지 않고 이어가는가? | **Planned / no independent public release yet** |
| **[DLS — Data Layer Standard](https://github.com/dlehdrb9750/ai-state-governance)** | 여러 저장소와 세션에서 무엇이 정본이고, 실패한 상태를 어떻게 복구하는가? | **Independent public repository: educational prototype + 8 local tests** |
| **AI Learning Workflows** | 학습 문제·사용자 응답·평가·복습 이력을 어떻게 일관되게 운영하는가? | **Demonstration under consideration** |
| **Reliable AI Research** | 반복 연구의 출처, 불확실성, 결과 수용, 인계를 어떻게 관리하는가? | **Future candidate** |
| **AI Audit & Verification** | AI 작업의 저장 성공과 실질적 판단의 타당성을 어떻게 별도로 검증하는가? | **Future candidate** |

## Shared operating model

각 아키텍처는 범위가 다릅니다.

- **AWPS** organizes *work*: goals, work packages, batches, checkpoints, continuity and completion criteria.
- **DLS** governs *state*: accepted authority, writer routing, durable storage, version checks and recovery.
- **Research / learning applications** define *domain-specific work*: what should be researched, taught, assessed or reviewed.
- **Audit / verification** distinguishes *observed evidence* from claims that have not passed an applicable check.

[Read the public conceptual operating model](operating-model.md).

## Publication approach

새로운 공개 저장소는 해당 아키텍처가 다음 네 가지를 갖출 때 생성합니다.

1. 비공개 자료와 분리된 독립적인 설계 설명.
2. 제3자가 이해하거나 재현할 수 있는 비민감 예제.
3. 무엇이 실제로 검증됐는지에 대한 기록.
4. 사용 조건과 한계를 설명하는 문서.

DLS는 [독립적인 공개 저장소](https://github.com/dlehdrb9750/ai-state-governance)에 교육용 설계와 예제를 게시했습니다. 다른 미공개 아키텍처는 **향후 후보**이며 출시된 서비스가 아닙니다. 상세한 공개용 아키텍처는 준비 후 별도 GitHub 저장소에 출판하고 이 페이지에서 연결할 예정입니다.
