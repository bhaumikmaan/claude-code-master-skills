# Project Overrides — Systematic Debugging

## Log Locations
<!-- Where to find logs for different components. -->
- App logs: <!-- e.g., ~/.local/state/myapp/debug.log -->
- Server logs: <!-- e.g., /var/log/myapp/server.log -->
- Build logs: <!-- e.g., .next/trace (Next.js build trace) -->

## Common Failure Modes
<!-- Known recurring issues to check first when diagnosing. -->
- <!-- e.g., OOM kills during large batch jobs — check /var/log/kern.log -->
- <!-- e.g., Stale connection pool after DB failover — restart needed -->
- <!-- e.g., Flaky tests caused by shared test database state -->

## Diagnostic Commands
<!-- Tech-stack-specific commands for this project. -->
- Health check: <!-- e.g., curl http://localhost:3000/healthz -->
- DB status: <!-- e.g., docker compose exec postgres pg_isready -->
- Queue depth: <!-- e.g., redis-cli llen job_queue -->
- Process list: <!-- e.g., pm2 status -->

## Escalation Procedures
<!-- What to do when investigation exceeds local debugging. -->
- <!-- e.g., Production issues: check PagerDuty runbook at wiki/runbooks/prod -->
- <!-- e.g., Infrastructure: escalate to #platform-eng with diag output -->
- <!-- e.g., Data issues: never modify production DB — escalate to DBA -->
