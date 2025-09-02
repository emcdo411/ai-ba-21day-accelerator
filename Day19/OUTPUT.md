# ✅ Day 19 — End-to-End Bundle (Sample Output for Students)

> This file gives you a preview of what your mock project bundle should look like.  
> - Every file has a clear purpose and uses **placeholders** (`{{ProjectName}}`, `{{Owner}}`).  
> - Cross-links are **repo-relative** (no broken links).  
> - CSV, YAML, and JSON have valid structures.  
> - Page/word caps keep everything concise.  

---

## 1. `Projects/Mock_EndToEnd/BRD.md`
A short **Business Requirements Document** (≤2 pages).  
**What to expect:**  
- Sections: Purpose, Scope, Requirements, Assumptions, Out of Scope.  
- Jira IDs like `JIRA-101`, `JIRA-102` referenced inside.  
- Example line: *“Requirement JIRA-101: Users must log in with MFA.”*  

---

## 2. `Projects/Mock_EndToEnd/jira_export.csv`
A small **Jira export** with 12–20 rows.  
**What to expect:**  
- Columns: ID, Summary, Description, Status, Priority, Assignee.  
- IDs (JIRA-101, etc.) match BRD and test cases.  
- Example row:  
```

ID,Summary,Description,Status,Priority,Assignee
JIRA-101,Login with MFA,As a user I want MFA login,To Do,High,{{Owner}}

````

---

## 3. `Projects/Mock_EndToEnd/openapi.yaml`
A minimal, valid **OpenAPI spec**.  
**What to expect:**  
- At least one endpoint like `GET /items`.  
- Valid YAML structure.  
- Example snippet:  
```yaml
openapi: 3.0.0
info:
  title: {{ProjectName}} API
  version: "1.0"
paths:
  /items:
    get:
      summary: Get all items
      responses:
        "200":
          description: OK
````

---

## 4. `Projects/Mock_EndToEnd/uat_test_plan.md`

A short **User Acceptance Test Plan**.
**What to expect:**

* Sections: Scope, Entry/Exit Criteria, Environment, Roles, Risks.
* References at least 5 Jira IDs.
* Example: *“Scope includes validating JIRA-101, JIRA-104, and JIRA-110.”*

---

## 5. `Projects/Mock_EndToEnd/test_cases.csv`

At least **15 test cases** in CSV.
**What to expect:**

* Columns: TestID, JiraID, Preconditions, Steps, Expected, Priority.
* TestIDs like TC-01, TC-02 mapped to Jira IDs.
* Example row:

  ```
  TestID,JiraID,Preconditions,Steps,Expected,Priority
  TC-01,JIRA-101,User registered,Login with MFA,Access granted,High
  ```

---

## 6. `Projects/Mock_EndToEnd/dashboard_notes.md`

Notes about the **dashboard**.
**What to expect:**

* KPIs: uptime, conversion, latency.
* Layout notes: tiles, charts, alerts.
* Export guidance: *“Save as `dashboard.png` in assets folder.”*

---

## 7. `Projects/Mock_EndToEnd/automation_flow.json`

Valid **automation flow in JSON**.
**What to expect:**

* Keys: `steps`, `retryPolicy`, `alertConfig`.
* At least 3 steps with one retry.
* Example snippet:

  ```json
  {
    "steps": [
      {"id": "S1", "action": "ingest", "next": "S2"},
      {"id": "S2", "action": "transform", "retry": true},
      {"id": "S3", "action": "load"}
    ],
    "retryPolicy": ["1m","4m","15m"],
    "alertConfig": {"channel": "#alerts", "onFail": true}
  }
  ```

---

## 8. `Projects/Mock_EndToEnd/decision_memo.md`

An internal **Decision Memo** (≤1 page).
**What to expect:**

* Why a choice was made, trade-offs, who owns it.
* Example: *“Decision: adopt cloud-native. Trade-off: higher upfront cost. Owner: {{Owner}}.”*

---

## 9. `Projects/Mock_EndToEnd/board_brief.md`

An external-facing **Board Brief** (≤1 page).
**What to expect:**

* High-level summary for executives/board.
* Plain English, no jargon.
* Example: *“Recommendation: migrate to cloud-native within 90 days. Impact: reduced outages, \$500K annual savings.”*

---

## 10. `Projects/Mock_EndToEnd/README.md`

The **navigation file** tying everything together.
**What to expect:**

* Repo-relative links to each file.
* A 60-second tour of the project.
* Example excerpt:

  ```markdown
  # Mock End-to-End Project

  ## 📖 Tour
  1. Start with [BRD](Projects/Mock_EndToEnd/BRD.md)  
  2. Review [Jira Export](Projects/Mock_EndToEnd/jira_export.csv)  
  3. Explore [OpenAPI Spec](Projects/Mock_EndToEnd/openapi.yaml)  
  4. Check [UAT Plan](Projects/Mock_EndToEnd/uat_test_plan.md) and [Test Cases](Projects/Mock_EndToEnd/test_cases.csv)  
  5. See [Dashboard Notes](Projects/Mock_EndToEnd/dashboard_notes.md) and export as `dashboard.png`  
  6. Inspect [Automation Flow](Projects/Mock_EndToEnd/automation_flow.json)  
  7. Read the [Decision Memo](Projects/Mock_EndToEnd/decision_memo.md) and [Board Brief](Projects/Mock_EndToEnd/board_brief.md)
  ```

---

## ✅ Submission Checklist

* [x] BRD ≤2 pages with Jira references.
* [x] Jira export = 12–20 rows, correct headers, IDs consistent.
* [x] OpenAPI = valid YAML with at least one endpoint.
* [x] UAT plan references ≥5 Jira IDs.
* [x] Test cases ≥15 rows, mapped to Jira IDs.
* [x] Dashboard notes include export guidance (`dashboard.png`).
* [x] Automation flow JSON valid with steps, retryPolicy, alertConfig.
* [x] Decision Memo ≤1 page, Board Brief ≤1 page.
* [x] README provides 60-second tour with repo-relative links.

---
