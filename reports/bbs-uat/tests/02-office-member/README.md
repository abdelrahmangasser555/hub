# 02 — Office Member (Joseph Essam)

Executed by a regular office (Bahri) member. Observes data; may create/own content but does not administer.

## TC-02-001 — Office member signs in
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01/02.
- **Steps:** 1. `/sign-in` → Password. 2. `joseph.essam@bahri.sa` + office-member password. 3. Sign in.
- **Expected:** Redirect to `/office`, sidebar identifies "Joseph Essam". Screenshot: `office-member-home.png`.

## TC-02-002 — Home dashboard
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Confirm Home view. 2. Read metric cards + observations table.
- **Expected:** Dashboard populates (office role view).

## TC-02-003 — Observations log
**Type:** data | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Open Observations. 2. Apply filters.
- **Expected:** Log renders with standard columns.

## TC-02-004 — Action items
**Type:** workflow | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Open Action Items.
- **Expected:** List renders; member can open details.

## TC-02-005 — No admin management panels
**Type:** permission | **Status:** pass

- **Preconditions:** logged in as office member.
- **Steps:** 1. Confirm sidebar. 2. Try `/office/users`, `/office/vessels`.
- **Expected:** Admin management (users/vessels/orgs) is **not** exposed to a plain office member (permission boundary). Direct access denied/redirected.