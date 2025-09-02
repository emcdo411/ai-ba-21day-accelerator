# Day 08 — AI in Jira & Confluence

Turn your Week 1 BRD into a **clean Jira backlog** and a **Confluence BRD space** that execs can skim in 60 seconds. Aim for **traceability you can defend**: Story ↔ AC ↔ Decision/Risk ↔ Jira issue.

---

## 🎯 Objectives
- Convert BRD stories/AC into a **Jira-ready backlog** with labels and traceability.
- Stand up a **Confluence BRD space** with Executive Summary (≤150 words), scoped child pages, and links to Jira.
- Publish **repeatable JQL filters** for scope, status, and hygiene checks.

---

## 🧠 Key Concepts
- **Backlog hygiene:** Titles ≤10 words, AC in Given/When/Then, labels from a **controlled list** (e.g., `frontend`, `backend`, `data`, `risk`, `api`, `security`).
- **Traceability:** Story ↔ AC ↔ Decision/Risk ↔ Jira issue (store Decision Log & Risks in Confluence; link from BRD + Jira).
- **Confluence structure:** Parent **BRD** page, children: **Scope**, **Stories** (links to Jira filter), **Decisions (DDL)**, **Risks**.

---

## 📥 Inputs You Need
- Week 1 BRD (stories + acceptance criteria).
- Your project key and epic key in Jira (e.g., `PROJ`, `PROJ-123`).
- Access to a Confluence space for this project.

---

## 📦 Deliverables
- `Day08_jira_confluence.md` — links (Jira filters, Confluence pages), screenshots, and the JQL snippets you used.
- `tools/templates/jira_bulk_template.csv` — headers: `Summary,Description,Issue Type,Labels,Story Points,Epic Link`.

---

## 🛠 Hands-On (60–90m)

### 1) Extract & Normalize (BRD → backlog draft)
- Pull **8–12 stories** with AC from the BRD.
- Normalize titles to **≤10 words**; rewrite AC to Given/When/Then.
- Assign labels from the **controlled list**.

**AI Prompt (copy/paste):**
> “You are a BA lead. Normalize these story titles (≤10 words), rewrite AC in Given/When/Then, and assign labels from {frontend, backend, data, api, security, risk}. Return CSV columns: Summary, Description (include AC), Issue Type=Story, Labels (semicolon-separated), Story Points (S/M/L/XL), Epic Link={{EPIC_KEY}}.”

---

### 2) Create CSV for **Jira Bulk Create**
Save as `tools/templates/jira_bulk_template.csv`:

```csv
Summary,Description,Issue Type,Labels,Story Points,Epic Link
"User can reset password","AC:\nGiven ...\nWhen ...\nThen ...","Story","frontend;security","S","PROJ-123"
"Export orders to CSV","AC:\nGiven ...\nWhen ...\nThen ...","Story","backend;data","M","PROJ-123"

