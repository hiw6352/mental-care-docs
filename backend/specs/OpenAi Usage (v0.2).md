# OpenAI Usage (v0.2)

## Models

- 기본: `gpt-4.1-mini` — 일상 상담/요약/경량 분류
- 승격: `gpt-5` — 애매/고위험 맥락 2차 판정
- Moderation: `omni-moderation-latest` (입/출력 전후 검사)

## 호출 흐름

1) Pre-Moderation(입력) → 2) mini(JSON 스키마 응답) → 3) 조건부 GPT-5 승격 → 4) Post-Moderation(출력)

## Responses API (최신)

- `response_format` ❌ → `text.format` ✅
- `text.format`에는 `type`, `name`, `strict`, `json_schema`가 위치
- strict=true면 **properties의 모든 키가 required에 포함**되어야 함

## DTO/Enum 원칙

1) DTO에는 Map 금지 → **강타입 DTO 파일 분리**
2) Enum은 **별도 파일 분리** (예: `RiskLevel`)