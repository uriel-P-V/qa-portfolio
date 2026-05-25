Title:
POST /booking returns 200 OK instead of 201 Created

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: RestfulBooker
- Endpoint: POST /booking

Severity:
Low

Priority:
P3

Steps to Reproduce:
1. Send a POST request to:
   https://restful-booker.herokuapp.com/booking

2. Use a valid JSON request body

3. Observe the response status code

Expected Behavior:
The API should return:
- HTTP 201 Created
- Created booking information

Actual Behavior:
The API returns:
- HTTP 200 OK

The booking is created successfully, but the response status code does not follow standard REST conventions for resource creation.

Attachments:
- Behave test execution logs
- Failed assertion output

## Notes
RestfulBooker is a public API designed for testing practice.
The booking is created successfully — this is not a functional bug
but a deviation from REST standards where POST should return 201 Created.
The test was updated to expect 200 to match actual API behavior.
This is an API design issue, not a code bug.