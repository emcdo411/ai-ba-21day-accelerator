# ✅ Day 14 Prompt — MiniProject2 Submission Pack (Final)

You are compiling **MiniProject2**. Produce or update the following **files inside one folder**:

**Project folder:** `Projects/MiniProject2_ProcessFlow/`

---

## 1) BRD v2 (Markdown)

* **Filename:** `Projects/MiniProject2_ProcessFlow/BRD_v2.md`
* Include at the top:

  * **Executive Summary** (≤150 words, decision-first)
  * **Table of Contents** (anchors to sections below)
  * **Links (relative):** Jira filter URL(s), `decision_log.md`, `process_current.png`, `process_target.png`, `openapi.yaml`, `postman_collection.json`, `uat_test_plan.md`, `uat_test_cases.csv`, `traceability_matrix.csv`, `kpi_backlog_sheet.csv`
* Sections to include: **Problem**, **Scope (In/Out)**, **Actors**, **User Stories & AC**, **Risks & Mitigations**, **KPIs**, **Traceability overview**.

## 2) Decision Log (Markdown)

* **Filename:** `Projects/MiniProject2_ProcessFlow/decision_log.md`
* Table columns (exact): `Date | Decision | Owner | Due | Rationale | Status | Link`
* Use **ISO-8601** dates (YYYY-MM-DD). Include ≥3 rows.

## 3) Process Maps (Mermaid + PNG export steps)

* **Filename:** `Projects/MiniProject2_ProcessFlow/process_notes.md`
* Include **two Mermaid diagrams** (Current and Target), each **< 12 nodes**, with **actor prefixes** (e.g., `Cust:`, `Ops:`, `Fin:`).
* **Do not** include placeholders.
* Add **explicit PNG export steps** targeting:

  * `Projects/MiniProject2_ProcessFlow/process_current.png`
  * `Projects/MiniProject2_ProcessFlow/process_target.png`

## 4) OpenAPI + Postman

* **OpenAPI file:** `Projects/MiniProject2_ProcessFlow/openapi.yaml`

  * OpenAPI **3.0+**, include **auth header**, **examples**, and **errors** (400/401/404/409/429/500).
* **Postman collection:** `Projects/MiniProject2_ProcessFlow/postman_collection.json`

  * **schema:** `https://schema.getpostman.com/json/collection/v2.1.0/collection.json`
  * Use variables `{{baseUrl}}`, `{{token}}`
  * **≥2 tests per endpoint** (status code, body field present, response time < 2000ms).

## 5) UAT Pack

* **UAT Plan (Markdown):** `Projects/MiniProject2_ProcessFlow/uat_test_plan.md`

  * Scope, Env & Data, Roles, **Entry/Exit**, Risks, Reporting cadence.
* **Test Cases (CSV):** `Projects/MiniProject2_ProcessFlow/uat_test_cases.csv`

  * Columns (exact): `Test ID,Story,AC ID,Type,Priority,Preconditions,Steps,Expected Result,Data/Role,Status`
  * Include **Positive**, **Negative**, **Edge** coverage; **≥12** rows.
* **Traceability (CSV):** `Projects/MiniProject2_ProcessFlow/traceability_matrix.csv`

  * Columns (exact): `Story,AC ID,Test ID,Type,Priority,Status`
  * Prove Story ↔ AC ↔ Test joins; **no orphans**.

## 6) KPI / Backlog Sheet (CSV)

* **Filename:** `Projects/MiniProject2_ProcessFlow/kpi_backlog_sheet.csv`
* Two tabs simulated as CSV sections separated by a header comment:

  * **Backlog Ops** headers: `Story ID,Title,Status,Owner,Points,Start,Due,Completed,Risk`
  * **KPI Scorecard** headers: `KPI,Value,Target,Status,Owner,Next Review`
* Provide **2–3 sample rows** for each table; use placeholders where data unknown.

---

## Output Format (critical)

Return **multiple fenced code blocks**, one per file.
Inside the **first line** of each fence, include a **FILE marker** like this:

* For Markdown/YAML/JSON/CSV:

```markdown
<!-- FILE: Projects/MiniProject2_ProcessFlow/BRD_v2.md -->
# BRD v2 — …
```

```markdown
<!-- FILE: Projects/MiniProject2_ProcessFlow/decision_log.md -->
# Decision Log
| Date | Decision | Owner | Due | Rationale | Status | Link |
…
```

```yaml
# FILE: Projects/MiniProject2_ProcessFlow/openapi.yaml
openapi: 3.0.3
info: { title: "{{project_name}} API", version: "0.2.0" }
…
```

```json
{
  "_file": "Projects/MiniProject2_ProcessFlow/postman_collection.json",
  "info": { "name": "{{project_name}} API", "_postman_id": "placeholder", "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json" },
  "item": [ … ],
  "variable": [
    { "key": "baseUrl", "value": "https://api.example.com" },
    { "key": "token", "value": "{{token}}" }
  ]
}
```

```csv
# FILE: Projects/MiniProject2_ProcessFlow/uat_test_cases.csv
Test ID,Story,AC ID,Type,Priority,Preconditions,Steps,Expected Result,Data/Role,Status
TC-001,US-001,AC-1.1,Positive,High,"Admin logged in","1) … 2) …","201 + body includes id","Admin, valid payload",Not Run
…
```

**Do not** include secrets or real tokens; use placeholders (`{{token}}`, `{{project_key}}`, etc.).
**Ensure JSON/YAML are valid** (no trailing commas, proper quoting).

---

## Acceptance (unchanged but explicit)

* **All files present** in `Projects/MiniProject2_ProcessFlow/` and **internally cross-linked** from `BRD_v2.md`.
* **Mermaid renders** (no placeholders, < 12 nodes); **PNG export steps** included.
* **OpenAPI/Postman validate** (v2.1 schema; tests included).
* **UAT plan/cases/traceability align**; CSV headers exact; **no orphan AC/tests**.
* **KPI CSV usable**; shows at least 2 KPIs and owners.

## Final “Lint” Section (add at bottom of BRD)

* Link check list (tick when each relative link opens in GitHub).
* OpenAPI quick-parse passed.
* Postman imported without errors.
* CSVs opened and column headers matched.

---

