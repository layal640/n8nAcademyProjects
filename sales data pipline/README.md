# n8nSalesDataPipline
Sales Data Pipeline built with n8n (N8N101 Academy) to automate fetching sales data, filtering delivered orders, aggregating regional stats, and generating CSV reports using branching logic and header auth.

# What it does:
 Secure Data Fetching: Retrieves sales data using HTTP Header Authentication (`X-Assessment-ID`).
 Smart Filtering & Branching: Separates delivered orders from pending/cancelled ones using `IF` logic.
 Data Aggregation: Calculates regional totals, counts, and averages.
 Report Generation: Converts processed JSON data into a CSV file and posts it to the destination API.

# Skills Learned:
Header Auth | Workflow Branching | Data Transformation | Expressions | Aggregation | Binary File Generation
