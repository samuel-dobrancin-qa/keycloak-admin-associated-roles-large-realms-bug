# Reproduction Steps and Environment

## Environment

- **Keycloak version:** 26.5.4
- **Deployment:** Docker, single-node
- **Browser:** Safari 26.2 and Firefox 148.0 
- **Host OS:** Mac OS Tahoe 26.2

## Setup

1. Start Keycloak in dev mode:

   ```bash
   docker run -p 8080:8080 quay.io/keycloak/keycloak:<version> start-dev

