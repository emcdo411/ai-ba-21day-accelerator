# Day 08 — AI in Jira & Confluence

## 🎯 Objectives
- Convert BRD stories/AC into a Jira-ready backlog with labels and traceability.
- Stand up a Confluence BRD space with executive summary, scoped pages, and cross-links.
- Produce repeatable queries (JQL) for status views.

## 🧠 Key Concepts
- **Backlog hygiene:** consistent titles, testable AC, labels (frontend/backend/data/risk).
- **Traceability:** Story ↔ AC ↔ Decision/Risk ↔ Jira issue.
- **Confluence structure:** Parent BRD page with children (Scope, Stories, Decisions, Risks).

## 🛠 Hands-On (60–90m)
1) From Week 1 BRD, extract 8–12 stories + AC.  
2) Normalize titles (≤10 words), add labels; prepare CSV for Jira bulk create.  
3) Create Confluence BRD parent page (with Executive Summary ≤150 words) and children:
   - **Scope**, **Stories** (link to Jira filter), **Decisions** (DDL table), **Risks**.
4) Draft starter JQL filters for epic scope and “ready for dev”.

## 📦 Deliverables
- `Day08_jira_confluence.md` (links, screenshots, JQL snippets).
- `tools/templates/jira_bulk_template.csv` (Summary, Description, Issue Type, Labels, Story Points, Epic Link).

## 🧪 QA Checklist
- Titles normalized; AC are testable; labels present.
- Confluence pages created with working links to Jira.
- JQL returns the intended set.

## 📎 Snippets
**Starter JQL**
```text
project = {{PROJECT_KEY}} AND type in (Story, Task)
AND "Epic Link" = {{EPIC_KEY}} ORDER BY Rank ASC
# {{PROJECT_NAME}} — BRD (Executive Summary ≤150 words)

## Scope
- In / Out

## Stories (linked to Jira)
- {{JIRA_FILTER_URL}}

## Decisions (DDL)
- YYYY-MM-DD | Decision | Owner | Rationale | Status

## Risks
- Risk | Impact | Likelihood | Mitigation | Owner

