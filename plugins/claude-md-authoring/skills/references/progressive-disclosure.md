# Progressive Disclosure

## Contents

- Concept
- Directory Structure
- CLAUDE.md Reference Section
- Reference Section Patterns
- File Content Guidelines
- Pointer vs Copy

---

## Concept

Instead of putting everything in CLAUDE.md, store task-specific information in separate files. Claude reads them only when needed, keeping the context window focused.

## Directory Structure

Recommended structure:

```
project/
├── CLAUDE.md              # Universal info only (<100 lines)
└── agent_docs/            # Task-specific documentation
    ├── building.md
    ├── testing.md
    ├── database.md
    ├── deployment.md
    └── code_patterns.md
```

## CLAUDE.md Reference Section

In CLAUDE.md, include a brief index:

```markdown
## Documentation

Read relevant docs before starting work:

- `agent_docs/building.md` - Build commands and troubleshooting
- `agent_docs/testing.md` - Test commands, fixtures, mocking patterns
- `agent_docs/database.md` - Schema, migrations, query patterns
- `agent_docs/deployment.md` - Deploy process, environments, rollback
- `agent_docs/code_patterns.md` - Preferred patterns for common tasks
```

## Reference Section Patterns

When writing the reference section in CLAUDE.md, use one of these patterns:

**Autonomous (recommended for most projects)**:
```markdown
Before starting work, review relevant files in `agent_docs/` to understand conventions and patterns.
```

**Approval-based (for sensitive projects)**:
```markdown
Before starting work, list which `agent_docs/` files you plan to read and wait for approval.
```

## File Content Guidelines

Each agent_docs file should:

- Focus on one topic
- Be self-contained (no dependencies on other agent_docs)
- Use file:line references instead of code snippets
- Start with a brief summary of when to use this file

**Example agent_docs/database.md**:
```markdown
# Database Guidelines

Read this when: creating migrations, writing queries, modifying schemas.

## Schema Location
See `src/models/` for all table definitions.

## Migration Commands
- Create: `alembic revision --autogenerate -m "description"`
- Apply: `alembic upgrade head`
- Rollback: `alembic downgrade -1`

## Query Patterns
For complex queries, reference `src/repositories/user_repository.py:45-60` for the preferred pattern.
```

## Pointer vs Copy

**Bad (copy)**:
```markdown
Use this pattern for repository methods:
```python
async def get_by_id(self, id: int) -> Model | None:
    result = await self.session.execute(
        select(Model).where(Model.id == id)
    )
    return result.scalar_one_or_none()
```

**Good (pointer)**:
```markdown
For repository patterns, see `src/repositories/base.py:20-35`.
```

Pointers prevent staleness and reduce token usage.
