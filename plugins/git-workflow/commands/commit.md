---
description: Create a single Git commit for the current repository changes.
model: sonnet
allowed-tools: Bash(git status:*), Bash(git diff:*), Bash(git --no-pager diff:*), Bash(git branch:*), Bash(git log:*), Bash(git --no-pager log:*), Bash(git add:*), Bash(git commit:*), Skill, Read, Grep, Glob, AskUserQuestion
disable-model-invocation: true
---

## Context

- Current git status: !`git status`
- Current git diff (staged and unstaged changes): !`git --no-pager diff HEAD`
- Current branch: !`git branch --show-current`
- Recent commits: !`git --no-pager log --oneline -10`

## Your task

Based on the above changes, create a single git commit.

1. First, use the Skill tool to invoke `git-workflow:git-commit` skill for detailed workflow guidance
2. Follow the skill's procedure to create a well-structured commit

**IMPORTANT**: DO NOT push to remote repository. Only create the local commit unless explicitly requested.
