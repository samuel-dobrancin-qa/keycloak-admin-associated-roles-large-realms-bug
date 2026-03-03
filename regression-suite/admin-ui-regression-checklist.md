# Regression Checklist – Admin Console Roles and Realms

After a fix for Issue #46606, re-test:

## Associated Roles view

- Load time with few realms (3–5).
- Load time with many realms (50–100).
- Scrolling responsiveness.
- Clicking and interaction responsiveness.
- Absence of browser “unresponsive” warnings.

## Related admin views

- Roles list page performance.
- Role details page performance.
- Realm list page performance (especially with many realms).

## Cross-browser behavior

- Chrome.
- Firefox.
- (Optionally) Edge or other supported browsers.

## Upgrade scenario

- Upgrade from a previous Keycloak version to the fixed version.
- Confirm that Associated Roles remains responsive after upgrade.

