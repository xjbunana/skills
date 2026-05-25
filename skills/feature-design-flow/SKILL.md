---
name: feature-design-flow
description: Turn a feature idea, rough requirement, or product discussion into an AI-ready design document flow. Use when Codex needs to help plan software features before implementation; create or maintain requirement docs, QA decision records, module breakdowns, common project context, module design docs, progress gates, or cross-document design reviews; enforce a human-in-the-loop flow from requirements to reviewed design before coding.
---

# Feature Design Flow

Use this skill to guide a feature from fuzzy intent to reviewed design documents that another AI coding session can implement safely. The goal is not to over-document; the goal is to make assumptions, decisions, module boundaries, and review gates explicit.

## Resource Location

Paths such as `references/...` and `assets/templates/...` are relative to the skill root directory, the same directory that contains `SKILL.md`.

When using bundled resources:

1. If the runtime provides the skill path, use that path as the skill root.
2. If only `SKILL.md` is known, use the directory containing `SKILL.md` as the skill root.
3. Read reference files from `<skill-root>/references/...`.
4. Copy templates from `<skill-root>/assets/templates/...`.

Do not resolve these paths from the project working directory. The project docs output directory and the skill installation directory are separate concepts.

## Flow Choice

Choose lightweight flow or full flow before creating documents.

Use lightweight flow when most of these are true:

- The feature affects only 1 or 2 modules.
- There is no complex data model or cross-system state transition.
- There are no external APIs, payment flows, permissions, audit requirements, AI tools, or prompt behavior risks.
- The user mainly needs a fast path from idea to implementable design.

Lightweight flow:

```text
requirement doc + QA decision record -> module design -> small recheck -> development
```

Use full flow when any of these are true:

- The feature spans 3 or more modules, frontend/backend boundaries, or multiple services.
- It includes database design, auth, state transitions, async work, or external dependencies.
- It includes AI prompts, tool calling, model behavior rules, or other unstable behavior.
- Multiple people will collaborate, or the feature needs long-term maintainability.
- The user explicitly asks for a standardized design document flow.

Full flow:

```text
feature idea -> requirement doc -> QA decision record -> design overview
-> common context -> module design docs -> progress gate
-> cross-document review -> confirmed revisions -> development
```

## Core Rule

Separate design from development. In full flow, do not start implementation until the design stage is complete, cross-checked, and confirmed by the user. In lightweight flow, still preserve requirements, key decisions, module design, and recheck conclusions.

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

For more detail, read `<skill-root>/references/document-roles.md`.

## Design Workflow

1. Capture requirements.
   - Extract goals, non-goals, actors, flows, data, APIs, constraints, and acceptance criteria.
   - Mark assumptions and unresolved questions instead of pretending they are settled.

2. Run QA clarification.
   - Convert ambiguity into explicit questions and decisions.
   - Record decisions in the QA document with rationale and date when useful.
   - Use only these QA statuses: confirmed, pending, deferred.

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
   - Before confirmation, check the document against the Definition of Done.
   - After confirmation, re-check upstream docs and sync differences before moving forward.

7. Recheck actively before development.
   - AI should compare requirements, QA decisions, overview, common context, and module docs, then output an issue summary.
   - The user confirms each issue decision: apply change, defer, or keep pending.
   - Only then enter development.

Use `<skill-root>/references/flow-rules.md` for gatekeeping details and `<skill-root>/references/review-checklist.md` for review coverage.

## Definition of Done

Before marking a design document complete, ensure:

- Goals, scope, and non-goals do not conflict.
- Key QA questions have statuses, and blockers are not ignored.
- Module dependencies and development order are clear.
- APIs include method, path, request example, response example, and error boundary when relevant.
- Data design includes fields, types, requiredness, status meanings, and query/index notes when relevant.
- Business logic covers the main path and at least one error or edge path.
- AI behavior includes prompt/tool trigger conditions, parameter sources, and response handling when relevant.
- Verification points are testable and not just "works correctly".
- Unresolved items are marked pending or deferred.

See `<skill-root>/references/flow-rules.md` for the full gate checklist.

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

Use the templates in `<skill-root>/assets/templates/` when creating a new flow:

- `requirement.md`
- `qa-decisions.md`
- `design-overview.md`
- `common-context.md`
- `module-design.md`
- `progress.md`
- `review-template.md`

Templates include small filled examples. Keep examples while drafting if useful, then remove them from final project docs when they would confuse the actual feature content.