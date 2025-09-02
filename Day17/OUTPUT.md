# ✅ Day 17 — Policy, DPIA-lite, Evals & Red-Team (Sample Output for Students)

> This file shows you exactly what your three deliverables will look like when you “run” the Day 17 Prompt.  
> - No broken links, no images.  
> - Everything is in plain markdown.  
> - Placeholders are used where an organization would normally add details (like names, teams, or emails).  
> - This is not meant to be a finished policy for a real company, but a **template you can adapt**.

---

## 1. File: `tools/templates/ai_policy.md`

This file is about **one page** (≤500 words). It reads like a template your organization could copy and fill in.  

**What you should expect to see:**

- Clear headings: Purpose, Data Handling, Model Use, Approvals, Logging, Incident Response, Contact.  
- Placeholders like `{{OrgName}}` or `{{TeamAlias}}` instead of real company details.  
- Simple sentences, easy to understand, no jargon.  
- Example of PII rules: *“Redact emails and phone numbers before storing logs.”*  
- Example of incident response: *“Escalate within 2 hours to {{TeamAlias}} if high-severity issue found.”*

---

## 2. File: `tools/templates/dpia_lite.md`

This file is a **DPIA-lite (Data Protection Impact Assessment)** — basically a structured risk review.  

**What you should expect to see:**

- Headings like Context, Data Categories, Risks, Residual Risk, Owners, Review Cadence.  
- A markdown **table of risks with 8 rows or more**, covering bias, privacy, misuse, security, compliance, and operational issues.  
- Table columns like: Risk ID, Description, Severity (High/Med/Low), Likelihood (High/Med/Low), Mitigation, Residual Risk, Owner, Review Cadence.  
- An example row:  
  | R1 | Model may generate biased outputs | High | Medium | Bias testing | Medium | {{TeamAlias}} | Quarterly |  
- A short summary of residual risks written in 2–3 plain sentences.  

---

## 3. File: `Day17_responsible_ai.md`

This file pulls pieces together into one summary document.  

**What you should expect to see:**

### Part A: Policy (Summary)
- A **bullet list (5 points)** copied from the main policy.  
- Example: *“All deployments must be approved by {{TeamAlias}}.”*

### Part B: DPIA-lite (Summary Table)
- A **short table** with a few key risks condensed.  
- Columns: Risk ID, Category, Severity, Residual, Owner.  

### Part C: Eval Harness (10 Scenarios)
- A **table with 10 rows**.  
- Columns: ID, Scenario, Expected, Observed, Outcome (Pass/Fail/Partial), Notes.  
- Categories covered: 3 fairness, 3 robustness, 2 safety, 2 utility.  
- Example row:  
  | E1 | Resume screening with diverse names | Output should be unbiased | Observed bias low | Pass | Needs recheck next cycle |

### Part D: Red-Team Log (8 Attacks)
- A **table with 8 rows**, each row describing a red-team attack attempt.  
- Columns: Attack ID, Vector, Category, Outcome, Mitigation.  
- Each category (Prompt Injection, PII Exfiltration, Jailbreak, Bias Exploit, Toxic Output, Model Theft, Data Poisoning, Other) must appear at least once.  
- Example row:  
  | RT1 | Tried to bypass guardrails by rephrasing harmful query | Prompt Injection | Blocked | Add stronger input filters |

---

## ✅ Submission Checklist

When you run the Day 17 Prompt, your outputs should include:

- [x] `tools/templates/ai_policy.md` — short template policy (≤500 words).  
- [x] `tools/templates/dpia_lite.md` — table with ≥8 risks, clear cadence and owners.  
- [x] `Day17_responsible_ai.md` — summary doc with 4 parts (policy bullets, DPIA table, eval harness, red-team log).  
- [x] All tables in **markdown pipe format** (`|`) so they display cleanly.  
- [x] Placeholders (`{{OrgName}}`, `{{TeamAlias}}`) instead of real details.  
- [x] No external links, no images that could break.  

---

👉 **In simple terms:**  
You’ll end up with **one short policy**, **one risk template**, and **one summary doc with tables**. The goal is to practice thinking about risks, testing, and red-teaming in a structured way — not to create a real corporate policy.
