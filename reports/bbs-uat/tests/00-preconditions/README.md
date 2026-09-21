# 00 — Global Preconditions

These must be true before ANY role folder runs. They are not role-specific tests; they set up the environment so each role can execute its own cases.

## PC-01 — Test tenant & seeded data available
**Type:** environment  
**Status:** pass (verified live against `dev-bbs` Atlas, dev server on :3000)

- **Preconditions:** Mongo Atlas `dev-bbs` seeded via `pnpm seed`.
- **Steps:** 1. Confirm dev server responds on `http://localhost:3000`. 2. Navigate to `/sign-in`.
- **Expected:** Sign-in page renders ("Sign in to Bahri BBS / Powered by TailoredTech"), with Password + Email code tabs.

## PC-02 — Known user accounts exist
**Type:** data  
**Status:** pass

- **Preconditions:** seed ran.
- **Steps:** Each listed account returns "No account found" if missing, so attempt login per role folder.
- **Expected:** All accounts in `local/seed-passwords.txt` resolve.

## PC-03 — General clean test data
**Type:** data  
**Status:** not-run (specific cases create their own data)

- **Preconditions:** —
- **Steps:** Ensure the tenant has at least: 1 office admin, 1 office member, 1 coordinator, 1 STO, 1 ETS, ≥2 vessels, ≥1 crew observer signed on.
- **Expected:** Record-level UI (observations, vessels, crew) is not empty.

## Account reference (for testers)

| Role | Email | Auth |
|---|---|---|
| Super admin | admin@tailoredtech.tech (admin panel password) | /administration/sign-in |
| Office admin | admin@tailoredtech.tech | /sign-in password |
| Office member | joseph.essam@bahri.sa | /sign-in password |
| Coordinator | test.coordinator@bahri.sa | /sign-in password |
| Office (basic) | test.office.user@bahri.sa | /sign-in password |
| STO | ahmed.alrashid@bahri.sa | /sign-in password |
| ETS | fatima.alzahrani@bahri.sa | /sign-in password |
| Crew observer | albin.baby.2641@bahri.sa | /sign-in email OTP |
| Vessel | ajwad.vessel@bahri.sa | /sign-in email OTP |

> **Note:** office/STO/ETS/coordinator/auth family authenticate by **password**; crew & vessel authenticate by **email OTP** (code delivered to the authorized inbox by SES). Full crew/vessel walkthrough therefore requires inbox access to read the OTP — flagged as a UAT **blocker** in the report.