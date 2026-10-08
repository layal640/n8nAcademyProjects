# Debugging a Broken n8n Workflow

A data enrichment workflow (orders + customers) that I imported broken and fixed.

Built during the n8n Foundations Program (N8N103).

## Flow
```
Manual Trigger → GetOrders → GetCustomers → Merge Orders + Customers → SendToOrdersQueue
```

## Issues found and fixed
| Node | Problem | Fix |
|---|---|---|
| GetOrders | Missing Header Auth credential and assessment header | Added credential and `X-Assessment-ID` |
| MergeOrdersCustomers | Match field was `customerId` | Changed to `customer_id` |
| SendToOrdersQueue | Expression referenced a deleted node and returned `undefined` | Used `{{ $input.all().map(i => i.json) }}` to send all merged items as an array |

## Debugging approach
- Run nodes one by one with **Test Step**
- Read the full error message
- Compare field names in expressions with the **Input** panel
- Check that merged output actually contains the joined fields

## Tech
n8n Cloud, HTTP Request, Merge node
