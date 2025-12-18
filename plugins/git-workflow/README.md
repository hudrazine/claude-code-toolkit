# git-workflow

Git commit and Pull Request workflow commands with semantic message guidance.

## Features

This plugin provides:

- **`/commit`** - Create well-structured Git commits with Conventional Commits format
- **`/draft-pr`** - Create Draft Pull Requests using GitHub CLI (backed by Skill for natural language triggers)

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
| Draft Pull Request Workflow | "create PR", "draft PR", "open PR" |

The Draft PR skill is automatically activated when you mention relevant keywords, even without using the slash command.

## Safety

Both workflows enforce safety constraints:

- Never push to remote without explicit request
- Never skip pre-commit hooks
- Never include secrets in commits or PR descriptions
- Never force-push or rebase without explicit request
