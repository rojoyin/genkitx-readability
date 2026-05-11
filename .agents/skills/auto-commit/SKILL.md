---
name: auto-commit
description: Stages all changes, generates a conventional commit message from the diff, and commits. Use when the user asks to commit, save changes, or auto-commit.
---

# Auto-commit

## Workflow

1. Run `git status` to see what will be committed
2. Run `git diff --staged` and `git diff` to understand the changes
3. Stage everything: `git add .`
4. Generate a commit message following Conventional Commits format:
   - `feat:` new feature
   - `fix:` bug fix
   - `refactor:` code change without behavior change
   - `docs:`, `test:`, `chore:` as appropriate
   - Keep the subject line under 72 characters, imperative mood
5. Commit: `git commit -m "<generated message>"`
6. Confirm by showing `git log -1 --oneline`

## Gotchas

- Never commit if `git status` shows merge conflicts — stop and report.
- Do not include secrets, `.env` files, or large binaries. Check `git diff --staged --name-only` first.
- If pre-commit hooks modify files, re-stage and retry once.