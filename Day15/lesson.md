# Day 15 — AI for Data Visualization (PowerBI / Tableau / R Shiny)

## 🎯 Objectives
- Build an exec-grade dashboard that answers “so what?” not “so what’s shown?”
- Use tidy data and minimal visuals to surface insight → action → owner/date.
- Document narrative beneath each visual to make decisions obvious.

## 🧠 Key Concepts
- **Tidy data**: (date, cohort, feature, metric, value).
- **Design rules**: ≤5 visuals, left→right decision flow, deltas + targets, traffic lights.
- **Narrative layer**: “Takeaway (≤20 words)” + “Action (verb + owner + date)”.

## 🛠 Hands-On (60–90m)
1) Prepare a tidy table with 3–5 KPIs (ARR/throughput/churn etc.).  
2) Build visuals:
   - KPI tiles with Δ vs prior period + target line.
   - Trend w/ YoY or DoD deltas annotated.
   - Funnel **or** Pareto to localize loss/variance.
   - Plan vs Actual variance waterfall.
3) Add annotation cards under each visual: Insight / Cause Hypothesis / Action.  
4) Export **dashboard_kpis.png** and **dashboard_variance.png**.

## 📦 Deliverables
- `Day15_ai_data_viz.md` (screenshots + “insight text” under each viz)
- `assets/dashboard_kpis.png`, `assets/dashboard_variance.png`
- Optional: `pbix/` or `twbx/` or `rshiny/`

## ✅ QA Checklist
- ≤5 visuals; targets + p50/p95 when relevant; traffic lights applied.
- Every chart has **Takeaway** and **Action (owner/date)**.
- Narrative states decision implied, not just observation.

## 📝 Prompt Aid
“You are a data storytelling coach. From these KPIs and trends, write 3 bullets: (1) insight, (2) cause hypothesis, (3) action with owner/date. Keep each bullet ≤18 words.”
