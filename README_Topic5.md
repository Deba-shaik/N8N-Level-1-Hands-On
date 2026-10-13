# Topic 5 – Expressions & Variables

**Course:** N8N Hands-On Beginner Course  
**Workflow:** Topic 5 Expressions

## Objective
Learn to use n8n expressions to combine first and last names, convert text to uppercase, format ISO birth dates, and generate a dynamic processing date.

## Prerequisites
- Complete Topics 1–4.
- Access an n8n workspace with workflow editing permissions.
- Basic understanding of JavaScript expressions and JSON fields.

## Workflow Overview
Manual Trigger → Student Info (Edit Fields) → Format and Transform (Edit Fields)

## Workflow Steps
1. Create a workflow named **Topic 5 Expressions** and save it.
2. Add a **Manual Trigger** node.
3. Add an **Edit Fields (Set)** node named **Student Info** and configure String fields: `firstName = alex`, `lastName = smith`, `birthDate = 1998-04-12T10:15:30.000Z`.
4. Connect another **Edit Fields (Set)** node named **Format and Transform**.
5. Configure the String field **FULL NAME** (the screenshot's field name) using `{{ ($json.firstName + ' ' + $json.lastName).toUpperCase() }}`. The implementation plan calls this field `fullNameUpperCase`.
6. Configure **formattedBirthDate** as a String using `{{ DateTime.fromISO($json.birthDate).toFormat('MMMM dd, yyyy') }}`.
7. Configure **processedDate** as a String using `{{ $now.toFormat('yyyy-MM-dd') }}`.
8. Execute the workflow and inspect the Format and Transform output in the n8n panel.
9. Save the workflow.

## Execution Instructions
1. Open **Topic 5 Expressions** in n8n.
2. Click **Execute workflow**.
3. Confirm the Manual Trigger, Student Info, and Format and Transform nodes display green checkmarks.
4. Open **Format and Transform** to inspect the expressions and output values.

## Evidence
- **Workflow canvas:** All three connected nodes executed successfully; one item passes between nodes.
- **Format and Transform panel:** The supplied screenshot shows `ALEX SMITH`, `April 12, 1998`, and a dynamic `processedDate` value of `2026-10-12` from that execution.

See `N8N_Topic5_Workflow_Evidence.pdf` for annotated screenshots.
