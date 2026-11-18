# 개발 컨벤션

사람과 AI 에이전트가 모두 따르는 기본 규칙이다. 각 영역의 세부 규칙은 `backend/AGENTS.md`, `frontend/AGENTS.md`에 있다.

## 브랜치

- `main`: 항상 실행 가능한 상태. 직접 커밋하지 않고 PR로만 병합한다.
- 작업 브랜치: `종류/영역-설명`
  - 종류: `feat` `fix` `refactor` `docs` `test` `chore`
  - 영역: `be` `fe` `ai` `infra` `docs`
  - 예: `feat/fe-interview-page`, `fix/be-session-owner-check`, `docs/ai-rubric-v1`

## 커밋 메시지

```text
종류(영역): 무엇을 했는지 한 줄

필요하면 빈 줄 뒤에 이유를 적는다.
```

- 예: `feat(be): 이메일 인증 코드 발급 API 추가`
- 한 커밋에는 한 가지 변경만 담는다.

## PR 병합

- Squash merge로 병합한다. PR 제목이 main의 커밋 메시지가 되므로 커밋 메시지 규칙을 따른다.
- 병합 조건: 필수 리뷰 승인 1개 이상, CI 통과(도입 후).

## 코드와 문서의 언어

- 코드 식별자(변수, 함수, 클래스, API 경로): 영어
- 주석, 문서, 커밋 메시지, PR: 한국어
- 공통 용어는 `COWORK_RULE.md` 3장을 따른다. 예: Submission, InterviewSession, QATurn, fact

## 폴더별 역할

| 경로 | 내용 | 소유 |
|---|---|---|
| `backend/` | Spring Boot 서버 | BE (마이그레이션·AI 코드는 Lead) |
| `frontend/` | React 앱 | FE |
| `prompts/` | LLM 프롬프트 | Lead |
| `eval/` | 평가셋 | FE |
| `problems/` | 문제 데이터 | BE |
| `docs/api/` | API·SSE 명세 | Lead |
| `docs/decisions/` | 설계 결정 기록 | 결정한 사람 |
| `infra/` | 배포 설정 | Lead |
| `sandbox/` | 실험용 코드 | 각자 폴더 |

## 추후 채울 항목

- 코드 포매터와 린트 설정 (골격 생성 시)
- 테스트 작성 기준
- 환경 변수 이름 규칙
