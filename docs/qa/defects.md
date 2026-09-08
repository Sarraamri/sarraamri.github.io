# Defects I find while documenting

<span class="badge b-qa">Bug reporting</span><span class="badge b-work">Work</span><span class="badge b-doc">Jira</span>

!!! note "Why writers find bugs"
    Documenting a feature means executing every step of it — which makes technical writers
    accidental exploratory testers. I file Jira tickets for the defects and product gaps I find
    while writing. Below: my reporting format and sanitized real examples.

## My report format

Every report includes a one-line summary (*[where] — [what goes wrong] [under what condition]*),
environment details, numbered steps to reproduce, expected vs. actual result, severity and
priority, and evidence (screenshot or recording).

## Example report *(sanitized)*

| Field | Value |
| --- | --- |
| **Summary** | [Screen] — [what breaks] [under what condition] `TODO: rewrite from a real ticket` |
| **Severity / Priority** | Major / High |
| **Environment** | [Product module] · staging build [version] |

**Steps to reproduce**

1. Open [screen] as [role]
2. Enter [input] in [field]
3. Trigger [action] via keyboard (Tab + Enter)
4. Observe the [result area]

!!! success "Expected"
    What the spec / documentation says should happen.

!!! failure "Actual"
    What actually happens, including how to recover (e.g., refresh corrects the state).

<!-- TODO: add one sanitized annotated screenshot here:
![Annotated screenshot of the defect](../assets/defect-example.png) -->

!!! warning "Insight note"
    The judgment part: why it matters, which user path is affected, and the reasoning behind the
    severity. This is what separates a report from a complaint.

## Full report set

<!-- TODO: add 2–3 more sanitized reports, each in a collapsible block like this: -->

??? example "BUG-00X — [summary line]"
    Environment · steps · expected vs. actual · severity reasoning.

## What this shows

- :white_check_mark: Real defect tracking in Jira, in production software — daily, not aspirational
- :white_check_mark: Reproduction steps a developer can follow on the first try
- :white_check_mark: Severity judgment and edge-case instinct (keyboard paths, state after refresh)
