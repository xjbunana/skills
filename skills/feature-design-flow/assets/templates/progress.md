# Progress: <Feature Name>

Design and development are tracked separately.

## Rules

- Design must be complete and confirmed before development begins.
- After each confirmed design stage, re-check upstream docs and sync contradictions.
- Recheck must be completed before development.

## Design Stage

| Document | Status | Notes |
|----------|--------|-------|
| 00-common-context | pending | |
| 01-<module> | pending | |
| Design recheck | pending | |

## Development Stage

| Module | Status | Notes |
|--------|--------|-------|
| 01-<module> | blocked by design | |

## Current Blocker / Next Action

- Current blocker: <Example: waiting for user confirmation on module boundaries.>
- Next action: <Example: after confirmation, complete the 01 module API design and update status.>

## Filled Example: User Notification Settings

| Document | Status | Notes |
|----------|--------|-------|
| 00-common-context | complete | Confirmed by user |
| 01-notification-settings-data-model | awaiting confirmation | Waiting for default-value strategy confirmation |
| 02-notification-settings-api | blocked by design | Depends on 01 default-value strategy |

Current blocker / next action:

- Current blocker: notification default-value strategy is pending.
- Next action: after confirmation, update 01 and continue 02 API design.

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |