# Design Overview: <Feature Name>

This document maps module design documents, dependencies, and execution order.

## Document Map

```text
docs/<feature-name>/
├── 1-requirements.md
├── 2-qa-decisions.md
├── 3-design-overview.md
├── design/
│   ├── 00-common-context.md
│   ├── 01-<module>.md
│   └── PROGRESS.md
└── recheck/
    └── design-review.md
```

## Module Order

```text
00-common-context
      ↓
01-<module>
      ↓
02-<module>
```

## Module Summary

| Document | Depends On | Purpose | Status |
|----------|------------|---------|--------|
| 00-common-context | - | Shared project context | pending |

## Open Items

| Item | Notes |
|------|-------|
| | |

## Filled Example: User Notification Settings

```text
00-common-context
      ↓
01-notification-settings-data-model
      ↓
02-notification-settings-api
      ↓
03-settings-page-integration
```

| Document | Depends On | Purpose | Status |
|----------|------------|---------|--------|
| 00-common-context | - | Shared response, auth, and project structure | pending |
| 01-notification-settings-data-model | 00 | Define settings table, defaults, and entity shape | pending |
| 02-notification-settings-api | 01 | Query and update current user's notification switches | pending |
| 03-settings-page-integration | 02 | Settings page display and save interaction | pending |

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |