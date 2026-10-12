# Topic 3 – Working with Core Nodes & Data Mapping

**Course:** N8N Hands-On Beginner Course  
**Workflow:** Topic 3 Core Nodes Workflow

## Objective
Learn to create typed product data with Edit Fields (Set), overwrite an existing Boolean field, map values dynamically between nodes, and calculate a price using an n8n expression.

## Prerequisites
- Complete Topics 1 and 2.
- Have access to the n8n editor and permission to save workflows.
- Understand JSON key-value pairs and String, Number, and Boolean data types.

## Workflow Overview
`Manual Trigger → Set Original Data → Modify & Map`

## Workflow Steps
1. Create and save a workflow named **Topic 3 Core Nodes Workflow**.
2. Add a **Manual Trigger** node.
3. Add an **Edit Fields (Set)** node and rename it **Set Original Data**.
4. Configure the first node with:
   - `productName` (String): `Wireless Mouse`
   - `basePrice` (Number): `25`
   - `isAvailable` (Boolean): `true`
5. Test **Set Original Data** to generate input values.
6. Add a second **Edit Fields (Set)** node named **Modify & Map**.
7. Set `isAvailable` (Boolean) to `false` to overwrite the incoming value.
8. Add `inventoryLabel` (String), mapped dynamically with `{{ $json.productName }}`.
9. Add `priceWithTax` (Number), calculated with `{{ $json.basePrice * 1.1 }}`.
10. Ensure original fields are retained in the output, run the workflow, inspect the execution result, and save.

## Execution Instructions
1. Open **Topic 3 Core Nodes Workflow** in n8n.
2. Click **Execute workflow** / **Test workflow**.
3. Check that all three nodes show green success checkmarks.
4. Open **Modify & Map**, inspect the execution status.
5. Save the final workflow.

## Evidence
![Topic 3 workflow canvas showing successful execution](Topic3_Evidence/workflow-canvas.png)

The provided screenshot shows the workflow name, Manual Trigger, Set Original Data, and Modify & Map nodes connected in sequence. All three visible nodes have green checkmarks, and the links display **1 item**. The screenshot does not show the node configuration ; configuration details require separate screenshots for field-level verification.
