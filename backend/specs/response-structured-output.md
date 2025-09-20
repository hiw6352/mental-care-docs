# Structured Output Spec (v0.2)

## Enum

- `RiskLevel`: ok | watch | concern | crisis  (JSON 직렬화 시 소문자)

## RiskReply (모델 생성 대상)

required: reply, next_question, risk_level, confidence

```json
{
  "type": "object",
  "properties": {
    "reply": {
      "type": "string"
    },
    "next_question": {
      "type": "string"
    },
    "risk_level": {
      "type": "string",
      "enum": [
        "ok",
        "watch",
        "concern",
        "crisis"
      ]
    },
    "confidence": {
      "type": "number",
      "minimum": 0,
      "maximum": 1
    }
  },
  "required": [
    "reply",
    "next_question",
    "risk_level",
    "confidence"
  ],
  "additionalProperties": false
}
```

## RiskOnly (승격 판정 전용)

required: risk_level, confidence

```json
{
  "model": "gpt-4.1-mini",
  "input": "시스템+유저 프롬프트로 구성된 문자열",
  "text": {
    "format": {
      "type": "json_schema",
      "name": "RiskReply",
      "strict": true,
      "json_schema": {
        ...
        위
        RiskReply
        스키마
        ...
      }
    }
  },
  "max_output_tokens": 400
}
```

## Responses API 요청 예시

```json
{
  "model": "gpt-4.1-mini",
  "input": "시스템+유저 프롬프트로 구성된 문자열",
  "text": {
    "format": {
      "type": "json_schema",
      "name": "RiskReply",
      "strict": true,
      "json_schema": {
        ...
        위
        RiskReply
        스키마
        ...
      }
    }
  },
  "max_output_tokens": 400
}
```