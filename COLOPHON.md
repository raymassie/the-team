# Colophon

How Crucible was built, what it draws from, and who deserves credit.

---

## Concept and design

Crucible was designed and built by Ray Massie in a single session on September 6–7, 2026, with Watson (Claude Sonnet 4.6) as collaborator. The core architectural decision — handoff contracts rather than personas, with defined reads, produces, and refuses-when for each role — emerged from the observation that most AI marketing skill packs are prompt libraries wearing agent clothing. The governance layer (provenance markers, refusal conditions that redirect rather than reject, a scored grading loop, a three-round cap) was designed to prevent the failure mode where a gap gets filled by a guess, the guess reads as fact in the next document, and by the third step the whole chain is built confidently on something nobody ever said.

---

## Influence Atlas

The behavioral voice of each role is informed by profiles from the [Influence Atlas](https://raymassie.github.io/influence-atlas/), a research index of 324 influential figures evaluated through a Behavioral Humanism framework, originally compiled from JSON context profiles created by [@EXM7777](https://twitter.com/EXM7777) on Twitter and extended by Ray Massie.

The Atlas profiles the roles draw from, and what specifically they take:

| Role | Profiles | What was taken |
|---|---|---|
| Strategist | Al Ries, Jack Trout | Positioning is relative not absolute; occupy a position in the mind before claiming it on paper; the competitive map comes before the claim |
| Copywriter | Eugene Schwartz, Gary Halbert | Schwartz: map the buyer's awareness level before writing a word; Halbert: conversational storytelling, the sentence should sound spoken not assembled |
| Editor | John Caples, George Orwell | Caples: testing beats intuition, nothing gets through without proof, headlines determine success; Orwell: if a sentence sounds assembled rather than said, it fails |
| Researcher | Daniel Kahneman, Nassim Nicholas Taleb | Kahneman: mark what you know versus what you assumed, systematic doubt before confidence; Taleb: ask what would break this if the consensus assumption is wrong |
| Analyst | Charlie Munger | Inversion thinking: not "did this work" but "what would have to be true for this to have failed deliberately"; avoiding stupidity over seeking brilliance; blunt without hedging |
| PM | David Ogilvy | Research-driven, systematic, institutionally minded; build incrementally with checks at each stage; the chain holds because someone is watching it |
| Strategist (council mode) | Seth Godin, Dan Kennedy, Theodore Levitt | Godin: remarkable or invisible, distrust positioning that offends no one; Kennedy: direct-response discipline, every claim tied to a specific buyer taking a specific action; Levitt: marketing myopia, define by the job the buyer hires the product to do rather than by the product category |

The full heuristics, with sources, live in `skills/crucible/voices.md`. The table above is the summary; that file is what the roles actually read.

The Atlas data is used to inform behavioral heuristics and reasoning patterns, not to impersonate these individuals. The role files describe how a person with these documented patterns would approach the work, not what that person would say.

The Influence Atlas is licensed separately. Commercial use requires written permission from Ray Massie. See [influence-atlas/LICENSE](https://github.com/raymassie/influence-atlas/blob/main/LICENSE).

---

## Research

The competitive landscape analysis that informed the positioning of Crucible was conducted in September 2026 against the following repositories. All findings are source-anchored; star counts are point-in-time as of that date.

| Repository | Stars | Notes |
|---|---|---|
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | 49.4k | The de-facto standard; shared context file pattern; lacks hard refusal gates |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 24.8k | Most architecturally ambitious; deterministic routers; policy gates in Python |
| [borghei/Claude-Skills](https://github.com/borghei/Claude-Skills) | 489 | Explicit scope and success criteria per skill |
| [indranilbanerjee/digital-marketing-pro](https://github.com/indranilbanerjee/digital-marketing-pro) | 336 | Most governance-heavy; machine-verifiable depth contract; human-approval write gates |
| [louisblythe/Sales-Skills](https://github.com/louisblythe/Sales-Skills) | 112 | Fork of coreyhaines31; stalled circa January 2026 |
| [Salesably/salesably-marketplace](https://github.com/Salesably/salesably-marketplace) | 37 | Maintained; 10 marketing + 9 sales skills |

The gap identified: no repository in the ecosystem marks confirmed facts versus assumptions versus inferences inside deliverables. No repository has handoff contracts between marketing roles with defined inputs, outputs, and acceptance criteria. Crucible was built to fill both.

---

## Design decisions

**Handoff contracts, not personas.** Every role declares what it reads, what it produces, and what it refuses to do without. The handoffs are the product; the role names are labels.

**Refusals redirect.** A refusal names what is missing, why it is needed, and the next question or step that would supply it. It never tells the user their goal is invalid. Narrowing a vague answer is the job, not passing judgment on the idea.

**The goal question comes before the product question.** Money is one valid answer. Free or loaned equipment, credibility, an audience, a portfolio piece, or enjoying the work are equally valid, and each implies completely different work downstream. The system is calibrated against the stated goal, not against a default revenue assumption.

**Provenance travels.** Every document marks load-bearing facts as confirmed, inferred, or assumed. Markers survive handoffs. The editor checks for markers that went missing between documents, because that is the failure mode: a gap gets filled by an inference, the inference reads as fact in the next document, and by the third step the chain is built on something nobody said.

**The editor can say no.** Five passes: truth, provenance, positioning drift, voice, cut. Then scoring against a rubric. Below threshold returns to the copywriter with specific criteria named. Three rounds maximum, then the system stops and names which upstream document is actually broken. The editor is the only role that can block a ship.

**Scores are earned against the goal, not against engagement.** The rubrics reward specificity, evidence, and movement toward the stated goal. An opening line that would get more reach but pulls the reader away from the goal scores lower. Optimising for engagement is the default gravity of every writing tool, and the rubric exists to resist it.

**Roles staff by the work required, not by the org chart.** A project whose goal does not involve money never runs the Offer role. A project with nothing to look at yet never runs the Designer. The example runs six of thirteen roles and notes which nine do not run, because skipping is normal and not a gap.

---

## Tools

Built with Claude Code (claude-sonnet-4-6). Repository at [github.com/raymassie/crucible](https://github.com/raymassie/crucible).

---

## License

MIT. See LICENSE.

The Influence Atlas behavioral data used to inform role voices is separately licensed. See above.
