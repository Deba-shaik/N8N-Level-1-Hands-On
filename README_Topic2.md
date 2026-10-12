# Topic 2 - Understanding Workflow Execution & Debugging Basics

**Course:** N8N Hands-On Beginner Course  
**Workflow:** Topic 2 Debugging Workflow

## Objective
Understand how data moves between n8n nodes, identify and investigate a deliberately failed HTTP Request, test a corrected node, and review execution history.

## Prerequisites
- Complete Topic 1: Create Your First Workflow.
- Access an active n8n editor with permission to edit workflows.
- Access to the Executions section and saved execution history.
- Network access to test HTTP requests.

## Workflow Overview
`Manual Trigger -> Edit Fields (Set) -> HTTP Request (GET)`

## Workflow Steps
1. Duplicate **My First N8N Workflow** and name the copy **Topic 2 Debugging Workflow**.
2. Keep the Manual Trigger and Edit Fields nodes connected. The Edit Fields node supplies `greeting: Hello, n8n!`.
3. Add an **HTTP Request** node after Edit Fields and choose the **GET** method.
4. Initially set the URL to `https://this-domain-does-not-exist-12345.com` to deliberately reproduce a connection failure.
5. Execute the workflow and observe the red failed HTTP Request node. Open its output/error details to investigate the connection problem.
6. Replace the invalid URL with the valid mock endpoint specified in the implementation plan: `https://1cb106c19a1049339451476e8e4885c5.api.mockbin.io/`.
7. Use **Test step** on the HTTP Request node. Inspect the incoming JSON and the returned response.
8. Run the complete workflow again to confirm all three nodes succeed.
9. Open **Executions** to compare historical failed and successful runs, including node-level input and output. Save the workflow.

## Expected Output and Observed Results
- **Deliberate failure:** The HTTP Request node shows a red failure indicator and a connection/host error.
- **Corrected run:** All three nodes show green success checks and the HTTP Request returns one item.
- **Input shown:** `{ "greeting": "Hello, n8n!" }`.
- **HTTP response shown:** A table with `message` set to `Hello World`.

## Execution Instructions
1. Open **Topic 2 Debugging Workflow** in the n8n editor.
2. Execute with the invalid URL and inspect the failed HTTP Request node.
3. Enter the valid URL and select **Test step**.
4. Inspect **Input** and **Output**, then execute the full workflow.
5. Review the **Executions** history for the failed and successful runs.

## Evidence
1. **Intentional HTTP failure:** `Topic2_Evidence/evidence-1.png` shows a red HTTP Request node and the connection error notification.
2. **Successful node test and data inspection:** `Topic2_Evidence/evidence-2.png` shows the input greeting, successful HTTP Request output (`Hello World`), and the success notification.
3. **Successful full workflow:** `Topic2_Evidence/evidence-3.png` shows all three nodes green with one output item.

The screenshots do not show the historical Executions page; that step is described in the instructions but is not independently evidenced here.
