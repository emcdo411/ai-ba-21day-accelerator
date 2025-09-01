# Day 13 — AI for UAT & Testing Docs

## 🎯 Objectives
- Transform AC into positive/negative/edge test cases.
- Build a Story ↔ AC ↔ Test traceability matrix.
- Draft a concise UAT test plan with entry/exit criteria.

## 🧠 Key Concepts
- **Boundary values**, **negative paths**, **coverage**.
- **Traceability**: evidence that requirements are testable and tested.

## 🛠 Hands-On
1) Convert 6–12 AC into test cases (table).  
2) Build traceability matrix (Story, AC ID, Test ID, Type, Priority, Status).  
3) Draft UAT test plan (scope, env, risks, entry/exit).

## 📦 Deliverables
- `Day13_ai_for_testing.md` (plan + cases + matrix).
- `tools/templates/uat_test_cases.xlsx`, `tools/templates/traceability_matrix.xlsx` (or CSV import).

## 🧪 QA Checklist
- Positive/negative/edge covered.
- Entry/exit criteria clear.
- Matrix joins every Story ↔ AC ↔ Test.

## 📎 Matrix snippet
```md
| Story | AC ID | Test ID | Type | Priority | Status |
|-------|------:|---------|------|----------|--------|
| US-12 | AC-12.1 | TC-045 | Positive | High | Not Run |

