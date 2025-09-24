# LLM 유틸/레이어 분리

## 유틸 모듈

- PromptBuilder: system/developer/user 메시지 조합, 히스토리 압축.(차후 고려)
- MessageMapper: 히스토리 ↔︎ input_text/output_text 변환.
- EnvelopeParser: output_text 우선 파싱, 실패 폴백.
- ~~StyleSelector: 최근 턴 패턴 보고 다음 턴 형태 로테이션(질문/비질문/요약/선택지).~~ -> 프롬프트로 처리
- RiskGate: 승격 조건/후처리(상수화, 테스트 용이).

## 적용 원칙

- 외부 API/LLM 호출부(OpenAiGateway)에서 위 유틸만 사용.
- 서비스/컨트롤러는 DTO만 다룸(Map 금지), 유틸의 인터페이스에 의존.
