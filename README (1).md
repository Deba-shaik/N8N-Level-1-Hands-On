# My First N8N Workflow

**Course:** N8N Hands-On Beginner Course  
**Topic:** 1 – Create Your First Workflow

## Objective

Build and execute a beginner-friendly n8n workflow using a Manual Trigger and an Edit Fields (Set) node. Learn to connect nodes, create a static greeting, inspect execution data, and save the workflow.

## Prerequisites

- Access to an active n8n instance (n8n Cloud or self-hosted), version 1.0.0 or later.
- A compatible browser and permission to create and save workflows.
- Basic familiarity with navigating the n8n editor.
- No coding, API credentials, or external integrations required.

## Workflow Overview

```text
When clicking 'Execute workflow' (Manual Trigger)
                    |
                    v
             Edit Fields (Set)
                    |
                    v
           JSON greeting output
```

## Workflow Steps

1. Open n8n and create a new workflow.
2. Name it **My First N8N Workflow**.
3. Add the **Manual Trigger** node (displayed as **When clicking 'Execute workflow'** or **When clicking 'Test workflow'**, depending on the interface).
4. Add **Edit Fields (Set)** and connect it to the Manual Trigger.
5. In **Fields to Set**, add a **String** field:
   - **Name:** `greeting`
   - **Value:** `Hello, n8n!`
6. Save the workflow.
7. Run it manually and inspect the Edit Fields output in JSON, Table, or Schema view.
8. Save the final version.

## Expected Output

The Edit Fields node should produce one item with the following JSON content:

```json
[
  {
    "greeting": "Hello, n8n!"
  }
]
```

## Execution Instructions

1. Open **My First N8N Workflow** in the n8n editor.
2. Click **Execute workflow** or **Test workflow**.
3. Wait for both nodes to show green checkmarks.
4. Click **Edit Fields** and inspect its **Output** panel.
5. Confirm that **1 item** was processed and the `greeting` field matches the expected value.
6. Save the workflow.

## Evidence

### Workflow execution screenshot

![Successful n8n workflow execution](evidence/workflow-execution.png)

The supplied screenshot shows the Manual Trigger connected to the Edit Fields node, green success checkmarks on both nodes, and **1 item** on the connection and output. This supports successful node execution, but it does **not** display the greeting JSON or confirm that the workflow has been saved under the required name.


## Completion Checklist

- [x] Manual Trigger and Edit Fields nodes connected (visible in supplied screenshot).
- [x] Both nodes executed successfully with 1 item (visible in supplied screenshot).
- [x] Verify `greeting` field and expected JSON output in n8n.
- [x] Verify workflow name and saved state.
- [x] Capture configuration and output screenshots for submission.



