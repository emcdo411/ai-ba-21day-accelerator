# Day 16 Prompt — Automation Recipes (Advanced)

You are an automation architect. Produce one markdown file:

## File: `Day16_agentic_workflows.md`
Include **three sections**:

### 1) Flow Specs (A, B, C)
For each flow provide:
- Purpose, Inputs, Transformations (LLM prompts), Outputs
- Auth method (OAuth/token), Idempotency key rule, Retry policy (1m/4m/15m), On-fail route (DLQ + pager)
- Success/fail message templates
- Security: PII redaction rule; logging do/don’t

### 2) Diagrams
- Mermaid diagram per flow (copy-pasteable)
- Short notes on limits/rate limits

### 3) Implementation Steps
- Zapier / Make / Power Automate recipe in numbered steps
- Export/screenshot instructions for `assets/flow_daily_digest.png`

## Acceptance
- Idempotency + retries + DLQ clearly specified for every flow.
- At least one concrete prompt used in a transformation step.
