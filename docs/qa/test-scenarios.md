# Test scenarios for Reis™ TBML

<span class="badge b-qa">Test design</span><span class="badge b-work">Work</span>

!!! note ""
    Writing test scenarios is part of the TBML documentation set I own. This page shows how I turn
    a feature into an organized, prioritized test effort.

## My approach

<!-- TODO: describe your real process. Suggested shape below, edit to match reality: -->
Start from the user workflow as documented in the guide; derive the happy path as P1, then
alternate paths, then error and edge cases. One test scenario per documented workflow, so the
documentation and the tests stay in sync by construction.

## Excerpt *(sanitized / generalized)*

| ID | Priority | Scenario | Expected result |
| --- | --- | --- | --- |
| TC-01 | P1 | [Happy path of a core workflow] | [Outcome visible to the user] |
| TC-02 | P1 | [Same workflow, required field missing] | Inline validation; no submission |
| TC-03 | P2 | [State persistence across sessions] | [State restored correctly] |

<!-- TODO: replace with 3–5 real-shaped cases, generalized -->

## What this shows

- :material-check-circle:{ .sa-check } Test design as part of my actual job, not an aspiration
- :material-check-circle:{ .sa-check } Coverage thinking: happy path → alternates → edge cases
- :material-check-circle:{ .sa-check } Docs and tests as one system
