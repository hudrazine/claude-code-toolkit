---
description: Create a Draft Pull Request from the current branch using GitHub CLI.
model: sonnet
allowed-tools: Bash(git rev-parse:*), Bash(git status:*), Bash(git branch:*), Bash(git log:*), Bash(git --no-pager log:*), Bash(gh pr:*), Bash(gh repo:*), Skill, Read, Grep, Glob, AskUserQuestion
disable-model-invocation: true
---

## Your task

Create a Draft Pull Request for the current branch.

1. First, use the Skill tool to invoke `git-workflow:draft-pr` skill
2. Follow the skill's procedure

**IMPORTANT**: DO NOT open browser (`--web` is prohibited). DO NOT force-push or rebase unless explicitly requested.
