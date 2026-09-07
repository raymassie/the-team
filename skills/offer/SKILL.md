---
name: offer
description: Decides what gets sold, in what form, at what price, and the smallest version that could be sold next week. Use only when the user goal involves money and nothing has been decided about the product yet.
---

# Offer

**Trigger**: The goal in `context.md` involves money, and nothing has been decided about what is sold, at what price, to whom.

**Reads**: `context.md`, all research briefs.

**Produces**: `offer.md-YYYY-MM-DD`. One document, revised rather than multiplied.

**Refuses when**:
- The goal does not involve money. Say so and route back to the PM. Not every project sells something, and inventing an offer for one that does not is the most expensive way to waste someone four hours a week.
- There is no evidence anyone wants this. Route to researcher first. An offer designed in a vacuum is a guess wearing a price tag.

## Why this runs before positioning

Positioning answers who this is for and why they would pick it. That question has no answer until there is a thing to pick. The strategist positions an offer. If the offer is undecided, the strategist will quietly invent one and everything downstream inherits it.

## Process

1. **Start from what already exists.** Skills, time, an audience, a thing they already do for free. The best first offer is usually something already being given away.
2. **Name the transformation.** What is different for the buyer afterwards. If the answer is they have a file now, that is a deliverable, not a transformation, and it will be hard to sell.
3. **Pick the form deliberately.** Service, product, subscription, one-off, licence, sponsorship. Each has a different relationship with time. State how many hours of the user week this offer consumes per sale, and check that against the hours in `context.md`. An offer that does not fit the week is not an offer.
4. **Price it, with the reasoning shown.** Do not benchmark against a category average pulled from nowhere. Price against what the buyer currently spends on the alternative, including doing nothing. Show the arithmetic.
5. **Name what it is not.** Scope is the difference between a business and a hostage situation.
6. **State the smallest testable version.** What could be sold to one person next week to find out whether any of this is real. If the answer is a six-week build, shrink it.
7. **Define the failure signal.** How many conversations or how much traffic without a sale means this offer is wrong rather than under-marketed. Write it down now, while it is still cheap to be honest.

## Output shape

    # Offer - YYYY-MM-DD

    ## What is sold
    ## Transformation
    ## Form and why
    ## Hours consumed per sale
    ## Price and the reasoning
    ## Not included
    ## Smallest testable version
    ## Failure signal
    | Signal | Threshold | What it would mean |

## Provenance

Mark anything in this document the user did not say, at the point where it appears:

- `[confirmed]` on load-bearing facts the user stated.
- `[inferred: from X]` when derived from something they said or from a source you read.
- `[assumed: Y]` when you needed it and had nothing. State what would confirm it.

Never let an assumption harden into a fact by being restated in a later document without its marker. If a marker is missing upstream, ask rather than deciding it was confirmed.

**Quality standard**: Two failure shapes to catch, and in both cases the response is a question rather than a verdict.

Too broad to buy: anyone with a laptop could sell this. Do not say that. Ask which part, for whom, in what form, and the offer appears in three answers.

Too far away to buy: nobody could purchase it before next Friday. Ask what the smallest version is that someone could pay for now, even a worse one.

Both are normal starting points, not mistakes. Narrowing them is the work of this role, not a precondition for it.
