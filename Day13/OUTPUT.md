File: output.md

# ✅ Day 13 — UAT Pack (What Good Output Looks Like)

> This example shows exactly what your three deliverables should look like.
> - **No clickable external links**: all URLs are shown in inline code (e.g., `https://test.example.com`) to avoid 404s.
> - **Use relative repo paths** (e.g., `tools/templates/uat_test_cases.csv`) rather than web URLs.

---

## Deliverable 1 — `Day13_ai_for_testing.md`

Below is the full content you should place in `Day13_ai_for_testing.md`. It includes the **UAT Test Plan** first, then the **Test Cases** (as a markdown table), then the **Traceability Matrix** (as a markdown table).

---

# UAT Test Plan — Day 13

## Overview & Objectives
Validate the critical user journeys for the “Account & Profile” slice: Authentication, Password Reset, and Profile Management. UAT focuses on business acceptance: “Does this meet stakeholder needs?”

## Scope
- In scope: Login, Logout, Password Reset (email), Profile View/Edit, Basic Accessibility checks (keyboard, labels), Light Performance check (page load/snappy save).
- Not in scope: SSO, MFA, advanced performance testing, penetration testing, analytics.

## Assumptions & Dependencies
- Stories and acceptance criteria (AC) are baselined for STY-101, STY-102, STY-103.
- Stable UAT environment and seeded synthetic test data.
- Defect tracker is configured (IDs auto-generated).

## Environments
- UAT URL: `https://uat.example.com` (shown as code to avoid 404)
- Test accounts: `user_01@example.com`, `user_02@example.com` (synthetic)
- Reset policy: database snapshots refreshed nightly at 02:00 local.

## Test Data Strategy
- **Synthetic only**. No production PII.
- Use masked values for any personal fields in screenshots or logs.

## Roles & Responsibilities
- UAT Lead (triage/sign-off): Jordan Lee
- Testers (execution/reporting): Student Team
- Dev Lead (fixes/clarifications): A. Chen
- PM (go/no-go): R. Patel

## Risks & Mitigations
| Risk | Owner | Mitigation |
|---|---|---|
| Unstable env breaks test runs | UAT Lead | Re-run after 30 min; escalate to DevOps |
| Ambiguous AC | PM | Host 15-min AC clinic; update AC notes |
| Test data collisions | UAT Lead | Unique suffix per tester (e.g., `_u15`) |

## Entry Criteria (minimum)
- UAT env healthy; smoke tests Pass.
- Accounts provisioned.
- Defect tracker ready.
- Stories/AC baselined and accessible in repo docs.

## Exit Criteria (minimum)
- ≥95% tests Pass.
- 0 open Sev-1/2 defects.
- Sev-3/4 have documented workarounds approved by PM.
- Traceability complete (Story ↔ AC ↔ Test).
- Formal sign-offs recorded.

## Reporting & Cadence
- Daily standup (15 min).
- End-of-day test status posted to `Day13_ai_for_testing.md`.
- Defect triage immediately after standup if any Sev-1/2 appear.

## Sign-off & Go/No-Go
- UAT Lead recommends Go/No-Go to PM.
- PM records final decision and rationale in Decision Log (`Projects/MiniProject2_ProcessFlow/decision_log.md`).

---

### Global Conventions
- **ID Patterns:** Story=`STY-###` (e.g., STY-101), AC=`AC-#.#` (e.g., AC-1.2), Test=`UAT-###` (e.g., UAT-015).
- **Enumerations:**
  - Priority: P0 (Critical), P1 (High), P2 (Medium), P3 (Low)
  - Status: Draft, Ready, In-Progress, Blocked, Pass, Fail, Deferred
  - Type: Functional, Regression, NFR, UAT
  - CoverageTag (choose one): Auth, PasswordReset, Profile, Accessibility, Perf
- **Mix Requirements:** ≥15 test cases; ≥30% must be Negative/Edge; include ≥2 Accessibility and ≥1 light Performance check.
- **CSV Hygiene:** UTF-8, comma-delimited, quote fields containing commas/newlines, include header row.

---

## Test Cases (Markdown View)
> The same rows also appear in `tools/templates/uat_test_cases.csv`.  
> Tip: keep Steps short and atomic; keep Expected outcomes verifiable.

| Test ID | Preconditions | Steps | Expected | Priority | Data | CoverageTag | Status |
|---|---|---|---|---|---|---|---|
| UAT-001 | User exists, active | 1) Go to `https://uat.example.com/login` 2) Enter valid email/pass 3) Click **Login** | Redirect to Dashboard; username visible | P0 | email=user_01@example.com | Auth | Ready |
| UAT-002 | None | 1) Go to `.../login` 2) Submit empty form | Inline errors for required fields | P1 | — | Auth | Ready |
| UAT-003 | User exists, wrong pass | 1) Enter valid email + wrong pass 2) Login | Error banner “Invalid credentials” | P0 | wrong pass | Auth | Ready |
| UAT-004 | Locked account | 1) Enter locked user creds 2) Login | Error “Account locked”; no session created | P1 | locked user | Auth | Ready |
| UAT-005 | None | 1) Click **Forgot password** 2) Enter valid email 3) Submit | Confirmation message; reset email sent | P0 | email=user_01@example.com | PasswordReset | Ready |
| UAT-006 | None | 1) Forgot password 2) Enter unknown email 3) Submit | Generic confirmation (no user enumeration) | P1 | unknown email | PasswordReset | Ready |
| UAT-007 | Reset token valid | 1) Open reset page 2) New strong pass 3) Submit | Success; can log in with new pass | P0 | token=valid | PasswordReset | Ready |
| UAT-008 | Reset token expired | 1) Open reset with expired token | Error “Link expired”; prompt to request new | P1 | token=expired | PasswordReset | Ready |
| UAT-009 | Logged in | 1) Go to Profile 2) Edit display name 3) Save | Success toast; value persists on refresh | P1 | displayName="Alex U15" | Profile | Ready |
| UAT-010 | Logged in | 1) Edit profile with invalid phone 2) Save | Field-level validation error | P2 | phone="abc" | Profile | Ready |
| UAT-011 | Logged in | 1) Keyboard-only navigate Profile 2) Tab through fields/buttons | All interactive elements reachable; visible focus | P2 | — | Accessibility | Ready |
| UAT-012 | Logged in, screen reader on | 1) Inspect labels for inputs/buttons | Inputs/buttons have meaningful labels | P2 | — | Accessibility | Ready |
| UAT-013 | None | 1) Load Login page | Page renders <2s on first paint (baseline) | P2 | — | Perf | Ready |
| UAT-014 | Logged in | 1) Logout | Redirect to Login; session cleared | P1 | — | Auth | Ready |
| UAT-015 | Logged in | 1) Deep link to Profile Save API without CSRF | Request blocked; safe error | P0 | — | Profile | Ready |

**Negative/Edge coverage check:** UAT-002, -003, -004, -006, -008, -010, -015 (7/15 = 46.7%) ✅  
**Accessibility checks:** UAT-011, -012 ✅  
**Perf check:** UAT-013 ✅

---

## Traceability Matrix (Markdown View)
> Every AC maps to ≥1 test, and every test maps up to a Story and AC.

| Story | AC ID | Test ID | Type | Priority | Status |
|---|---|---|---|---|---|
| STY-101 (Login) | AC-1.1 (Valid login) | UAT-001 | Functional | P0 | Ready |
| STY-101 (Login) | AC-1.2 (Errors) | UAT-002, UAT-003 | Functional | P0–P1 | Ready |
| STY-101 (Login) | AC-1.3 (Account lock) | UAT-004 | Functional | P1 | Ready |
| STY-101 (Login) | AC-1.4 (Logout) | UAT-014 | Functional | P1 | Ready |
| STY-102 (Password Reset) | AC-2.1 (Request) | UAT-005, UAT-006 | Functional | P0–P1 | Ready |
| STY-102 (Password Reset) | AC-2.2 (Reset) | UAT-007, UAT-008 | Functional | P0–P1 | Ready |
| STY-103 (Profile) | AC-3.1 (Edit) | UAT-009, UAT-010 | Functional | P1–P2 | Ready |
| STY-103 (Profile) | AC-3.2 (Accessibility) | UAT-011, UAT-012 | NFR | P2 | Ready |
| STY-103 (Profile) | AC-3.3 (Performance) | UAT-013 | NFR | P2 | Ready |
| STY-103 (Profile) | AC-3.4 (Security/CSRF) | UAT-015 | NFR | P0 | Ready |

---

### Submission Checklist (to avoid 404s)
- ✅ Save this file as `Day13_ai_for_testing.md` in your repo root (or your course folder).
- ✅ Use **inline code** (not links) for any URLs (e.g., `https://uat.example.com`).
- ✅ Place CSVs under `tools/templates/` exactly as named below.
- ✅ Do **not** paste web URLs as markdown links in this file.

---
```

```csv
File: tools/templates/uat_test_cases.csv
"Test ID","Preconditions","Steps","Expected","Priority","Data","CoverageTag","Status"
"UAT-001","User exists, active","Go to `/login` → Enter valid email/password → Click Login","Redirect to Dashboard; username visible","P0","email=user_01@example.com","Auth","Ready"
"UAT-002","None","Go to `/login` → Submit empty form","Inline errors for required fields","P1","","Auth","Ready"
"UAT-003","User exists, wrong pass","Enter valid email + wrong pass → Login","Error banner “Invalid credentials”","P0","wrong pass","Auth","Ready"
"UAT-004","Locked account","Enter locked user creds → Login","Error “Account locked”; no session created","P1","locked user","Auth","Ready"
"UAT-005","None","Forgot password → Enter valid email → Submit","Confirmation shown; reset email sent","P0","email=user_01@example.com","PasswordReset","Ready"
"UAT-006","None","Forgot password → Enter unknown email → Submit","Generic confirmation (no user enumeration)","P1","unknown email","PasswordReset","Ready"
"UAT-007","Reset token valid","Open reset page → Enter strong pass → Submit","Success; can log in with new pass","P0","token=valid","PasswordReset","Ready"
"UAT-008","Reset token expired","Open reset with expired token","Error “Link expired”; prompt to request new","P1","token=expired","PasswordReset","Ready"
"UAT-009","Logged in","Open Profile → Edit display name → Save","Success toast; value persists","P1","displayName=""Alex U15""","Profile","Ready"
"UAT-010","Logged in","Edit profile with invalid phone → Save","Field-level validation error","P2","phone=""abc""","Profile","Ready"
"UAT-011","Logged in","Keyboard-only navigate Profile → Tab through elements","All interactive elements reachable; visible focus","P2","","Accessibility","Ready"
"UAT-012","Logged in, screen reader on","Inspect labels for inputs/buttons","Inputs/buttons have meaningful labels","P2","","Accessibility","Ready"
"UAT-013","None","Load Login page","Page renders <2s on first paint (baseline)","P2","","Perf","Ready"
"UAT-014","Logged in","Click Logout","Redirect to Login; session cleared","P1","","Auth","Ready"
"UAT-015","Logged in","Attempt Profile Save API without CSRF","Request blocked; safe error","P0","","Profile","Ready"
```

```csv
File: tools/templates/traceability_matrix.csv
"Story","AC ID","Test ID","Type","Priority","Status"
"STY-101","AC-1.1","UAT-001","Functional","P0","Ready"
"STY-101","AC-1.2","UAT-002","Functional","P1","Ready"
"STY-101","AC-1.2","UAT-003","Functional","P0","Ready"
"STY-101","AC-1.3","UAT-004","Functional","P1","Ready"
"STY-101","AC-1.4","UAT-014","Functional","P1","Ready"
"STY-102","AC-2.1","UAT-005","Functional","P0","Ready"
"STY-102","AC-2.1","UAT-006","Functional","P1","Ready"
"STY-102","AC-2.2","UAT-007","Functional","P0","Ready"
"STY-102","AC-2.2","UAT-008","Functional","P1","Ready"
"STY-103","AC-3.1","UAT-009","Functional","P1","Ready"
"STY-103","AC-3.1","UAT-010","Functional","P2","Ready"
"STY-103","AC-3.2","UAT-011","NFR","P2","Ready"
"STY-103","AC-3.2","UAT-012","NFR","P2","Ready"
"STY-103","AC-3.3","UAT-013","NFR","P2","Ready"
"STY-103","AC-3.4","UAT-015","NFR","P0","Ready"
```
