# Design Review: <Feature Name>

AI should actively perform this review before development and output this document or an equivalent issue list. The user confirms the decision for each issue.

## Issue Summary

| # | Issue | Document | Severity | Status | Decision/Notes |
|---|-------|----------|----------|--------|----------------|
| 1 | | | medium | pending | |

## Severity

| Severity | Meaning |
|----------|---------|
| severe | Blocks development or causes major behavior/data risk |
| medium | May cause inconsistent implementation or user-visible bugs |
| minor | Cleanup or clarity issue |

## Issue N: <Title> [pending]

**Document:** 

**Location:** 

**Problem:** 

**Suggested Fix:** 

**Decision:** pending

## Filled Example: Notification Default Conflict [pending]

**Document:** `1-requirements.md`, `01-notification-settings-data-model.md`

**Location:** requirement acceptance criteria; data model default-value section

**Problem:** Requirement says marketing notifications default to disabled, but the data model uses `marketing_notify_enabled DEFAULT true`.

**Suggested Fix:** Change the data model default to `false` and document the source of the default-value rule.

**Decision:** pending

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |