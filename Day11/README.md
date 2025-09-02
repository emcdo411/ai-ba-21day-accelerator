# Day 11 — AI for Meeting Notes/Transcripts

Turn messy notes into **decisions, owners, and dates** a stakeholder can act on. Today is about **evidence-first summarization**: no hallucinations, no vibes—just traceable decisions.

---

## 🎯 Objectives
- Convert raw notes/transcripts into a **Decision & Action Register (DAR)** with Owners and Due dates.
- Extract a compact **RACI** for the top decisions.
- Produce an **executive brief ≤120 words** that is decision-first.

---

## 🧠 Key Concepts
- **DAR** (Decision & Action Register): the single source of truth for what was decided, who owns it, and by when.
- **RACI**: Responsible, Accountable, Consulted, Informed (keep it lightweight, decision-scoped).
- **Evidence-based summarization**: only include claims supported by the notes; mark “Unknown” or “Needs source” otherwise.

---

## 📥 Inputs You Need
- Transcript or raw notes (can be bullets).
- Meeting date/time, attendee list (if available).
- Any pre-reads or Jira/Confluence links referenced.

---

## 📦 Deliverables
- `Day11_meeting_notes.md` — DAR table, unresolved/conflicts list, RACI for top 3 decisions, executive brief.
- `tools/templates/decision_log.md` — a reusable decision-log template (keep in `tools/templates/` for future projects).

---

## ✅ QA Checklist
- [ ] Every **decision** has an **Owner** and **Due** date (or “TBD” with a follow-up task).
- [ ] **Conflicts / unresolved items** are listed explicitly.
- [ ] **Executive brief ≤120 words**, begins with the most important decision/request.
- [ ] No unsupported claims; unknowns labeled as **Unknown**/**Needs source**.

---

## 🧭 Workflow (20–40 min)

1) **Normalize inputs (5 min)**  
   - Remove small talk and duplicates; keep timestamps if present.
   - Tag lines with speaker where possible.

2) **Draft the DAR (10–15 min)**  
   - Identify explicit decisions and implied actions.
   - Assign Owner and Due; if unknown, add a follow-up item.

3) **Extract RACI for Top 3 Decisions (5–10 min)**  
   - Keep to one row per decision; 1 Accountable per decision.

4) **Executive Brief (≤120 words) (5–10 min)**  
   - Decision-first opening → three bullets: impact, risks, next step.
   - Include the date/time of the meeting in the header.

---

## 📑 Templates (Copy/Paste)

### A) DAR (Decision & Action Register)
```md
| Date       | Decision / Action                                     | Owner      | Due        | Rationale / Context            | Dependencies         | Status  |
|------------|--------------------------------------------------------|------------|------------|--------------------------------|----------------------|---------|
| YYYY-MM-DD | Adopt auth library X for SSO                          | Eng Lead   | YYYY-MM-DD | OWASP alignment, vendor support| Vendor contract sign | Open    |
| YYYY-MM-DD | Draft data retention policy (PII ≤ 90d)               | BA Lead    | YYYY-MM-DD | Compliance requirement         | Legal review         | Open    |

