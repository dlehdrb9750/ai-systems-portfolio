# Case Studies

사례 연구는 **문제 → 설계 선택 → 실제 관찰 → 한계 → 재현 가능한 공개 예제 계획**으로 구성합니다.

| Case study | Main capability | Evidence status |
| --- | --- | --- |
| [Verified state migration](state-migration.md) | 상태·정본 관리 및 저장 검증 | 내부 연결 환경에서 실제 쓰기·재조회 관찰; 공개 DLS 예제와 로컬 테스트 검증 |
| [Continuity in long-running AI work](long-running-workflows.md) | 장기 작업 분해와 오류 대응 | 운영 피드백 기반 설계; AWPS 공개 시뮬레이션 및 로컬 테스트 14개 통과 |
| [AI learning workflow](ai-learning-system.md) | 학습 UI·세션·기록 설계 | 학습 백엔드 준비 확인; 전체 학습 사이클 종단 간 검증 미완료 |

## Evidence labels

- **Observed:** 특정 연결 환경에서 결과를 실제 확인함.
- **Documented design:** 설계 문서 또는 운영 계약이 존재함.
- **Publicly reproducible:** 제3자가 실행 가능한 공개 자료와 테스트가 있음.
- **Planned:** 아직 구현·검증·출판되지 않음.

하나의 사례에 여러 수준이 함께 존재할 수 있습니다. 내부에서 확인한 결과라고 해서 외부에서 즉시 재현 가능하다고 주장하지 않습니다.

비공개 출처와 파일 식별자, 연구 내용, 계정 설정, 운영 로그 원본은 싣지 않습니다.
