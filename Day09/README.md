# Day 09 — Excel/Google Sheets + AI Copilots

Build a **Backlog Ops** sheet and a **KPI Scorecard** that leaders can scan in seconds. Use AI/Copilot to propose formulas, spot risk, and keep sizing honest.

---

## 🎯 Objectives
- Create a **Backlog Ops** tab and a **KPI Scorecard** with traffic-light rules.
- Calculate **throughput**, **aging**, and a simple **forecast** to clear the backlog.
- Use AI to propose formulas and sizing heuristics you can defend.

---

## 🧠 Key Concepts
- **Throughput:** items completed per week.  
- **Aging:** days since an item started (or since it entered “In Progress”).  
- **Leading vs Lagging KPIs:** *leading* = early signals (e.g., blockers, WIP); *lagging* = outcomes (e.g., cycle time).  
- **Conditional formatting:** green/yellow/red at a glance.

---

## 📥 Inputs You Need
- A list of stories/issues (from Jira CSV or manual): ID, Title, Status, Owner, Points, Start Date, Due Date, Completed Date (if done), Risk flag.

---

## 📦 Deliverables
- `Day09_excel_google_sheets.md` — screenshots, formulas, brief rationale.  
- `tools/templates/kpi_backlog_sheet.xlsx` *(or import CSV then save as .xlsx)*.

**Optional**: If you prefer CSV first, start with `tools/templates/kpi_backlog_sheet.csv` and import it into Excel/Sheets.

---

## 🛠 Hands-On

### 1) Backlog Ops tab (table named `Stories`)
Columns (in this order):

