
Bug analysis – Keycloak Issue #46606

Summary

When a large number of realms exist, the **Admin Console → Associated Roles** view becomes slow or unusable. UI interactions degrade significantly, making it hard for administrators to manage roles at scale.

Context

- **Product:** Keycloak
- **Area:** Admin Console UI (associated roles)
- **Type:** Performance / usability bug
- **Issue:** https://github.com/keycloak/keycloak/issues/46606

Expected vs actual behavior

- **Expected:** Admin associated roles view remains responsive even with many realms.
- **Actual:** With many realms, the view becomes extremely slow or unusable (e.g., long load times, frozen UI, delayed interactions).

Impact

- Affects administrators managing multi-tenant or multi-realm deployments.
- Increases risk of misconfiguration because the UI becomes hard to use.
- Particularly relevant for large enterprises and hosted IAM platforms.

Root cause hypothesis

- The page may be loading or processing associated roles for all realms at once.
- Possible N×M queries or heavy client-side rendering with large datasets.
- Lack of pagination, lazy loading, or server-side filtering for associated roles.

Risks and edge cases

- Behavior may differ by browser and machine performance.
- Impact likely grows non-linearly as the number of realms increases.
- Could interact with other admin console features that query roles/realms.
