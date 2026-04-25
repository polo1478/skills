# Skills

This repository contains Codex skills that can be installed or copied into a local skills directory.

## Included Skills

### `commit-message-writer`

Write clear git commit messages from repository changes.

- Inspect staged changes before unstaged changes
- Prefer concise conventional commit subjects
- Fall back to project context when a git diff is unavailable

## Structure

Each skill lives in its own folder and includes:

- `SKILL.md` for trigger and workflow instructions
- `agents/openai.yaml` for UI metadata

## Usage

Place a skill folder in your Codex skills directory, then invoke it by name in a prompt.

Example:

```text
Use $commit-message-writer to write a concise commit message from my current git diff.
```
