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

Do not mark a design document complete only because it exists. It must be internally coherent and confirmed.

## Confirmation Gates

Require user confirmation before:
- Freezing requirements
- Freezing module boundaries
- Marking each major design document complete
- Applying review conclusions that change scope or architecture
- Moving from design stage to development stage

After a design document is confirmed, re-check upstream documents and update any contradictions before advancing.

## Design Before Development

Development can begin only when:
- Requirements are captured
- Key QA decisions are recorded
- Design overview exists
- Common context exists
- Required module docs are complete
- Recheck has been performed
- Severe and medium confirmed issues are resolved or explicitly deferred

If the user asks to skip design and implement directly, obey the user, but preserve any discovered assumptions in a lightweight note.

## Change Handling

When requirements change mid-flow:
- Update the requirement document
- Add or update the QA decision
- Check whether module order or dependencies changed
- Update affected module docs
- Add a review issue if the change creates inconsistency

Do not silently update progress status after a scope-changing edit.
