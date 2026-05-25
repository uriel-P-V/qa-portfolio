BUG-003 — Incorrect wind speed field name

Title:
Open-Meteo API returns "windspeed" instead of expected "wind_speed"

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: Open-Meteo
- Endpoint: GET /forecast
- Project: weather-bdd-tests

Severity:
Medium

Priority:
P2

Steps to Reproduce:
1. Send a GET request to the Open-Meteo forecast endpoint
2. Retrieve the weather response JSON
3. Validate the field name for wind speed

Expected Behavior:
The API response should contain:

"wind_speed"

Actual Behavior:
The API response contains:

"windspeed"

This causes assertion failures in automated tests expecting the field "wind_speed".

Impact:
- Automated scenario failing
- Schema validation mismatch
- Test assertions failing

Attachments:
- Behave execution logs
- Failed assertion message

## Notes
The field name discrepancy was identified by inspecting the actual API response.
The test was updated to use "windspeed" to match the actual API contract.
This is a documentation/assumption issue, not an API bug.