# Day 12 — API Docs + Swagger/Postman with AI

## 🎯 Objectives
- Translate user stories into minimal, valid OpenAPI.
- Provide request/response examples and basic Postman tests.

## 🧠 Key Concepts
- **OpenAPI 3.0** schemas and paths.
- **Error codes** and **rate limits**.
- **Postman tests** for status and schema sanity.

## 🛠 Hands-On
1) Draft endpoints implied by stories (create/list/get-status).  
2) Add examples and standard errors (400/401/429/500).  
3) Provide 2 Postman tests per endpoint.

## 📦 Deliverables
- `Day12_api_docs_ai.md` (notes + snippet).
- `tools/openapi.yaml` (minimal spec, valid).
- `Projects/MiniProject2_ProcessFlow/postman_collection.json` (tests).

## 🧪 QA Checklist
- Spec validates; examples present.
- Postman tests run and pass.

## 📎 Skeleton
```yaml
openapi: 3.0.3
info: { title: "{{PROJECT_NAME}} API", version: "0.1.0" }
paths:
  /orders:
    post:
      summary: Create order
      requestBody:
        required: true
        content:
          application/json:
            schema: { $ref: "#/components/schemas/OrderIn" }
      responses:
        "201": { description: Created, content: { application/json: { schema: { $ref: "#/components/schemas/OrderOut" }}}}
        "400": { description: Bad Request }
components:
  schemas:
    OrderIn: { type: object, required: [customerId, items], properties: { customerId: {type: string}, items: {type: array, items: {type: string}} } }
    OrderOut: { type: object, properties: { id: {type: string}, status: {type: string} } }

