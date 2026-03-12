# Quickstart: Testing a REST API with Postman

This guide explains how to send a basic API request using Postman and review the response. Postman is commonly used by developers and QA engineers to test APIs during development and debugging.

By the end of this tutorial, you will be able to:
- Send a GET request to an API endpoint
- Add authorization headers
- View and interpret a JSON response
- Troubleshoot common errors

---

## Prerequisites

Before starting, make sure you have:

- Postman installed
- An API endpoint to test
- An API key (if authentication is required)

You can download Postman from the official site:

https://www.postman.com/downloads/

---

## Step 1: Create a New Request

1. Open Postman.
2. Click **New**.
3. Select **HTTP Request**.

In the request tab:

- Choose the request type **GET**
- Enter the API endpoint URL.

Example:
```
GET https://api.example.com/v1/users
```


---

## Step 2: Add Authorization (If Required)

Many APIs require authentication.

To add an API key:

1. Click the **Headers** tab.
2. Add the following header:

| Key | Value |
|----|----|
| Authorization | Bearer YOUR_API_KEY |

Example:
```
Authorization: Bearer 12345abcde
```

---

## Step 3: Send the Request

Click **Send**.

Postman sends the request to the server and displays the response in the lower panel.

---

## Step 4: Review the Response

Most APIs return responses in **JSON format**.

Example response:

```json
{
  "users": [
    {
      "id": 245,
      "name": "Jane Doe",
      "email": "jane@example.com"
    },
    {
      "id": 246,
      "name": "John Smith",
      "email": "john@example.com"
    }
  ]
}
```
Important things to check:

- Status code
- Response time
- Returned data

Common success status code:

```
200 OK
```

### Understanding Status Code
| Status Code | Meaning |
|-------------|---------|
|200          | Request successful |
|401          | Unauthorized request |
|404          | Resource not found|
|500          | Server error |

Status codes help developers quickly identify issues with an API request.

### Troubleshooting
| Error            | Cause                          | Fix                              |
|------------------|--------------------------------|--------------------------------- |
|401 Unauthorized  | Missing or incorrect API key.  | Verify the Authorization header. |
|404 Not Found     | Incorrect endpoint URL.        | Confirm the endpoint path.       |
|500 Internal Server Error | Server-side issue.     | Check API logs or contact the API provider. |



