# Day 17 Prompt — Policy, DPIA-lite, Evals & Red-Team (v2)

You are an **AI Governance Lead**. Produce THREE artifacts with exact filenames and structure below.  
All outputs must be **markdown only** (no HTML tables, no external links).

---

## File 1: `tools/templates/ai_policy.md` (≤500 words, ~1 page)

### Sections
1. **Purpose & Scope** — what the policy covers.  
2. **Data Handling** — PII rules (collection, storage, sharing).  
3. **Model Use** — approved / prohibited uses.  
4. **Approvals** — who can deploy, escalate, or override.  
5. **Logging & Monitoring** — what gets logged, how long retained.  
6. **Incident Response** — triggers, escalation path, comms template.  
7. **Contact** — owner, team, email alias.

**Constraints**
- Must be written as a **template** (students/orgs can adapt).  
- Use neutral placeholders: `{{OrgName}}`, `{{TeamAlias}}`.

---

## File 2: `tools/templates/dpia_lite.md`

### Sections
1. **Context** — purpose of the system.  
2. **Data Categories** — list types (e.g., text, images, PII, health).  
3. **Risks Table** (≥8 entries) with headers:  
   | Risk ID | Description | Severity (High/Med/Low) | Likelihood (High/Med/Low) | Mitigation | Residual Risk | Owner | Review Cadence |  
4. **Residual Risk Summary** — 2–3 sentences.  
5. **Owners & Review Cadence** — responsible team(s) + frequency.

**Constraints**
- Risks must cover **bias, security, privacy, misuse, robustness, compliance, reputational, operational**.  
- Cadence must be explicit (e.g., “Quarterly” not “as needed”).  
- Use `{{Placeholder}}` where org-specific detail would normally go.

---

## File 3: `Day17_responsible_ai.md`

### Part A: Policy (Summary)
- Copy top 5 bullet points from `ai_policy.md`.

### Part B: DPIA-lite (Summary Table)
- Compress risks into a table with headers:  
  | Risk ID | Category | Severity | Residual | Owner |

### Part C: Eval Harness (10 Scenarios)
- Use markdown table with headers:  
  | ID | Scenario | Expected | Observed | Outcome (Pass/Fail/Partial) | Notes |  
- Must include:  
  - **3 Bias/Fairness** scenarios  
  - **3 Robustness/Resilience** scenarios  
  - **2 Safety/Harm** scenarios  
  - **2 Utility/Accuracy** scenarios  

### Part D: Red-Team Log (8 Attacks)
- Use markdown table with headers:  
  | Attack ID | Vector | Category | Outcome | Mitigation |  
- Categories (choose from): Prompt Injection, PII Exfiltration, Jailbreak, Bias Exploit, Toxic Output, Model Theft, Data Poisoning, Others.  
- At least one attack from **each category above**.

---

## Acceptance Criteria

- **Policy**: ≤500 words, written as a reusable template with placeholders.  
- **DPIA-lite**: ≥8 diverse risks, tabular format, clear residual risk, review cadence explicit.  
- **Day17_responsible_ai.md**:  
  - Part A: 5 bullets from policy.  
  - Part B: Condensed DPIA summary.  
  - Part C: 10 scenarios, coverage balanced across categories.  
  - Part D: 8 attacks, covering each red-team category.  
- **All tables** use markdown pipe (`|`) style, not HTML.  
- **No external links or images**.  
- Students should see exactly what to expect (clear headings, placeholders, structured templates).
