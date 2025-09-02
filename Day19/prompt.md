# Day 19 Prompt — End-to-End Bundle (v2)

You are assembling a **mock project portfolio**. Produce the following files with exact names and paths:

---

## Files to Produce

1. `Projects/Mock_EndToEnd/BRD.md`  
   - ≤2 pages.  
   - Sections: Purpose, Scope, Requirements, Assumptions, Out of Scope.  
   - Must reference Jira IDs (e.g., JIRA-101).  

2. `Projects/Mock_EndToEnd/jira_export.csv`  
   - 12–20 rows.  
   - Columns: ID, Summary, Description, Status, Priority, Assignee.  
   - IDs must match those referenced in BRD, UAT, and test cases.  

3. `Projects/Mock_EndToEnd/openapi.yaml`  
   - Minimal, valid OpenAPI 3.x spec.  
   - At least one path (e.g., `GET /items`).  
   - Must pass a YAML linter.  

4. `Projects/Mock_EndToEnd/uat_test_plan.md`  
   - Sections: Scope, Entry/Exit Criteria, Environment, Roles, Risks.  
   - Must reference at least 5 Jira IDs.  

5. `Projects/Mock_EndToEnd/test_cases.csv`  
   - ≥15 rows.  
   - Columns: TestID, JiraID, Preconditions, Steps, Expected, Priority.  
   - TestIDs must map to UAT and Jira IDs.  

6. `Projects/Mock_EndToEnd/dashboard_notes.md`  
   - Notes on dashboard KPIs, layout, and insights.  
   - Must include **export guidance** with inline code path: `dashboard.png`.  

7. `Projects/Mock_EndToEnd/automation_flow.json`  
   - Valid JSON.  
   - Keys: `steps[]`, `retryPolicy` (1m, 4m, 15m), `alertConfig`.  
   - At least 3 steps, one with retry.  

8. `Projects/Mock_EndToEnd/decision_memo.md`  
   - ≤1 page.  
   - Internal rationale: why chosen approach, trade-offs, owner.  

9. `Projects/Mock_EndToEnd/board_brief.md`  
   - ≤1 page.  
   - External-facing: summary for executives/board.  
   - Plain language, high-level impact, request.  

10. `Projects/Mock_EndToEnd/README.md`  
    - Provides a **60-second tour** of the project.  
    - Repo-relative markdown cross-links to all files.  
    - Includes a suggested reading order (e.g., 1 → 2 → 3).  

---

## Acceptance Criteria

- **Cross-linking**: README must link to each artifact with relative paths.  
- **Consistency**: Jira IDs used consistently across BRD, UAT, test cases.  
- **Validity**:  
  - OpenAPI parses as valid YAML.  
  - CSVs are UTF-8, comma-delimited, with headers.  
  - JSON is valid and contains required keys.  
- **Export guidance**: Dashboard export shown as inline code path `dashboard.png` (not links).  
- **Conciseness**: BRD ≤2 pages, Memo ≤1 page, Board Brief ≤1 page.  
- **Placeholders**: Use `{{ProjectName}}`, `{{Owner}}`, `{{DecisionDate}}` where real details are needed.  
- **Portfolio-ready**: All files form a coherent, end-to-end mock project.

---
