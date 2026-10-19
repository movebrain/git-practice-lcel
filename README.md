# git-practice-lcel

6명이 한 파일(`sequential_chain_02_practice.py`)을 나눠 작업하며 Git 협업 흐름(이슈 → 브랜치 → 커밋 → PR → 리뷰 → 병합)을 연습하는 저장소입니다.
실습 주제는 **LCEL Sequential Chain으로 해외 고객 문의(CS) 이메일 자동 처리**(번역 → 요약 → 긴급도 → 언어 식별 → 답변 → 답변 번역)입니다.

## 작업 분담

| 이슈 | 담당 영역 (파일 내 `# [Issue #N]`) | 제안 브랜치 |
|------|-------------------------------------|-------------|
| [#1](https://github.com/movebrain/git-practice-lcel/issues/1) | 환경 변수 로드, LLM 초기화, 입력 데이터 | `feat/1-setup-llm-env` |
| [#2](https://github.com/movebrain/git-practice-lcel/issues/2) | 번역·요약 체인 | `feat/2-translate-summarize-chain` |
| [#3](https://github.com/movebrain/git-practice-lcel/issues/3) | 긴급도 평가·언어 식별 체인 | `feat/3-urgency-language-chain` |
| [#4](https://github.com/movebrain/git-practice-lcel/issues/4) | 답변 생성·답변 번역 체인 | `feat/4-reply-chain` |
| [#5](https://github.com/movebrain/git-practice-lcel/issues/5) | 전체 체인 결합 (`RunnablePassthrough.assign`) | `feat/5-combined-chain` |
| [#6](https://github.com/movebrain/git-practice-lcel/issues/6) | 체인 실행 및 결과 출력 | `feat/6-run-and-output` |

각자 자신의 이슈 영역만 수정하면 서로 다른 위치를 고치게 되어 병합 충돌이 거의 나지 않습니다. #5·#6은 #1~#4가 병합된 뒤 통합 확인을 합니다.

## 시작하기

```bash
git clone https://github.com/movebrain/git-practice-lcel.git
cd git-practice-lcel
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # OPENAI_API_KEY 입력 (.env 는 커밋 금지)
```

## 규칙

- 브랜치·작업 절차: [CONTRIBUTING.md](CONTRIBUTING.md)
- 커밋 메시지: [Conventional Commits 1.0.0 (한국어)](https://www.conventionalcommits.org/ko/v1.0.0/) — 프로젝트 규칙은 [`.claude/skills/commit-convention/SKILL.md`](.claude/skills/commit-convention/SKILL.md)
