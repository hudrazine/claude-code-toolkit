# Custom Slash Commands for Claude Code

Utility commands that extend Claude Code's capabilities through slash commands.

## Available Commands

### 📝 `/commit` - Create Git Commit
Intelligently creates a git commit based on current changes in your repository.

**Features:**
- Automatically analyzes staged and unstaged changes
- Reviews recent commit history to maintain consistent commit message style
- Creates descriptive commit messages based on the changes
- **Safety**: Only creates local commits, never pushes to remote unless explicitly requested

**Example use:**
```
/commit
```

The command will:
1. Check current git status and changes
2. Review recent commits for style consistency
3. Create an appropriate commit message
4. Create the commit locally (without pushing)

## Usage

### Installation
1. **For your project**: Copy command files to `.claude/commands/` in your project
2. **For global use**: Copy to `~/.claude/commands/` in your home directory

### Basic Syntax
```
/<command-name> <your question or task>
```
