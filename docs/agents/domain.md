# Domain docs

Some skills (`improve-codebase-architecture`, `diagnose`, `tdd`) read a `CONTEXT.md` file to learn the project's domain language, and `docs/adr/` for past architectural decisions. This file tells those skills where to look and how to consume what they find.

## Layout

This repo uses a **single-context** layout:

- `CONTEXT.md` at the repo root — one global context file
- `docs/adr/` at the repo root — architectural decision records

If you later split into a monorepo with separate frontend/backend domains, switch to a multi-context layout by adding a `CONTEXT-MAP.md` at the root.

## Consumer rules

When a skill reads domain docs:

1. **CONTEXT.md** — read the full file. It describes the project's domain language, goals, and constraints. Treat it as ground truth for naming and terminology.
2. **docs/adr/** — read ADR files (named `NNNN-title.md`) to understand past decisions. Don't re-litigate settled architecture without a new ADR.
3. If `CONTEXT.md` does not exist, treat the project as having no domain context — proceed without it, but note the gap in your output.

## Creating CONTEXT.md

If you're bootstrapping a new project, create `CONTEXT.md` with:

```markdown
# Context

## What is this project?

[One paragraph description]

## Domain language

[Key terms and their meanings]

## Goals

[What the project is trying to achieve]

## Constraints

[Technical or business constraints]
```

## Creating ADRs

When making a significant architectural decision, create `docs/adr/NNNN-title.md`:

```markdown
# N: Title of Decision

## Status

Accepted

## Context

[What is the issue we're seeing that motivates this decision?]

## Decision

[What is the change we're proposing?]

## Consequences

[What are the trade-offs?]
```

Number ADRs sequentially (0001, 0002, etc.).
