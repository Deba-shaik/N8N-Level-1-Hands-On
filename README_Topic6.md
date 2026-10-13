# Topic 6 – Data Transformation Workflow

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 6 Data Transformation

## Objective
Clean and standardize raw customer information using n8n Edit Fields nodes. Trim whitespace, normalize name and email casing, rename fields, and exclude original raw fields from the final payload.

## Prerequisites
- Active n8n instance and permission to create workflows.
- Completed Topics 1–5; basic familiarity with expressions and string methods.

## Workflow Structure
Manual Trigger → Dirty Raw Data → Reformat & Map

## Workflow Steps
1. Create and save a workflow named **Topic 6 Data Transformation**.
2. Add the **Manual Trigger** node.
3. Add an **Edit Fields (Set)** node named **Dirty Raw Data**. Create three String fields with sample unformatted customer data: `Raw Name`, `contact email`, and `phone_number`. The displayed field names use spaces for the first two fields, so bracket notation is needed in expressions.
4. Add a second **Edit Fields (Set)** node named **Reformat & Map**.
5. Disable **Include Other Input Fields** to omit the original fields.
6. Configure the three String fields with these expressions:
   - `cleanName`: `{{ $json["Raw Name"].trim().toUpperCase() }}`
   - `cleanEmail`: `{{ $json["contact email"].trim().toLowerCase() }}`
   - `cleanPhone`: `{{ $json.phone_number.trim() }}`
7. Execute the workflow and inspect the **Reformat & Map** output.
8. Save the completed workflow.

## Execution Instructions
Open the workflow in n8n and select **Execute workflow**. Confirm green checkmarks on all three nodes and inspect the final node's JSON view. The supplied screenshots show one item processed successfully.

## Evidence
- **Screenshot 1 – Workflow canvas:** Manual Trigger, Dirty Raw Data, and Reformat & Map connected and showing successful execution.
- **Screenshot 2 – Mapping and result:** Expression configuration and a single cleaned record with `cleanName`, `cleanEmail`, and `cleanPhone`.

## Observed Result
The screenshots show `JANE DOE`, `jane@example.com`, and `123-456-7890` as the cleaned values. The original fields are absent from the displayed final output.

## Source Notes
The supplied implementation plan uses `Raw_Name` and `contact_email`, whereas the actual screenshot uses `Raw Name` and `contact email`. The expressions above match the screenshot's field names.
