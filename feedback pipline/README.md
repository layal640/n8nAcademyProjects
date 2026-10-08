# AI-Powered Customer Feedback Pipeline (n8n)

An n8n workflow that fetches customer feedback, classifies it with an LLM into structured JSON, and generates a tailored reply.

Built during the n8n Foundations Program (N8N103).

## Flow
```
Manual Trigger → Get Feedback → Classify (LLM + Structured Output Parser) → Set Result → Generate Reply (LLM) → Send Result
```

## Key concepts
- Structured Output Parser for reliable JSON (`sentiment`, `topic`, `urgency`, `key_issue`)
- Mixed models: `openai/gpt-oss-20b` for classification, `openai/gpt-oss-120b` for replies
- Retry On Fail (3 tries) for resilient AI nodes

## Tech
n8n Cloud, Groq, HTTP Request (Header Auth)

## Run it
1. Import `workflow.json` into n8n
2. Create Groq and Header Auth credentials
3. Replace `YOUR_ASSESSMENT_ID` in the HTTP nodes
4. Execute workflow

> Endpoints belong to the n8n Academy training environment.