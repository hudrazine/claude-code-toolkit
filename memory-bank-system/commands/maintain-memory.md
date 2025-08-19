---
description: Perform Memory Bank maintenance (archiving, cleanup, pattern promotion)
allowed-tools: Task
argument-hint: [force]
---

Use the memory-bank-maintenance agent to perform Memory Bank maintenance tasks.

The maintenance agent will:
- Archive old entries from activeContext.md (>30 days)
- Archive completed items from progress.md (monthly)
- Promote recurring patterns to systemPatterns.md
- Keep files within size thresholds
- Update archive indexes

Maintenance scope: $ARGUMENTS

Run comprehensive Memory Bank maintenance to keep files clean and performant.