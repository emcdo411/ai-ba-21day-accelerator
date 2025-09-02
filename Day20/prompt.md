# Day 20 Prompt — Impact Story Builder (v2)

You are a **Career Editor**. Produce three files with the exact names and structures below.  
All outputs must be written in **plain markdown**.

---

## File 1: `Day20_resume_linkedin.md`

### Section A: Guidance Summary
- ≤150 words.  
- Provide coaching on how to phrase impact (verb + metric + outcome).  
- Use simple, motivational tone.

### Section B: Resume Bullets
- 5 bullets **per role** (if multiple roles, group under headings).  
- Format: **Action verb + metric (%/$/time) + outcome (impact/benefit)**.  
- Each ≤22 words.  
- At least 1 bullet per role must include cost or time savings.  
- Example: *Reduced onboarding time by 30% by automating training modules, saving $50K annually.*

### Section C: LinkedIn Headline Options
- Provide 5 options.  
- Each ≤12 words.  
- Each must combine: **credibility (title/cert), outcome (metric/impact), niche (industry/domain).**  
- Example: *Data Analyst | 10+ Years | Healthcare Cost Savings & Predictive Models*

### Section D: LinkedIn About
- Exactly 3 paragraphs (≤120 words each).  
- **Paragraph 1**: Who you help + credibility.  
- **Paragraph 2**: Proof via one **concrete measurable case study**.  
- **Paragraph 3**: What you’re building now + invitation to connect.  
- Example case line: *“Improved claim processing accuracy by 25%, reducing customer disputes by 40%.”*

### Section E: Featured Links
- 3–5 items.  
- Each entry: **Title** — one-sentence blurb with a clear outcome.  
- Example: *GitHub Portfolio — Built AI-powered dashboard saving 15 hours/month in reporting.*

---

## File 2: `resume.md`
- Contains only the bullet lists from Section B.  
- Must match Section B **exactly** (no drift).  
- Formatted for direct copy-paste into a resume builder.  

---

## File 3: `linkedin_about.md`
- Contains only the final 3-paragraph LinkedIn About (from Section D).  
- Must match Section D **exactly** (no drift).  

---

## Acceptance Criteria
- **Resume bullets**: quantified, ≤22 words, consistent format (verb + metric + outcome).  
- **Headlines**: 5 distinct, ≤12 words, mixing credibility + outcome + niche.  
- **LinkedIn About**: 3 paragraphs, each ≤120 words, includes one measurable case study.  
- **Featured links**: 3–5, formatted with title + one-sentence outcome blurb.  
- **Consistency**: Bullets and About reused correctly across files (`resume.md`, `linkedin_about.md`).  
- **Placeholders**: Use `{{Role}}`, `{{Metric}}`, `{{Outcome}}` where data is not provided.  
