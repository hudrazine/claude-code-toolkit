---
description: Create a single Git commit for the current repository changes.
allowed-tools: Bash(git status:*), Bash(git diff:*), Bash(git --no-pager diff:*), Bash(git branch:*), Bash(git log:*), Bash(git --no-pager log:*), Bash(git add:*), Bash(git commit:*), Skill
model: sonnet
disable-model-invocation: true
---

## Your task

Create a single git commit for the current repository changes.

1. First, use the Skill tool to invoke `git-workflow:git-commit` skill
2. Follow the skill's procedure

**IMPORTANT**: DO NOT push to remote repository unless explicitly requested.
