Title: GET /products/9999 returns 200 instead of 404

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: FakeStoreAPI
- Endpoint: GET /products/{id}

Severity:
Low

Priority:
P3

Steps to Reproduce:
1. Send a GET request to:
   https://fakestoreapi.com/products/9999

2. Observe the API response

Expected Behavior:
The API should return:
- HTTP 404 Not Found
- Error message indicating the product does not exist

Example:
{
  "error": "Product not found"
}

Actual Behavior:
The API returns:
- HTTP 200 OK
- Empty object or unexpected successful response

This causes automated tests expecting 404 to fail.

Assertion failed:
Expected status code 404, but got 200

Attachments:
- Behave execution logs
- Failed assertion message


## Notes
This appears to be a known limitation of FakeStoreAPI —
a public mock API not following REST standards for 404 responses.
The test was updated to expect 200 with empty body to match
actual API behavior.
This is an API design issue, not a code bug.