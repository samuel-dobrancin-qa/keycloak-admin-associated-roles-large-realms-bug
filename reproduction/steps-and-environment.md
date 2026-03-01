# Reproduction Steps and Environment

## Environment

- **Keycloak version:** (use the version mentioned in the GitHub issue)
- **Deployment:** Docker, single-node
- **Browser:** Chrome and Firefox
- **Host OS:** (your OS, e.g., Windows 11 / macOS / Linux)

## Setup

1. Start Keycloak in dev mode:

   ```bash
   docker run -p 8080:8080 quay.io/keycloak/keycloak:<version> start-dev

