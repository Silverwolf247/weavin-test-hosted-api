# weavin-test-hosted-api (branch: broken-smoke)

REPLACES README.md on branch broken-smoke. Identical to main EXCEPT the base URL points at a version that does not exist, so the smoke call returns HTTP 404 and generation must fail at the smoke stage.

- Host: `raw.githubusercontent.com`
- Base URL: `https://raw.githubusercontent.com/Silverwolf247/weavin-test-hosted-api/main/api/v9`
- Authentication: none

### GET /numbers/{n}.json
Path parameter `n`: integer 1 to 6. Response fields: `n`, `square`, `cube`, `isEven`, `isPrime`, `roman`.
Example: `GET /numbers/5.json` returns `{"n":5,"square":25,"cube":125,"isEven":false,"isPrime":true,"roman":"V"}`
