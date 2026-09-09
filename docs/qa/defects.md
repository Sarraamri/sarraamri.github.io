# Defects I find while documenting

<span class="badge b-qa">Bug reporting</span><span class="badge b-work">Work</span><span class="badge b-doc">Jira</span>

!!! note "Why writers find bugs"
    Documenting a feature means executing every step of it, which makes technical writers
    accidental exploratory testers. I file Jira tickets for the defects and product gaps I find
    while writing. Below: the format every one of those reports follows.

## My report format

| Field | What I put in it |
| --- | --- |
| **Summary** | One line: where it happens, what goes wrong, under what condition |
| **Severity / Priority** | Severity from user impact, priority from release urgency; the two are not the same |
| **Environment** | Module, build version, browser, and the role I was signed in as |
| **Steps to reproduce** | Numbered, from a known starting state, one action per step, including the input path, because mouse and keyboard don't always behave the same |
| **Expected** | What the specification or the documentation says should happen |
| **Actual** | What happens instead, and whether the state recovers on refresh |
| **Evidence** | Annotated screenshot or a short recording |
| **Insight note** | Why it matters, which user path is affected, and the reasoning behind the severity |

!!! warning "Confidentiality"
    Reis™ is compliance software for financial institutions. Examples on this site are sanitized:
    no client names, no real data, no internal screenshots. Structure and approach are shown;
    specifics are not.

<!-- ==========================================================================
     TODO (Sarra): paste one real Jira ticket in chat and I'll anonymize it
     into the section below, then uncomment it. Two more go in "Full report
     set" as ??? example collapsibles.

## Example report *(sanitized)*

| Field | Value |
| --- | --- |
| **Summary** |  |
| **Severity / Priority** |  |
| **Environment** |  |

**Steps to reproduce**

1.
2.
3.

!!! success "Expected"

!!! failure "Actual"

!!! warning "Insight note"

![Annotated screenshot of the defect](../assets/defect-example.png)

## Full report set

??? example "BUG-00X: summary line"
    Environment · steps · expected vs. actual · severity reasoning.

     ========================================================================== -->

## What this shows

- :material-check-circle:{ .sa-check } Real defect tracking in Jira, in production software: daily, not aspirational
- :material-check-circle:{ .sa-check } Reproduction steps a developer can follow on the first try
- :material-check-circle:{ .sa-check } Severity judgment and edge-case instinct (keyboard paths, state after refresh)
