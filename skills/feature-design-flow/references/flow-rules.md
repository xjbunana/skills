# Flow Rules

## Status Discipline

Use separate status tables for design and development.

Recommended design states:
- pending
- in progress
- awaiting confirmation
- complete
- needs revision

Recommended development states:
- blocked by design
- pending
- in progress
- complete
- needs fix

QA decision statuses are fixed:
- confirmed
- pending
- deferred

Do not mark a design document complete only because it exists. It must satisfy the Definition of Done and be confirmed by the user.

## Flow Choice

Lightweight flow is appropriate for low-risk, small, single-module work:

```text
requirement doc + QA decision record -> module design -> small recheck -> development
```

Full flow is appropriate for multi-module, high-risk, long-lived, or AI-behavior-heavy work:

```text
requirement doc -> QA decision record -> design overview -> common context
-> module design docs -> progress gates -> design recheck -> development
```

When unsure, start with the early full-flow steps and decide whether to downgrade once module boundaries are clear.

## Confirmation Gates

Require user confirmation before:
- Freezing requirements
- Freezing module boundaries
- Marking each major design document complete
- Applying review conclusions that change scope or architecture
- Moving from design stage to development stage

After a design document is confirmed, re-check upstream documents and update any contradictions before advancing.

## Definition of Done

Requirement doc is done when:
- Background, goal, scope, and non-goals are clear.
- At least one core flow or typical scenario exists.
- Acceptance criteria are verifiable.
- Important unknowns are marked pending.

QA decision record is done when:
- Each key question has a decision, rationale, and status.
- Status uses only confirmed, pending, or deferred.
- Pending items are not used as implementation facts.

Design overview is done when:
- Module boundaries and dependencies are clear.
- Each module has a purpose statement.
- Design and development order are justified.

Common context is done when:
- It contains stable conventions shared by all modules.
- It avoids module-specific details.
- A new session can understand core project rules from it.

Module design is done when:
- Purpose and dependencies are clear.
- APIs include method, path, request example, and response example when relevant.
- Data includes fields, types, requiredness, and status meanings when relevant.
- Logic covers the main path and at least one edge or error path.
- AI behavior includes prompt/tool trigger conditions, parameter sources, and response handling when relevant.
- Verification points are testable or manually checkable.

Recheck is done when:
- AI has actively checked scope, naming, data, APIs, module boundaries, AI/tool/prompt behavior, and development readiness.
- Severe and medium issues have a decision: apply change, defer, or keep pending.
- Development blockers are not silently skipped.

## Design Before Development

Development can begin only when:
- Requirements are captured
- Key QA decisions are recorded
- Required design overview or lightweight module design exists
- Common context exists for full flow
- Required module docs are complete
- Recheck has been performed
- Severe and medium issues are resolved or explicitly deferred

If the user asks to skip design and implement directly, obey the user, but preserve any discovered assumptions in a lightweight note.

## Change Handling

When requirements change mid-flow:
- Update the requirement document
- Add or update the QA decision
- Check whether module order or dependencies changed
- Update affected module docs
- Add a review issue if the change creates inconsistency

Do not silently update progress status after a scope-changing edit.