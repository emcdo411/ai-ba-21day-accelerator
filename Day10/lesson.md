File: output.md

# ✅ Day 10 — Process Mapping (Sample Output for Students)

> This shows what your `Day10_ai_process_maps.md` file should look like.  
> - Two Mermaid diagrams (current + target) with explanations.  
> - Bottlenecks and improvements annotated using Mermaid comments (`%%`).  
> - Export guidance at the end with repo-relative paths.  
> - Node counts follow the rules: Current (6–12), Target (≤8).  

---

## Current State Explanation
This current state shows how customers place orders, which flow through Ops and Finance.  
The diagram highlights **handoff bottlenecks** where delays or errors occur.  

```mermaid
flowchart LR
  %% Bottleneck 1: Payment verification is manual, slows process
  %% Bottleneck 2: Ops approval adds 2-day delay
  %% Bottleneck 3: Finance reconciliation often mismatched data

  Cust:Start["Cust: Place Order"] --> Ops:Check["Ops: Verify Order"]
  Ops:Check --> Fin:PayAuth["Fin: Payment Auth"]
  Fin:PayAuth -->|OK| Ops:Approve["Ops: Manager Approve"]
  Ops:Approve --> Ops:Fulfill["Ops: Fulfill Order"]
  Ops:Fulfill --> Fin:Invoice["Fin: Generate Invoice"]
  Fin:Invoice --> Cust:Confirm["Cust: Receive Confirmation"]

Target State Explanation

This target state reduces handoffs and simplifies the process.
Improvements include automated payment checks and removing manager approval.

flowchart LR
  %% Improvement 1: Automated payment authorization replaces manual step
  %% Improvement 2: Removed Ops manager approval, reducing delays

  Cust:Start["Cust: Place Order"] --> Fin:PayAuth["Fin: Auto-Payment Auth"]
  Fin:PayAuth --> Ops:Fulfill["Ops: Fulfill Order"]
  Ops:Fulfill --> Fin:Invoice["Fin: Auto-Invoice"]
  Fin:Invoice --> Cust:Confirm["Cust: Receive Confirmation"]

Export Guidance

Verify diagrams render in GitHub preview.

Recreate diagrams in Lucid or Visio (use swimlanes if available).

Export each diagram as PNG.

Save to:

Projects/MiniProject2_ProcessFlow/process_current.png

Projects/MiniProject2_ProcessFlow/process_target.png

Confirm files display locally before submission.
