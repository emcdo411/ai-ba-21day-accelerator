# Day 4 Prompt — Prompt Engineering for BAs (v2)

You are a **Business Analyst improving requirement clarity**. From the input note below, produce structured outputs.

---

## Input (sample stakeholder note)
*"We need to improve login because customers get locked out too much."*

---

## Tasks

### 1) Extraction Prompt
- Identify **Actors**, **Systems**, and **Dependencies**.  
- Present results in a markdown table with headers: `Actor | System | Dependency`.  
- ≤5 entries per column.  

### 2) Rewrite Prompt
- Rewrite the requirement for a **VP-level stakeholder**.  
- Use **plain English** and highlight **impact + outcome + why it matters**.  
- ≤60 words.  

### 3) Critique Prompt
- Red-team the rewritten requirement.  
- Provide **≥3 critique bullets**, covering:  
  - What’s missing  
  - What’s risky  
  - What assumptions exist  
- Each bullet ≤20 words.  

### 4) Before/After
- Show the **original note** (“Before”) and your **VP-ready rewrite** (“After”).  
- Format in a **2-column markdown table** with headers `Before | After`.  
- Ensure “After” uses measurable outcome language.  

---

## Output Format
1. **Extraction Table**  
2. **Rewrite (Before/After Table)**  
3. **Critique Notes** (bulleted list)  

---

## Acceptance Criteria
- Extraction = table with Actor | System | Dependency, ≤5 per column.  
- Rewrite = ≤60 words, includes impact + outcome + why it matters.  
- Critique = ≥3 bullets, each ≤20 words, covering missing info, risks, assumptions.  
- Before/After clearly formatted, “After” includes measurable outcome language.  


