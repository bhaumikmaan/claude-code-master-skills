# Project Overrides — Safe Autonomous Mode

## Custom Allow Rules
<!-- Actions to permit without confirmation in this project. -->
- <!-- e.g., docker compose up -d (safe, local dev only) -->
- <!-- e.g., pnpm test (configured test suite, no side effects) -->
- <!-- e.g., gh pr create (creating PRs is routine in this workflow) -->

## Custom Deny Rules
<!-- Additional actions requiring confirmation beyond the defaults. -->
- <!-- e.g., Any write to migrations/ (always confirm before creating migrations) -->
- <!-- e.g., npm publish (accidental publish is irreversible) -->
- <!-- e.g., Any delete operation on S3 buckets -->

## Pacing Preferences
<!-- How aggressive autonomous behavior should be. -->
- <!-- e.g., Always ask before committing — user prefers reviewing diffs first -->
- <!-- e.g., Push automatically after commit — CI will catch issues -->
- <!-- e.g., Run tests after every file change, not just at milestones -->

## Environment Context
<!-- Additional context for the risk classifier. -->
- <!-- e.g., This is a monorepo — changes may affect multiple packages -->
- <!-- e.g., Production database is accessible from dev — extra caution on DB operations -->
- <!-- e.g., CI/CD is configured — pushes trigger automatic deploys to staging -->
