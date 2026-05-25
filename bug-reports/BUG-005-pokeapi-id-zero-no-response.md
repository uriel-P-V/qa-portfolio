Title:
GET /pokemon/0 hangs instead of returning 404

Environment:
- OS: Windows 10
- Python: 3.13
- Behave
- Requests library
- API: PokeAPI
- Endpoint: GET /pokemon/0

Severity:
High

Priority:
P1

Steps to Reproduce:
1. Send a GET request to:
   https://pokeapi.co/api/v2/pokemon/0

2. Observe the API response

Expected Behavior:
The API should return:
- HTTP 404 Not Found

This should behave consistently with other invalid Pokémon IDs..

Actual Behavior:
The request hangs and does not return a response within a reasonable time.

Impact:
- Automated tests without timeout configuration remain blocked indefinitely
- CI/CD pipelines may freeze waiting for the request to finish
- Test execution time becomes unpredictable

Workaround applied:
```python
requests.get(url, timeout=10)


## Notes
This behavior was discovered while testing boundary values for invalid Pokémon IDs.
IDs such as 99999 and "invalidname" correctly return 404, but ID 0 produces
no response. This inconsistency suggests ID 0 may trigger an unhandled edge case
in the API. The workaround is to configure a timeout in all HTTP requests to
prevent indefinite blocking.