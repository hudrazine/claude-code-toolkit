---
description: Initialize Memory Bank structure for persistent context
allowed-tools: Read, Write, LS, Glob
---

# Initialize Memory Bank System

Create a Memory Bank structure to maintain project context across Claude Code sessions.

## Analysis Phase

Gather information from sources in priority order:
1. **Existing Memory Bank**: Check `memory-bank/projectbrief.md`
2. **Project Documentation**: Read README.md
3. **Configuration Files**: package.json, pyproject.toml, go.mod, Cargo.toml, etc.
4. **Directory Structure**: Analyze project layout

Priority: projectbrief.md > README.md > configs > structure

## Execution Decision

### Scenario A: Limited Information
If no projectbrief.md AND insufficient project information:
- Create ONLY `memory-bank/projectbrief.md` template
- Include guided prompts and examples
- Instruct user to complete and re-run command

### Scenario B: Full Initialization
If projectbrief.md exists OR sufficient information available:
- Use existing projectbrief.md as primary source
- Create all 6 Memory Bank files
- Auto-extract available information
- Add TODOs for missing sections

## Implementation Details

### Scenario A: Template Creation
Create `memory-bank/projectbrief.md` with guided template containing:
- Project Name (with directory reference)
- One-line Description (with examples)
- Why This Exists (problem/motivation prompts)
- Target Users (with examples)
- Core Features (3 TODO items)
- Technologies Used (auto-detect when possible)
- Current Status (development state)
- Success Criteria (goal definition)

Output summary includes:
- Created files
- Detected information (language, directory)
- Clear next steps for user

### Scenario B: Full Initialization

Create all 6 Memory Bank files based on claude-memory-bank.md structure:

1. **memory-bank/projectbrief.md** (if not exists)
   - Extract: name, description, features from README/configs
   - Auto-detect: technologies, status
   - Add TODOs for missing sections

2. **memory-bank/productContext.md**
   - Why this exists, target users, value proposition
   - Extract from projectbrief.md or README
   - TODOs for UX goals

3. **memory-bank/activeContext.md**
   - Current focus, recent changes, next steps
   - Include initialization date
   - Extract from git activity if available

4. **memory-bank/systemPatterns.md**
   - Project structure (auto-generate tree)
   - Architecture overview, key components
   - TODOs for patterns and critical paths

5. **memory-bank/techContext.md**
   - Auto-detect: language, framework, build tools
   - Extract: dependencies, scripts
   - TODOs for constraints

6. **memory-bank/progress.md**
   - Completed, in progress, planned items
   - Extract from README/issues
   - Decision log with initialization record

## Output Summary

Display comprehensive initialization report:
- Information sources analyzed
- Files created/preserved
- Auto-detected project details (language, framework, tools)
- Integration statistics (auto-filled vs TODOs)
- Clear next steps for user

## Key Principles

- Two-phase approach: template first if information limited
- Preserve existing Memory Bank files
- Use projectbrief.md as primary source when available
- Maximize auto-extraction before adding TODOs
- Provide transparent source tracking
- Guide users with clear next steps
