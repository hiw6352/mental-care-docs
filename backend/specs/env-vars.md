# Environment Variables (v0.2)

| Key                    | Example  | Notes                           |
|------------------------|----------|---------------------------------|
| OPENAI_API_KEY         | sk-***   | 필수                              |
| SPRING_PROFILES_ACTIVE | local    | 실행 프로필                          |
| SERVER_PORT            | 8080     | 선택                              |
| OPENAI_PROJECT_ID      | proj_xxx | 필요 시 headers.OpenAI-Project에 매핑 |

## .env.example

OPENAI_API_KEY="보안상 비공개"
SPRING_PROFILES_ACTIVE=local
SERVER_PORT=20001
OPENAI_PROJECT_ID=proj_japfzkNBSe3IW31O6HRgBSxH