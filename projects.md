# 🎯 Projects — Expanded Scopes, Deliverables & Rubrics

## Mini-Project 1 — AI-Generated BRD Draft

**Objective:** Turn a messy problem statement into a crisp, AI-assisted Business Requirements Document.

**Inputs:** Stakeholder notes, 1–2 user personas, 3–5 business goals.
**Core Tasks:** Problem framing → scope & out-of-scope → requirements (business/functional/non-functional) → assumptions/risks → acceptance criteria.
**Deliverables:**

* `Projects/MiniProject1_BRD_Draft/BRD.md` (≤6 pages)
* `stakeholders.md` (RACI + contact cadence)
* `requirements_traceability.csv` (Req ↔ AC ↔ Test placeholder)
  **Acceptance (0–100):** Clarity 30 • Traceability 25 • Risk/assumptions 20 • Testability 15 • Executive tone 10
  **Timebox:** 4–6 hours
  **Starter prompt:** “You are a principal BA. Draft a BRD from these notes. Separate business/functional/non-functional reqs; each must be testable.”

---

## Mini-Project 2 — Process Flow + Refined BRD

**Objective:** Visualize the target process and harden requirements.

**Inputs:** Mini-Project 1 BRD; event/exception cases.
**Core Tasks:** As-Is/To-Be flows, swimlanes, exceptions, data handoffs; refine BRD and ACs.
**Deliverables:**

* `process_to_be.mmd` (Mermaid) + PNG export
* `exceptions_catalog.md` (top 10 edge cases)
* Updated `BRD.md` (versioned diffs)
  **Acceptance (0–100):** Correctness 30 • Exceptions 25 • Readability 20 • Alignment w/ BRD 15 • Versioning hygiene 10
  **Timebox:** 6–8 hours
  **Starter prompt:** “Create a To-Be swimlane in Mermaid from this BRD. Call out 5 exception paths and data handoffs.”

---

## Mini-Project 3 — Refined BRD + Testing Plan

**Objective:** Prove testability with a tight UAT pack and traceability.

**Inputs:** Refined BRD, flows, ACs.
**Core Tasks:** UAT test plan, test cases, entry/exit criteria, defect triage flow, RTM.
**Deliverables:**

* `uat_test_plan.md` (scope, roles, E2E scenarios)
* `test_cases.xlsx` (scenario → steps → expected → priority)
* `rtm.csv` (Req → AC → TestCase → Owner)
  **Acceptance (0–100):** Coverage 35 • Clarity 25 • RTM integrity 25 • Triage workflow 15
  **Timebox:** 6–8 hours
  **Starter prompt:** “Generate UAT scenarios from these ACs. Prioritize with MoSCoW; include negative tests and data setup.”

---

## Capstone — AI BA Portfolio Pitch

**Objective:** Package your artifacts into a 7–10 minute board-ready narrative.

**Core Tasks:** Story arc, live or screenshot demo, quantified outcomes, risks/mitigations, next steps.
**Deliverables:**

* `slides/capstone_deck.pdf` (9–12 slides)
* `demo_script.md` (timestamps + links)
* `portfolio_index.md` (artifact map + outcomes)
  **Acceptance (0–100):** Narrative 20 • Artifact quality 30 • Executive clarity 20 • Governance 15 • Q\&A 15
  **Timebox:** 1–2 days (including rehearsal)
  **Starter prompt:** “Turn these artifacts into a 9-slide exec deck: decision-first, outcomes quantified, one risk slide.”

---

## 🔁 Optional Project Tracks (Pick 1–3 to stand out)

### A) Data-Viz Decision Pack (PowerBI/Tableau/R)

**Goal:** One page that answers “What changed? Why? What now?”
**Deliverables:** KPI tiles, trend with deltas, funnel/pareto, variance waterfall + **3 action bullets** with owners/dates.
**Acceptance:** Insight/actionability over aesthetics (0–100): Insight 40 • Accuracy 30 • Storytelling 20 • Hygiene 10.
**Timebox:** 6–8 hours.

### B) API-First Requirements (OpenAPI + Postman)

**Goal:** Make requirements unambiguous via contracts.
**Deliverables:** `openapi.yaml`, Postman collection, sample payloads + error codes, contract tests.
**Acceptance:** Spec completeness 40 • Error handling 25 • Examples 20 • Collection usability 15.

### C) Agentic Automation (Zapier/Make/Power Automate)

**Goal:** Automate a daily digest or BRD change notifier with retries and alerts.
**Deliverables:** Flow export, error policy (idempotency, 3× retry, DLQ), ops runbook.
**Acceptance:** Reliability 40 • Observability 25 • Security (no secrets in logs) 20 • Docs 15.

### D) Responsible AI Pack

**Goal:** Prove you can ship AI safely.
**Deliverables:** 1-page AI Use Policy, DPIA-lite, eval harness (10 prompts w/ expected), red-team log (8 attacks).
**Acceptance:** Policy clarity 30 • Risk coverage 30 • Evals/metrics 25 • Red-team insights 15.

### E) UAT Simulation w/ Stakeholders

**Goal:** Run a time-boxed UAT with two personas.
**Deliverables:** Schedule, scripts, sign-off sheet, defect log with severities/SLAs, summary.
**Acceptance:** Coverage 35 • Evidence 30 • Triage discipline 20 • Comms 15.

### F) Stakeholder Comms Pack

**Goal:** Decision-first communication at exec level.
**Deliverables:** One-pager (Problem/Options/Rec/Risks/Next 30/90), 10-Q FAQ, 5-slide mini-deck.
**Acceptance:** Executive clarity 40 • Concision 30 • Anticipatory FAQ 20 • Visual hygiene 10.

### G) ROI & Scenario Modeling (Finance)

**Goal:** Tie requirements to dollars.
**Deliverables:** Driver-based model (assumptions tab), 3 scenarios (base/low/high), sensitivity tornado, 1-page CFO brief.
**Acceptance:** Assumption rigor 35 • Scenario clarity 30 • Visuals 20 • CFO-friendly narrative 15.

---

## 🧰 Suggested Repo Layout (Projects)

```text
Projects/
├── MiniProject1_BRD_Draft/
│   ├── BRD.md
│   ├── stakeholders.md
│   └── requirements_traceability.csv
├── MiniProject2_ProcessFlow/
│   ├── process_to_be.mmd
│   ├── process_to_be.png
│   └── exceptions_catalog.md
├── MiniProject3_Refined_BRD/
│   ├── uat_test_plan.md
│   ├── test_cases.xlsx
│   └── rtm.csv
├── Capstone_AI_BA_Pitch/
│   ├── slides/capstone_deck.pdf
│   ├── demo_script.md
│   └── portfolio_index.md
└── Optional_Tracks/
    ├── DataViz_DecisionPack/
    ├── API_First_OpenAPI/
    ├── Agentic_Automation/
    ├── Responsible_AI/
    ├── UAT_Simulation/
    ├── Stakeholder_Comms/
    └── ROI_Scenarios/
```

---

## ✅ Portfolio Bar (What “Great” Looks Like)

* Traceability from **BRD → Flow → AC → Test → API** is demonstrably tight.
* Dashboards tell a **decision story** (insight, cause, action with owner/date).
* Automation has **retries, idempotency, and alerts**; runbook included.
* AI work shows **governance** (policy, DPIA-lite, evals, red-team).
* Exec materials are **decision-first** and succinct.
* Capstone is **rehearsed** and time-boxed with clean handoffs.

---

## 🧪 Quick Rubric (Global, 0–100)

* Problem clarity & scoping — 15
* Requirements quality & testability — 20
* Visualization & narrative (insight/action) — 15
* Automation reliability & ops hygiene — 15
* Governance (policy, risk, evals) — 15
* Executive communication — 20
  **Pass bar:** ≥ 90; no category < 60.

---

Want me to auto-generate empty stubs and template files for each project folder too?
