# Common Context: <Feature Name>

Read this before designing or developing any module in this feature.

## Project Summary

## Technology Stack

| Area | Technology | Version/Notes |
|------|------------|---------------|
| Backend | | |
| Frontend | | |
| Database | | |

## Project Structure

```text
<project-root>/
```

## Shared Conventions

### Naming

### Response Format

### Error Handling

### Auth/User Context

### Database

## Reference Code

| Path | Purpose |
|------|---------|
| | |

## Module Index

| Document | Purpose |
|----------|---------|
| 01-<module>.md | |

## Filled Example: User Notification Settings

**Project summary:** Add notification preference settings to the existing user center. All APIs operate on the current logged-in user only.

**Shared convention examples:**

- Backend APIs return `ResultData<T>`.
- Current user ID comes from auth context, not from request body.
- Database fields use snake_case; Java/TypeScript fields use camelCase.

**Module index example:**

| Document | Purpose |
|----------|---------|
| 01-notification-settings-data-model.md | Settings table, defaults, and entity design |
| 02-notification-settings-api.md | Query and update notification settings APIs |

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |