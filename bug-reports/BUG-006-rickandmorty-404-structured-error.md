Title:
GET /character/99999 correctly returns 404 with structured error body

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: Rick and Morty API
- Endpoint: GET /character/{id}
- Project: rickandmorty-bdd-tests

Severity:
Informational

Priority:
P4

Steps to Reproduce:
1. Send a GET request to:
   https://rickandmortyapi.com/api/character/99999

2. Observe the response status code and response body

Expected Behavior:
The API should return:
- HTTP 404 Not Found
- Structured JSON error response

Example:
{
  "error": "Character not found"
}

Actual Behavior:
The API correctly returns:
- HTTP 404 Not Found
- JSON error body:
  {
    "error": "Character not found"
  }

Observations:
Unlike some public APIs that return:
- empty bodies
- HTML pages
- plain text errors

the Rick and Morty API returns a structured JSON error response that supports reliable contract testing.

Impact:
This behavior allowed automated tests to validate:
- response status code
- structured error payload
- exact error contract using:
  data["error"]

Result:
This is not considered a defect.
The behavior follows good REST API and error-handling practices.

Attachments:
- Behave execution logs
- API error response payload

Notes
This document serves as a positive behavior reference.
Compared to FakeStoreAPI (BUG-001) and RestfulBooker (BUG-002),
the Rick and Morty API correctly implements REST error handling standards.
This consistency makes it suitable for contract testing validation.