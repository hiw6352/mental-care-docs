# Mental Care Docs

- 프로젝트 비전/로드맵
- 요구사항/화면 흐름/API 명세 초안
- ADR(Architecture Decision Record)

## 폴더 구조

```text
docs/
  backend/
    specs/            # API 명세, 요청/응답 예시, 에러코드
    architecture/     # 외부 API, 모듈 다이어그램, 시퀀스
    runbooks/         # 실행/배포/트러블슈팅
    adr/              # 소프트웨어 아키텍처 관련 중요 이력 관리(BE-ADR-001, 002)
  frontend/
    specs/            # 화면 플로우, 상태 흐름, 컴포넌트 계약
    architecture/     # 라우팅, 상태관리, API 연동 구조
    runbooks/         # 로컬 실행, 빌드, 배포, 트러블슈팅
    adr/              # 소프트웨어 아키텍처 관련 중요 이력 관리(FE-ADR-001, 002)
  shared/
    api/              # OpenAPI 스키마(OpenAPI yaml/json), 공통 계약
    guidelines/       # 코드/커밋/문서 스타일, 접근성/복잡도 기준
    glossary.md       # 용어집(한/영)
    changelog.md      # 릴리즈/변경 로그(요약)
```