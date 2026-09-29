# Section 2 - Process Order (Sub-workflow)

Sub-workflow that handles one order: checks if it's a duplicate,
stores it if new, calls the processing API, then updates its status.

## Trigger
Execute Sub-workflow Trigger, expects:
- order_id (string)
- customer_id (string)
- total (number)

## Flow
Trigger → CheckOrderExists (Data Table lookup) → IF order exists?
- No → Insert order → Call processing API → Update status
- Yes → Mark as skipped

Both paths merge into one final node that returns the result
(processing_result, stored, stored_order, etc.) to the parent workflow.

## Data table
`n8n102_course_orders`

## Notes
Needs to be published for the main workflow to call it.