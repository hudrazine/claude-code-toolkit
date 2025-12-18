# Anti-Patterns

## Contents

- Code Style Guidelines
- Exhaustive Command Lists
- Task-Specific Instructions in Root
- Embedded Code Snippets
- Hotfix Accumulation
- Negative Instructions

---

When creating or reviewing CLAUDE.md, identify and refactor these patterns. Each section shows the problem, a bad example, and the recommended solution.

## ❌ Code Style Guidelines

**Problem**: Style rules add many instructions that degrade overall compliance.

**Bad**:
```markdown
## Code Style
- Use 2 spaces for indentation
- Always use trailing commas
- Prefer `const` over `let`
- Use arrow functions for callbacks
- ...
```

**Solution**: Use ESLint, Prettier, Biome, or equivalent. Set up a Stop hook to run formatters.

## ❌ Exhaustive Command Lists

**Problem**: Listing every possible command bloats the file.

**Bad**:
```markdown
## Commands
- `npm run dev` - Start dev server
- `npm run build` - Build for production
- `npm run test` - Run tests
- `npm run test:watch` - Run tests in watch mode
- `npm run test:coverage` - Run tests with coverage
- `npm run lint` - Run linter
- `npm run lint:fix` - Run linter with auto-fix
- `npm run typecheck` - Run TypeScript check
- `npm run format` - Format code
- `npm run db:migrate` - Run migrations
- `npm run db:seed` - Seed database
- `npm run db:reset` - Reset database
...
```

**Solution**: Include only essential commands. Claude can read `package.json` for others.

```markdown
## Commands
Build: `npm run build` | Test: `npm test` | Lint: `npm run lint:fix`
```

## ❌ Task-Specific Instructions in Root

**Problem**: Instructions that apply to specific tasks get ignored in other contexts.

**Bad**:
```markdown
## Database Schema Guidelines
When creating new tables:
1. Use snake_case for column names
2. Always include created_at and updated_at
3. Use UUID for primary keys
...
```

**Solution**: Move to `agent_docs/database.md` and reference it.

## ❌ Embedded Code Snippets

**Problem**: Code snippets become outdated and waste tokens.

**Bad**:
```markdown
## Auth Pattern
```typescript
const authenticate = async (req, res, next) => {
  const token = req.headers.authorization?.split(' ')[1];
  if (!token) return res.status(401).json({ error: 'No token' });
  // ... 20 more lines
};
```

**Solution**: Reference the actual file.

```markdown
## Auth
See `src/middleware/auth.ts` for authentication pattern.
```

## ❌ Hotfix Accumulation

**Problem**: Appending fixes for specific issues creates a sprawling file.

**Bad**:
```markdown
## Notes
- Don't use deprecated `findOne` method
- Remember to close database connections
- The auth middleware expects Bearer token format
- Don't forget to handle null cases in user lookup
- ...
```

**Solution**: If an instruction applies universally, integrate it properly. If it's task-specific, move to agent_docs. If it's a code pattern, let the codebase demonstrate it.

## ❌ Negative Instructions

**Problem**: "Don't do X" instructions are less effective than positive guidance.

**Bad**:
```markdown
- Don't use `var`, use `const` or `let`
- Don't write functions longer than 50 lines
- Don't forget error handling
```

**Solution**: State what to do, or use linters for enforcement.

```markdown
Prefer small, focused functions. See `src/utils/` for examples.
```
