# Project Overrides — Security Review

## Compliance Requirements
<!-- Frameworks or standards this project must meet. -->
- <!-- e.g., SOC 2 Type II — audit logging required for all data access -->
- <!-- e.g., HIPAA — PHI must be encrypted at rest and in transit -->
- <!-- e.g., PCI DSS — no cardholder data in logs or error messages -->

## Trust Boundaries
<!-- Known boundaries where untrusted data enters the system. -->
- <!-- e.g., POST /api/upload — user file uploads, validate MIME + size + content -->
- <!-- e.g., Webhook handler at /hooks/stripe — verify Stripe signature header -->
- <!-- e.g., GraphQL resolver layer — all user input enters here -->

## Security Scanning
<!-- Tools configured for automated security checks. -->
- <!-- e.g., npm audit (runs in CI) -->
- <!-- e.g., Snyk container scanning on Docker images -->
- <!-- e.g., CodeQL for static analysis -->

## Domain Threat Model
<!-- Attacker profiles and attack vectors specific to this project. -->
- <!-- e.g., Primary threat: credential stuffing on login endpoints -->
- <!-- e.g., Insider threat: API keys with overly broad permissions -->
- <!-- e.g., Supply chain: lock files must be reviewed in every PR -->

## Severity Overrides
<!-- Adjust default severity ratings for this project's context. -->
- <!-- e.g., Any auth bypass is CRITICAL regardless of scope -->
- <!-- e.g., XSS in admin panel is MEDIUM (trusted users only) -->
