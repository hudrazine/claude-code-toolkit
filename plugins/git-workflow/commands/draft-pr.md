---
description: Create a Draft Pull Request from the current branch using GitHub CLI.
model: sonnet
allowed-tools: Bash(git rev-parse:*), Bash(git status:*), Bash(git branch:*), Bash(git log:*), Bash(git --no-pager log:*), Bash(gh pr:*), Bash(gh repo:*), Skill, Read, Grep, Glob, AskUserQuestion
disable-model-invocation: true
---

## Context

- Current branch: !`git rev-parse --abbrev-ref HEAD`
- Branch status: !`git status -sb`
- Remotes: !`git remote -v`
- Recent commits: !`git --no-pager log --oneline -10`
- Existing PRs from this branch: !`gh pr list --limit 5 --head $(git rev-parse --abbrev-ref HEAD) 2>/dev/null || echo "None"`

## Your task

Based on the above context, create a Draft Pull Request for this branch.

1. First, use the Skill tool to invoke `git-workflow:draft-pr` skill for detailed workflow guidance
2. Follow the skill's procedure to create a well-structured Draft PR

**IMPORTANT**: DO NOT open browser (`--web` is prohibited). DO NOT force-push or rebase unless explicitly instructed.
