# 05 — ETS (Engine- / Electrical-Technical Specialist — Fatima Al-Zahrani)

Executed by the ETS, the second STO-ETS workspace member.

## TC-05-001 — ETS signs in
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01/02.
- **Steps:** 1. `/sign-in` → Password. 2. `fatima.alzahrani@bahri.sa` + ETS password. 3. Sign in.
- **Expected:** ETS authenticates successfully. Sidebar identifies "Fatima Al-Zahrani". Screenshot: `ets-home.png`.

## TC-05-002 — ETS landing route after login
**Type:** auth/UX | **Status:** **needs-feedback**

- **Preconditions:** logged in.
- **Steps:** 1. Note the post-login destination.
- **Expected:** Like the STO, land in the STO-ETS workspace (`/sto-ets`) or its counterpart.
- **Observed:** ETS is redirected to **`/notifications`**, and navigating to `/sto-ets` **redirects back to `/notifications`**. STO lands correctly on `/sto-ets`. → **Recorded as a logical/UX uncertainty for the product owner** (does the ETS intentionally share a different landing, or should it match STO?). See report, §5. Defect candidate.

## TC-05-003 — ETS access to STO-ETS module content
**Type:** permission | **Status:** blocked / needs-feedback

- **Preconditions:** logged in as ETS.
- **Steps:** 1. From sidebar, open Chatrooms ("STO & ETS Hub"). 2. Try the analytics/observations views.
- **Expected:** ETS participates in the STO-ETS hub and sees shared workspace items.
- **Observed:** Notifications render (3 items incl. announcements). Full STO-ETS workspace reachability while routing through a `/notifications` landing needs a product decision + follow-up test.

## TC-05-004 — Notifications correctness (ETS)
**Type:** functional | **Status:** pass

- **Preconditions:** logged in as ETS.
- **Steps:** 1. Open Notifications. 2. Check unread/announcement badges (All / Unread 2 / Announcements).
- **Expected:** Announcements from Bahri BBS / Tailored Tech Admin render with dates.