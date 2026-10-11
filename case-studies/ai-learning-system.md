# Case Study: AI Learning Workflows

**Category:** Applied AI · Interactive learning · State continuity  
**Maturity:** Backend readiness observed; end-to-end learning cycle not yet verified

## The problem

학습용 AI가 문항을 제시하는 것과 **정답·응답·복습 이력을 신뢰할 수 있게 운영하는 것**은 다른 문제입니다.

문항의 원문, 정답·해설, 사용자 응답, 평가 결과, 세션 진행 상태가 명확하게 연결되지 않으면 같은 문항을 중복 처리하거나 실제로 제출하지 않은 학습을 완료한 것으로 기록할 수 있습니다.

## Architecture concepts

```text
Approved learning content
        |
        v
Question/package selection
        |
        v
Interactive user session
        |
        v
Response capture -> Evaluation
        |
        v
Verified progress -> Review/retry
```

원칙적으로 문제 본문·정답·해설·사용자 응답을 별도 역할로 취급하고, 화면에 표시한 결과와 공식 학습 기록을 구분합니다.

## What was observed

학습용 외부 백엔드와 O/X 학습 워크플로 구성이 존재하고, 연결 환경에서 **backend-ready 상태**가 확인되었습니다. 그러나 점검 당시 **Chat 세션 시작부터 공식 Owner 기록 반영까지 전체 과정의 종단 간 검증은 완료되지 않았습니다.**

따라서 이 사례는 작동하는 범용 공개 제품이 아니라 **실제 응용 아키텍처와 검증 경계의 설명**입니다.

## Proposed public demo

저작권·비공개 시험 자료와 무관한 자체 작성 예제 문항으로 다음 흐름을 구현할 예정입니다.

1. 승인된 샘플 문항 패키지 로드
2. O/X 응답과 세션 식별
3. 정답 공개 및 평가
4. 중복 제출 인식
5. 기록 검증 후 세션 재개

**Not yet available:** public demo and confirmed end-to-end operational result.  
**Excluded:** actual exam question banks, private learning history, personal identifiers, private educational source documents.
