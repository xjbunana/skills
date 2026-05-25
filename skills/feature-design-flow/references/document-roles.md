# Document Roles

Use these roles to keep the document system clean and navigable.

## Requirement Document

Purpose: define what the feature is trying to achieve.

Include:
- Background and goal
- Current-phase scope
- Non-goals
- Core user flows
- Functional requirements
- Data/API expectations
- Acceptance criteria
- Future extensions

Avoid:
- Deep implementation details that belong in module designs
- Decisions that are still under discussion without marking them as assumptions

Completion standard: after reading the requirement doc, another session should know why the feature exists, who it serves, what is in scope, what is explicitly out of scope, and how it will be accepted.

## QA Decision Record

Purpose: preserve the reasoning trail from requirement discussion.

Include:
- Question
- Decision
- Rationale or tradeoff
- Status: confirmed, pending, deferred
- Date or version when useful

Status values:
- confirmed: can be used as design input
- pending: requires user confirmation before relying on it
- deferred: recorded but out of current scope

Use this document to prevent the same question from being re-litigated across sessions.

## Design Overview

Purpose: show the system decomposition and development order.

Include:
- Directory/document map
- Module list
- Module dependencies
- Recommended design order
- Recommended development order
- Current open items

Avoid turning this into a full implementation spec.

Completion standard: a new session can read only the overview and know which docs to read first, which modules to implement first, and which modules are blocked.

## Common Context

Purpose: provide stable context every module and coding session must read.

Include:
- Tech stack and versions
- Project layout
- Naming conventions
- Shared base classes/types
- Response envelope and error style
- Database conventions
- Auth/user context conventions
- Reference code locations

Keep it stable. If something only matters to one module, put it in that module doc.

## Module Design

Purpose: make one implementation unit AI-ready.

Include:
- Module purpose
- Dependencies and upstream/downstream relationship
- File/package structure
- Data model or DTOs
- API contract
- Service logic
- Tool/prompt behavior when relevant
- Edge cases
- Verification or acceptance checks

Module docs should be specific enough to code from, but not so rigid that they duplicate every final line of code.

Completion standard: another AI session can read the common context and this module doc, start implementation, and know how to verify the result.

## Progress Document

Purpose: act as the process gate.

Track design and development separately. Require explicit confirmation before changing statuses that unlock the next stage.

Prefer a "current blocker / next action" field over a generic "current stage" field, because it tells the next session what to do.

## Recheck Document

Purpose: find contradictions before implementation.

AI should actively run the recheck and output an issue summary. The user confirms each issue decision.

Record:
- Issue title
- Affected document and location
- Severity
- Description
- Suggested fix
- User decision
- Final status