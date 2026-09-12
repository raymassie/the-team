# Crucible

Thirteen roles that take a project from I do not know what I am building to it is live and here is what the numbers say.

It starts by asking what you do, then what you want out of it. Money is one valid answer. Free equipment, credibility, an audience, a portfolio piece, or just enjoying it are equally valid, and each one changes what the rest of the work should be. From there it works out what is missing, in what order, and does that instead of whatever you asked for.

The first half is figuring out what the thing is: what you are building, who pays, what makes it different, what gets sold. The second half is getting it in front of people: content, campaigns, email, copy, the site, the results. Same chain, one direction. Nothing later in it is allowed to invent what something earlier should have decided.

Most AI marketing prompt packs are personas: files that say you are a seasoned CMO with twenty years of experience. That buys nothing. Every role here declares what it reads, what it produces, and what it refuses to do without. The handoffs are the product. The role names are labels.

## Install in Claude Code

Open Claude Code in any folder and run these two commands:

    /plugin marketplace add raymassie/crucible
    /plugin install crucible@the-team

The first adds this repo as a source. The second installs the plugin from it. Restart is not needed. To confirm it worked, run `/plugin` and look for the-team in the installed list.

To update later, `/plugin marketplace update the-team`. To remove it, `/plugin uninstall the-team@the-team`.

## Install in the Claude apps

Sidebar, then Customize, then Plugins, then Add Marketplace. Paste `raymassie/crucible` and click Sync. The plugin appears in the list. Click Install.

## Using it

**Start with `/the-team`.** That loads the map: the roster, the order roles run in, and the routing rules. Put what you want on the same line:

    /the-team I want help marketing the thing I make. Start with intake.

It asks what you do, then what you want out of it, then a few more questions. From there it works out which role runs and whether anything upstream is missing first.

You can also just describe what you want without the command. The roles fire on their own, because Claude reads their descriptions and picks. Starting with `/the-team` is more reliable, since it guarantees the routing rules are loaded before anything else happens.

**Calling one role directly.** Type a forward slash and the list filters as you type:

    /the-team:intake      start over, or fill in a gap
    /the-team:researcher  check a claim or look at competitors
    /the-team:strategist  work out positioning
    /the-team:copywriter  write a specific asset
    /the-team:editor      score and check a draft
    /the-team:designer    set visual direction
    /the-team:dev         build it and instrument it
    /the-team:analyst     read results once numbers exist

Every role in the table below works this way. Calling one directly skips the routing, so if it needs something that does not exist yet it will say so and point upstream rather than guessing.

**If nothing fires**, the plugin is probably not installed on the surface you are using. Plugins install per surface, so Claude Code and the Claude apps are separate installations. Run the /plugin command to see what is installed where you are.

In Claude Code the team writes real files into your working folder. In the apps it hands you documents in the chat for you to save.

## Using it in ChatGPT

There is no plugin format for ChatGPT, so the whole system goes in as one file.

1. Download `THE-TEAM-SINGLE-FILE.md` from this repo.
2. Go to Explore GPTs, then Create, then Configure.
3. Under Knowledge, upload that file.
4. Paste this into Instructions:

> You are The Team. The attached file contains a map and thirteen role skills. Before responding to anything, read the map section at the top in full: roster, order, routing, document handling. Follow its routing rather than answering directly. If no context has been established in this conversation, run intake first. Never skip a step. Read a role in full before acting as it.

5. Save, then start a chat with it.

Two differences from Claude. You cannot call a role by name, so ask for it in words. And the single file is generated from `skills/`, so if the two ever disagree, the files in `skills/` are correct.

The same file works for any other assistant that takes documents.

## A note on memory

If Claude memory is on, it may recall things from your past conversations. Intake treats anything it did not hear from you in this conversation as a lead rather than an answer: it can ask whether something is relevant, but it will not hand you a list of things you might build and ask you to pick.

If you would rather it worked from a blank slate, turn memory off in Settings before your first run.

## Nothing is saved in chat interfaces

Claude apps and ChatGPT have no filesystem. The team hands you finished documents. Save the ones you want, and paste them back when a later step needs them. Claude Code writes real files instead.

## What is in here

| File | Role |
|---|---|
| `EXAMPLE.md` | A worked example, invented case. |
| `THE-TEAM-SINGLE-FILE.md` | Everything in one file, for ChatGPT and others. |
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

MIT. See [COLOPHON.md](COLOPHON.md) for design decisions, influences, and source credits.
