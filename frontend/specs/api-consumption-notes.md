# 프론트 연동 노트 (초안)

## 호출 규칙

- 헤더: `Content-Type: application/json`
- 타임아웃/재시도: 10s / 1회 (임시)

## 엔드포인트별 기대 형태

- **/assessments/phq9**: `score:number`, `severity:string`
- **/chat/messages
  **: `reply:string`, `next_question:string`, `risk_level:"ok|watch|concern|crisis"`, `confidence:number(0~1)`

## UI 처리

- 로딩 스피너: 요청~응답 사이 표시
- 에러: `message` 있으면 토스트로 노출
- i18n: 서버 필드는 영어, 화면 문구는 한글

## 추후 전환

- 스웨거 활성화 후 `/v3/api-docs(.yaml)`를 타입 생성에 사용
