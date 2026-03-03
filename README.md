Keycloak Issue #46606 — Reproduction Attempt & QA Analysis

This project documents a full QA investigation into Keycloak Issue #46606, which reports UI performance degradation when navigating to Roles → Associated Roles in environments with many realms.

The goal was to reproduce the issue, analyze behavior across versions and browsers, and provide evidence‑based conclusions suitable for open‑source contribution and QA portfolio demonstration.
Summary of Findings

The issue could not be reproduced under the tested conditions.

- Keycloak 26.5.4 — smooth, responsive UI
- Keycloak 26.0.0 — smooth, responsive UI
- 150 realms created via REST API
- Safari 17.x and Firefox 148 on macOS M3
- No lag, freezing, or UI degradation observed
- Associated Roles tab loads instantly and scrolls smoothly

This suggests the issue may be:

- fixed or improved in newer versions
- browser‑specific (likely Chrome)
- environment‑specific (slower hardware, Linux servers)
- dependent on more complex role structures

A detailed comment was posted on the real GitHub issue summarizing these findings.
Project Structure

pdfjs-search-bug-portfolio/
│
├── test-cases/
│   └── roles-associated-roles.md
│
├── regression-checklist/
│   └── ui-performance-checklist.md
│
├── automation-outline/
│   └── navigation-performance-outline.md
│
├── evidence/
│   ├── logs/
│   │   └── keycloak-server.log
│   │
│   └── screenshots/
│       └── realms-list/
│
└── README.md   ← (this file)

##Environment

Hardware
    - macOS Sonoma
    - Apple M3
    - 16GB RAM

Browsers
    - Safari 17.x
    - Firefox 148

Keycloak Versions Tested
    - 26.5.4 (latest at time of testing)
    - 26.0.0 (close to version where issue was reported)

Deployment
    - Docker single‑node instance

Code

docker run -p 8080:8080 \
  -e KEYCLOAK_ADMIN=admin \
  -e KEYCLOAK_ADMIN_PASSWORD=admin \
  quay.io/keycloak/keycloak:<version> start-dev

Test Data
- 150 realms created via Admin REST API
- Script included in evidence/api-script-used.md

🔍 Reproduction Steps

1. Start Keycloak in dev mode
2. Log in as admin
3. Create 150 realms using REST API
4. Open any realm
5. Navigate to:
    Roles → Select a role → Associated Roles
    Scroll, interact, and observe UI responsiveness

📊 Expected vs Actual Behavior

Expected (from GitHub Issue #46606)
- Slow loading
- UI lag
- Freezing
- Unresponsive scrolling

Actual (Observed)
-  Instant load times
- Smooth scrolling
- No freezing
- No performance degradation
- Identical behavior across both tested versions

📁 Evidence

All supporting evidence is stored in the evidence/ folder:
    - logs/keycloak-server.log — full server startup logs
    - screenshots/realms-list/ — proof of 150 realms
    - screenshots/before-degradation/ — UI before interaction
    - screenshots/after-degradation/ — UI after interaction
    - api-script-used.md — script used to generate realms

This evidence demonstrates that the environment was correctly prepared and tested.
Automation Outline

The automation outline includes:
- Login flow
- Realm selection
- Navigation to Roles
- Opening Associated Roles
- Measuring load time and scroll responsiveness

This provides a foundation for future automated performance checks.

Conclusion

The issue could not be reproduced on:
- Keycloak 26.5.4
- Keycloak 26.0.0
- macOS M3
- Safari and Firefox
- 150 realms

The UI remained fully responsive throughout testing.

This suggests the issue may be:
- fixed in newer versions
- browser‑specific (likely Chrome)
- dependent on more complex role structures
- environment‑specific

A detailed comment summarizing these findings was posted on the real GitHub issue:

https://github.com/keycloak/keycloak/issues/46606 (github.com in Bing)
