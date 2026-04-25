---
name: commit-message-writer
description: Write clear git commit messages from repository changes. Use when Codex needs to inspect staged or unstaged diffs, summarize file changes, propose conventional commit subjects, or explain the main purpose of the current git diff.
---

# Commit Message Writer

Inspect the repository before drafting anything.

## Workflow

1. Check staged changes first.
2. If nothing is staged, inspect unstaged changes.
3. Summarize the highest-impact change rather than listing every file.
4. Write the subject in imperative mood.
5. Add a body only when it clarifies scope, motivation, or notable side effects.

## Output Format

Prefer conventional commit style when it fits:

- `feat: add keyboard shortcuts for search`
- `fix: handle empty API responses in dashboard`
- `refactor: simplify token validation flow`
- `docs: clarify local setup steps`
- `test: cover pause toggle behavior`
- `chore: update lint configuration`

Keep the subject under 72 characters when possible.

## Diff Inspection Rules

Check `git diff --staged` before `git diff`.

If both staged and unstaged changes exist, base the commit message on staged changes unless the user explicitly asks for everything.

If the repository is missing, git is unavailable, or there is no diff to inspect, say that directly and offer the best commit message you can infer from the available project context.

## Heuristics

Use `feat` for new user-facing behavior.

Use `fix` for bug fixes or regressions.

Use `refactor` for internal restructuring without intended behavior changes.

Use `docs` for documentation-only changes.

Use `test` for test-only additions or updates.

Use `chore` for maintenance, tooling, or configuration work.

Favor a single, specific change over broad wording like `update project files`.
