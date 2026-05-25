# <Module Name>

> Depends on: <common context and upstream modules>
> Status: pending

## Purpose

## Responsibilities

## Relationship to Other Modules

| Direction | Module | Notes |
|-----------|--------|-------|
| Upstream | | |
| Downstream | | |

## File Structure

```text
<paths>
```

## Data Model / DTOs

## APIs

### <METHOD> <path>

Request:

```json
{}
```

Response:

```json
{}
```

## Service Logic

1. 

## Edge Cases

## Verification

- [ ] 

## Definition of Done

- [ ] Responsibilities are clear and do not include unrelated modules.
- [ ] Dependencies and downstream effects are described.
- [ ] APIs include request and response examples when relevant.
- [ ] Data design includes fields, types, requiredness, and status meanings when relevant.
- [ ] Service logic covers the main path and at least one edge or error path.
- [ ] Verification points are testable or manually checkable.
- [ ] Pending questions are not used as confirmed facts.

## Filled Example: Notification Settings API Module

**Purpose:** Provide APIs for querying and updating the current user's notification settings.

**Responsibilities:**

- Query current user's notification settings.
- Update order and marketing notification switches.
- Return default settings when no setting row exists for the user.

**API example:**

### GET /api/user/notification-settings

Response:

```json
{
  "code": "200",
  "msg": "success",
  "data": {
    "orderNotifyEnabled": true,
    "marketingNotifyEnabled": false
  }
}
```

### PUT /api/user/notification-settings

Request:

```json
{
  "marketingNotifyEnabled": false
}
```

**Service logic:**

1. Get current user ID from auth context.
2. Query notification settings by user ID.
3. If no row exists, return defaults: order enabled, marketing disabled.
4. On update, modify only fields present in the request.
5. Return the standard unauthenticated error when the user is not logged in.

**Verification:**

- [ ] Anonymous access returns 401.
- [ ] New users receive default settings.
- [ ] After disabling marketing notifications, querying again returns disabled state.

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |