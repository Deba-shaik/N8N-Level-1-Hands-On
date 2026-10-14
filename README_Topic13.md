# Topic 13 – IF Node & Conditional Logic

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 13 IF Node Workflow

## Objective
Use an IF node to evaluate customer order values independently and route qualifying orders to VIP status and other orders to Regular status. The threshold is **100**.

## Prerequisites
- Access to an n8n workspace.
- Completion of Topics 1–12 and basic understanding of true/false comparisons.
- Familiarity with Manual Trigger, Code, Edit Fields (Set), and IF nodes.

## Workflow Steps
1. **Manual Trigger:** Start the workflow manually.
2. **Mock Orders (Code node):** Generate two separate items: Alice with `orderValue: 150`, and Bob with `orderValue: 75`. A Code node was used to produce multiple items.
3. **Check Order VIP Status (IF):** Set a Number condition using `{{ $json.orderValue }}` with the operator **is greater than or equal to** and comparison value `100`.
4. **True branch – Set VIP:** Set a String field to `VIP` and enable **Include Other Input Fields** to preserve the customer data.
5. **False branch – Set Regular:** Set a String field to `Regular` and enable **Include Other Input Fields**.

## Execution Instructions
1. Open **Topic 13 IF Node Workflow** in n8n.
2. Confirm the nodes are connected: Manual Trigger → Mock Orders → Check Order VIP Status → Set VIP / Set Regular.
3. Click **Execute workflow**.
4. Inspect the two IF branches and the Set VIP and Set Regular outputs.
5. Save the workflow.

## Evidence
- **Screenshot 1 – Workflow Execution:** All five nodes show green success marks; two items enter the IF node, with one routed to each branch.
- **Screenshot 2 – Mock Orders:** The Code node returns Alice (150) and Bob (75).
- **Screenshot 3 – VIP Branch:** The Set VIP node returns Alice, 150, and `Status: VIP`.
- **Screenshot 4 – Regular Branch:** The Set Regular node returns Bob, 75, and `Status: Regular`.

## Observations
Both items were routed to the appropriate branch, and their original fields were preserved. The screenshots use the field name `Status` with a capital S, while the implementation plan specifies lowercase `status`; rename this field in both Edit Fields nodes if exact field-name compliance is required.
