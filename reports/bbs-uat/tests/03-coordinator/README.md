# 03 — Coordinator (Test Coordinator)

Executed by the coordinator — an office-level role that coordinates observation workflow and sign-ons across vessels/crew.

## TC-03-001 — Coordinator signs in
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01/02.
- **Steps:** 1. `/sign-in` → Password. 2. `test.coordinator@bahri.sa` + coordinator password. 3. Sign in.
- **Expected:** Redirect to `/office`, sidebar identifies "Test Coordinator". Screenshot: `coordinator-home.png`.

## TC-03-002 — Home dashboard
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Confirm Home. 2. Read metrics.
- **Expected:** Coordinator sees office dashboard with populated metrics.

## TC-03-003 — Observations (create + log)
**Type:** workflow | **Status:** list pass / create not-run

- **Preconditions:** logged in, vessel+checklist exist.
- **Steps:** 1. Open Observations. 2. Confirm log rows. 3. Create a new observation end-to-end.
- **Expected:** Log renders; new observation submits and appears.

## TC-03-004 — Action items
**Type:** workflow | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Open Action Items.
- **Expected:** List renders and detail opens.

## TC-03-005 — Sign-on requests
**Type:** workflow | **Status:** not-run (needs crew sign-on data)

- **Preconditions:** ≥1 crew sign-on request exists.
- **Steps:** 1. Open **Administration → Sign-on requests** (`/office/sign-on-requests`). 2. Review an in-flight request.
- **Expected:** Requests list with status; coordinator can review/approve.

## TC-03-006 — Crew management visibility
**Type:** data | **Status:** not-run

- **Preconditions:** logged in, crew seeded.
- **Steps:** 1. Open **Administration → Crew Management**. 2. Inspect crew list (observers, signed-on status).
- **Expected:** Crew members render with status (e.g. "signed on").