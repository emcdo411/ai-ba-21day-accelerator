<!-- FILE: Projects/MiniProject2_ProcessFlow/EXPECTED_OUTPUT.md -->
# MiniProject2 — Sample Submission (What “Good” Looks Like)

> **Purpose:** Show students the shape, depth, and linking quality we expect.  
> **Note:** This is a *sample*, not a template to copy verbatim. Replace all placeholders (`{{...}}`) in your own work.

---

## 👀 Visual Index (All Artifacts Linkable)

- **BRD v2:** [BRD_v2.md](BRD_v2.md)  
- **Decision Log:** [decision_log.md](decision_log.md)  
- **Process Maps:** Current → ![process_current.png](process_current.png) · Target → ![process_target.png](process_target.png)  
- **API:** [openapi.yaml](../../tools/openapi.yaml)  
- **Postman Collection:** [postman_collection.json](postman_collection.json)  
- **UAT Plan:** [uat_test_plan.md](uat_test_plan.md)  
- **Test Cases:** [uat_test_cases.csv](uat_test_cases.csv)  
- **Traceability:** [traceability_matrix.csv](traceability_matrix.csv)  
- **KPI / Backlog:** [kpi_backlog_sheet.csv](kpi_backlog_sheet.csv)

> Tip: Open this page on GitHub and click every link above. In your own submission, your BRD’s **Links** section should mirror this list.

---

## 📘 BRD v2 Snapshot (Above the Fold)

**Executive Summary (≤150 words, decision-first).**  
This initiative improves {{target outcome}} for {{audience}} by {{timeframe}}. Success is measured by **KPI1** (target {{n}}) and **KPI2** (target {{n}}). In scope: {{flows/systems}}. Out of scope: {{deferrals}}. Top risks include vendor rate-limits and AC ambiguity; mitigations include idempotent retries, error contracts, and UAT coverage. See **Links** for Jira scope, API, UAT, and KPIs.

**Scope (In/Out) — Example Lines**
- **In:** Order create/list/status; auth; rate-limit handling  
- **Out:** Loyalty points, returns (phase 2)

**Actors**
- Cust, Ops, Fin, Eng, BI

**User Stories + AC (excerpt)**
- **US-001 Place Order**  
  - **AC-1.1**: Given valid cart/payment, when submit, then order ID returns ≤2s  
  - **AC-1.2**: Given declined payment, when submit, then reason shown; **no order** created

**Risks & Mitigations (excerpt)**
- Vendor 429s → Backoff, cache, alert; KPI monitor (Owner: Eng)

**KPIs (excerpt)**
- Lead time (order→ship) < 48h (Owner: Ops; Weekly)

---

## 🗓 Decision Log (Excerpt)

See: [decision_log.md](decision_log.md)

| Date       | Decision                              | Owner     | Due        | Rationale                   | Status | Link            |
|------------|----------------------------------------|-----------|------------|-----------------------------|--------|-----------------|
| 2025-09-01 | Add idempotency key to payment capture | Fin Lead  | 2025-09-08 | Prevent duplicates on retry | Open   | {{JIRA_LINK_2}} |

---

## 🗺 Process Maps

**Rendered PNGs**:  
- Current: ![Current](process_current.png)  
- Target: ![Target](process_target.png)

**Source** (see [process_notes.md](process_notes.md)) contains two **Mermaid** diagrams (<12 nodes each) and the export steps to produce these PNGs.

---

## 🔌 API & Postman (Validation Snapshot)

**OpenAPI**: [openapi.yaml](../../tools/openapi.yaml) (3.0.3, bearer auth, examples, errors 400/401/404/409/429/500).

**Postman Collection**: [postman_collection.json](postman_collection.json)  
- Variables: `{{baseUrl}}`, `{{token}}`, `{{orderId}}`  
- Each endpoint has **≥2 tests** (status, body field, response time < 2000ms).  
- Example test (Create Order):
```js
pm.test('Status 201', () => pm.response.to.have.status(201));
pm.test('Body has id', () => pm.expect(pm.response.json()).to.have.property('id'));
pm.test('Response < 2000ms', () => pm.expect(pm.response.responseTime).to.be.below(2000));
````

---

## 🧪 UAT Pack

**Plan**: [uat\_test\_plan.md](uat_test_plan.md)

* Scope/Out of Scope, Env & Data, Roles, Entry/Exit, Risks, Reporting cadence.

**Test Cases (CSV)**: [uat\_test\_cases.csv](uat_test_cases.csv) *(sample rows)*

```
Test ID,Story,AC ID,Type,Priority,Preconditions,Steps,Expected Result,Data/Role,Status
TC-001,US-001,AC-1.1,Positive,High,"Admin logged in","POST /orders (valid)","201 + id",Admin; valid payload,Not Run
TC-002,US-001,AC-1.1,Negative,High,"Admin logged in","POST /orders (invalid card)","400 BAD_REQUEST; no order",Admin; invalid,Not Run
```

**Traceability (CSV)**: [traceability\_matrix.csv](traceability_matrix.csv) *(no orphans)*

```
Story,AC ID,Test ID,Type,Priority,Status
US-001,AC-1.1,TC-001,Positive,High,Not Run
US-001,AC-1.1,TC-002,Negative,High,Not Run
```

---

## 📊 KPI / Backlog (CSV)

See: [kpi\_backlog\_sheet.csv](kpi_backlog_sheet.csv)

**Backlog Ops**

* Overdue flag, Aging, Throughput computed in your sheet.

**KPI Scorecard (example rendering)**

| KPI                      | Value | Target | Status | Owner | Next Review |
| ------------------------ | ----: | -----: | :----: | :---- | :---------- |
| Throughput (items/wk)    |     8 |     10 |   🔴   | PMO   | 2025-09-08  |
| Aging (median days, WIP) |    11 |      7 |   🟡   | QA    | 2025-09-08  |
| High-risk items open     |     3 |      1 |   🔴   | BA    | 2025-09-08  |

---

## ✅ Submission Checklist (Student)

* [ ] All required files exist at exact paths in `Projects/MiniProject2_ProcessFlow/`.
* [ ] **BRD links work** (open each on GitHub).
* [ ] Mermaid renders; **both PNGs committed**.
* [ ] OpenAPI parses; Postman imports; tests present.
* [ ] Test cases cover **positive + negative/edge** per AC.
* [ ] Traceability has **no orphans**.
* [ ] KPI CSV includes at least **2 KPIs with owners/targets**.

---

## 🧮 Self-Assessment (Rubric Ready)

| Category                              | Max | Self | Notes |
| ------------------------------------- | --: | ---: | ----- |
| Traceability (Story↔AC↔Test↔API)      |  25 |      |       |
| Diagrams (clarity, handoffs)          |  20 |      |       |
| API realism (errors, examples, tests) |  20 |      |       |
| UAT depth & coverage                  |  20 |      |       |
| KPI/ops readiness                     |  15 |      |       |
| **Total (Pass ≥ 80; no < 60)**        | 100 |      |       |

---

## 🆘 Common Issues (and fixes)

* **Broken relative links** → copy exact filenames/paths; click-test on GitHub.
* **Mermaid doesn’t render** → block must start with ` ```mermaid ` and not be nested/indented.
* **CSV headers wrong** → use headers exactly as provided.
* **No idempotency** → add idempotency key in API + test for duplicate submit.

---

### Reviewer Notes (What we look for)

* Can we follow links from BRD to every artifact without hunting?
* Do diagrams show fewer than 12 nodes with clear handoffs?
* Do Postman tests assert status, body, and latency?
* Does traceability prove coverage (no hand-waving)?
* Do KPIs communicate “what changed and why” with owners/dates?

```
