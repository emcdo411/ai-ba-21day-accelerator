# Day 08 Prompt — Jira & Confluence Package

You are a BA lead. Generate TWO artifacts from the BRD material I provide:

1) **Jira Bulk Create CSV**
   - Columns: Summary, Description, Issue Type, Labels, Story Points, Epic Link
   - Normalize titles (≤10 words), expand AC in bullets, add labels {frontend, backend, data, risk}, include rough Story Points (S/M/L/XL → map to 2/5/8/13).
   - **Return in a fenced CSV block** and label it:
     Filename: `tools/templates/jira_bulk_template.csv`

2) **Confluence Page Kit**
   - Parent: BRD page (Executive Summary ≤150 words) + child pages: Scope, Stories (link placeholder), Decisions (DDL table), Risks.
   - Include the DDL and Risks tables with 2–3 example rows.
   - Provide 2 starter JQL queries.
   - **Return in a fenced Markdown block** and label it:
     Filename: `Day08_jira_confluence.md`

### Input
- I will paste BRD excerpts (stories + AC) after this message.

### Output Format
- One ```csv``` block named `tools/templates/jira_bulk_template.csv`
- One ```markdown``` block named `Day08_jira_confluence.md`

### Acceptance
- CSV imports to Jira without header issues.
- Executive summary ≤150 words, clear child-page structure, working JQL snippets.

