# ADR-005: HTTP Client Strategy

- 상태: Accepted
- 날짜: 2025-09-21

## 결정

- 외부 API 호출은 **Spring WebClient로 통일**
- `ExternalWebClientFactory` + 프로퍼티(`external.apis.clients.*`)로 확장
- 관측/타임아웃/로깅/보안 정책은 공용 필터에서 관리

## 근거

- 라이브러리 난립 방지, 환경별 설정/교체 쉬움, 유지보수성↑