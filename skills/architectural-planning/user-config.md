# Project Overrides — Architectural Planning

## Architecture Constraints
<!-- Domain-specific design rules the planner must respect. -->
- <!-- e.g., All new services must be stateless and horizontally scalable -->
- <!-- e.g., No new runtime dependencies without team lead approval -->
- <!-- e.g., Database changes require a migration + rollback pair -->

## Design Decision Format
<!-- Override the default table format if your team uses ADRs or another format. -->
- <!-- e.g., Use ADR format: Status, Context, Decision, Consequences -->
- <!-- e.g., Include a "Security Implications" column in the decision table -->

## Key Architecture Documents
<!-- Existing docs the planner should read before designing. -->
- <!-- e.g., docs/architecture.md — system overview and module boundaries -->
- <!-- e.g., docs/api-contracts.md — API versioning and compatibility rules -->
- <!-- e.g., CLAUDE.md — project conventions and rules -->

## Review Gates
<!-- Approval steps required before implementation begins. -->
- <!-- e.g., Plans touching auth/ require security team sign-off -->
- <!-- e.g., Database schema changes need DBA review -->

## Exploration Entry Points
<!-- Where the planner should start investigating for common task types. -->
- <!-- e.g., API changes: start in src/api/routes/ and src/api/middleware/ -->
- <!-- e.g., UI features: start in src/components/ and src/pages/ -->
- <!-- e.g., Data model changes: start in src/models/ and migrations/ -->
