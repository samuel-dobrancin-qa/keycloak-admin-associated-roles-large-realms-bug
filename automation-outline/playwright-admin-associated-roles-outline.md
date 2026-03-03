# Automation Outline – Playwright for Associated Roles Performance

## Goal

Automate a basic performance and responsiveness check for the Admin Console **Associated Roles** view when many realms exist.

## Tooling

- **Framework:** Playwright
- **Language:** TypeScript or JavaScript
- **Target:** Keycloak Admin Console (web UI)

## High-level flow

1. Launch browser and navigate to the Admin Console.
2. Log in as an admin user.
3. Select a realm.
4. Navigate to Roles → select a role → Associated Roles.
5. Measure:
   - Time until the Associated Roles list is rendered.
   - Time until the page is responsive to scroll and click.
6. Assert:
   - The view becomes interactive within an acceptable threshold.
   - No unhandled JavaScript errors are present in the console.

## Implementation ideas

- Use `page.fill` and `page.click` for login.
- Use `page.waitForSelector` to detect when the Associated Roles list is visible.
- Capture Playwright traces to analyze timing.
- Parameterize the test to run with different realm counts (e.g., 10, 50, 100).
- Optionally, collect performance metrics via the browser’s Performance API.

