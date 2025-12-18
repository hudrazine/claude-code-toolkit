---
description: Create a single Git commit for the current repository changes.
allowed-tools: Bash(git status:*), Bash(git diff:*), Bash(git --no-pager diff:*), Bash(git branch:*), Bash(git log:*), Bash(git --no-pager log:*), Bash(git add:*), Bash(git commit:*)
model: sonnet
---

## Context

- Current git status: !`git status`
- Current git diff (staged and unstaged changes): !`git --no-pager diff HEAD`
- Current branch: !`git branch --show-current`
- Recent commits: !`git --no-pager log --oneline -10`

## Task

Create a git commit for the current repository changes using Conventional Commits format.

## Commit Message Format

```
<type>(<scope>): <subject>

<body>
```

### Types

- `feat`: User-facing feature
- `fix`: User-facing bug fix
- `docs`: Documentation only
- `style`: Formatting, no logic change
- `refactor`: Code change without behavior change
- `test`: Add/modify tests only
- `chore`: Maintenance, tooling, infrastructure

### Guidelines

- `<scope>`: Optional - affected component/module
- `<subject>`: ≤50 chars ideal, ≤72 max
- `<body>`: Focus on the "why", not the "what" (1-2 sentences)

## Additional Checks

Before committing, verify no secrets are staged:
- API keys, tokens, passwords
- `.env` files, credential files
- Private keys

If detected, report and stop.
