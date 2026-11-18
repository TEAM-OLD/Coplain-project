# Coplain

**Code + Explain.** 코딩테스트 구술면접 연습 서비스

서비스 안에서 문제를 풀고 제출하면, 제출 코드를 분석한 결과를 근거로 AI 면접관이 질문과 꼬리질문을 합니다. 면접이 끝나면 루브릭 6개 항목의 별점과 질문별 피드백을 리포트로 받습니다.

EOS 학술제 Engineering Track · 팀 OLD (Original Lovers of Development)

## 팀

| 역할 | 이름 |
|---|---|
| Lead | 박준서 |
| BE | 김민서 |
| FE | 서재욱 |

## 시작하기 전에

1. [협업 규약](COWORK_RULE.md)을 읽습니다.
2. [개발 컨벤션](docs/conventions.md)을 읽습니다.
3. AI 에이전트는 저장소 최상위에서 실행합니다. 공통 지시는 `AGENTS.md`에 있습니다. `AGENTS.md`를 자동으로 읽지 않는 도구라면 시작할 때 읽게 해 주세요.

## 로컬 실행

프로젝트 골격을 만든 뒤 작성합니다.

```bash
cp .env.example .env   # 값은 팀에서 따로 공유받습니다
docker compose up
```

## 구조

```text
coplain/
├── backend/      Spring Boot 서버
├── frontend/     React 앱
├── prompts/      LLM 프롬프트
├── eval/         평가셋
├── problems/     문제 데이터
├── docs/         API 명세, 설계 결정 기록, 컨벤션
├── infra/        배포 설정
└── sandbox/      실험용 코드
```

## 학습용 에이전트 요청

어떤 에이전트를 쓰든 아래처럼 요청하면 `AGENTS.md`의 절차대로 동작합니다.

| 용도 | 요청 예시 |
|---|---|
| 커밋 전 내 변경을 체크리스트로 점검하고, 내가 답해 볼 질문 받기 | "셀프 리뷰 해 줘" |
| 파일이나 개념을 튜터처럼 설명받기 (코드는 고치지 않음) | "`<대상>` 설명해 줘" |
