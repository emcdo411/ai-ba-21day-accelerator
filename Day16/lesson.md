# Day 16 — Agentic AI & Workflow Automation (Zapier / Make / Power Automate)

## 🎯 Objectives
- Design 2–3 hands-free workflows (summarize, file, notify) with safe failure.
- Implement guardrails: idempotency, retries, dead-letter alerts, PII redaction.

## 🧠 Key Concepts
- **Idempotency**: hash payload (e.g., title+timestamp) to prevent duplicates.
- **Retries**: exponential backoff (e.g., 1m/4m/15m); circuit break after 3x.
- **DLQ**: send failed payloads to a queue + page on threshold.

## 🛠 Hands-On
- Flow A: **Meeting → Summary → Jira** (append/create ticket; link to Confluence).
- Flow B: **Daily digest** (Slack/Teams → Top 10 decisions → email + page).
- Flow C: **Backlog hygiene** (stale >7d → ping owner; 48h no response → escalate).

## 📦 Deliverables
- `Day16_agentic_workflows.md` (flow specs, Mermaid diagrams, config notes)
- `assets/flow_daily_digest.png`
- Error policy snippet (idempotency keys, 3x retry, DLQ)

## ✅ QA Checklist
- Each flow lists **inputs, transforms, outputs, auth, retries, alerts**.
- PII redacted before LLM calls; logs avoid secrets.
- Mermaid renders; screenshot/export instructions included.

## 🧭 Sample Mermaid
```mermaid
flowchart LR
  M[Transcript] --> C[Summarize LLM]
  C --> J[Jira API: create/append]
  J --> N[Notify Channel]
  J -->|fail| DLQ[Dead-letter + Pager]
