# Case Study: Continuity in Long-Running AI Work

**Category:** AI workflow orchestration · Interruption recovery  
**Maturity:** Documented design informed by operational feedback; independently published educational example, with 14 locally and in public CI passing tests; no production benchmark

## The problem

실제 AI 작업은 여러 도구 호출과 중간 결과를 거칩니다. 작업 배치가 끝났다는 이유로 전체 목표를 종료하거나, 일시적 저장·연결 오류를 모든 작업의 중단으로 해석하면 생산성이 저하됩니다.

## The approach

A goal-oriented workflow separates:

- **Goal / Plan:** 사용자가 달성하려는 결과와 완료 기준.
- **Work package:** 목표 달성에 의미가 있는 작업 단위.
- **Execution batch:** 실제 환경에 맞춰 실행되는 물리적 묶음.
- **Checkpoint:** 다음 실행에서 회복하는 데 필요한 최소 상태.

핵심 설계 원칙은 **batch completion does not imply goal completion**입니다.

일부 작업에서 도구 문제가 발생해도 범위를 벗어나지 않는 독립 작업은 진행할 수 있습니다. 저장 성공 여부가 불명확하면 기존 상태를 조회하고 충돌을 확인한 뒤 복구 여부를 판단합니다.

## What was observed

장기 연구와 문서·저장 작업에서 발생한 실제 중단, 재시도, 저장 실패 문제를 바탕으로 실행 규칙을 반복 개정했습니다. 작업의 계속 수행, 최소 체크포인트, 오류의 범위별 처리, 권한이 없는 작업의 비자동 승격 등이 설계에 반영되었습니다.

이 경험은 **문제 발견과 실행 표준의 개선**을 입증하지만, 모든 도구나 모든 모델에서 같은 수준의 자율 지속성이 검증됐다는 주장은 아닙니다.

## Public demonstration

[AI Workflow Orchestration](https://github.com/dlehdrb9750/ai-workflow-orchestration)에 합성 데이터를 이용한 실행 가능한 Python 시뮬레이션과 14개의 단위 테스트를 공개했습니다. 공개 데이터 브리핑을 작성하는 과정을 예제로 구성합니다.

1. 긴 목표를 여러 작업 패키지로 분리합니다.
2. 중간에 예상된 저장 실패를 주입합니다.
3. 검증된 결과는 유지하고 미완료 항목만 다음 배치로 넘깁니다.
4. 실제 저장·재조회 결과와 완료 기준을 비교합니다.

**Available:** standalone public in-memory workflow simulator; 14 tests passed locally and in [public GitHub Actions CI](https://github.com/dlehdrb9750/ai-workflow-orchestration/actions/runs/38136344974) on 2026-10-11. **Not yet available:** real LLM/tool orchestration, provider integration test or statistically validated reliability improvements.

## Boundaries

정상적인 권한 및 플랫폼 제한은 준수합니다. 복구 규칙은 접근 권한이나 안전 정책을 변경하지 않습니다.
