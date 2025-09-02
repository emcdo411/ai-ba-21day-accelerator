# Day 16 Prompt — Automation Recipes (Advanced, v2)

You are an **Automation Architect**. Produce **one markdown file** with exact structure and guardrails below.

---

## File: `Day16_agentic_workflows.md`

Include **three sections**:

---

### 1) Flow Specs (A, B, C)

For each flow provide:

- **Purpose** — concise description  
- **Inputs** — sample payload with `placeholder` values  
- **Transformations** — at least one **concrete LLM prompt** used to enrich/transform data  
- **Outputs** — target system, expected format  

**Reliability & Control**
- **Auth method** — OAuth2 or Token (must specify)  
- **Idempotency Key Rule** — format `flow:{A|B|C}:{sourceId}:{yyyy-mm-dd}`; dedupe window=24h; store in KV/Redis  
- **Retry Policy** — exponential backoff with jitter: 1m → 4m → 15m  
- **On-fail Route** — DLQ (Dead Letter Queue) + PagerDuty alert  

**Messaging**
- **Success Template** — short, specific success message  
- **Fail Template** — error + escalation hint  

**Security**
- **PII Redaction Rule** — redact `email`, `phone`, `ssn` with `***` before logging  
- **Secrets Handling** — use managed vault (no secrets in logs/code)  
- **Logging Do** — log status, latency, retries, flow ID  
- **Logging Don’t** — log PII, secrets, full payloads  

**Observability**
- **Metrics** — latency (p95), success rate, retry count, DLQ size  
- **Alert Thresholds** — success <95%, DLQ >10 msgs, latency >3s  
- **Runbook Notes** — how to reprocess DLQ, how to silence/resume pager  

---

### 2) Diagrams

- **One Mermaid diagram per flow** (must be copy-pasteable)  
- Label auth, idempotency, retries, DLQ, and output node  
- Include **notes on limits/rate limits**:  
  - Numeric values: e.g., “100 req/min per user, bursts of 20 allowed”  
  - Back-pressure handling: queue + exponential retry  

---

### 3) Implementation Steps

- Provide recipe in **Zapier**, **Make**, or **Power Automate** (pick one per flow)  
- Numbered setup steps with specific modules/actions  
- Explicit sandbox/test instruction with table-driven test cases  
- Show **sample payload** and expected transformed output  
- Export guidance:  
  - Screenshot flows and save to `assets/flow_daily_digest.png`  
  - Show path as inline code: `assets/flow_daily_digest.png` (not a clickable image link)

---

## Acceptance

- Each flow has: idempotency rule, retries, DLQ, and pager.  
- At least one concrete LLM prompt per flow.  
- Diagrams are copy-pasteable Mermaid blocks.  
- Numeric rate limits + concurrency strategies specified.  
- Security + PII redaction + vault use clearly described.  
- Observability (metrics + thresholds) documented.  
- Runbook + test instructions included.  
- Asset path shown as inline code `assets/...`, never as a link.  
