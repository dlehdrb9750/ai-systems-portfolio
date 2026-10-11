# Architecture Catalog

> 공개 포트폴리오용 아키텍처 지도입니다. 내부 운영 시스템의 정본이나 실시간 설정 문서가 아닙니다.

## Architecture map

| System | Fundamental question | Public release status |
| --- | --- | --- |
| **[AWPS — Adaptive Work Planning Standard](https://github.com/dlehdrb9750/ai-workflow-orchestration)** | AI가 복잡한 목표를 어떻게 분해하고, 중단 이후에도 목적을 잃지 않고 이어가는가? | **Independent public educational prototype + 14 local tests** |
| **[DLS — Data Layer Standard](https://github.com/dlehdrb9750/ai-state-governance)** | 여러 저장소와 세션에서 무엇이 정본이고, 실패한 상태를 어떻게 복구하는가? | **Independent public repository: educational prototype + 8 local tests** |
| **AI Learning Workflows** | 학습 문제·사용자 응답·평가·복습 이력을 어떻게 일관되게 운영하는가? | **Demonstration under consideration** |
| **[AI Research Automation & Continuity](https://github.com/dlehdrb9750/ai-research-automation)** | 반복 연구의 증거, 생산자 패킷, 연구 수용 및 회차 간 인계를 어떻게 안전하게 관리하는가? | **Independent educational prototype; 21/21 public CI tests passed** |
| **[AUDS + RIS — Audit & Recursive Improvement](https://github.com/dlehdrb9750/ai-audit-and-improvement)** | AI 산출물의 결함을 어떻게 감사하고 반복 결함을 구조적으로 개선하는가? | **Independent educational repository; 16/16 public CI tests passed** |

## Shared operating model

각 아키텍처는 범위가 다릅니다.

- **AWPS** organizes *work*: goals, work packages, batches, checkpoints, continuity and completion criteria.
- **DLS** governs *state*: accepted authority, writer routing, durable storage, version checks and recovery.
- **Research continuity** uses independent, source-scoped attempts, producer handoff and Owner batch admission. See [AI Research Automation](https://github.com/dlehdrb9750/ai-research-automation); actual scheduled execution is not part of the public demo.
- **Learning applications** define domain-specific content and record rules.
- **Audit / verification (AUDS)** separates evidence-scoped findings and local R1 corrections from substantive acceptance.
- **Recursive improvement (RIS)** analyzes repeated findings and produces governance proposals rather than automatic changes.

[Read the public conceptual operating model](operating-model.md).

## Publication approach

새로운 공개 저장소는 해당 아키텍처가 다음 네 가지를 갖출 때 생성합니다.

1. 비공개 자료와 분리된 독립적인 설계 설명.
2. 제3자가 이해하거나 재현할 수 있는 비민감 예제.
3. 무엇이 실제로 검증됐는지에 대한 기록.
4. 사용 조건과 한계를 설명하는 문서.

AUDS/RIS는 [AI Audit & Improvement](https://github.com/dlehdrb9750/ai-audit-and-improvement)에 공개용 자료를 게시했습니다. DLS는 [AI State Governance](https://github.com/dlehdrb9750/ai-state-governance), AWPS는 [AI Workflow Orchestration](https://github.com/dlehdrb9750/ai-workflow-orchestration)에 각각 공개용 설계와 학습 예제를 게시했습니다. 장기 연구의 공개 예제는 [AI Research Automation](https://github.com/dlehdrb9750/ai-research-automation)에 별도 게시했습니다. 학습 등 다른 미공개 아키텍처는 **향후 후보**이며 출시된 서비스가 아닙니다. 상세한 공개용 아키텍처는 준비 후 별도 GitHub 저장소에 출판하고 이 페이지에서 연결할 예정입니다.
