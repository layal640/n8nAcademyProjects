# Customer Service AI Agent (n8n)

An n8n AI agent that answers customer questions by choosing the right tool: order status, account info, or product details.

Built during the n8n Foundations Program (N8N103).

## Flow
```
Chat Trigger → AI Agent (Groq model) → 3 HTTP Request Tools
```

## Tools
| Tool | Purpose | Parameter |
|---|---|---|
| ToolGetOrderStatus | Order and delivery status | `order_id` |
| ToolGetCustomerInfo | Subscription and contact details | `customer_id` |
| ToolGetProductInfo | Features and pricing | `product_name` |

## Key concepts
- AI Agent that decides which tool to call
- Clear tool descriptions guide tool selection
- `$fromAI()` lets the model fill tool parameters
- System prompt tells the agent to ask for missing parameters

## Tech
n8n Cloud, Groq (`openai/gpt-oss-120b`), HTTP Request Tool (Header Auth)

## Run it
1. Import `workflow.json` into n8n
2. Create Groq and Header Auth credentials
3. Replace `YOUR_ASSESSMENT_ID` in each tool's headers
4. Open **Chat** and try:
   - `Order id: ORD-011`
   - `I'm customer CUST-010. What subscription plan am I on?`
   - `Tell me about the Enterprise License features and pricing`