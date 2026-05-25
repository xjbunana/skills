---
name: feature-design-flow
description: Turn a feature idea, rough requirement, or product discussion into an AI-ready design document flow. Use when Codex needs to help plan software features before implementation; create or maintain requirement docs, QA decision records, module breakdowns, common project context, module design docs, progress gates, or cross-document design reviews; enforce a human-in-the-loop flow from requirements to reviewed design before coding.
---

# Feature Design Flow

Use this skill to guide a feature from fuzzy intent to reviewed design documents that another AI coding session can implement safely. The goal is not to over-document; the goal is to make assumptions, decisions, module boundaries, and review gates explicit.

## Core Rule

Separate design from development. Do not start implementation until the design stage is complete, cross-checked, and confirmed by the user.

The durable flow is:

```text
feature idea -> requirement doc -> QA decision record -> design overview
-> common context -> module design docs -> progress gate
-> cross-document review -> confirmed revisions -> development
```

## When Starting

Inspect existing docs first if the project already has them. Look for paths such as `docs/intention/`, `docs/design/`, `docs/requirements/`, `docs/recheck/`, `CLAUDE.md`, or project-specific planning files.

If no structure exists, create a feature-scoped docs directory such as:

```text
docs/<feature-name>/
├── 1-requirements.md
├── 2-qa-decisions.md
├── 3-design-overview.md
├── design/
│   ├── 00-common-context.md
│   ├── 01-<module>.md
│   ├── ...
│   └── PROGRESS.md
└── recheck/
    ├── REVIEW_TEMPLATE.md
    └── design-review.md
```

Adapt names and language to the repository conventions.

## Document Roles

Keep each document focused:

- Requirement doc: business goal, scope, non-goals, user flows, data/API expectations, acceptance criteria.
- QA decision record: questions, tradeoffs, decisions, open items, and why choices were made.
- Design overview: module split, dependencies, document map, design/development order.
- Common context: stable project conventions that every module design and coding session must read first.
- Module design: one implementation unit with dependencies, data shapes, APIs, service logic, edge cases, and verification points.
- Progress doc: gatekeeper for design and development status. Require confirmation before marking stages complete.
- Recheck doc: cross-document issues, severity, status, decision, and required edits.

For more detail, read `references/document-roles.md`.

## Design Workflow

1. Capture requirements.
   - Extract goals, non-goals, actors, flows, data, APIs, constraints, and acceptance criteria.
   - Mark assumptions and unresolved questions instead of pretending they are settled.

2. Run QA clarification.
   - Convert ambiguity into explicit questions and decisions.
   - Record decisions in the QA document with rationale and date when useful.

3. Split modules.
   - Build a dependency-ordered design overview.
   - Prefer modules that match code ownership and implementation boundaries.

4. Write common context.
   - Include only stable conventions: tech stack, package/layout rules, response formats, database conventions, auth/user context, reference code locations, and global error handling.
   - Avoid copying module-specific design into common context.

5. Write module design docs.
   - Start every module doc with purpose, dependencies, and status.
   - Include enough detail for AI implementation: paths, class/function names when known, request/response shapes, schema changes, service steps, edge cases, and verification.
   - Make each module doc mostly self-contained, while still linking to common context and dependencies.

6. Maintain progress gates.
   - Track design and development separately.
   - Do not mark a design document complete until the user confirms it.
   - After confirmation, re-check upstream docs and sync differences before moving forward.

7. Recheck before development.
   - Compare requirements, QA decisions, overview, common context, and module docs.
   - Record issues by severity and status.
   - Apply confirmed changes to source docs.
   - Only then enter development.

Use `references/flow-rules.md` for gatekeeping details and `references/review-checklist.md` for review coverage.

## Human Interaction

Treat human confirmation as part of the workflow, not an interruption.

Ask the user to confirm when:

- A requirement or module boundary changes the scope.
- A decision affects data model, auth, API contract, user-visible behavior, or development order.
- A design doc is about to be marked complete.
- A recheck issue is severe or has multiple valid fixes.
- The flow is ready to move from design to development.

Make reasonable low-risk wording and template choices yourself.

## Templates

Use the templates in `assets/templates/` when creating a new flow:

- `requirement.md`
- `qa-decisions.md`
- `design-overview.md`
- `common-context.md`
- `module-design.md`
- `progress.md`
- `review-template.md`

Copy only the templates needed for the user's task and adapt them to local naming conventions.
