# QA Portfolio — Uriel Alejandro Pérez Valdovinos

Documentation artifacts from real QA engineering work —
bug reports and defect analysis from automated test suites.

---

## Bug Reports

| ID | Title | Severity | Priority | Project |
|----|-------|----------|----------|---------|
| [BUG-001](bug-reports/BUG-001-fakestore-invalid-product.md) | GET /products/9999 returns 200 instead of 404 | Low | P3 | FakeStoreAPI |
| [BUG-002](bug-reports/BUG-002-restfulbooker-post-status.md) | POST /booking returns 200 OK instead of 201 Created | Low | P3 | RestfulBooker |
| [BUG-003](bug-reports/BUG-003-openmeteo-windspeed-field.md) | API returns "windspeed" instead of expected "wind_speed" | Medium | P2 | Open-Meteo |
| [BUG-004](bug-reports/BUG-004-fakestore-403-ci-environment.md) | GET /products returns 403 Forbidden in GitHub Actions CI | High | P1 | FakeStoreAPI |
| [BUG-005](bug-reports/BUG-005-pokeapi-id-zero-no-response.md) | GET /pokemon/0 hangs instead of returning 404 | High | P1 | PokeAPI |
| [BUG-006](bug-reports/BUG-006-rickandmorty-404-structured-error.md) | GET /character/99999 correctly returns 404 with structured error | Informational | P4 | Rick and Morty API |
| [BUG-007](bug-reports/BUG-007-bobsburgers-500-invalid-id.md) | GET /characters/9999 returns 500 instead of 404 | High | P1 | Bob's Burgers API |
| [BUG-008](bug-reports/BUG-008-minio-upload-latency.md) | Upload is 37x slower than download — performance deviation | Medium | P2 | MinIO |

---

## About

These bug reports were identified during the development of automated test suites.
Each report follows industry-standard defect documentation including environment details,
steps to reproduce, expected vs actual behavior, and root cause analysis.

---

## BDD Automation Projects

| Project | Framework | API | Scenarios | CI/CD |
|---------|-----------|-----|-----------|-------|
| [weather-bdd-tests](https://github.com/uriel-P-V/weather-bdd-tests) | Behave + Gherkin | Open-Meteo | 6 | ✅ |
| [booking-bdd-tests](https://github.com/uriel-P-V/booking-bdd-tests) | Behave + Gherkin | RestfulBooker | 6 | ✅ |
| [fakestore-bdd-tests](https://github.com/uriel-P-V/fakestore-bdd-tests) | Behave + Gherkin | FakeStoreAPI | 9 | ✅ |
| [pokeapi-bdd-tests](https://github.com/uriel-P-V/pokeapi-bdd-tests) | Behave + Gherkin | PokéAPI | 5 | ✅ |
| [rickandmorty-bdd-tests](https://github.com/uriel-P-V/rickandmorty-bdd-tests) | Behave + Gherkin | Rick and Morty API | 5 | ✅ |
| [southpark-bdd-tests](https://github.com/uriel-P-V/southpark-bdd-tests) | Behave + Gherkin | South Park API | 6 | ✅ |
| [bobsburgers-bdd-tests](https://github.com/uriel-P-V/bobsburgers-bdd-tests) | Behave + Gherkin | Bob's Burgers API | 6 | ✅ |
| [jsonplaceholder-bdd-tests](https://github.com/uriel-P-V/jsonplaceholder-bdd-tests) | Behave + Gherkin | JSONPlaceholder | 8 | ✅ |
| [shinchan-bdd-tests](https://github.com/uriel-P-V/shinchan-bdd-tests) | Behave + Gherkin | Jikan (MyAnimeList) | 10 | ✅ |
| [onepiece-bdd-tests](https://github.com/uriel-P-V/onepiece-bdd-tests) | Behave + Gherkin | One Piece API | 9 | ✅ |
| [futurama-bdd-tests](https://github.com/uriel-P-V/futurama-bdd-tests) | Behave + Gherkin | Futurama API | 8 | ✅ |

---

## Pytest + Requests Projects

| Project | What it demonstrates | Tests | CI/CD |
|---------|---------------------|-------|-------|
| [requests-pytest](https://github.com/uriel-P-V/requests-pytest) | REST API testing — GET, POST, PUT, DELETE, auth, sessions | 24 | ✅ |
| [storage-test-automation](https://github.com/uriel-P-V/storage-test-automation) | Full test suite — markers, fixtures, defect reporting | 53 | ✅ |
| [storage-audit-system](https://github.com/uriel-P-V/storage-audit-system) | SQLite in tests, in-memory fixtures, CI with coverage | 13 | ✅ |
| [storage-performance-tests](https://github.com/uriel-P-V/storage-performance-tests) | Latency, throughput, P95, pytest-benchmark | 11 | ✅ |
| [storage-api-client](https://github.com/uriel-P-V/storage-api-client) | MagicMock, side_effect, assert_called_once_with | 11 | ✅ |
| [notification-test-suite](https://github.com/uriel-P-V/notification-test-suite) | Contract testing, dependency injection, schema validation | 16 | ✅ |
| [disk-health-monitor](https://github.com/uriel-P-V/disk-health-monitor) | Agile workflow, Bash scripting, Unix monitoring | 8 | ✅ |
| [minio-storage-tests](https://github.com/uriel-P-V/minio-storage-tests) | Real storage testing — MinIO buckets, objects, performance, Docker CI | 15 | ✅ |

---

## Skills Demonstrated

| Skill | Projects |
|-------|---------|
| REST API Testing | requests-pytest, storage-test-automation |
| BDD / Gherkin | weather-bdd-tests, booking-bdd-tests, fakestore-bdd-tests + 8 more |
| CRUD Lifecycle Testing | jsonplaceholder-bdd-tests |
| Mock-based Testing | storage-api-client, notification-test-suite, fakestore-bdd-tests |
| Contract Testing | notification-test-suite |
| Performance Testing | storage-performance-tests, minio-storage-tests |
| Storage Domain | minio-storage-tests, storage-test-automation, storage-audit-system |
| Docker | minio-storage-tests |
| Database in Tests | storage-audit-system |
| CI/CD — GitHub Actions | All projects |
| Bash Scripting | disk-health-monitor, storage-test-automation |
| Defect Reporting | qa-portfolio (this repo) |
| Agile Workflow | disk-health-monitor |

---

## Author

**Uriel Alejandro Pérez Valdovinos**  
[github.com/uriel-P-V](https://github.com/uriel-P-V) · [linkedin.com/in/uriel-pv](https://linkedin.com/in/uriel-pv)