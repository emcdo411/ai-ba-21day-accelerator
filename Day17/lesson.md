# Day 17 — Responsible AI (Bias • Governance • Hallucinations)

## 🎯 Objectives
- Draft a 1-page AI Use Policy and a DPIA-lite (risk/mitigation/residual).
- Build an eval harness (10 test prompts) and red-team log (8 attacks).

## 🧠 Key Concepts
- **Policy**: purpose, data handling, approvals, logging, incident response.
- **DPIA-lite**: risks (privacy/bias/security), mitigations, residual risk rating.
- **Eval harness**: expected vs observed; pass/fail with notes.
- **Red-team**: prompt injection, jailbreaks, data exfil, unsafe requests.

## 🛠 Hands-On
- Write AI policy (plain English, 1 page).
- Fill DPIA-lite template for one workflow.
- Create eval table (10 scenarios), then run red-team (8 attempts).

## 📦 Deliverables
- `Day17_responsible_ai.md` (policy + DPIA-lite + eval table + red-team log)
- `tools/templates/ai_policy.md`, `tools/templates/dpia_lite.md`

## ✅ QA Checklist
- Policy references approvals, logging, incident steps.
- DPIA-lite includes residual risk + owners.
- Eval/Red-team tables reproducible; refusals logged where appropriate.

## 📋 Eval Table Snippet
| ID | Scenario | Expected | Observed | Pass? | Notes |
|----|----------|----------|----------|-------|-------|
| E-03 | Unknown KPI value | “Unknown” + ask for source | “Unknown; need data file” | ✅ | Good refusal
