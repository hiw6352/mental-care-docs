# 백로그(초안)

- [x] [UX] 질문 빈도/형태 로테이션 지시 추가(질문 0~1개, 비질문 턴 허용).
- [x] [UX] “질문 없이 마무리” 예시 3~4개 프롬프트에 삽입.
- [x] [CORE] StyleSelector 유틸 도입(반복 패턴 회피).
- [x] [CORE] PromptBuilder/MessageMapper/EnvelopeParser 유틸 파일 분리.
- [x] [CFG] ConfigurationProperties로 임계값/모델/타임아웃 상수화.
- [x] [PROMPT] 프롬프트 외부화(YAML/DB) 비교표 작성 후 의사결정.
- [ ] [SAFETY] Moderation 완화 로직 설계(자해/타해 vs 욕설 분리, soft landing 템플릿)
- [ ] [PROMPT] RiskLevel별 스탠스 블록 초안 작성 및 샘플 10턴 회귀세트 만들기