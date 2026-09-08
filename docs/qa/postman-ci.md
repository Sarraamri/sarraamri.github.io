# Postman collection as runnable API documentation

<span class="badge b-qa">API testing</span><span class="badge b-perso">Personal project</span>

!!! note "The idea"
    A Postman collection covering authentication, CRUD flows, and common error cases for a REST
    API — written so that the documentation **is** the test suite. Newman runs the full collection
    in GitHub Actions on every push: if an example in the docs stops working, the build fails.

## Context

At Vneuron I produce API documentation from Swagger/OpenAPI specs and build Postman collections to
illustrate and validate endpoints. This personal project takes that practice further: documentation
that cannot silently go stale.

## What's inside

- **Auth flow** — token retrieval, expiry, refresh, with tested examples
- **CRUD requests** for each resource, expected responses saved as examples
- **Error cases** — missing auth (`401`), bad input (`400`), not found (`404`), rate limiting
  (`429`) — each with assertions on status code and response body
- **Newman + GitHub Actions** — the collection runs on every push; failures block the merge

```yaml title=".github/workflows/api-tests.yml (excerpt)"
# TODO: paste the real excerpt from your repo
- name: Run API test suite
  run: newman run collection.json -e staging.postman_environment.json
```

## Links

- :material-github: **Repository:** `TODO: link your repo`
- :material-play-circle: **A green CI run:** `TODO: link one successful Actions run`

<!-- TODO: screenshot of the Actions run with all tests green, and/or one request with its
assertions visible: ![CI run](../assets/postman-ci-green.png) -->

## What this shows

- :white_check_mark: API testing with assertions, not just example requests
- :white_check_mark: CI/CD thinking applied to quality — tests on every push
- :white_check_mark: The docs-as-code / QA overlap I want to work in
