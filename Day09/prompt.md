# Day 09 Prompt — Backlog Ops + KPI Scorecard

You are a PMO analyst. Produce THREE outputs I can paste/import:

1) **Backlog Sample Data (CSV)**
   - Columns: Story ID, Title, Status, Owner, Points, Start, Due, Risk
   - 12–20 rows with realistic spread of statuses and dates.
   - Filename: `tools/templates/kpi_backlog_seed.csv`

2) **KPI & Ops Instructions (Markdown)**
   - Step-by-step to build two tabs in Sheets/Excel:
     - Backlog Ops: overdue flag, throughput/aging formulas, conditional formatting rules.
     - KPI Scorecard: 3 leading + 3 lagging metrics with formulas and thresholds.
   - Include the exact formulas in a code fence.
   - Filename: `Day09_excel_google_sheets.md`

3) **Import Helper (CSV)**
   - Pre-baked KPI thresholds table: KPI, GreenFrom, YellowFrom, RedFrom, CalcFormula
   - Filename: `tools/templates/kpi_thresholds.csv`

### Output Format
- One ```csv``` block named `tools/templates/kpi_backlog_seed.csv`
- One ```markdown``` block named `Day09_excel_google_sheets.md`
- One ```csv``` block named `tools/templates/kpi_thresholds.csv`

### Acceptance
- I can import both CSVs into Sheets and paste the formulas to reproduce your results.

