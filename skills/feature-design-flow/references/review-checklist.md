# Review Checklist

Use this checklist during cross-document recheck.

## Scope

- Requirement goals match module designs.
- Non-goals are not accidentally implemented in design docs.
- Acceptance criteria are covered by modules or explicitly deferred.
- Future-phase items are not mixed into current-phase implementation.

## Naming

- Module names, file names, package names, routes, table names, and tool names are consistent.
- API field casing is consistent between request/response examples and code design.
- Database snake_case maps cleanly to application camelCase where relevant.

## Data

- Tables/entities/DTOs agree on required fields, types, defaults, and status meanings.
- Logical delete, conversion state, audit fields, timestamps, and ownership fields are not overloaded.
- Indexes support described query patterns.

## APIs

- Method and path conventions are consistent.
- Request/response examples match the response envelope.
- Auth source and user identity handling are explicit.
- Pagination, sorting, and filtering behavior are clear where needed.

## Module Boundaries

- Dependencies follow the design overview.
- Shared behavior is in common context or shared modules.
- Module docs do not require hidden knowledge from unrelated docs.

## AI, Tools, and Prompts

- Tool names and parameters match implementation design.
- Prompt rules tell the model when to call tools and when not to.
- User-visible examples do not include internal notes.
- Conversation state injected into prompts has a clear source of truth.

## Development Readiness

- Each module has enough path/class/function/API detail for implementation.
- Important edge cases are named.
- Verification checks or acceptance tests are clear.
- Open questions are either resolved or explicitly blocking.
