# Topic 12 – API & Data Storage Integration

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 12 API & Data Storage

## Objective
Fetch multiple user records from a public REST API with the n8n HTTP Request node, map flat and nested JSON fields, and store all records in Google Sheets automatically.

## Prerequisites
- Access to n8n and basic understanding of GET requests and JSON.
- Working Google Sheets OAuth2 or service account credentials.
- Internet access to the JSONPlaceholder API.
- Google spreadsheet **N8N API Storage Spreadsheet**, tab **Sheet1**, with headers `ID`, `Name`, `Email`, and `Company`.

## Workflow Steps
1. **When clicking 'Execute workflow'**: Manual Trigger starts the workflow.
2. **Fetch API Users**: HTTP Request node with method `GET`, URL `https://jsonplaceholder.typicode.com/users`, and Authentication `None`. The API returns 10 user items.
3. **Append row in sheet**: Google Sheets node with operation `Append Row`; select the target spreadsheet and `Sheet1` tab, and map each incoming item to one row.

### Google Sheets Field Mapping
| Sheet column | n8n expression |
|---|---|
| ID | `{{ $json.id }}` |
| Name | `{{ $json.name }}` |
| Email | `{{ $json.email }}` |
| Company | `{{ $json.company.name }}` |

The Company expression accesses the nested `name` property of the `company` object. n8n processes all 10 incoming items without a separate looping node.

## Execution Instructions
1. Open the saved Topic 12 workflow in n8n.
2. Confirm the HTTP Request URL and Google Sheets credentials, spreadsheet, tab, and column mappings.
3. Click **Execute workflow** and wait for all three nodes to show green success indicators.
4. Open **N8N API Storage Spreadsheet** and inspect the 10 populated rows.
5. Save the workflow. Repeated runs of the Append operation can create duplicate rows.

## Evidence
- **Screenshot 1 — Successful Workflow:** Manual Trigger, Fetch API Users, and Append row in sheet show green checks; 10 items pass from the API to Google Sheets.
- **Screenshot 2 — API Response:** Fetch API Users executes GET on the users endpoint and returns 10 JSON items, including a nested `company.name` field.
- **Screenshot 3 — Stored Spreadsheet Data:** Google Sheets displays 10 populated records in the ID, Name, Email, and Company columns, including Leanne Graham with Romaguera-Crona.

## Observed Result
The supplied screenshots show the successful retrieval and storage of 10 user records, including nested company names.
