# Troubleshooting (v0.2)

## Moderations 403: invalid_request_error

- 원인: 프로젝트/조직 헤더 미설정 또는 접근 권한 미부여
- 조치: 대시보드에서 모델 접근 권한 추가

## Responses API: "Unsupported parameter: response_format"

- 원인: 구 파라미터 사용
- 조치: `text.format`로 이전 (`name/strict/json_schema` 포함)

## Responses API: "Missing required parameter: text.format.name"

- 원인: name을 json_schema 안에 넣음
- 조치: `ResponseFormat`에서 `name/strict`를 최상위로 이동

## Responses API: "Invalid schema ... Missing 'next_question'"

- 원인: strict=true인데 required에 누락
- 조치: `required`에 `next_question` 추가 또는 strict=false

## 팁

- `curl -v`로 헤더/상태 확인
- 로컬에서 `OPENAI_API_KEY`, (필요 시) `OPENAI_PROJECT_ID` 설정 재확인
