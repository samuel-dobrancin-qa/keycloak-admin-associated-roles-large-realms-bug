
---

### `test-cases/associated-roles-test-cases.md`

```markdown
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
  - Page remains responsive and usable.
  - No long freezes or unresponsive behavior.
- **Actual result (current bug):**
  - Long load time.
  - UI becomes sluggish or temporarily unresponsive.
  - Possible browser “Page is unresponsive” warnings.

---

## TC-003 – Browser comparison (Chrome vs Firefox)

- **Goal:** Check whether the issue is browser-specific.
- **Preconditions:** 50–100 realms exist.
- **Steps:**
  1. Execute TC-002 in Chrome.
  2. Execute TC-002 in Firefox.
- **Expected result:**
  - Similar performance characteristics across browsers.
- **Actual result:**
  - (Record any differences you observe.)

---

## TC-004 – Realm count threshold analysis

- **Goal:** Identify the realm count at which performance degradation becomes noticeable.
- **Preconditions:** Ability to create realms in batches.
- **Steps:**
  1. Test with ~10 realms → run TC-002.
  2. Test with ~25 realms → run TC-002.
  3. Test with ~50 realms → run TC-002.
  4. Test with ~75 realms → run TC-002.
  5. Test with ~100 realms → run TC-002.
- **Expected result:**
  - Performance degrades gracefully, not catastrophically.
- **Actual result:**
  - (Document at which point the UI becomes clearly problematic.)

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
  - (Describe any lag, freezes, or delayed responses.)

