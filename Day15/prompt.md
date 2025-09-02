# Day 15 Prompt — Dashboard + Narrative (Advanced, v2)

You are a **Senior Data Storytelling Coach**. From KPI data I will provide, produce the following:

---

## Required File
1) `Day15_ai_data_viz.md` — A single markdown report that includes:

### Section 1: Dataset Summary
- Concise overview (≤120 words) of metrics, date range, cohorts.  
- If a metric is missing, write `placeholder`. Do **not** invent values.

### Section 2: Visuals & Narrative
Describe ≤5 visuals. Each must include **repo-relative image links** (not external URLs).  

- **KPI Tiles** — Layout + narrative  
  - **Include image link:** `assets/dashboard_kpis.png`  
- **Trend** — with YoY/DoD deltas; explain annotations  
- **Funnel or Pareto** — highlight top loss/variance  
- **Plan vs Actual Variance Waterfall**  
  - **Include image link:** `assets/dashboard_variance.png`  

For each visual provide a 3-bullet block (each ≤18 words):  
- **Insight** — What the visual shows  
- **Cause Hypothesis** — Why this happened  
- **Action** — `[Owner=Role] [Due=MM/DD]`, concrete next step  

### Section 3: Design Rationale
≤150 words explaining why this layout supports executive decision-making.

### Section 4: Next Iterations
Propose **3 improvements across different areas**:  
- 1 Design change  
- 1 Metric/data enhancement  
- 1 Narrative/communication tweak  

---

## Export Guidance
Append at bottom of `Day15_ai_data_viz.md`:  
- **PowerBI** — ≤5 bullets to export `assets/dashboard_kpis.png` and `assets/dashboard_variance.png`  
- **Tableau** — ≤5 bullets for the same exports  
- **R (ggplot2 / plotly)** — ≤5 bullets for the same exports  

---

## Style Constraints
- Executive tone, crisp, decision-first.  
- Repo-relative image links only (e.g., `assets/...`), never external links.  
- No invented data — use `placeholder` explicitly if missing.  

---

## Acceptance
- ≤5 visuals described.  
- Each visual includes Takeaway (Insight) + Action (with owner/date).  
- Both image links (`dashboard_kpis.png`, `dashboard_variance.png`) included.  
- Export guidance present for PowerBI, Tableau, and R.  
- Iterations span design, data, and narrative.  

