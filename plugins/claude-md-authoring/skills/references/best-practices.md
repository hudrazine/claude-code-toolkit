# Best Practices

## Contents

- Instruction Limits Research
- File Length Guidelines
- Content Quality Checklist
- Effective Content Examples
- Identifying Content at Risk of Being Ignored

---

## Instruction Limits Research

Research indicates:

- Frontier thinking LLMs follow ~150-200 instructions consistently
- Smaller models exhibit exponential decay in instruction-following as count increases
- Larger thinking models show linear decay (more graceful degradation)
- LLMs bias toward instructions at context peripheries (beginning and end)
- As instruction count increases, compliance decreases uniformly across all instructions

**Practical implication**: Claude Code's system prompt uses ~50 instructions. The CLAUDE.md competes for the remaining capacity.

## File Length Guidelines

| Length | Assessment |
|--------|------------|
| <60 lines | Excellent (HumanLayer's production setup) |
| <100 lines | Very good |
| <300 lines | Acceptable maximum |
| >300 lines | Needs refactoring |

## Content Quality Checklist

Before including any content, evaluate:

1. Does this apply to >80% of tasks the user will perform?
2. Is this something the operating Claude couldn't infer from the codebase?
3. Would removing this cause repeated failures?
4. Is this the most concise way to express this?

If any answer is "no," reconsider including it.

## Effective Content Examples

**Good: Concise project overview**
```markdown
## Project
E-commerce API built with FastAPI + PostgreSQL. Monorepo with:
- `/api` - FastAPI backend
- `/shared` - Common models and utilities
- `/scripts` - Deployment and maintenance scripts
```

**Good: Essential commands**
```markdown
## Commands
- Build: `make build`
- Test: `make test`
- Lint: `make lint` (auto-fixes issues)
```

**Good: Non-obvious conventions**
```markdown
## Conventions
- Use `bun` instead of `npm`
- Environment variables in `.env.local` (never commit)
- All API routes require authentication except `/health`
```

## Identifying Content at Risk of Being Ignored

Claude Code wraps CLAUDE.md with:
```
<system-reminder>
IMPORTANT: this context may or may not be relevant to your tasks.
You should not respond to this context unless it is highly relevant to your task.
</system-reminder>
```

When reviewing or creating CLAUDE.md, flag content that may be ignored by the operating Claude:

1. **Check relevance**: Is the instruction universally applicable?
2. **Check specificity**: Is it too detailed for general tasks?
3. **Recommend separation**: Task-specific content should be in agent_docs/
4. **Reduce total length**: Shorter files have higher signal-to-noise ratio
