# Test Cases – Associated Roles Performance and Usability

## TC-001 – Baseline behavior with few realms

- **Goal:** Establish baseline performance and responsiveness.
- **Preconditions:** 3–5 realms exist.
- **Steps:**
  1. Log in to the Admin Console.
  2. Select a realm.
  3. Go to Roles → select a role → Associated Roles.
- **Expected result:**
  - Page loads within a short time (e.g., under 2 seconds).
  - Scrolling and clicking are smooth.
  - No browser warnings.

---

## TC-002 – Behavior with many realms

- **Goal:** Observe performance with a large number of realms.
- **Preconditions:** 50–100 realms exist.
- **Steps:**
  1. Log in to the Admin Console.
  2. Select a realm.
  3. Go to Roles → select a role → Associated Roles.
- **Expected result:**
  - Long load time.
  - UI becomes sluggish or temporarily unresponsive.
  - Possible browser “Page is unresponsive” warnings.
- **Actual result (current bug):**
  - Keycloak (26.5.4): UI responsive, no lag.
  - Keycloak (26.0.0): UI responsive, no lag.
Notes: Tested with 150 realms; Safari and Firefox both smooth.

---

## TC-003 – Browser comparison (Safari vs Firefox)

- **Goal:** Check whether the issue is browser-specific.
- **Preconditions:** 50–100 realms exist.
- **Steps:**
  1. Execute TC-002 in Safari.
  2. Execute TC-002 in Firefox.
- **Expected result:**
  - Similar performance characteristics across browsers.
- **Actual result:**
  - Keycloak (26.5.4): UI responsive, no lag.
  - Keycloak (26.0.0): UI responsive, no lag.
Notes: Tested with 150 realms; Safari and Firefox both smooth.

---

## TC-005 – Interaction responsiveness within Associated Roles

- **Goal:** Evaluate responsiveness of interactions once the view is loaded.
- **Preconditions:** Many realms exist (e.g., 50–100).
- **Steps:**
  1. Open Associated Roles as in TC-002.
  2. Scroll through the list.
  3. Click on items, filters, or controls (if available).
- **Expected result:**
  - Interactions respond promptly.
  - No noticeable freezing or multi-second delays.
- **Actual result:**
  - Keycloak (26.5.4): UI responsive, no lag.
  - Keycloak (26.0.0): UI responsive, no lag.

