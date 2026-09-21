# 08 — Cross-cutting (all roles & environments)

Cases that span roles, permissions, data integrity, and device behavior. Run last; covered in the report's readiness assessment.

## TC-08-001 — Role-based module isolation
**Type:** permission | **Status:** partially verified

- **Preconditions:** all roles created.
- **Steps:** Log in as each role and confirm the sidebar/URLs expose **only** their permitted modules; direct URL access to unauthorized modules is denied/redirected.
- **Expected:** Office admin vs office member vs STO/ETS vs crew/vessel have distinct, correct module sets.

## TC-08-002 — Password vs OTP auth segregation
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01/02.
- **Steps:** Confirm office family uses password and crew/vessel use email OTP on the same `/sign-in` screen.
- **Expected:** Choosing **Password** for a crew email fails; **Email code** then sends a code (correct segregation).

## TC-08-003 — Direct deep-link resolves (no misleading 404)
**Type:** technical | **Status:** needs-feedback

- **Preconditions:** logged in.
- **Steps:** Visit plausible-but-nested routes directly (e.g. `/office/observations` vs `/observations`).
- **Expected:** Real pages live under their role prefix; bare top-level routes 404. Confirm this is intended navigation design (sidebar is canonical). Root cause of my earlier mis-discovery: `src/app` genuinely has no `/observations` layout — routes are grouped per role.

## TC-08-004 — Data integrity / persistence
**Type:** data | **Status:** not-run

- **Preconditions:** write access.
- **Steps:** Create, refresh, re-login and confirm a record persists across sessions.
- **Expected:** No data loss; IDs unique.

## TC-08-005 — Mobile readability
**Type:** UI | **Status:** not-run

- **Preconditions:** responsive app.
- **Steps:** Test at 390px and 768px widths for the main dashboards.
- **Expected:** No horizontal scroll; readable fonts; usable touch targets.

## TC-08-006 — Error handling on bad input
**Type:** robustness | **Status:** partial

- **Preconditions:** sign-in reachable.
- **Steps:** Enter a malformed/invalid account → observe message.
- **Expected:** Graceful, non-crashing message (e.g. "Could not sign in / Invalid credentials").

## TC-08-007 — Production parity
**Type:** environment | **Status:** not-run

- **Preconditions:** staging/prod deployed.
- **Steps:** Repeat TC-01 to TC-07 against the deployed environment (not localhost dev).
- **Expected:** Same behavior as dev; run full regression before client UAT.