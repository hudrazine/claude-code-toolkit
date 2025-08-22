# Prompt Templates for Claude Code

Reusable prompt templates designed for import into CLAUDE.md files. Import these to maintain consistent development principles and workflows across projects.

## Available Prompts

### 🎯 `principles.md` - Universal Development Principles
Comprehensive software engineering principles and best practices for senior-level development.

**Key Features:**
- SOLID principles and core design patterns (DRY, KISS, YAGNI)
- Senior developer mindset and decision-making frameworks
- AI-driven development principles
- Ethical guidelines and quality philosophy

**Best for:**
- Establishing project coding standards
- Ensuring consistent architectural decisions
- Maintaining high code quality standards

### 🧭 `meta-router-protocol.md` - Complex Problem-Solving Framework
Systematic framework for tackling complex problems with adaptive thinking strategies.

**Key Features:**
- Problem characteristics assessment (action requirements, solution space, complexity)
- Method selection (Meta-ReAct, Meta-Tree, or Hybrid protocols)
- Sequential-thinking integration for dynamic strategy adaptation
- Automatic activation for complex problems

**Best for:**
- Complex multi-step tasks requiring strategic planning
- Problems with unclear solution paths
- Tasks needing adaptive problem-solving approaches
- Situations requiring both design thinking and implementation

## Usage

### Basic Import
Add to your project's CLAUDE.md:
```markdown
## Additional Instructions
- @prompts/principles.md
```

### Combining Templates
Stack multiple prompts for comprehensive coverage:
```markdown
## Project Guidelines
- @prompts/principles.md
- @prompts/security-guidelines.md
- @prompts/testing-standards.md
```
