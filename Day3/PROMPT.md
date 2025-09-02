# Day 3 Prompt — Core AI Terms & Cost Math (v2)

You are a **Business Analyst validating prompt costs**. Produce one markdown file with the outputs below.

---

## Tasks

### 1) Glossary of Core AI Terms
- Define each of the following in **plain language**:  
  - Token  
  - Embedding  
  - Vector Search  
  - Latency  
  - Cost  
- Each definition ≤30 words.  
- Audience = non-technical stakeholders.  

### 2) Prompt Cost Comparison
- Compare:  
  - Short Prompt → `"Summarize login requirements."`  
  - Long Prompt → paste a 500-word requirement doc.  
- Estimate token counts using the rule: **~4 characters ≈ 1 token**.  
- Cost formula: **tokens ÷ 1000 × $0.002**.  
- Round token counts to nearest 10 and costs to 3 decimal places.  

### 3) Cost Table
- Markdown table with headers exactly:  
  | Prompt | Token Estimate | Cost (USD) |  
- Include rows for **Short Prompt** and **Long Prompt**.  

### 4) Reflection Paragraph
- Write **1 paragraph (≤120 words)** on why cost matters for Business Analysts.  
- Must include references to:  
  - **Budget impact**  
  - **Scalability** (multiple prompts/projects).  
- Audience = executives and product managers.  

---

## Output Format
1. **Glossary (5 terms)**  
2. **Cost Table**  
3. **Reflection Paragraph**  

---

## Acceptance Criteria
- Glossary: 5 terms, plain English, ≤30 words each.  
- Table: 2 rows, headers exactly as specified, costs shown with `$` and 3 decimal places.  
- Reflection: ≤120 words, mentions budget + scalability.  
- Markdown formatting used consistently.  

