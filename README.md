# QA Portfolio — Uriel Alejandro Pérez Valdovinos
 
Documentation artifacts from real QA engineering work —
bug reports and defect analysis from automated test suites.
 
---
 
## Bug Reports
 
| ID | Title | Severity | Priority | API |
|----|-------|----------|----------|-----|
| [BUG-001](bug-reports/BUG-001-fakestore-invalid-product.md) | GET /products/9999 returns 200 instead of 404 | Low | P3 | FakeStoreAPI |
| [BUG-002](bug-reports/BUG-002-restfulbooker-post-status.md) | POST /booking returns 200 OK instead of 201 Created | Low | P3 | RestfulBooker |
| [BUG-003](bug-reports/BUG-003-openmeteo-windspeed-field.md) | API returns "windspeed" instead of expected "wind_speed" | Medium | P2 | Open-Meteo |
| [BUG-004](bug-reports/BUG-004-fakestore-403-ci-environment.md) | GET /products returns 403 Forbidden in GitHub Actions CI | High | P1 | FakeStoreAPI |
 
---
 
## About
 
These bug reports were identified during the development of automated BDD test suites.
Each report follows industry-standard defect documentation including environment details,
steps to reproduce, expected vs actual behavior, and root cause analysis.
 
---
 
## Author
 
**Uriel Alejandro Pérez Valdovinos**  
[github.com/uriel-P-V](https://github.com/uriel-P-V) · [linkedin.com/in/uriel-pv](https://linkedin.com/in/uriel-pv)