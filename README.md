# weavin-test-hosted-api

A tiny, read-only, key-free public HTTP API about the integers 1 to 6. It is served as static JSON files by GitHub (raw.githubusercontent.com), so the answers never change. Use it to look up properties of a small integer.

## Server

- Host: `raw.githubusercontent.com`
- Base URL: `https://raw.githubusercontent.com/Silverwolf247/weavin-test-hosted-api/main/api/v1`
- Authentication: none (no token, no API key)
- All endpoints are `GET` and read-only. Responses are JSON (the server labels them text/plain; parse the body as JSON).

## Endpoints

### GET /meta.json
Service info. Response: `{"name":"weavin-test-hosted-api","version":"1.0.0","ok":true,"range":"1-6"}`

### GET /numbers/{n}.json
Path parameter `n`: integer from 1 to 6. Any other value returns HTTP 404.

Response fields: `n`, `square`, `cube`, `isEven`, `isPrime`, `roman`.

Examples:

| Request | Response |
|---|---|
| `GET /numbers/5.json` | `{"n":5,"square":25,"cube":125,"isEven":false,"isPrime":true,"roman":"V"}` |
| `GET /numbers/4.json` | `{"n":4,"square":16,"cube":64,"isEven":true,"isPrime":false,"roman":"IV"}` |
| `GET /numbers/6.json` | `{"n":6,"square":36,"cube":216,"isEven":true,"isPrime":false,"roman":"VI"}` |
| `GET /numbers/9.json` | HTTP 404 |

## Smoke test suggestion
`GET /numbers/5.json` should return `square` equal to 25 and `isPrime` equal to true.
