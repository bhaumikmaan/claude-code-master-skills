# Project Overrides — Task Orchestration

## Workflow Phases
<!-- Override or extend the default Research → Synthesis → Implementation → Verification flow. -->
- <!-- e.g., Add "Design Review" phase between Synthesis and Implementation -->
- <!-- e.g., Require user approval before Implementation phase begins -->

## Branch & PR Conventions
<!-- Rules workers must follow for git operations. -->
- Branch naming: <!-- e.g., fix/SHORT-DESCRIPTION or feat/TICKET-ID-description -->
- PR target: <!-- e.g., Always target develop, never main directly -->
- PR format: <!-- e.g., Draft PR first, mark ready after verification passes -->
- Reviewers: <!-- e.g., Always add @team-leads as reviewer -->

## Concurrency Limits
<!-- Constraints on parallel workers based on project infrastructure. -->
- Max parallel workers: <!-- e.g., 3 (CI runners are limited) -->
- File locking: <!-- e.g., Only one worker may touch migrations/ at a time -->
- Test parallelism: <!-- e.g., Tests are not parallelizable — run verification sequentially -->

## Default Worker Commands
<!-- Commands every worker should run before reporting completion. -->
- Build: <!-- e.g., pnpm build -->
- Test: <!-- e.g., pnpm test -->
- Typecheck: <!-- e.g., pnpm tsc --noEmit -->
- Lint: <!-- e.g., pnpm lint -->

## Research Entry Points
<!-- Where workers should start investigating for common task types. -->
- <!-- e.g., API changes: start in src/api/routes/ and src/api/middleware/ -->
- <!-- e.g., DB changes: start in src/models/ and migrations/ -->
