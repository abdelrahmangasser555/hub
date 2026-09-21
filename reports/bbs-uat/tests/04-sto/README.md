# 04 — STO (Ships' Technical Officer — Ahmed Al-Rashid)

Executed by the STO. Owns the STO & ETS analytics/circulation module plus observations/activities across vessels.

## TC-04-001 — STO signs in
**Type:** auth | **Status:** pass

- **Preconditions:** PC-01/02.
- **Steps:** 1. `/sign-in` → Password. 2. `ahmed.alrashid@bahri.sa` + STO password. 3. Sign in.
- **Expected:** Redirect to **/sto-ets** module. Sidebar identifies "Ahmed Al-Rashid". Screenshot: `sto-home.png`, `sto-ets-module.png`.

## TC-04-002 — STO-ETS module is the landing module
**Type:** auth/UX | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. After login, confirm destination is `/sto-ets` (not `/office`).
- **Expected:** STO is routed to the STO/ETS workspace. *(Contrast with ETS — see 05-002.)*

## TC-04-003 — STO analytics
**Type:** functional | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Open **Analytics** within `/sto-ets/analytics`.
- **Expected:** Analytics view renders with metrics. Screenshot: `sto-analytics.png`.

## TC-04-004 — Active chatroom hub
**Type:** functional | **Status:** pass

- **Preconditions:** logged in, STO & ETS Hub exists.
- **Steps:** 1. Open Chatrooms → "STO & ETS Hub".
- **Expected:** Hub opens; announcements/messages visible.

## TC-04-005 — Observations + activities access
**Type:** data | **Status:** pass

- **Preconditions:** logged in.
- **Steps:** 1. Open `/sto-ets/observations` & activities.
- **Expected:** Data renders without error. Screenshot: `sto-observations.png`.