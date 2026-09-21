# 01 — Office Admin (Tailored Tech Admin)

Executed by the office administrator. Full read/write access to organization data.

## TC-01-001 — Admin signs in
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01, PC-02.
- **Steps:** 1. Open `/sign-in`. 2. Toggle **Password**. 3. Enter `admin@tailoredtech.tech`. 4. Enter office-admin password. 5. Click **Sign in**.
- **Expected:** Redirect to `/office`. Sidebar shows role as "Tailored Tech Admin". Screenshot: `office-admin-home.png`.

## TC-01-002 — Admin dashboard metrics load
**Type:** functional | **Status:** pass

- **Preconditions:** logged in as admin.
- **Steps:** 1. Confirm **Home** is the default view. 2. Read the metrics cards (Observations / At-risk / Red flags) for MONTH/WEEK/DAY.
- **Expected:** Metric cards populate with numbers (e.g. Observations MONTH=4, At-risk 75%, Red flags 1), plus a date-range observations table.

## TC-01-003 — Observations log renders
**Type:** data | **Status:** pass

- **Preconditions:** logged in, ≥1 existing observation.
- **Steps:** 1. Go to **Observations**. 2. Apply a date range. 3. Inspect the table (ID, Status, Created, Observed, Organization, Vessel, Created by, Task observed, No. observed, Checklist).
- **Expected:** Rows render with all columns; filters narrow results; "Observation Log" and "New Observation" entries present.

## TC-01-004 — Create a new observation
**Type:** workflow | **Status:** not-run (data-creation, run by testers)

- **Preconditions:** logged in, ≥1 vessel and ≥1 checklist exist.
- **Steps:** 1. **Observations → New Observation**. 2. Select vessel/crew/task. 3. Choose a checklist & populate. 4. Record flags & save.
- **Expected:** Observation is created, appears on the log, status reflects submission.

## TC-01-005 — Action items (create & list)
**Type:** workflow | **Status:** pass (list renders) / create not-run

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Action Items**. 2. Review "Create Action Item" and "Action Item List". 3. Open an existing item's detail.
- **Expected:** List renders; navigation to create & detail works. Screenshot: `office-admin-action-items.png`.

## TC-01-006 — Administration shell
**Type:** UI | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Administration**. 2. Confirm sub-sections for Users, Vessels, Crew, Organizations, Sign-on requests, STO-ETS.
- **Expected:** Administration panel renders with links. Screenshot: `office-admin-administration.png`.

## TC-01-007 — Office users management
**Type:** data | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Administration → Office Users** (`/office/users`). 2. Confirm office account list renders (incl. test users).
- **Expected:** User list renders with identity columns. Screenshot: `office-admin-users.png`.

## TC-01-008 — Vessel management
**Type:** data | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Administration → Vessel Management** (`/office/vessels`).
- **Expected:** Vessel list renders (e.g. target vessels incl. `ajwad`). Screenshot: `office-admin-vessels.png`.

## TC-01-009 — ICB Checklists
**Type:** data | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **ICB Checklists**.
- **Expected:** Checklist list renders with default-behavior configuration. Screenshot: `office-admin-checklist.png`.

## TC-01-010 — Chatrooms
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Chatrooms**. 2. Open "STO & ETS Hub".
- **Expected:** Chatroom list renders and opens; messages visible. Screenshot: `office-admin-chatrooms.png`.

## TC-01-011 — Settings
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Settings**.
- **Expected:** Settings view renders with the configured options. Screenshot: `office-admin-settings.png`.

## TC-01-012 — Notifications
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Go to **Notifications**.
- **Expected:** Notification list renders (unread/announcements). Screenshot: `office-admin-notifications.png`.

## TC-01-013 — Direct nested routes resolve (no 404)
**Type:** technical | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Navigate directly to each: `/office/observations`, `/office/actions`, `/office/users`, `/office/vessels`, `/office/chatrooms`, `/office/settings`, `/office/checklists`.
- **Expected:** Each resolves to its UI (no "Page not found"). *(Top-level `/observations` etc. are intentionally NOT routes — sidebar buttons are the app navigation.)*

## TC-01-014 — Explore Data
**Type:** functional | **Status:** needs-feedback (permission-bound)

- **Preconditions:** logged in as admin.
- **Steps:** 1. Navigate to **Explore Data** (`/office/explore` or sidebar).
- **Expected:** Analytics/explore view. **Observed:** the admin path for analytics is gated; STO/ETS own the analytics module — confirm whether office admin should see it (see report, logical uncertainty).

## TC-01-015 — Office member scopes are NOT exposed to non-admin
**Type:** permission | **Status:** pass

- **Preconditions:** two office accounts (admin + basic member).
- **Steps:** 1. Log in as basic member (`test.office.user@bahri.sa`). 2. Confirm whether admin-only items (e.g. user/vessel management) are hidden.
- **Expected:** Non-admin office user sees office dashboards without admin management panels. Screenshot: `office-user-home.png`.