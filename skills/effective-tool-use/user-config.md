# Project Overrides — Effective Tool Use

## Shell Commands
<!-- Project-specific commands and aliases the agent should know about. -->
- Package manager: <!-- e.g., pnpm (not npm or yarn) -->
- Build: <!-- e.g., pnpm build -->
- Test: <!-- e.g., pnpm test -->
- Lint: <!-- e.g., pnpm lint -->
- Dev server: <!-- e.g., pnpm dev (port 3000) -->

## Git Conventions
<!-- Override default git behavior for this project. -->
- Branch naming: <!-- e.g., feat/TICKET-description, fix/TICKET-description -->
- Commit format: <!-- e.g., Conventional Commits (feat:, fix:, chore:) -->
- Default base branch: <!-- e.g., develop (not main) -->
- PR template: <!-- e.g., .github/PULL_REQUEST_TEMPLATE.md -->

## Sandbox Overrides
<!-- Additional paths or hosts the sandbox should allow. -->
- <!-- e.g., Allow writes to /data/cache for local dev -->
- <!-- e.g., Allow network access to internal.api.company.com -->

## Tool Restrictions
<!-- Commands or tools the agent should avoid in this project. -->
- <!-- e.g., Never use docker compose down -v — it destroys dev data -->
- <!-- e.g., Don't run migrations without --dry-run first -->
- <!-- e.g., Avoid rm -rf on any directory under src/ -->

## Background Tasks
<!-- Long-running commands that should use run_in_background. -->
- <!-- e.g., pnpm test:e2e (takes ~5 minutes) -->
- <!-- e.g., docker build (takes ~3 minutes) -->
