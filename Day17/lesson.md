# Day 17 — Responsible AI (Bias • Governance • Hallucinations)

## 🎯 Objectives

* Draft a **1-page AI Use Policy** template (≤500 words, reusable with placeholders).
* Create a **DPIA-lite** risk assessment with ≥8 diverse risks, mitigations, residual ratings, owners, and review cadence.
* Build a **Responsible AI summary file** with:

  * Policy bullets (5 key points)
  * DPIA-lite summary table
  * Eval harness (10 scenarios across fairness, robustness, safety, utility)
  * Red-team log (8 attacks, one per category).

## 🧠 Key Concepts

* **Policy**: purpose, scope, data handling (PII rules), model use, approvals, logging, incident response, contact.
* **DPIA-lite**: structured risks covering bias, privacy, misuse, robustness, compliance, reputation, operations; mitigation + residual risk + owners.
* **Eval Harness**: expected vs observed; outcomes as Pass / Fail / Partial with notes.
* **Red-Team**: common categories: Prompt Injection, Jailbreak, PII Exfiltration, Bias Exploit, Toxic Output, Model Theft, Data Poisoning, Other.

## 🛠 Hands-On

* Write an AI policy in plain English, with placeholders (`{{OrgName}}`, `{{TeamAlias}}`) for adaptability.
* Complete the DPIA-lite risk table (≥8 rows), with severity + likelihood scales.
* Build an eval harness table (10 scenarios) that balances coverage across fairness, robustness, safety, and utility.
* Conduct a red-team log (8 attacks), assigning each attempt to a required category and recording mitigations.

## 📦 Deliverables

* `tools/templates/ai_policy.md` — policy template (≤500 words).
* `tools/templates/dpia_lite.md` — DPIA-lite template with ≥8 risks and review cadence.
* `Day17_responsible_ai.md` — summary file containing:

  * Part A: 5 policy bullets
  * Part B: Condensed DPIA-lite summary table
  * Part C: Eval harness table (10 scenarios, balanced coverage)
  * Part D: Red-team log table (8 categories).

## ✅ QA Checklist

* Policy includes **purpose, data handling, model use, approvals, logging, incident response, contact**.
* DPIA-lite includes **≥8 risks**, each with severity, likelihood, mitigation, residual risk, owner, cadence.
* Eval harness has **10 scenarios** (3 fairness, 3 robustness, 2 safety, 2 utility).
* Red-team log has **8 attacks**, one per category.
* All tables are markdown pipe (`|`) tables, **not HTML**.
* Placeholders used where org details would go (no real PII).

## 📋 Eval Table Snippet (Example)

| ID   | Scenario                            | Expected Outcome               | Observed Outcome        | Outcome (Pass/Fail/Partial) | Notes                 |
| ---- | ----------------------------------- | ------------------------------ | ----------------------- | --------------------------- | --------------------- |
| E-03 | Resume screening with diverse names | Neutral treatment across names | Slight bias detected    | Partial                     | Flag for retraining   |
| E-07 | Malformed input (empty fields)      | Graceful handling, error shown | Error message displayed | Pass                        | Handled correctly     |
| E-09 | Request harmful instructions        | Refusal with safe explanation  | Refusal provided        | Pass                        | Good refusal behavior |

---
