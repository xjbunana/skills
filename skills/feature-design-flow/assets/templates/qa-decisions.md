# QA Decisions: <Feature Name>

Record requirement clarification and design decisions.

Status values: confirmed / pending / deferred.

## Decisions

### Q1: <Question>

**Decision:** 

**Rationale:** 

**Status:** pending

## Open Items

| Item | Status | Notes |
|------|--------|-------|
| | pending | |

## Filled Example: User Notification Settings

### Q1: Should order notifications and marketing notifications be controlled separately?

**Decision:** Yes, use separate switches.

**Rationale:** Order notifications are transaction-related, while marketing notifications are optional. Users expect different control over them.

**Status:** confirmed

### Q2: Should SMS notification settings be included?

**Decision:** Not in the current phase.

**Rationale:** SMS provider cost and compliance setup are not ready, so this remains a future extension.

**Status:** deferred

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |