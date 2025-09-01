# Day 12 Prompt — OpenAPI + Postman

You are an API tech writer. From stories/AC I provide:

1) **OpenAPI (YAML)**
   - Endpoints: create/list/get-status for a simple resource.
   - Include request/response examples, auth header, errors 400/401/429/500.
   - Filename: `tools/openapi.yaml`

2) **Postman Collection (JSON)**
   - Requests for each endpoint with 2 tests each (status, basic schema check).
   - Filename: `Projects/MiniProject2_ProcessFlow/postman_collection.json`

3) **Notes (Markdown)**
   - Brief mapping from stories → endpoints + any assumptions.
   - Filename: `Day12_api_docs_ai.md`

### Output Format
- One ```yaml``` block named `tools/openapi.yaml`
- One ```json``` block named `Projects/MiniProject2_ProcessFlow/postman_collection.json`
- One ```markdown``` block named `Day12_api_docs_ai.md`

### Acceptance
- OpenAPI parses; Postman imports; tests pass on mock data.

