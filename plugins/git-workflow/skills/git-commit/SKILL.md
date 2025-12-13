---
name: Git Commit Workflow
description: This skill should be used when the user requests to commit changes to the repository (e.g., "commit", "create a commit"). Provides workflow guidance for creating semantic, well-structured Git commits.
---

# Git Commit Workflow

This skill provides procedural knowledge for creating well-structured Git commits with semantic messages that focus on intent and motivation.

## Safety Constraints

- Never update git config
- Never push to remote repository (unless explicitly requested)
- Never use interactive flags (e.g., `-i`, `-p`)
- Never skip hooks (`--no-verify` prohibited unless explicitly requested)
- Never create empty commits when no changes exist

## Procedure

### 1. Validate Changes

Before proceeding, verify changes exist and are safe to commit:

```bash
# Check for changes
git status
git --no-pager diff HEAD
```

**Stop conditions:**
- No changes exist (empty diff, nothing to stage) → Report and stop
- Secrets or sensitive data detected (API keys, tokens, passwords, private keys, `.env` files, credential files) → Report and stop

### 2. Analyze and Draft Message

Review the changes to understand:
- Nature of the change (feature, fix, refactor, etc.)
- Scope of impact (which components/modules affected)
- Motivation behind the change

Draft a commit message following the style guide below.

### 3. Stage and Commit

```bash
# Stage relevant files
git add <files>

# Verify staged content
git --no-pager diff --cached

# Commit using HEREDOC format
git commit -m "$(cat <<'EOF'
<type>(<scope>): <subject>

<body>
EOF
)"
```

**Staging guidelines:**
- Include only files that support the intended change
- Exclude unrelated or transient artifacts
- Double-check staged files before committing

### 4. Handle Pre-commit Hooks

If pre-commit hooks modify files:

1. **Hook fails with changes**: Retry commit once to include hook-made changes
2. **Hook succeeds but modifies files**: Amend to include those changes
3. **Hook still fails after retry**: Stop and report error details (do not force through)

Before amending, verify:
```bash
# Check HEAD commit authorship
git log -1 --format='[%h] (%an <%ae>) %s'

# Ensure commit is not pushed
git status  # Should show "Your branch is ahead"
```

### 5. Verify and Report

After successful commit:

```bash
# Verify clean state
git status

# Show commit details
git --no-pager log -1 --stat
```

Report:
- Commit hash and subject
- List of changed files
- Any remaining unstaged changes

## Commit Message Style

### Format

```
<type>(<scope>): <subject>

<body>
```

- `<type>`: Required - nature of change
- `<scope>`: Optional - affected component/module
- `<subject>`: Required - concise description (≤50 chars ideal, ≤72 max)
- `<body>`: Optional - motivation and context (1-2 sentences)

### Types

- `feat`: User-facing feature
- `fix`: User-facing bug fix
- `docs`: Documentation only
- `style`: Formatting, no logic change
- `refactor`: Code change without behavior change
- `test`: Add/modify tests only
- `chore`: Maintenance, tooling, infrastructure

### Examples

```
feat: add hat wobble animation

Introduces smooth wobble effect for hat accessories.
```

```
fix(search): prevent crash on empty query

Guards against null input that caused IndexError.
```

```
refactor(auth): extract token validation logic

Improves testability by separating validation concerns.
```

### HEREDOC Template

Always use HEREDOC for multi-line messages:

```bash
git commit -m "$(cat <<'EOF'
<type>(<scope>): <subject>

<body focusing on the "why" (1-2 sentences)>
EOF
)"
```

## Quick Reference

### Validation Checklist

- Changes exist (non-empty diff)
- No secrets in staged files
- All staged files are intentional
- Commit message follows format
- Subject line ≤72 characters
- Body explains motivation (if needed)

### Common Pitfalls

- Committing unrelated changes together
- Vague messages like "fix bug" or "update code"
- Missing the "why" in the body
- Staging generated or temporary files
