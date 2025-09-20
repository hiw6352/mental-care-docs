# API Index (v0.2)

| Method | Path              | Description                   | Status |
|-------:|-------------------|-------------------------------|--------|
|    GET | /ping             | Health check                  | Ready  |
|    GET | /version          | App version info              | Ready  |
|   POST | /assessments/phq9 | Score PHQ-9                   | Ready  |
|   POST | /chat/messages    | Chat (Moderation→mini→승격 라우터) | Ready  |

## /chat/messages

- Request

```json
{
  "message": "요즘 잠이 잘 안 와요."
}
```

-- Response

```json
{
  "reply": "잠들기 어려웠겠다...",
  "next_question": "보통 잠드는 데 얼마나 걸리나요?",
  "risk_level": "ok",
  "confidence": 0.78
}
```
