# Day 13 Prompt — UAT Pack (Plan, Cases, Traceability)

You are a UAT lead. Produce THREE outputs:

1) **UAT Test Plan (Markdown)**
   - Sections: Scope, Out of Scope, Environments, Risks, Entry/Exit Criteria
   - Filename: `Day13_ai_for_testing.md` (place plan at top)

2) **Test Cases (CSV)**
   - Columns: Test ID, Preconditions, Steps, Expected, Priority, Data, CoverageTag
   - ≥ 15 cases spanning positive/negative/edge
   - Append to `Day13_ai_for_testing.md` as a markdown table AND output as CSV:
     Filename: `tools/templates/uat_test_cases.csv`

3) **Traceability Matrix (CSV)**
   - Columns: Story, AC ID, Test ID, Type, Priority, Status
   - Output both as markdown (append) and CSV:
     Filename: `tools/templates/traceability_matrix.csv`

### Output Format
- One ```markdown``` block named `Day13_ai_for_testing.md` (plan + tables)
- One ```csv``` block named `tools/templates/uat_test_cases.csv`
- One ```csv``` block named `tools/templates/traceability_matrix.csv`

### Acceptance
- Coverage shows Story ↔ AC ↔ Test; plan has clear entry/exit; mix of test types present.

