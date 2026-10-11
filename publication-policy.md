# Public Publication & Evidence Policy

이 포트폴리오는 **공개 가능한 일반화된 작업 경험과 설계 원리**를 소개합니다. 비공개 운영 시스템의 라이브 미러가 아닙니다.

## Separation of responsibilities

| Layer | Role | Public? |
| --- | --- | --- |
| Internal operational systems | 업무별 실제 정본, 원문, 설정, 프로젝트별 실행 상태 | **No** |
| Public architecture releases | 별도 구성한 범용 설계, 비민감 예제, 테스트 | 검토·검증 후 공개 |
| This portfolio | 공개된 설계와 실제 경험을 소개하는 안내 및 사례 기록 | **Yes** |

내부에 새로운 버전이 생겨도 공개 저장소의 내용이 자동으로 최신 정본이 되는 것은 아닙니다. 공개 버전에는 별도 릴리스와 검증이 필요합니다.

## Excluded content

- 비공개 투자 연구, 독창적인 알파·거래 전략, 자산·주문 관련 사항
- 비공개 정치경제 연구의 실질적 가설·결과와 민감한 운영 자료
- 다른 프로젝트의 비공개 소스, 연구 원문 및 내부 파일 경로
- 개인 학습 기록, 접근 토큰, 인증 정보, 개인 식별 데이터
- 공개 라이선스를 확인하지 않은 제3자 저작물
- 내부 실패 로그 전체를 여과 없이 복제한 자료

## Publication checklist

- [ ] 공개 가치와 대상 독자를 확인했는가?
- [ ] 원문 복제가 아닌 공개용 독립 서술인가?
- [ ] 비공개 경로·기밀 데이터·과거 커밋 이력의 노출 위험을 점검했는가?
- [ ] 관찰 사실과 추론·설계 목표를 명확히 구분했는가?
- [ ] 실행 가능성, 공개 재현성, 테스트 범위를 실제 근거로 확인했는가?
- [ ] 공개 범위와 사용 조건·라이선스 여부를 명시했는가?
- [ ] 최종 출판 내용을 점검했는가?

## Evidence wording

- **Observed in an internal connected environment:** 내부 연결 환경에서 특정 동작을 확인했습니다.
- **Documented design:** 아키텍처 또는 운영 계약을 설계·문서화했습니다.
- **Publicly reproducible:** 제3자가 실행 가능한 공개 예제 및 검증 방법을 제공합니다.
- **Planned:** 공개 구현이나 독립 검증은 아직 없습니다.

**Never claim** that a staging copy is a live authority, that backend readiness equals user-facing end-to-end success, or that archived automation settings demonstrate currently active unattended operation.

## Licensing

This repository currently publishes portfolio text for viewing. No explicit open-source license is granted by this document. A license for any future independently released architecture will be chosen separately, considering third-party rights and intended reuse.
