# Safety: Moderation & Escalation (v0.2)

## 라이프사이클(한 턴)

1) Pre-Moderation(입력) — 고위험 즉시 위기 플로우
2) mini(JSON) — reply/next_question/risk_level/confidence
3) 게이트(승격 기준)
    - risk_level ∈ {concern, crisis} && confidence ≥ 0.6
4) GPT-5 판정(RiskOnly)
5) Post-Moderation(출력)
6) 로깅: session_id, risk_level, ts 등 최소 데이터

## 의사코드

```text
if moderate(input).highRisk -> crisisTemplate()
rr = mini.classify(...)
if rr.risk ∈ {concern,crisis} && rr.conf ≥ T:
verdict = gpt5.verdict(...)
if verdict.risk ∈ {concern,crisis}: crisisTemplate()
if moderate(rr.reply).highRisk -> crisisTemplate()
return rr
```

## 파라미터(초안)

- `safety.confidence-threshold = 0.6`
- 모델: `openai.primary-model=gpt-4.1-mini`, `openai.primary-model=gpt-5`