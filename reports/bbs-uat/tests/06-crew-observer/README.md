# 06 — Crew Observer (e.g. albin.baby.2641 — signed-on observer)

Executed by a crew member assigned as a signed-on observer on a vessel. Auth = **email OTP**.

> **Blocker:** Crew/vessel log in via email OTP delivered to the authorized inbox (AWS SES). Executing the interactive steps below requires reading that OTP. The login *flow* was verified (send-verification-code → OTP step renders). Full interactive walkthrough is **blocked** pending inbox access — see report §5.

## TC-06-001 — Crew observer OTP request
**Type:** auth | **Status:** pass (flow) / blocked (completion)

- **Preconditions:** PC-01/02, account signed-on on a vessel.
- **Steps:** 1. `/sign-in` → toggle **Email code**. 2. Enter crew email (`albin.baby.2641@bahri.sa`). 3. Click **Send verification code**.
- **Expected:** OTP step appears ("Send verification code"); no error. Screenshot: `crew-observer-home.png` (login screen reachable).

## TC-06-002 — Crew observer completes sign-in
**Type:** auth | **Status:** blocked

- **Preconditions:** OTP delivered to inbox.
- **Steps:** 1. Read 6-digit code from inbox. 2. Enter it. 3. Submit.
- **Expected:** Redirect to vessel/crew workspace (`/vessel` or `/crew/observations`).

## TC-06-003 — Crew observations (log + submit)
**Type:** workflow | **Status:** not-run (blocked)

- **Preconditions:** signed in, vessel assigned.
- **Steps:** 1. Open `/crew/observations`. 2. Review log. 3. Submit a new observation for a task on the checklist.
- **Expected:** Observation records and appears in the log.

## TC-06-004 — Offline capability
**Type:** functional | **Status:** not-run (needs device/offline harness)

- **Preconditions:** `/~offline` route + device support.
- **Steps:** 1. Load observation flow offline. 2. Submit offline.
- **Expected:** Observation queued and synced when online.

## TC-06-005 — Trainings
**Type:** data | **Status:** not-run

- **Preconditions:** signed in, trainings assigned.
- **Steps:** 1. Open `/crew/trainings`.
- **Expected:** Assigned trainings render.