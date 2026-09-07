---
name: channel-planner
description: Plans a finite dated campaign with one primary metric and a kill criterion set before launch. Use when the request has an end date and needs distribution rather than ongoing publishing.
---

# Channel Planner

**Trigger**: Positioning exists and something needs to reach people.

**Reads**: `positioning.md`, the Constraints and Current numbers blocks in `context.md`, relevant research.

**Produces**: `campaign-YYYY-MM-DD-[name].md`

**Refuses when**: Time budget in `context.md` is blank. Ask for the realistic number first. A plan built on hours that do not exist is how three channels get started and none get finished.

## Process

1. Start from the time and money constraint, not from the channel list. Pick the fewest channels that fit. Default is one. Two requires justification.
2. For each channel, state the mechanic: what gets published, how often, and what specifically causes a stranger to see it. Distribution is the plan. Publishing is not distribution.
3. Define one primary metric and the number that means stop. Kill criteria go in before launch, not after the sunk cost accrues.
4. List the assets required, by name, and hand them to the copywriter.
5. Sequence it. Week by week. If week one has six items, it is wrong.

## Output shape

```markdown
# Campaign: [name] - YYYY-MM-DD

## Objective and primary metric
## Channel(s) and why these, not others
## Mechanic
## Assets required
- [asset] -> copywriter
## Schedule
| Week | Action | Owner | Hours |
## Kill criteria
## Budget
```

## Provenance

Mark anything in this document the user did not say, at the point where it appears:

- `[confirmed]` on load-bearing facts the user stated.
- `[inferred: from X]` when derived from something they said or from a source you read.
- `[assumed: Y]` when you needed it and had nothing. State what would confirm it.

Never let an assumption harden into a fact by being restated in a later document without its marker. If a marker is missing upstream, ask rather than deciding it was confirmed.

**Quality standard**: If the plan would collapse in a busy week, cut it until it survives one. Build for the realistic week, not the good one.
