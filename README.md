# The Team

A marketing department made of nine role skills that hand work to each other in a fixed order.

Most AI marketing prompt packs are personas: files that say you are a seasoned CMO with twenty years of experience. That buys nothing. This is built the other way round. Each role declares what it reads, what it produces, and what it refuses to do without. The handoffs are the product. The role names are just labels.

## Install

    /plugin marketplace add raymassie/the-team
    /plugin install the-team@the-team

That is it. Then say what you are working on:

> I want help marketing [one sentence about what you are selling]. Start with intake.

Works in Claude Code, and in the Claude apps under Customize, then Plugins, then Add Marketplace, then the repo above.

### A note on memory

If Claude memory is on, it may recall things from your past conversations. Intake treats anything it did not hear from you in this conversation as a lead rather than an answer: it can ask whether something is relevant, but it will not hand you a list of things you might build and ask you to pick.

If you would rather it worked from a blank slate, turn memory off in Settings before your first run.

### Without the plugin

Download the repo, upload the contents of `skills/` into a Project or Custom GPT as knowledge, and paste this into the instructions box:

> You are The Team. Before responding to anything, read the-team/SKILL.md in full. It is the map: roster, order, routing rules, document handling. Follow its routing rather than answering directly. If no context has been established, run intake first. Never skip a step. Read the full role file before acting as any role.

Project knowledge is searched rather than read whole, so without that instruction the assistant grabs one file, misses the routing, and answers normally.

### Nothing is saved

Chat interfaces have no filesystem. The team hands you finished documents. Save the ones you want, and paste them back when a later step needs them. Running it in Claude Code gives you real files instead.

## How you use it

You do not pick roles. Say what you want to happen and the PM works out which role should be running and whether anything upstream is missing first.

## What is in here

| File | Role |
|---|---|
| `EXAMPLE.md` | A worked example, invented case. |
| `skills/the-team/` | The map. Chain, routing, document table. Read this first. |
| `skills/intake/` | Fills `context.md` by asking you questions. |
| `skills/pm/` | Front door. Routes requests, holds chain state. |
| `skills/researcher/` | Evidence. Competitors, buyers, verified claims. |
| `skills/offer/` | What gets sold, at what price. Only if money is the goal. |
| `skills/strategist/` | Positioning: who it is for, what it replaces, why they would pick it. |
| `skills/content-strategist/` | Ongoing publishing program. |
| `skills/channel-planner/` | Finite campaigns with kill criteria. |
| `skills/email/` | Sequence architecture and lifecycle. |
| `skills/designer/` | What it looks like and why. Direction, not artwork. |
| `skills/copywriter/` | All words. Single source of voice. |
| `skills/the-team/rubrics.md` | Scoring sheets for each asset type. |
| `skills/editor/` | The only role that can block a ship. |
| `skills/dev/` | Builds it, and makes it measurable. |
| `skills/analyst/` | What the numbers actually support. |
| `skills/the-team/context.md` | Your situation. Written by intake, read by everyone. |


## See it run

[EXAMPLE.md](EXAMPLE.md) walks one invented case from first message to a blocked draft. It shows the document shapes and the handoffs. One path through, not the path: a different goal staffs a different team.

## Design decisions you may disagree with

**One copywriter.** Three planning roles feed one writing role, so you get one voice with three reasons to speak rather than three voices.

**Drafts get scored, not vibed.** The copywriter writes against a rubric, the editor scores it with a reason per criterion, and below-threshold work goes back with specific failures named. Three rounds maximum, then it stops and tells you which earlier decision is the real problem. Scores are earned against your goal, not against engagement.

**The editor can say no.** It blocks on unproven claims, positioning drift, and voice. If it approves everything, it is not working.

**Dev owns measurement.** A campaign brief names a metric. That metric is fiction until an event fires somewhere. A build is not finished until the analyst can read the number.

**Refusals redirect, they never reject.** Roles stop when something upstream is missing, and a stop always comes with the next question rather than a verdict on your idea. It will not tell you your goal is invalid or that your thing will not sell. Narrowing a vague answer into a specific one is the job.

**Your goal is taken as given.** It asks what you do before it asks what you want, because the second question is impossible to answer cold. Whatever you say is the standard everything downstream gets measured against. Revenue is not assumed.

**Nothing gets invented quietly.** Every document marks what you actually said, what was worked out from it, and what was assumed outright. Assumptions keep their marker as they move down the chain, and the editor checks for ones that lost it. This is the single most common way these systems go wrong: a gap gets filled by a guess, the guess reads as fact in the next document, and by the third step the whole thing is built on something you never said.

**It asks what winning looks like before it asks what you sell.** Money is one valid answer. So are free product, credibility, an audience, a portfolio piece, or just enjoying it. Each implies completely different work, and assuming a revenue model that is not there sends everything downstream in the wrong direction.

**Unknowns travel, they do not block.** Intake marks what it does not know and states the assumption being used instead. Downstream documents carry the caveat where you will see it. You are never stopped, and you are never quietly guessed at either.

**Kill criteria go in before launch.** Every campaign defines the number that means stop, before there is any sunk cost to defend.

## What this will not do

It will not invent numbers. It will not make a claim you have no proof for. It will not write a nurture sequence for a list that does not exist. When it refuses, the refusal names what is missing and where to get it.

## Licence

MIT.
