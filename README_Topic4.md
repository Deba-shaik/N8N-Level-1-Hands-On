# Topic 4 - JSON & Data Structure Basics

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 4 JSON Basics Workflow

## Objective
Understand nested JSON objects and arrays in n8n, inspect node data, and extract nested values using dot notation and array indexing.

## Prerequisites
- Completed Topics 1, 2, and 3.
- Basic understanding of JSON key-value pairs.
- Access to n8n with permission to create and execute workflows.

## Workflow Steps
1. Create and save a workflow named **Topic 4 JSON Basics Workflow**.
2. Add the **Manual Trigger** node.
3. Add a **Code** node named **Mock Nested JSON Data**, set JavaScript and **Run Once for All Items**, and generate a nested customer object with address, orders array, and status.
4. Execute the Code node and inspect the data in **JSON**, **Table**, and **Schema** views.
5. Add an **Edit Fields (Set)** node named **Extract Values**.
6. Map `customerName` (String) using `{{ $json.customer.name }}`.
7. Map `cityOfCustomer` (String) using `{{ $json.customer.address.city }}`.
8. Map `firstOrderTotal` (Number) using `{{ $json.orders[0].total }}`.
9. Execute the workflow and save it.

## Execution Instructions
1. Open the workflow in the n8n editor.
2. Click **Execute workflow**.
3. Confirm the Manual Trigger, Mock Nested JSON Data, and Extract Values nodes show green checkmarks.
4. Inspect the **Extract Values** node output and verify the three mapped fields.
5. Save the workflow.

## Evidence
- **Screenshot 1:** Code node configuration and nested customer JSON output.
- **Screenshot 2:** Workflow canvas showing successful execution of all three nodes.
- **Screenshot 3:** Extract Values node showing the expressions and extracted values.

The screenshots show a successful workflow run with one item passing between nodes and the extracted values Jane Doe, New York, and 45.99.
