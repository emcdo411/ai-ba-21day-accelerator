# Day 14 Prompt — MiniProject2 Submission Pack

You are compiling MiniProject2. Produce or update the following files:

1) **BRD v2 (Markdown)**
   - Add Jira links, Decision Log references, Risks.
   - Filename: `Projects/MiniProject2_ProcessFlow/BRD_v2.md`

2) **Decision Log (Markdown)**
   - Table: Date | Decision | Owner | Rationale | Status | Link
   - Filename: `Projects/MiniProject2_ProcessFlow/decision_log.md`

3) **Process Maps**
   - Provide two Mermaid diagrams (current/target) and export guidance to PNG:
     - `Projects/MiniProject2_ProcessFlow/process_current.png`
     - `Projects/MiniProject2_ProcessFlow/process_target.png`
   - Append Mermaid + steps to a short note file:
     Filename: `Projects/MiniProject2_ProcessFlow/process_notes.md`

4) **OpenAPI + Postman**
   - Refine `tools/openapi.yaml` (or output full YAML to overwrite)
   - Update Postman JSON with 2 tests/endpoint:
     Filename: `Projects/MiniProject2_ProcessFlow/postman_collection.json`

5) **UAT Pack**
   - Test Plan (Markdown): `Projects/MiniProject2_ProcessFlow/uat_test_plan.md`
   - Test Cases (CSV acceptable): `Projects/MiniProject2_ProcessFlow/uat_test_cases.csv`
   - Traceability (CSV acceptable): `Projects/MiniProject2_ProcessFlow/traceability_matrix.csv`

6) **KPI Sheet (CSV acceptable)**
   - Provide a KPI/backlog CSV if Excel not possible:
     Filename: `Projects/MiniProject2_ProcessFlow/kpi_backlog_sheet.csv`

### Output Format
- Multiple fenced blocks:
  - ```markdown``` named files for BRD_v2.md, decision_log.md, process_notes.md, uat_test_plan.md
  - ```yaml``` named `tools/openapi.yaml` (or the project path if you prefer)
  - ```json``` named `Projects/MiniProject2_ProcessFlow/postman_collection.json`
  - ```csv``` named for each CSV deliverable

### Acceptance
- All files present and internally cross-linked.
- Mermaid renders; PNG export steps provided.
- OpenAPI/Postman validate; UAT plan/cases/traceability align; KPI csv usable.

