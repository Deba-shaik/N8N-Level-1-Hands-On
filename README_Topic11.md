# Topic 11 – HTTP Request Node

**Course:** n8n Hands-On Beginner Course  
**Workflow:** Topic 11 HTTP Request Node

## Objective
Learn to retrieve public API data using HTTP GET, transform selected fields with Edit Fields, and submit a JSON payload using HTTP POST in n8n.

## Prerequisites
- Access to an n8n workspace with workflow edit and test permissions.
- Basic knowledge of REST APIs, GET/POST methods, and JSON.
- Outbound internet access to the JSONPlaceholder test API.
- Completion of earlier beginner-course topics.

## Workflow Steps
1. **When clicking 'Execute workflow' (Manual Trigger):** Starts the workflow.
2. **Fetch User (HTTP Request):** Configure GET `https://jsonplaceholder.typicode.com/users/1` with Authentication `None`. The returned user record contains fields such as `id`, `name`, and `email`.
3. **Prepare Post Payload (Edit Fields):** Create two string fields using dynamic values from the GET response:
   - `title`: `User Post by {{ $json.name }}`
   - `body`: `Email: {{ $json.email }}`
4. **Send Custom Post (HTTP Request):** Configure POST `https://jsonplaceholder.typicode.com/posts`, Authentication `None`, enable **Send Body**, choose **JSON**, and map `title` to `{{ $json.title }}` and `body` to `{{ $json.body }}`.

## Execution Instructions
1. Open the saved workflow in n8n.
2. Confirm the GET and POST endpoint URLs and node connections.
3. Click **Execute workflow**.
4. Inspect the Fetch User response and the Send Custom Post response.
5. Save the workflow after testing.

## Evidence
- **Screenshot 1 – Complete workflow:** Four nodes show green success checks, each processing one item.
- **Screenshot 2 – GET request:** The Fetch User node uses GET `/users/1` and returns the user profile for Leanne Graham.
- **Screenshot 3 – POST request:** The final node uses POST `/posts`, sends a JSON body, and receives a mock response with resource ID `101`.

## Observed Result and Notes
The screenshots demonstrate successful GET and POST execution. The POST screenshot displays `title` as `Leanne Graham` and `body` as `Sincere@april.biz`, rather than the prefixed text specified in the implementation plan (`User Post by ...` and `Email: ...`). The POST is a mock API operation and does not create a persistent production record.
