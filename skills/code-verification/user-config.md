# Project Overrides — Code Verification

## Verification Commands
<!-- Project-specific commands the verifier must run. These are mandatory baseline checks. -->
- Build: <!-- e.g., npm run build -->
- Test: <!-- e.g., npm test -- --coverage -->
- Typecheck: <!-- e.g., npx tsc --noEmit -->
- Lint: <!-- e.g., npm run lint -->
- E2E: <!-- e.g., npx playwright test -->

## Domain-Specific Probes
<!-- Additional adversarial checks beyond the universal defaults. -->
- <!-- e.g., Auth: always test with expired tokens, missing roles, and admin escalation -->
- <!-- e.g., Payments: test zero-amount, negative-amount, and currency mismatch -->
- <!-- e.g., File upload: test empty file, oversized file, and wrong MIME type -->

## Risk Thresholds
<!-- Change types that require elevated rigor regardless of size. -->
- HIGH: <!-- e.g., any change touching auth/, payments/, or migrations/ -->
- MEDIUM: <!-- e.g., any change to API response shapes or public exports -->

## Environment Setup
<!-- Steps needed before verification can begin (servers, seeds, etc). -->
- <!-- e.g., docker compose up -d postgres redis -->
- <!-- e.g., npm run db:seed -->
- <!-- e.g., Dev server: npm run dev (port 3000) -->

## Known Limitations
<!-- Checks that cannot run in this environment — maps to PARTIAL verdict. -->
- <!-- e.g., No iOS simulator available — skip mobile verification -->
- <!-- e.g., Stripe webhook testing requires ngrok — note as PARTIAL if unavailable -->
