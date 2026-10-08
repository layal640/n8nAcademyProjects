# n8n Academy Course Workflows

# Table of Contents
Workflows Overview

Project Structure

Tech Stack

# Workflows Overview
# 1. Section 1 - AI & Advanced Workflows (n8n103)
Feedback Agent: Implements an AI LangChain conversational agent utilizing Groq language models, window memory, and custom HTTP request tools to handle customer support inquiries regarding orders, products, and accounts.

Feedback Pipeline: Processes customer feedback by classifying sentiment, topics, urgency, and key issues using LLM chains and structured output parsers, then generates context-aware automated replies.

# 2. Section 2 - Core Operations & Data Pipelines (n8n101 & n8n102)
Sales Data Pipeline (n8n101): Fetches raw sales order data via authenticated HTTP requests, splits items, calculates order totals, filters delivered statuses, summarizes regional metrics, converts reports into files, and submits validation payloads.

Order Webhook Processor (n8n102): Listens for incoming HTTP POST webhook requests for new orders, validates mandatory payload fields, and stores valid orders into n8n data tables while returning appropriate response codes.

# 3. Section 3 - Error Handling & Debugging Practice (n8n103)
Error Handler (Error Workflow): Global error handling workflow triggered automatically upon failures, capturing workflow metadata, execution URLs, error messages, and failed node details to report incidents via API requests.

Debugging Practice & Failure Test: Demonstrates robust retry configurations, HTTP error management, fallback assignment patterns for data merging, and webhook failure test endpoints.

Tech Stack
Platform: n8n

Core Nodes: Webhook, HTTP Request, Data Table, If, Set, Summarize, Convert to File, Error Trigger, Merge, Limit

AI & LangChain Nodes: Advanced AI Agent, LLM Chain, Groq Chat Model, Structured Output Parser, HTTP Request Tool, Window Buffer Memory
