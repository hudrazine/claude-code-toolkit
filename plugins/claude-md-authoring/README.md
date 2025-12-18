# claude-md-authoring

Guide for writing and optimizing CLAUDE.md files following context engineering best practices.

## Features

This plugin provides guidance for:

- Creating new CLAUDE.md files with proper structure
- Optimizing existing CLAUDE.md files for better instruction compliance
- Reviewing CLAUDE.md for common anti-patterns
- Troubleshooting why Claude ignores instructions

Also applicable to AGENTS.md for other AI coding agents.

## Skills

| Skill | Triggers |
|-------|----------|
| CLAUDE.md Authoring | "create CLAUDE.md", "improve CLAUDE.md", "review CLAUDE.md", "Claude ignores instructions" |

## Key Concepts

The skill teaches three core principles:

1. **Less is more** - Frontier models follow ~150-200 instructions; keep CLAUDE.md under 300 lines
2. **Universal applicability** - Include only content that applies to most tasks
3. **Progressive disclosure** - Store task-specific content in separate `agent_docs/` files

## References

Detailed guidance is organized into separate documents:

- `references/best-practices.md` - File length guidelines, content quality checklist
- `references/anti-patterns.md` - Common mistakes and how to fix them
- `references/progressive-disclosure.md` - Directory structure and file organization

## Credits

This skill is inspired by [Writing a good CLAUDE.md](https://www.humanlayer.dev/blog/writing-a-good-claude-md) by HumanLayer.
