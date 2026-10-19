# 협업 가이드

## 작업 절차

1. 담당 **이슈**를 확인하고 본인에게 할당(Assignee)합니다.
2. 최신 `main` 에서 **브랜치**를 만듭니다.
   ```bash
   git switch main && git pull origin main
   git switch -c feat/2-translate-summarize-chain
   ```
3. 이슈 영역(`# [Issue #N]`)만 수정하고 **커밋 컨벤션**에 맞춰 커밋합니다.
4. 푸시 후 **Pull Request** 를 만듭니다. 본문에 `Closes #N` 을 적어 이슈를 연결합니다.
5. 팀원 1명 이상의 리뷰(Approve)를 받으면 `main` 에 병합합니다. (merge commit 방식, 충돌은 PR 작성자가 해결)
6. 병합된 브랜치는 삭제합니다.

## 브랜치 컨벤션

```
<type>/<이슈번호>-<kebab-case-설명>
```

| 규칙 | 내용 |
|------|------|
| `type` | 커밋 type과 동일: `feat`, `fix`, `docs`, `refactor`, `test`, `chore` 등 |
| 이슈번호 | 연결된 GitHub 이슈 번호 (예: `2`) |
| 설명 | 영문 소문자 + 숫자 + 하이픈(`-`), 2~4 단어 |
| 금지 | 대문자, 공백, 한글, 밑줄, `main` 직접 푸시 |
| 수명 | 이슈 하나당 브랜치 하나, 병합 후 삭제 |

예시

- `feat/1-setup-llm-env`
- `feat/5-combined-chain`
- `fix/3-urgency-prompt-typo`
- `docs/7-update-readme`

## 커밋 컨벤션

[Conventional Commits 1.0.0](https://www.conventionalcommits.org/ko/v1.0.0/) 을 따릅니다. 상세 규칙·scope·예시는
[`.claude/skills/commit-convention/SKILL.md`](.claude/skills/commit-convention/SKILL.md) 를 참고하세요. (Claude Code 에서는 `commit-convention` 스킬로 자동 적용됩니다.)

```
feat(translate): 번역 체인 구현

Closes #2
```

## 주의

- `.env` 와 API 키는 절대 커밋하지 않습니다.
- 다른 사람의 영역, 함수 이름, 입력 변수 이름은 바꾸지 않습니다. (체인 결합이 이름에 의존합니다)
