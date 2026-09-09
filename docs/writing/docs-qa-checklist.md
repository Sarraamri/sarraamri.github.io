# Docs QA checklist

<span class="badge b-doc">Process</span><span class="badge b-work">Work practice</span>

!!! note ""
    Documentation is only correct if the product behaves the way the docs say. This is the
    checklist I run before publishing any guide. In practice, it makes every docs review an
    exploratory testing session, and it's how I regularly catch product bugs before users do.

## Accuracy against the live product

- [x] Every documented step performed end-to-end in the current build, not from memory
- [x] All UI labels, menu paths, and button names match the product exactly
- [x] Screenshots taken from the current version (no stale UI)
- [x] Default values, limits, and error messages verified, not assumed

## Behavior verification: where docs meet QA

- [x] Tried each flow with invalid input: does the product behave as the docs imply?
- [x] Checked what happens on cancel / back / refresh mid-flow
- [x] Verified permissions: does the flow work for the roles the docs claim it does?
- [x] Any mismatch between docs and product → decided which is wrong, filed a Jira ticket if it's the product

## Reader experience

- [x] Prerequisites stated before the first step needs them
- [x] Each step produces a visible result the reader can confirm
- [x] Troubleshooting section covers the failures I actually hit while testing

## Outcome

<!-- TODO: one true example, e.g. "While documenting [workflow] for TBML, this checklist
surfaced [type of issue], filed as a Jira ticket and fixed before release." -->
