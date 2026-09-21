# 07 — Vessel (e.g. ajwad — vessel-level account)

Executed by a vessel user (Captain / vessel admin). Auth = **email OTP** (same blocker as crew).

## TC-07-001 — Vessel OTP request
**Type:** auth | **Status:** pass (flow) / blocked (completion)

- **Preconditions:** PC-01/02.
- **Steps:** 1. `/sign-in` → **Email code**. 2. Enter vessel email (`ajwad.vessel@bahri.sa`). 3. Send code.
- **Expected:** OTP step appears, no error.

## TC-07-002 — Vessel completes sign-in
**Type:** auth | **Status:** blocked

- **Preconditions:** OTP delivered.
- **Steps:** 1. Enter code. 2. Submit.
- **Expected:** Redirect to vessel workspace (`/vessel`).

## TC-07-003 — Vessel dashboard / crew
**Type:** data | **Status:** not-run (blocked)

- **Preconditions:** signed in.
- **Steps:** 1. Open `/vessel/dashboards`. 2. Open `/vessel/crew`.
- **Expected:** Vessel crew + dashboards render.

## TC-07-004 — Vessel observations / requests / activities
**Type:** workflow | **Status:** not-run

- **Preconditions:** signed in.
- **Steps:** 1. Open `/vessel/observations`, `/vessel/requests`, `/vessel/activities`.
- **Expected:** Each renders and supports its workflow (create request, submit observation, log activity).

## Route reference (vessel)
- `/vessel` — hub
- `/vessel/dashboards`, `/vessel/crew`, `/vessel/observations`, `/vessel/requests`, `/vessel/activities`

> These were verified **reachable in routing** (all resolve without 404) but **interactive completion requires the OTP**.