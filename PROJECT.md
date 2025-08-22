# Project Information

## Executive Summary

This is a **Claude Code Enhancement Toolkit** - a collection of templates, systems, and methodologies that extend Claude Code's capabilities through its native features (Memory management, Subagents, and Slash commands).

## Project Purpose

- **Claude Code Enhancement**: Specialized tools and workflows for Claude Code
- **Reusable Templates**: Battle-tested patterns adaptable for any project

## Architecture

```
claude-code-agents/
├── memory-bank-system/    # Persistent context management
├── agents/               # Universal subagent templates
├── commands/             # Custom slash commands
├── prompts/              # Reusable prompt templates
└── references/           # Claude Code documentation
```

## Components

Each component has its own CLAUDE.md with detailed guidance:

- **Memory Bank** (`memory-bank-system/`) - Structured memory across sessions
- **Universal Agents** (`agents/`) - Generic templates for common tasks
- **Custom Commands** (`commands/`) - Reusable slash commands for various tasks
- **Prompts Library** (`prompts/`) - Reusable prompt templates

## References

Documentation on Claude Code features and specifications that should be understood when enhancing Claude Code in this repository:

- Memory management: @references/claude-code-memory.md
- Slash commands: @references/claude-code-slash-commands.md
- Subagents: @references/claude-code-sub-agents.md

Documents useful for prompt engineering:

- Claude 4 prompt engineering best practices: `references/claude-4-best-practices.md`
- Role with system prompt: `references/claude-system-prompt-engineering.md`
- Extended thinking tips: `references/claude-extended-thinking-tips.md`

## Prompt Engineering Tips

When creating prompts for Claude Code enhancement, keep these key architectural considerations in mind:

### Custom Slash Commands
- Think of custom slash commands as **user prompt shortcuts** - they're templates for common requests
- Commands are **user-initiated prompts** to Claude Code, not auto-executable scripts
- Claude Code cannot automatically trigger slash commands on its own

### Subagent Architecture (Task tool)
- Subagents automatically load CLAUDE.md files into their system prompt context, just like the main Claude Code instance
- Subagents are **initiated by Claude Code** (the parent agent) or by other subagents
- Subagents cannot enable Claude's native Extended thinking feature, but the sequential-thinking tool can be used as an alternative
- Subagents **do not recognize themselves as subagents** - they perceive themselves as the main Claude Code instance despite operating in isolated contexts

---

_This toolkit represents ongoing research in Claude Code enhancement and AI-assisted development methodologies._

--- END_OF_CONTENTS ---
