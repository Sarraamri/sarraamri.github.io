# User guides and technical docs

<span class="badge b-doc">User docs</span><span class="badge b-work">Work</span>

!!! note ""
    I author the five user guides for the Reis™ compliance suite (AML, KYC, TFS, TBML and
    Studio), each 400+ pages, each maintained in both English and French, in Confluence.

## The guides

| Guide | Languages | Notes |
| --- | --- | --- |
| **Reis™ AML** | EN · FR | |
| **Reis™ KYC** | EN · FR | |
| **Reis™ TFS** | EN · FR | maintained across two product versions |
| **Reis™ TBML** | EN · FR | [built from scratch](tbml-doc-set.md) |
| **Reis™ Studio** | EN · FR | |

What each module does is Vneuron's to describe, not mine. What is mine is the documentation: five
guides, two languages, one writer, kept consistent with each other and with the product.

## Beyond the user guides

The five guides are the largest piece of the job, not the whole of it. I also produce:

- **API reference documentation**, generated from Swagger and OpenAPI specifications, with
  Postman collections that illustrate and validate the endpoints they describe.
- **Technical and installation documentation** written for engineers rather than for end users,
  covering setup and configuration rather than day-to-day workflows.

<!-- TODO (Sarra): list the technical docs you want named here, for example the MCP server
installation guide, and anything else that is not an end-user guide. -->

## Scale

Five products · 400+ pages per guide · two languages · one writer. The guides are what the people
using each module actually work from.

Maintaining that surface means the guides cannot each be their own private world: a reader who
knows one guide has to be able to navigate the next one without relearning anything.

## How the guides are built

A chapter starts well before there is anything to write about.

1. **Sprint review and planning.** I attend both, so I know what is coming and can plan the
   documentation alongside development instead of after it.
2. **Read the specification tickets.** I go through the specs for everything in scope, and where
   something is ambiguous I take it to the business analysts rather than guess.
3. **Talk to the developers.** A specification describes the intent. The developers know what was
   actually built, and the gap between those two is where documentation usually goes wrong.
4. **Check the QA tickets, or test it myself.** If QA has already covered the feature and the
   tickets are in the timeline, I read them. If not, I test the whole thing end to end.
5. **Raise the defects I find.** Anything broken becomes a bug ticket. I also check that the
   technical behaviour matches both the functional specification and the business rules behind
   it, because a feature can work exactly as built and still be wrong for the people who have to
   use it.
6. **Write the draft**, then take the screenshots and adjust them.
7. **Split the chapter into pages.** I plan the chapter as a whole, then divide it into the pages
   a reader actually needs, adding notes wherever the product will trip someone up.
8. **Publish it into the guide.**

Steps 1 to 5 are the reason the QA pages on this site exist: by the time I start writing, I have
already exercised the feature and filed whatever it broke on.

## Keeping five guides consistent

<!-- TODO: your real process: how you handle a change that affects several guides at once,
how you track what still needs updating after a release, and what you check before publishing. -->

!!! warning "Confidentiality"
    Reis™ is compliance software for financial institutions. Nothing here includes client names,
    real data, or internal screenshots. Structure and approach are shown; specifics are not.

## What this shows

- :material-check-circle:{ .sa-check } Ownership of a large documentation estate: five products, not one page set
- :material-check-circle:{ .sa-check } Bilingual production documentation (EN/FR) kept in sync
- :material-check-circle:{ .sa-check } Consistency at scale: shared structure and conventions across every guide
