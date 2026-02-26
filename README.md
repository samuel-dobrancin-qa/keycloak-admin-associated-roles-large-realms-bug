Keycloak Admin Console – Associated Roles performance issue with many realms (Issue #46606)

This project documents my QA investigation of a real open bug in Keycloak:

- **Issue:** Admin associated roles view becomes unusable when many realms exist.
- **Project:** Keycloak (Red Hat identity and access management)
- **Issue link:** https://github.com/keycloak/keycloak/issues/46606

## What this project shows

- Testing an enterprise IAM admin console under scale (many realms).
- Designing reproducible steps for a performance/UI degradation bug.
- Writing structured test cases and a regression suite.
- Outlining UI automation (Playwright) for admin workflows.

## Repository structure

- `bug-analysis/` – context, impact, hypotheses.
- `reproduction/` – environment setup and exact steps.
- `test-cases/` – detailed manual test cases.
- `regression-suite/` – what to re-test after a fix.
- `automation-outline/` – how I would automate this scenario.
- `evidence/` – screenshots and logs from my runs.
