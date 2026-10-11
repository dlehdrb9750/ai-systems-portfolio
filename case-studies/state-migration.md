# Case Study: Verified State Migration

**Category:** State governance · Data reliability  
**Maturity:** Observed in connected internal workflows; public reproducible demo not yet released  
**Scope:** Sanitized architecture account

## 1. The problem

장기 AI 프로젝트의 자료가 여러 저장 환경에 분산되면 다음과 같은 문제가 생깁니다.

- 가장 최근에 수정한 파일이 반드시 유효한 정본은 아닙니다.
- 새 저장소로 복사했다고 해서 기존 작업의 Owner나 공식 실행 경로가 바뀌는 것은 아닙니다.
- 파일 쓰기 요청이 정상 응답을 반환해도 실제 결과를 재확인해야 합니다.
- 새 저장 경로와 기존 예약 실행 환경이 서로 다른 방식으로 동작할 수 있습니다.

## 2. Design approach

**Separate four facts:** canonical authority, execution route, stored artifact, and recoverable unaccepted data.

일반적인 절차:

1. 이전에 수용된 상태와 새로운 저장 위치의 관계를 명시합니다.
2. 변경 대상의 정확한 기존 버전을 확인합니다.
3. 가능한 경우 SHA 또는 동등한 버전 조건을 포함해 갱신합니다.
4. 갱신 후 실제 저장된 파일과 버전을 다시 읽습니다.
5. 저장 검증과 연구·업무 결과의 실질적인 수용을 분리합니다.
6. 일부 전환만 완료되었다면 전체 전환 완료라고 표시하지 않습니다.

## 3. What was observed

연결된 실제 GitHub 환경에서 여러 독립 작업의 상태 파일을 조건부로 갱신하고 저장 결과를 다시 읽어 확인하는 절차가 수행되었습니다. 문서와 Registry를 통한 단일 경로 선택 및 부분 전환 경계도 기록되었습니다.

확인된 것은 **특정 작업에서 GitHub 파일 갱신과 재조회가 성공했다는 사실**입니다. 이것만으로 모든 오래된 실행 진입점, 계정 설정, 자동 작업, 과거 증거 자료가 완전히 이관되었다는 결론을 내리지 않습니다.

## 4. Lessons

- **A commit is evidence of storage, not automatic acceptance of a conclusion.**
- 전환의 단위는 저장소 전체가 아니라 각 Owner / Workflow일 수 있습니다.
- 새 파일을 읽을 수 있어도 오래된 진입점이 옛 경로를 가리킬 수 있습니다.
- 완료·미완료·검증 대기 상태를 분리해야 실제 복구가 쉬워집니다.

## 5. Public verification plan

합성 데이터를 사용하는 독립적인 GitHub 예제를 준비합니다.

- Old state → candidate successor → version-guarded write → readback
- Deliberate stale-version conflict
- Explicit accepted vs. unaccepted flags
- Recovery checkpoint without modifying the accepted result

**Not yet available:** standalone public runnable example, automated test results, published benchmarks.

**Disclosure:** No private repositories, source IDs, production branches, or domain research content are reproduced in this case study.
