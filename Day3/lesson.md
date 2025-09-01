# Day 3 — Core Terms That Actually Matter

## 🎯 Objectives
- Get comfortable with the “math layer” of AI without being a data scientist.
- Learn how cost, tokens, and embeddings matter for BA workflows.

## 📘 Key Concepts
- **Token**: A chunk of text (≈4 chars in English).
- **Embedding**: Vector math representation of text.
- **Vector Search**: Find “semantic nearest neighbor” instead of exact match.
- **Latency/Cost**: Tokens in/out = time and dollars.

## 🛠 Hands-On
1. Take two prompts:  
   - Short: “Summarize password reset.”  
   - Long: Paste a 500-word requirement.  
2. Use a token estimator to count cost (mock: $0.002/1K tokens).
3. Calculate: tokens × rate.

## 📦 Deliverable
- `Day03_core_terms.md` with:
  - Table of key terms.
  - Cost comparison math.

## ✅ QA Check
Estimate a prompt cost within ±20%.

---

