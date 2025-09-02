# Day 13 — AI for UAT & Testing Docs

Turn acceptance criteria into **testable evidence**. Today you’ll produce a compact **UAT test plan**, a **test case pack** (positive/negative/edge), and a **traceability matrix** that proves coverage.

---

## 🎯 Objectives
- Transform AC into positive/negative/edge **test cases**.
- Build a **Story ↔ AC ↔ Test** traceability matrix.
- Draft a concise **UAT test plan** (scope, env, risks, entry/exit).

---

## 🧠 Key Concepts
- **Boundary values**: test at min/max, just-below/just-above (e.g., 0, 1, max-1, max).
- **Negative paths**: invalid input, unauthorized, rate limit, network fail.
- **Coverage**: every AC maps to ≥1 positive + ≥1 negative/edge test.
- **Traceability**: Story → AC → Test (and back), so gaps are obvious.

---

## 📥 Inputs You Need
- User stories with **Acceptance Criteria** (6–12 AC recommended).
- Non-functional constraints (e.g., perf, security) if available.
- Any test data requirements or role permissions.

---

## 📦 Deliverables
- `Day13_ai_for_testing.md` — UAT test plan + embedded tables (cases + matrix).
- `tools/templates/uat_test_cases.xlsx` and `tools/templates/traceability_matrix.xlsx` *(or CSV imports)*.

> If you prefer CSV for easy import, use:
> `tools/templates/uat_test_cases.csv` and `tools/templates/traceability_matrix.csv`.

---

## ✅ QA Checklist
- [ ] Each AC has **positive + negative/edge** coverage.
- [ ] **Entry/Exit** criteria are explicit and measurable.
- [ ] The matrix joins every **Story ↔ AC ↔ Test** (no orphans).
- [ ] Test data and roles are specified where relevant.
- [ ] Status fields use a consistent set: *Not Run, Pass, Fail, Blocked*.

---

## 🧭 Workflow (30–60 min)

1) **Normalize AC (5–10 min)**  
   - Rewrite AC into Given/When/Then where possible.  
   - Identify fields with minimums/maximums, required/optional, role constraints.

2) **Design Tests (15–25 min)**  
   - For each AC, create:
     - **Positive** test (happy path).
     - **Negative** test (invalid/unauthorized/failed dependency).
     - **Edge/boundary** test (e.g., length=0/1/max, date rollover, empty set).
   - Add **Priority** (*High/Medium/Low*) based on risk and business impact.

3) **Build the Traceability Matrix (5–10 min)**  
   - Map each Test ID back to **AC ID** and **Story**.
   - Ensure **no AC without tests** and **no test without an AC**.

4) **Draft UAT Test Plan (5–15 min)**  
   - Scope/Out of Scope, Environments, Roles & Responsibilities.  
   - Entry/Exit criteria, Risks, Defect triage, Reporting cadence.

---

## 📑 Templates (Copy/Paste)

### A) UAT Test Plan (paste into `Day13_ai_for_testing.md`)
```md
# UAT Test Plan — {{Project / Feature}}

## 1. Scope
- In Scope: {{features, flows}}
- Out of Scope: {{explicit exclusions}}

## 2. Environments & Data
- Env: {{UAT URL / version}} | Data: {{seed accounts, roles}}
- Access & permissions: {{how to request}}

## 3. Roles & Responsibilities
- BA: test design & coverage checks
- QA/UAT testers: execution & evidence
- Product Owner: acceptance & sign-off

## 4. Entry Criteria
- BRD v{{n}} approved, stable AC list
- UAT env deployed & accessible
- Seed data loaded / test accounts provisioned

## 5. Exit Criteria
- All **High** priority tests **Pass**
- No **Critical** open defects; **Major** ≤ {{threshold}}
- Traceability 100% Story↔AC↔Test

## 6. Risks & Mitigations
- Env instability → daily health check; retry window
- Test data drift → nightly refresh; data owner on-call
- External API quotas → stub or reduced schedule

## 7. Execution & Reporting
- Cycle: {{dates}}
- Cadence: daily stand-up + dashboard link
- Evidence: screenshots/logs attached to cases

## 8. Sign-off
- UAT Sign-off by {{role}} on {{date}}
````

### B) Test Cases Table (embed in `Day13_ai_for_testing.md` and export to CSV/XLSX)

```md
| Test ID | Story | AC ID  | Type      | Priority | Preconditions                | Steps                                                | Expected Result                                  | Data / Role     | Status   |
|---------|-------|--------|-----------|----------|------------------------------|-----------------------------------------------------|--------------------------------------------------|-----------------|----------|
| TC-001  | US-01 | AC-1.1 | Positive  | High     | User logged in (Role: Admin) | 1) Submit valid form 2) Confirm toast               | Record saved; success toast; appears in listing  | Valid dataset   | Not Run  |
| TC-002  | US-01 | AC-1.1 | Negative  | High     | User logged in (Viewer)      | 1) Attempt submit without permission                | 403 error; no change persisted                   | Viewer account  | Not Run  |
| TC-003  | US-01 | AC-1.1 | Edge      | Medium   | User logged in (Admin)       | 1) Submit field length = max 2) Save                | Saved; value truncated/validated per spec        | Max-length data | Not Run  |
```

### C) Traceability Matrix (embed + export)

```md
| Story | AC ID   | Test ID | Type      | Priority | Status  |
|------:|---------|---------|-----------|----------|---------|
| US-01 | AC-1.1  | TC-001  | Positive  | High     | Not Run |
| US-01 | AC-1.1  | TC-002  | Negative  | High     | Not Run |
| US-01 | AC-1.1  | TC-003  | Edge      | Medium   | Not Run |
```

> **Tip:** For boundary analysis, add TC-004/005 for min-1 and max+1 where constraints exist.

---

## 🤖 AI Prompts (Copy/Paste)

### 1) AC → Test Cases

> *“You are a UAT test designer. From these Acceptance Criteria, generate test cases covering **positive**, **negative**, and **edge/boundary** scenarios. Return a table with columns: Test ID, Story, AC ID, Type, Priority, Preconditions, Steps, Expected Result, Data/Role, Status=Not Run. Keep each step crisp and verifiable.”*

### 2) Cases → Traceability Matrix

> *“From the test cases table, build a **Story ↔ AC ↔ Test** traceability matrix. Highlight any **AC without tests** and any **tests without an AC**.”*

### 3) Plan (Entry/Exit + Risks)

> *“Draft a concise **UAT Test Plan** with Scope/Out-of-scope, Environments & Data, Roles, **Entry/Exit criteria**, Risks & mitigations, and Reporting cadence. Keep it one page.”*

---

## 📤 Export Instructions (CSV/XLSX)

* In your editor, copy the **Test Cases** table to a CSV named:
  `tools/templates/uat_test_cases.csv`
* Copy the **Traceability Matrix** table to a CSV named:
  `tools/templates/traceability_matrix.csv`
* (Optional) Import both CSVs into Excel and save as:

  * `tools/templates/uat_test_cases.xlsx`
  * `tools/templates/traceability_matrix.xlsx`

**Headers must match exactly** to avoid import quirks.

---

## 🧪 Review Rubric (Pass/Ready)

* **Coverage (40%)** — Each AC has Positive + Negative/Edge tests.
* **Quality (30%)** — Steps are clear; Expected is verifiable and unambiguous.
* **Traceability (20%)** — Matrix complete; no orphans.
* **Plan (10%)** — Entry/Exit criteria usable; risks realistic with mitigations.

---

## ❗ Common Mistakes (and quick fixes)

* **Only happy paths** → add at least one **negative** and one **edge** per AC.
* **Vague Expected** → specify exact message/status/state change.
* **Missing Data/Role** → state the role and data variant (valid/invalid/boundary).
* **No sign-off criteria** → add measurable **Exit** criteria.

---

## ✅ Done When

* `Day13_ai_for_testing.md` contains the **test plan** and the **two tables**.
* CSV/XLSX exports exist in `tools/templates/`.
* Every AC is covered by at least **2 tests** (positive + one of negative/edge).

```
