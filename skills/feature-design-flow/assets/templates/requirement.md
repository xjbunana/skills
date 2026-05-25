# Requirement: <Feature Name>

## Background

## Goals

## Non-Goals

## Core Flow

## Functional Scope

| # | Area | Requirement | Notes |
|---|------|-------------|-------|
| 1 | | | |

## Data Expectations

## API Expectations

## User Experience Notes

## Acceptance Criteria

- [ ] 

## Future Extensions

## Filled Example: User Notification Settings

> This example shows expected detail. Remove it from final project docs when it would confuse the actual feature.

**Background:** The system currently enables all notifications by default. Users cannot control email or in-app notification preferences, which causes too many promotional messages.

**Goal:** Users can independently enable or disable order status notifications and marketing notifications.

**Current-phase scope:**

| # | Area | Requirement | Notes |
|---|------|-------------|-------|
| 1 | User settings | View notification settings | Return both notification switches for the current user |
| 2 | User settings | Update notification settings | Support partial switch updates |

**Non-goals:**

- No SMS notification settings.
- No notification delivery history page.

**Core flow:**

```text
User opens settings page
    ↓
System loads current notification switches
    ↓
User disables marketing notifications
    ↓
System saves settings and applies them immediately
```

**Acceptance criteria:**

- [ ] User can view order and marketing notification switches.
- [ ] After disabling marketing notifications, the user no longer receives marketing emails.
- [ ] Anonymous users cannot access notification settings APIs.

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.0 | YYYY-MM-DD | Initial draft |