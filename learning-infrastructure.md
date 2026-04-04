# Learning Infrastructure

Last updated: 2026-04-04

## 1) Daily Execution Loop (Day5+)

1. Build output in `training/day-xx/`
2. Push branch
3. Open PR
4. Confirm Slack notification
5. Resolve comments
6. Merge

This is the mandatory completion loop.

If reviewer response is delayed, mark temporary completion as:
- PR opened
- Slack notification confirmed
- Quiz passed (100)

Convert to final completion after merge.

## 2) Quiz Loop

1. Read assigned resources
2. Take Google Forms quiz
3. Retake until 100%
4. Attach evidence in PR body
5. Merge only after quiz pass

## 3) Async Review Rules

- No progress blocking by in-person mentor explanation.
- Questions should be handled by docs, linked resources, and PR comments.
- Reviews should happen asynchronously in GitHub.

## 4) PR Body Template (Minimum)

- Objective of the day
- Output paths
- Quiz evidence (score 100)
- Links to resources used
- Review points

## 5) Local Private Context Policy

- Public repo must not include confidential internal business details.
- If internal context is needed, keep it in:
  - `references/farleap-context.local.md` (gitignored)
