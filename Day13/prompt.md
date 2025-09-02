# Day 13 Prompt — UAT Pack (Plan, Cases, Traceability)

You are the UAT Lead. Produce THREE outputs with the exact filenames and blocks below.

## Global Conventions (apply to all outputs)
- **ID Patterns:** Story=`STY-###` (e.g., STY-101), AC=`AC-#.#` (e.g., AC-1.2), Test=`UAT-###` (e.g., UAT-015).
- **Enumerations:**
  - Priority: P0 (Critical), P1 (High), P2 (Medium), P3 (Low)
  - Status: Draft, Ready, In-Progress, Blocked, Pass, Fail, Deferred
  - Type: Functional, Regression, NFR, UAT
  - CoverageTag (choose one): Auth, Payments, Search, Profile, PII, Accessibility, Perf, Email, Reports, Admin
- **Test Mix Requirements:** ≥15 test cases total; ≥30% must be Negative/Edge; include at least 2 Accessibility and 1 light Performance/NFR check.
- **CSV Hygiene:** UTF-8, comma-delimited, quoted fields when containing commas/newlines, include header row.

---

## 1) UAT Test Plan (Markdown)
- **Sections (in order):** Overview & Objectives, Scope, Out of Scope, Assumptions & Dependencies, Environments (URLs, data reset policy), Test Data Strategy (synthetic only; no production PII), Roles & Responsibilities (incl. defect triage owner), Risks & Mitigations, Entry Criteria, Exit Criteria, Reporting & Cadence, Sign-off & Go/No-Go.
- **Entry Criteria (minimum):** environments stable; accounts provisioned; stories & AC baselined; defect tracker ready; smoke tests Pass.
- **Exit Criteria (minimum):** ≥95% tests Pass; 0 open Sev-1/2; Sev-3/4 have approved workarounds; traceability complete; sign-offs recorded.
- **Add a short Risk table (3–5 rows) with owner + mitigation.**
- **Filename:** `Day13_ai_for_testing.md` (plan appears at the top of the file)

---

## 2) Test Cases (CSV + Markdown table)
- **Columns:** Test ID, Preconditions, Steps, Expected, Priority, Data, CoverageTag, Status
- Include positive, negative, and boundary cases; mark any a11y/perf checks via CoverageTag.
- **Append the table to `Day13_ai_for_testing.md` AND output as CSV:**
  - Filename: `tools/templates/uat_test_cases.csv`
- **Provide 1 example row first** to show formatting, then the full set.

---

## 3) Traceability Matrix (CSV + Markdown table)
- **Columns:** Story, AC ID, Test ID, Type, Priority, Status
- Each AC must map to ≥1 Test ID; every Test ID traces up to a Story and AC.
- **Append the table to `Day13_ai_for_testing.md` AND output as CSV:**
  - Filename: `tools/templates/traceability_matrix.csv`

---

## Output Format (exactly 3 code blocks)
1. One ```markdown``` block named `Day13_ai_for_testing.md` (plan first, then the two tables)
2. One ```csv``` block named `tools/templates/uat_test_cases.csv`
3. One ```csv``` block named `tools/templates/traceability_matrix.csv`

## Acceptance
- Traceability shows **Story ↔ AC ↔ Test** with no gaps.
- Plan includes roles, defect process, data/privacy policy, and clear entry/exit metrics.
- Test set meets mix quotas (positive/negative/edge, a11y/perf), uses required enums, and passes CSV hygiene.
````


