Title:
GET /characters/9999 returns 500 Internal Server Error for non-existing character ID

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: Bob's Burgers API
- Endpoint: GET /characters/{id}

Severity:
High

Priority:
P1

Steps to Reproduce:
1. Send a GET request to:
   /characters/9999

2. Observe the response status code and body

Expected Behavior:
The API should return:
- HTTP 404 Not Found
- Structured error response indicating the character does not exist

Example:
{
  "error": "Character not found"
}

Actual Behavior:
The API returns:
- HTTP 500 Internal Server Error

Response body:
{
  "error": "Error while retreiving data with id 9999"
}

Impact:
- Invalid client requests are incorrectly treated as server failures
- Automated tests expecting 404 fail
- API error handling does not follow REST conventions
- Makes client-side debugging more difficult

Observations:
This behavior contrasts with APIs such as Rick and Morty API, which correctly return:
- HTTP 404 Not Found
- Structured JSON error responses

A non-existing resource should be handled as a client error, not as an internal server error.

Attachments:
- Behave execution logs
- HTTP response payload
- Failed assertion output

## Notes
The test was updated to expect 500 instead of 404 to match actual API behavior.
This is an API design issue — the server should handle missing resources gracefully
with a 404 rather than propagating an internal error to the client.
Long-term recommendation: the API should catch the "not found" case and return 404.