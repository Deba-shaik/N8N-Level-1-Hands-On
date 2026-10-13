# Topic 7 – Schedule Trigger Workflow

**Course:** N8N Hands-On Beginner Course  
**Workflow:** Topic 7 Schedule Trigger

## Objective
Configure an n8n Schedule Trigger with a daily rule and a weekday cron rule, connect it to an Edit Fields node, and record a dynamic execution timestamp.

## Prerequisites
- Complete Topics 1–6 and have access to an n8n editor with permission to edit workflows.
- Understand basic date/time values and cron scheduling.

## Workflow Overview
`Schedule Trigger → Log Execution (Edit Fields)`

## Workflow Steps
1. Create and save a workflow named **Topic 7 Schedule Trigger**.
2. Add a **Schedule Trigger** node.
3. Configure the first schedule to run **daily at 09:00 AM** (every 1 day).
4. Add a second rule with the weekday cron expression `30 8 * * 1-5`, meaning 08:30 AM Monday through Friday. The five fields are minute, hour, day of month, month, and day of week.
5. Connect an **Edit Fields (Set)** node named **Log Execution**.
6. Create a String field named `executionTime` using the expression `{{ $now.toFormat('yyyy-MM-dd HH:mm:ss') }}`.
7. Execute the workflow manually, inspect the timestamp in the node output, and save the workflow.
8. Publish/activate the workflow when automatic scheduled execution is required. Confirm the workflow timezone before activation.

## Execution Instructions
1. Open the saved workflow in n8n.
2. Click **Execute workflow** to perform a manual test.
3. Confirm both nodes show green checkmarks and that one item reaches **Log Execution**.
4. Open **Log Execution** and inspect its Output panel to confirm the timestamp is generated dynamically.
5. Save the changes. Scheduled runs require the workflow to be active/published.

## Evidence
- **Screenshot 1 – Workflow Canvas:** Schedule Trigger connected to Log Execution; both nodes show green success checkmarks and one item.
- **Screenshot 2 – Timestamp Logging:** Log Execution uses the dynamic `$now.toFormat(...)` expression and shows an executionTime value in the output.

**Evidence scope:** The screenshots demonstrate a successful manual run and timestamp mapping. They do not independently establish that both schedule rules are configured or that the workflow is activated for unattended runs.
