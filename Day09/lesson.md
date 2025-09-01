# Day 09 — Excel/Google Sheets + AI Copilots

## 🎯 Objectives
- Build a Backlog Ops sheet and a KPI Scorecard with traffic-light rules.
- Compute throughput, aging, and a simple forecast to clear the backlog.
- Use AI to propose formulas and sizing heuristics.

## 🧠 Key Concepts
- **Throughput:** items done per week; **Aging:** days since started.
- **Leading vs lagging KPIs:** early signals vs outcomes.
- **Conditional formatting:** visual status at a glance.

## 🛠 Hands-On
1) Create **Backlog Ops** tab: Story ID, Title, Status, Owner, Points, Start, Due, Risk.  
2) Create **KPI Scorecard**: 3 leading + 3 lagging metrics, thresholds.  
3) Use formulas: Overdue flag, T-shirt sizing, XLOOKUPs from Stories table.  
4) Add conditional formatting (green/yellow/red).

## 📦 Deliverables
- `Day09_excel_google_sheets.md` (screens, formulas, description).
- `tools/templates/kpi_backlog_sheet.xlsx` (or import CSV to create).

## 🧪 QA Checklist
- Overdue rows correctly flagged.
- Throughput/aging formulas verified.
- KPI thresholds display traffic lights.

## 📎 Helpful formulas
```excel
=IF([@[Due]]<TODAY(),"Overdue","On Track")
=IFERROR(XLOOKUP([@[Story ID]],Stories[ID],Stories[Points]),"")
=LET(p,[@[Points]],IF(p<=3,"S",IF(p<=5,"M",IF(p<=8,"L","XL"))))

