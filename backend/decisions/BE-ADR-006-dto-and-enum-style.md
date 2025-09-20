# ADR-006: DTO/Enum Style

- 상태: Accepted
- 날짜: 2025-09-21

## 원칙

1) DTO에는 Map 사용 금지 → 강타입 DTO로 정의
2) Enum은 별도 파일 분리, JSON 직렬화는 소문자

## 적용

- Moderation/Responses/Risk 스키마 전부 강타입화
- RiskLevel Enum 분리 및 @JsonCreator/@JsonValue 적용
