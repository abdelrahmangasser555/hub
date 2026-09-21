# BBS — User Acceptance Testing (UAT) Suite v2

Behavior-Based Safety application. Bahri Maritime (client). Prepared by TailoredTech via Hermes.

## How to use this suite

- Cases are grouped in **folders**, one per **user level / role** (`01-office-admin`, `02-office-member`, …).
- Each test case is a numbered block with a fixed structure:

```
### TC-<NN> — <short title>
<Type: functional / UI / data / permission / workflow>
<Status: not-run | pass | fail | blocked | needs-feedback>

**Preconditions** — what must be true before executing.
**Steps** — numbered, one action per line.
**Expected result** — what a correct app does.
```

- A test "folder" (group of cases) is executed by the role that owns it.
- `00-preconditions` must be satisfied before any other folder runs.

## Roles covered

| Folder | Role | Sign-in method |
|---|---|---|
| 00 | Preconditions (global data) | n/a |
| 01 | Office Admin (Tailored Tech Admin) | password |
| 02 | Office Member (Joseph Essam) | password |
| 03 | Coordinator (Test Coordinator) | password |
| 04 | STO (Ahmed Al-Rashid) | password |
| 05 | ETS (Fatima Al-Zahrani) | password |
| 06 | Crew Observer (albin.baby.*) | email OTP |
| 07 | Vessel (ajwad) | email OTP |
| 08 | Cross-cutting (all roles) | mixed |

## Statuses used

- **not-run** — defined but not yet executed
- **pass** — executed, matched expected result
- **fail** — executed, did not match (defect)
- **blocked** — cannot execute (missing access / prerequisite)
- **needs-feedback** — behaves unexpectedly; correctness is a product decision (logical uncertainty)