# LLM 메시지 포맷(Responses 입력)

| role      | content[0].type | 설명                      |
|-----------|-----------------|-------------------------|
| system    | input_text      | 시스템 규칙(불변)              |
| user      | input_text      | 사용자 발화                  |
| assistant | output_text     | 과거 어시스턴트 발화(히스토리 재전송 시) |
| assistant | refusal (옵션)    | 거절 응답 재전송이 필요할 때        |

파서 규칙

- 모델 응답에서 content[].type이 **output_text**인 항목의 text를 1순위로 사용.