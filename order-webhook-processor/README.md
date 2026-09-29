n8n Order Webhook Processor

Webhook-driven order processing workflow built with n8n.

Flow:
Webhook (Header Auth) → Validate required fields → Execute sub-workflow → Respond

Features:
- Header Auth on the webhook
- Validation of order_id, customer_id, total (400 on missing fields)
- Order storage in an n8n Data Table
- Duplicate check via a reusable sub-workflow

Import:
In n8n: Workflows → Import from File → select the JSON file, then re-link your own credentials.