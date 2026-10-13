# Topic 10 – Gmail Integration

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 10 Gmail Integration Workflow

## Objective
Connect n8n to Gmail and automatically send a personalized plain-text email using recipient information from an earlier node.

## Prerequisites
- Access to an n8n workspace with edit and execution permissions.
- Gmail account and authorized Gmail OAuth2 credential in n8n.
- Completed foundational n8n exercises (Topics 1–9).
- An accessible recipient email inbox for testing.

## Workflow Steps
1. **Manual Trigger:** Add `When clicking 'Execute workflow'` to start a test execution.
2. **Mock Customer Data:** Add an Edit Fields node with `customerName` = `Alice Smith` and `customerEmail` = an email address you can access.
3. **Gmail – Send a message:** Add the Gmail node and choose the connected OAuth2 credential, Resource **Message**, and Operation **Send**.
4. **Dynamic recipient:** Set **To** to `{{ $json.customerEmail }}`.
5. **Personalized subject:** Set **Subject** to `Welcome to N8N Course, {{ $json.customerName }}!`.
6. **Plain-text body:** Greet `{{ $json.customerName }}`, mention completion of Topic 10, and note that the message was sent automatically through n8n.
7. Save the workflow.

## Execution Instructions
1. Open the saved workflow in n8n.
2. Confirm the Gmail credential is authorized and the test recipient is correct.
3. Click **Execute workflow**.
4. Review the green success indicators for the Manual Trigger, Mock Customer Data, and Gmail nodes.
5. Open the recipient inbox and inspect the received personalized message.

## Evidence
- **Screenshot 1 – Workflow Execution:** All three nodes show successful execution, with one item passed through the workflow.
- **Screenshot 2 – Delivered Gmail Message:** The recipient inbox displays a welcome email addressed to Alice Smith and indicating it was sent automatically using n8n.

## Observed Result
The provided screenshots show successful execution of the three-node n8n workflow and delivery of a personalized email in Gmail. The visible subject and message are slightly different in wording from the sample implementation plan but serve the same purpose.
