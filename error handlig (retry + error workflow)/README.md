# Resilient Workflows: Retry and Error Handling (n8n)

Three n8n workflows showing how to handle failures: retrying a flaky API and capturing unrecoverable errors with an Error Workflow.

Built during the n8n Foundations Program (N8N103).

## Workflows
| File | Purpose |
|---|---|
| `debugging-practice.json` | Calls a flaky API (~30% failure) with **Retry On Fail** (5 tries, 1000ms), sends the result, then triggers the failure test |
| `failure-test.json` | Webhook workflow that calls a guaranteed-failure endpoint to simulate a production error |
| `error-handler.json` | **Error Trigger** workflow that reports the workflow name, ID, failed node, error message, and execution URL |

## Flow
```
Debugging Practice → (calls) Failure Test → fails → Error Handler reports the error
```

## Key concepts
- Retry On Fail for transient errors
- Error Workflows only run on **production** executions, not manual tests
- Error workflow must be **published** and linked in the failing workflow's settings
- Retry for temporary failures, error workflows for failures retrying can't fix

## Setup
1. Import the three files
2. Create a Header Auth credential and replace `YOUR_ASSESSMENT_ID`
3. Publish `error-handler.json` and `failure-test.json`
4. In Failure Test: **Settings → Error Workflow** → select Error Handler
5. In Debugging Practice, set `TriggerFailureTest` to your own n8n domain URL
6. Execute Debugging Practice, then check the Error Handler's **Executions** tab
