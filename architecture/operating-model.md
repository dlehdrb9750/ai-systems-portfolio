# A Practical Operating Model for Stateful AI Work

**Type:** Public reference concept, not an executable framework.

## Why this matters

일회성 프롬프트는 결과를 한 번 받으면 끝납니다. 하지만 실제 업무에는 여러 자료 수집, 도구 호출, 파일 수정, 재검증, 후속 의사결정이 포함됩니다. 이런 작업에서는 단순한 텍스트 출력 이상의 계약이 필요합니다.

## Four separate concerns

| Concern | Key question | Example |
| --- | --- | --- |
| **Intent / Work** | 무엇을 완료해야 하는가? | 공개 자료 기반 보고서 작성 |
| **Execution / Progress** | 어디까지 실제로 수행했는가? | 4개 출처 중 3개 검증 완료 |
| **Authority / Admission** | 어떤 결과가 수용된 최신 상태인가? | 승인된 보고서 버전 |
| **Storage / Recovery** | 해당 상태를 어디에서 재조회·복구할 수 있는가? | Git 커밋과 검증된 체크포인트 |

**Stored ≠ Accepted.** 파일이 존재해도 실질적인 결과가 승인되었다고 볼 수는 없습니다.

**Batch ≠ Goal.** 한 번의 도구 실행을 마쳐도 전체 업무가 끝난 것은 아닙니다.

**A recovery buffer ≠ canonical state.** 임시 복구 데이터는 정본과 구별되어야 합니다.

## Example lifecycle (synthetic)

```text
Human-defined goal
       |
       v
Plan -> Work packages -> Execution batches
       |                     |
       |                     v
       |             Persist + read back
       |                     |
       v                     v
Acceptance criteria <- Verified work result
       |
       +----> Accepted / current result
       |
       +----> Unfinished work + recovery checkpoint
```

가상의 공개 데이터 보고서 작업을 예로 들면:

1. 사용자가 범위와 완료 조건을 정합니다.
2. AI는 필요한 출처 조사, 비교, 초안 작성, 검증 작업을 분리합니다.
3. 저장 도구의 실제 성공 여부와 저장된 내용을 재조회합니다.
4. 조건을 충족하지 못한 결과는 미수용 상태로 남깁니다.
5. 중단된 작업은 마지막 확인된 결과와 미완료 항목부터 재개합니다.
6. 최종 승인 권한을 갖는 주체만 정본 승격을 결정합니다.

## Design constraints

- 시스템 간 데이터 전달이 자동으로 상대 시스템의 판단을 변경해서는 안 됩니다.
- 버전 충돌 시 검증된 최신 상태를 확인하고 변경 사항을 다시 조정합니다.
- 승인·권한·안전 통제를 무효화하는 복구 방법을 전제하지 않습니다.
- 상태의 존재, 성공적인 저장, 결과의 정확성을 서로 다른 증거로 다룹니다.

## Maturity

이 문서는 범용 설계 개념입니다. 완전한 SDK, 분산 트랜잭션 시스템, 또는 모든 실행 환경에서 검증된 자동화 제품이 아닙니다.

See [case studies](../case-studies/index.md) for what has been observed and what remains unverified.
