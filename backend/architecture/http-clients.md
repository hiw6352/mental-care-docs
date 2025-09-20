# 외부 API 클라이언트 아키텍처 (v0.2)

## 목표

- 모든 외부 호출을 **WebClient로 통일**
- 프로퍼티만 추가하면 새로운 외부 API 클라이언트를 **코드 수정 없이** 생성

## 구성

- `ExternalApisProperties` (`external.apis.clients.*` 바인딩)
- `ExternalWebClientFactory` : 이름 기반 WebClient 제공 (캐시)
- 공용 타임아웃/로깅 필터는 `HttpClientConfig`에서 일괄 적용

## 설정 예시 (properties)

```properties
external.apis.clients.openai.base-url=https://api.openai.com/v1
external.apis.clients.openai.api-key=${OPENAI_API_KEY}
external.apis.clients.openai.timeout-ms=15000
external.apis.clients.openai.headers.Content-Type=application/json
# (필요 시) 프로젝트 헤더
external.apis.clients.openai.headers.OpenAI-Project=proj_xxxxx
```

## 사용 예시

```java
WebClient openai=factory.get("openai");
    openai.post().uri("/responses")...
```

## 확장

* 새 API: external.apis.clients.kakao.*만 추가 → factory.get("kakao")
* 전역 정책(재시도/서킷브레이커)은 팩토리 레벨 필터로 주입