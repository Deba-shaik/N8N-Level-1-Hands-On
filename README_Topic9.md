# Topic 9 – Google Sheets Integration

## Objective
Connect n8n to Google Sheets to append, read, and update customer records.

## Prerequisites
- n8n editor access
- Connected Google Sheets OAuth2 credential
- Google spreadsheet with `Name`, `Email`, `Status` columns

## Workflow Steps
1. **Manual Trigger** – Execute the workflow.
2. **Mock Customer Data** – Set `customerName` to `Charlie Brown` and `customerEmail` to `charlie@example.com`.
3. **Append row in sheet** – Map customer name and email dynamically and set initial Status to `Pending`.
4. **Read Customers** – Retrieve spreadsheet rows.
5. **Customer Status** – Match the row using the Email column and update Status to `Verified`.

## Execution Instructions
Open the workflow, confirm the Google Sheets credential and spreadsheet selection, click **Execute workflow**, inspect the nodes, and verify the updated customer record in Google Sheets. Save the workflow.

## Evidence
- Screenshot 1: All five workflow nodes completed successfully.
- Screenshot 2: Google Sheets shows Charlie Brown, charlie@example.com, and Verified status.
- Screenshot 3: Google Sheets OAuth2 account shows connected.

## Observed Result
The screenshots show successful workflow execution, a connected Google Sheets credential, and a customer row marked Verified.
