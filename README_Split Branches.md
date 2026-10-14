# Topic 15 - Split in Batches & Basic Error Handling

## Course
N8N Hands-On Beginner Course

## Objective
Process five mock URL records in batches of two, tolerate a deliberately invalid URL, and complete the workflow without interruption.

## Workflow structure
Manual Trigger -> Mock Items List (Code) -> Edit Fields -> Loop Over Items (Split in Batches; batch size 2)
- Loop output -> Fetch Details (HTTP GET) -> back to Loop Over Items
- Done output -> Compile Final List (Edit Fields)

## Input dataset
Five URL items: four valid requests to https://jsonplaceholder.typicode.com/posts/1 and one intentionally invalid request to https://invalid-url-domain-does-not-exist.xyz/.

## Configuration
1. Mock Items List generates five separate items, each containing a `url` string.
2. Edit Fields preserves a `url` field for each item.
3. Loop Over Items uses Batch Size = 2.
4. Fetch Details uses GET, no authentication, and the expression `{{ $json.url }}`.
5. Fetch Details is configured to continue on errors, allowing failed items to return error information.
6. Fetch Details feeds back into Loop Over Items. The Done output connects to Compile Final List.
7. Compile Final List adds `status` = `All Batches Processed`, with Include Other Input Fields disabled in the latest screenshot.

## Test and observed results
- The workflow canvas shows five input items, three Fetch Details executions, and five items at completion.
- The deliberately invalid domain produces an `ENOTFOUND` error payload.
- Processing continues after the error and the Done branch executes.
- Compile Final List outputs five items with `status: All Batches Processed`.

## Expected batch distribution
Batch 1: 2 items; Batch 2: 2 items (includes the invalid URL); Batch 3: 1 item.

## How to reproduce
1. Open the saved workflow in n8n.
2. Confirm Batch Size is 2 and Fetch Details > Settings > On Error is set to Continue.
3. Execute workflow and inspect each node's execution.
4. Verify three HTTP processing iterations, five completed items, and one `ENOTFOUND` error.
5. Save the workflow and export its JSON separately if required by the assessment.

## Evidence
See `Topic_15_Evidence_Updated.pdf` for the workflow canvas, five-item completion output, and the successful third Fetch Details run. The latest screenshot explicitly displays "Execution will continue even if the node fails."

## Notes
The invalid URL is intentional test data, not a production endpoint. Screenshots show an execution, not a downloadable workflow JSON export.
