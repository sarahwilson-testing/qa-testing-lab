# API Testing Scenarios (Postman)

This document outlines example API testing scenarios that would be executed using Postman if the Done-ish application exposed backend service endpoints.

The goal is to validate request/response behavior, authentication, and data integrity.

---

# Example API Test Scenarios

## Create Task Endpoint

Endpoint (Example)
POST /tasks

### Test Case: Create Task Successfully

Request Body Example

{
  "taskName": "Clean kitchen",
  "duration": 5
}

Expected Response

- HTTP status code: 201 Created
- Response body contains created task object
- Task ID is returned

---

### Test Case: Missing Task Name

Request Body Example

{
  "duration": 5
}

Expected Response

- HTTP status code: 400 Bad Request
- Error message indicating required field is missing

---

## Retrieve Tasks Endpoint

Endpoint (Example)

GET /tasks

### Test Case: Retrieve Task List

Expected Response

- HTTP status code: 200 OK
- Response contains list of tasks
- Each task includes:
  - id
  - taskName
  - completion status

---

## Update Task Completion

Endpoint (Example)

PATCH /tasks/{id}

### Test Case: Mark Task Complete

Request Example

{
  "completed": true
}

Expected Response

- HTTP status code: 200 OK
- Task completion status updated

---

# Additional Validation

Postman tests would also validate:

- Response time
- Response structure
- Correct status codes
- Error handling for invalid inputs
