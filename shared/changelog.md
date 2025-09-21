# Changelog (요약)

## v0.2.3 — 2025-09-22

- 프롬프트 정책 정리: 일상 대화 우선, 질문 0~1개/턴, 패턴 반복 방지, 정중 피벗 템플릿 확정
- LLM 메시지 포맷 문서화: system/user= input_text, assistant= output_text
- 유틸 분리 계획 초안: PromptBuilder, MessageMapper, EnvelopeParser, StyleSelector, RiskGate
- 설정/프롬프트 관리 방침: 현재 상수, 향후 YAML/DB 외부화 옵션 메모

## v0.2.1 — 2025-09-22

- Responses 입력을 **역할 분리(system/user/assistant)**로 전환, 히스토리 재전송 시 assistant는 **output_text** 사용
- `verdictWithGpt5`도 메시지 배열(system+user)로 호출하도록 수정
- 시스템 프롬프트에 **정중 피벗 블록** 도입: 오탑픽은 공감 1문장 + 건강 질문 1개, 구체 지침은 미제공
- 응답 파서가 **output_text** 우선 탐색하도록 보완
- 운영 정책: 서버 오탑픽 차단은 비활성(프롬프트 중심 방어), 인젝션 소프트 가드만 유지
-

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