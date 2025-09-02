<!-- FILE: Projects/MiniProject2_ProcessFlow/EXPECTED_OUTPUT.md -->

# MiniProject2 — Sample Submission (What “Good” Looks Like)

> **Purpose:** Help you understand the expected structure, clarity, and linking quality for your deliverables.
> **Note:** This is a *sample*, not a template. Do **not** copy it verbatim. Replace all placeholders (`{{...}}`) and make sure your links point to the **actual paths in your repo**.

---

## 👀 Visual Index (All Artifacts Must Be Linkable)

All links below assume your files are placed **inside `Projects/MiniProject2_ProcessFlow/`**, unless noted otherwise. If your file paths differ, your links **must reflect that** — otherwise, they will break (404).

### Required Artifacts

| Artifact                | Expected File Name/Path                                        |
| ----------------------- | -------------------------------------------------------------- |
| **BRD v2**              | [`BRD_v2.md`](BRD_v2.md)                                       |
| **Decision Log**        | [`decision_log.md`](decision_log.md)                           |
| **Current Process Map** | ![Current](process_current.png)                                |
| **Target Process Map**  | ![Target](process_target.png)                                  |
| **OpenAPI Spec**        | [`openapi.yaml`](openapi.yaml) *(put this in the same folder)* |
| **Postman Collection**  | [`postman_collection.json`](postman_collection.json)           |
| **UAT Plan**            | [`uat_test_plan.md`](uat_test_plan.md)                         |
| **UAT Test Cases**      | [`uat_test_cases.csv`](uat_test_cases.csv)                     |
| **Traceability Matrix** | [`traceability_matrix.csv`](traceability_matrix.csv)           |
| **KPI / Backlog Sheet** | [`kpi_backlog_sheet.csv`](kpi_backlog_sheet.csv)               |

> ✅ **Sanity Check:** After committing your files, open your repo on GitHub and click **each link** above. If any give you a 404, your path is wrong — **fix it before submitting.**

---

## 📘 BRD v2 Snapshot (Above the Fold)

**Executive Summary (≤150 words, decision-first):**
This initiative improves {{target outcome}} for {{audience}} by {{timeframe}}. Success is measured by **KPI1** (target {{n}}) and **KPI2** (target {{n}}). In scope: {{flows/systems}}. Out of scope: {{deferrals}}. Top risks include vendor rate-limits and AC ambiguity; mitigations include idempotent retries, error contracts, and UAT coverage. See **Links** for Jira scope, API, UAT, and KPIs.

**Scope (In/Out):**

* **In:** Order create/list/status; auth; rate-limit handling
* **Out:** Loyalty points, returns (phase 2)

**Actors:**
Cust, Ops, Fin, Eng, BI

**User Stories + AC (excerpt):**

* **US-001 Place Order**

  * **AC-1.1**: Given valid cart/payment, when submit, then order ID returns ≤2s
  * **AC-1.2**: Given declined payment, when submit, then reason shown; **no order** created

**Risks & Mitigations (excerpt):**

* Vendor 429s → Backoff, cache, alert; KPI monitor (Owner: Eng)

**KPIs (excerpt):**

* Lead time (order→ship) < 48h (Owner: Ops; Weekly)

---

## 🗓 Decision Log (Excerpt)

See: [`decision_log.md`](decision_log.md)

| Date       | Decision                               | Owner    | Due        | Rationale                   | Status | Link              |
| ---------- | -------------------------------------- | -------- | ---------- | --------------------------- | ------ | ----------------- |
| 2025-09-01 | Add idempotency key to payment capture | Fin Lead | 2025-09-08 | Prevent duplicates on retry | Open   | {{JIRA\_LINK\_2}} |

---

## 🗺 Process Maps

Rendered PNGs (you must **commit these image files**):

* **Current State** → ![Current](process_current.png)
* **Target State** → ![Target](process_target.png)

> 📝 You must also include a [`process_notes.md`](process_notes.md) file showing your **Mermaid** source and how the diagrams were exported.

---

## 🔌 API & Postman

* **OpenAPI Spec:** [`openapi.yaml`](openapi.yaml)
  Must support: bearer auth, examples, error responses (400, 401, 404, 409, 429, 500).
* **Postman Collection:** [`postman_collection.json`](postman_collection.json)

**Postman Collection Requirements:**

* Use variables: `{{baseUrl}}`, `{{token}}`, `{{orderId}}`
* Each endpoint must have **≥2 tests**: status code, body field, and response time < 2000ms

Example test:

```js
pm.test('Status 201', () => pm.response.to.have.status(201));
pm.test('Body has id', () => pm.expect(pm.response.json()).to.have.property('id'));
pm.test('Response < 2000ms', () => pm.expect(pm.response.responseTime).to.be.below(2000));
```

---

## 🧪 UAT Pack

* **Plan:** [`uat_test_plan.md`](uat_test_plan.md)
* **Test Cases CSV:** [`uat_test_cases.csv`](uat_test_cases.csv)
* **Traceability Matrix:** [`traceability_matrix.csv`](traceability_matrix.csv)

🧾 **CSV Formatting:** Headers must match exactly. Sample:

```
Test ID,Story,AC ID,Type,Priority,Preconditions,Steps,Expected Result,Data/Role,Status
TC-001,US-001,AC-1.1,Positive,High,"Admin logged in","POST /orders (valid)","201 + id",Admin; valid payload,Not Run
```

---

## 📊 KPI / Backlog Sheet

* File: [`kpi_backlog_sheet.csv`](kpi_backlog_sheet.csv)

Your sheet must show:

* KPI definitions and owners
* Backlog with aging, throughput, flags

Sample KPI table:

| KPI                      | Value | Target | Status | Owner | Next Review |
| ------------------------ | ----: | -----: | :----: | :---- | :---------- |
| Throughput (items/wk)    |     8 |     10 |   🔴   | PMO   | 2025-09-08  |
| Aging (median days, WIP) |    11 |      7 |   🟡   | QA    | 2025-09-08  |
| High-risk items open     |     3 |      1 |   🔴   | BA    | 2025-09-08  |

---

## ✅ Submission Checklist (for Students)

* [ ] All files above exist in `Projects/MiniProject2_ProcessFlow/`
* [ ] All links open correctly **on GitHub** (no 404s)
* [ ] Mermaid blocks render and **PNGs are committed**
* [ ] Postman imports successfully and has tests
* [ ] Positive + negative test cases written
* [ ] Traceability matrix has **no missing links**
* [ ] KPI CSV includes **at least 2 KPIs with owners and targets**

---

## 🧮 Self-Assessment (for Rubric)

| Category                                | Max | Self | Notes |
| --------------------------------------- | --: | ---: | ----- |
| Traceability (Story↔AC↔Test↔API)        |  25 |      |       |
| Diagrams (clarity, handoffs)            |  20 |      |       |
| API realism (errors, examples, tests)   |  20 |      |       |
| UAT depth & coverage                    |  20 |      |       |
| KPI/ops readiness                       |  15 |      |       |
| **Total (Pass ≥ 80; no category < 60)** | 100 |      |       |

---

## 🧯 Common Pitfalls (and Fixes)

| Problem                          | Solution                                                 |
| -------------------------------- | -------------------------------------------------------- |
| 🔗 Broken links (404)            | Click-test **every link on GitHub** before submitting    |
| 🖼 Mermaid diagrams don’t render | Use triple-backticks with `mermaid`; avoid indentation   |
| 📊 CSVs have incorrect headers   | Copy headers from this file exactly                      |
| ❌ Missing idempotency            | Add key to API + verify in test case                     |
| 📁 Wrong folder structure        | Ensure files are in `Projects/MiniProject2_ProcessFlow/` |

---

## 🔍 Reviewer Tips (What We Look For)

* Links in the BRD point to all key artifacts
* Process diagrams are clear, readable, and show fewer than 12 nodes
* Postman tests check status, body field, and response time
* Traceability matrix is complete and accurate
* KPIs clearly communicate outcomes, owners, and targets

---

