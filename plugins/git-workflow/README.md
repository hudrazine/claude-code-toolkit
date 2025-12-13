# git-workflow

Git commit and Pull Request workflow commands with semantic message guidance.

## Features

This plugin provides:

- **`/commit`** - Create well-structured Git commits with semantic messages
- **`/draft-pr`** - Create Draft Pull Requests using GitHub CLI

Both commands are backed by Skills that provide workflow knowledge, enabling natural language requests like "commit my changes" or "create a PR".

## Commands

### /commit

Creates a single Git commit from staged/unstaged changes.

- Analyzes changes and drafts semantic commit messages
- Follows Conventional Commits format (`feat`, `fix`, `docs`, etc.)
- Validates for secrets and sensitive data before committing

### /draft-pr

Creates a Draft Pull Request from the current branch.

- Runs quality gates (lint, test, build) before PR creation
- Drafts title and body following semantic conventions
- Requires user approval before creating the PR

## Skills

| Skill | Triggers |
|-------|----------|
| Git Commit Workflow | "commit", "create a commit" |
| Draft Pull Request Workflow | "create PR", "draft PR", "open PR" |

Skills are automatically activated when you mention relevant keywords, even without using slash commands.

## Safety

Both workflows enforce safety constraints:

- Never push to remote without explicit request
- Never skip pre-commit hooks
- Never include secrets in commits or PR descriptions
- Never force-push or rebase without explicit request
