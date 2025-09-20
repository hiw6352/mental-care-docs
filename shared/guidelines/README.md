# Guidelines (공통 가이드)

## 1) 코드 스타일

- **Backend (Java/Spring)**: DTO는 Map 사용 금지, Enum 분리. JSON 필드 `snake_case`, Code-Style :
  google-style
- **Frontend (Vue 3 + Vite)**: 상태는 Pinia, API 계약은 OpenAPI 기반 타입 생성 권장.
- 공통: 함수는 단일 책임, 파일은 300~400줄 내외 유지.

## 2) 커밋 규칙 (Conventional Commits)

### 커밋 메시지 타입 가이드 (Conventional Commits)

| type     | 언제 쓰나                    | 예시                                        |
|----------|--------------------------|-------------------------------------------|
| feat     | 사용자에게 보이는 **새 기능/기능 변경** | `feat(be): 안전 라우팅 추가`                     |
| fix      | **버그 수정**                | `fix(be): Responses text.format 누락 수정`    |
| docs     | **문서만** 변경               | `docs(shared): changelog 업데이트`            |
| style    | 코드 스타일/포맷(로직 변경 없음)      | `style(be): 포맷 정리`                        |
| refactor | 내부 구조 개선(기능 동일)          | `refactor(be-http): WebClient Factory 도입` |
| perf     | **성능 개선**                | `perf(be): 타임아웃/풀 튜닝`                     |
| test     | 테스트 추가/수정                | `test(be): PHQ-9 단위테스트 추가`                |
| build    | 빌드/의존성/도구 변경             | `build: springdoc-openapi 추가`             |
| ci       | CI 설정/스크립트 변경            | `ci: Jenkins 파이프라인 초기화`                   |
| chore    | 기타 잡무(코드/빌드/CI 제외)       | `chore: .env.example 추가`                  |
| revert   | **이전 커밋 되돌리기**           | `revert: feat(be): 안전 라우팅 추가`             |

- WIP 지양 → 작은 단위로 커밋
-

## 3) 문서 스타일

- 기본 **한국어**, 필드/키/코드는 영어
- 변경점은 `shared/changelog.md`에 요약

## 4) 복잡도 기준

- API 엔드포인트는 **한 책임**(SRP)
- 외부 호출은 **WebClient + Factory** 경유(설정/정책 일원화)
- 예외/에러 포맷은 `Problem` 스키마로 통일
- 안전 로직(Moderation/승격)은 서비스 단에서 캡슐화, 컨트롤러는 얇게

## 5) 보안/비밀값

- API 키는 환경변수/시크릿 스토어등 사용, Git 커밋 금지
- 로깅 시 민감 정보 마스킹
