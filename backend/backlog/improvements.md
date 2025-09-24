# Improvements (Backlog)

## 1) Moderation 과민 반응( flagged → 즉시 CRISIS 템플릿 )

- 현상: 사용자가 우울 맥락에서 감정적으로 공격적 표현을 쓰면, flagged=true로 바로 CRISIS 템플릿이 출력되어 대화가 끊김.
- 목표: 위험 맥락 유지 + 톤 완화(soft landing). "즉시 위기"가 아니라 "SUPPORTIVE/관찰 기반 확인" 단계 제공.

### 제안(설계만, 구현 보류)

- 입력 모더레이션 결과를 **단일 스위치**로 쓰지 말고, 카테고리/심각도 기반의 완화 규칙 도입:
    - 자해/타해 명시(high) → CRISIS
    - 욕설/공격적 어휘만(detached from self-harm) → SUPPORTIVE로 피벗 + 확인 질문 0~1개
- 출력 모더레이션은 유지하되, **soft template**(안내/라포) 우선 → CRISIS 템플릿은 확신도↑에서만.
- 지표: 과민 차단율↓, 대화 지속률↑

---

## 2) RiskLevel 기반 상담 스탠스 전환(승격 임계 대신)

- 현상: 승격 임계 튜닝의 실익 제한(궁극적으로 GPT-5 재평가 후 템플릿 출력).
- 방향: CONCERN/CRISIS 등 **RiskLevel에 따른 응답 전략**을 풍부화(프롬프트/규칙).
    - CONCERN: 질문 빈도 0~1, 라포/정서 명료화 중심, 자가 돌봄 선택지 1개
    - CRISIS: 간결·안전 우선, 지역/긴급 연락처 템플릿 + 사용자의 안전 확인
- 후속: 프롬프트 블록 분리(`stance_concern`, `stance_crisis`) 및 예시 문장 뱅크 확장
