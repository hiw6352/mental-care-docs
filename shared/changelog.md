# Changelog (요약)

## v0.2.0 — 2025-09-21

- Shared OpenAPI 초안 정리: `/assessments/phq9`, `/chat/messages`
- Structured Output 구조 확정: `reply`, `next_question`, `risk_level`, `confidence` (all required)
- 외부 호출 WebClient 통일 + Factory 패턴 문서화
- DTO/Enum 강타입 원칙 문서화(Map 금지, Enum 분리)
- 트러블슈팅 추가: Moderation 403, `text.format` 파라미터 변경, required 누락 오류
- 문서 전략: 최소 문서 유지 / docs 구조를 backend·frontend로 분리
- Swagger 전환 계획 수립

## v0.1.x — 2025-09-20

- 초기 스켈레톤, /ping, /version