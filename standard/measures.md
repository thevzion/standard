# Measures

Standard 0.1 · candidate

Everything is explicit, so the real state of a space can be computed. Every measure here comes without a target or a threshold: it says what is ([observe before constraining](doctrine.md#observe-before-constraining)).

## The dashboard

A dashboard shows the state, and lets you operate on it. It promises nothing and limits nothing.

- **It is a projection**: it reads `space.md`, `objects/` and the history of changes (`git log`, or the Changes database). It is never a source, and says which version it comes from.
- **It is launched from the repository**, in one command, without an account or a network.
- **The same in Notion**: views and charts on the Objects and Changes databases. The same measures, in two adapters.
- **Operating** from the dashboard writes a change at the source, with its author and its why, as with any adapter.

Trial: [11](../tests/trials/11-dashboard.md). Open: [dashboard stack](../objects/questions/dashboard-stack.md).

## Canonical measures (candidate)

The standard defines them so every space computes them the same way.

From the structure, in any space, whatever its models:

| Measure | What it says | From |
|---|---|---|
| **activity** | what happens, by operation and by author (person or agent) | `git log` |
| **accuracy** | the share of the inferred that was corrected later (a `reverse` or `revise` after a `Source: inferred`) | `git log`, headers |
| **corrections by type** | the ambiguous model questions | `git log` |
| **reuse** | the share of changes that revise or link an existing object rather than create one | `git log` |
| **liveness** | objects touched recently, and those asleep | `git log`, `objects/` |
| **gaps and tensions** | objects without `serves`, "contradicts" links | links |
| **waiting** | proposals: their number and age | proposed changes |
| **emergence** | local types, their growth, their return from one space to another | `objects/types/` |
| **migration debt** | objects on an outdated model version | headers |
| **anchoring** | the share of what is produced that goes back to a human intent, directly or through space objects; its complement is genericity | `draws on`, and the swap test on what rests on nothing |
| **use** | objects others draw on, and how often; those read but never drawn on | `read`, `draws on` |
| **context** | the share of what was read that is drawn on; `draws on` without a read | `read`, `draws on` |
| **stale** | objects that draw on an outdated version of another | `draws on`, `git log` |
| **left to review** | inferred objects the person has not seen yet | headers, and what they saw, if the adapter records it |
| **upkeep** | the share of changes that serve the structure (`restructure`, `migrate`, revisions that serve no intent) rather than an intent | `git log`, the `Intent:` trailer |
| **exposure** | what leaves the space, and to whom: shared and projected objects, and what the agent read, so sent, to each provider | `read`, access, projections |
| **size** | objects and pages that grow, and how fast; an object that grows often hides several questions | `objects/`, `git log` |

From the models:

| Measure | What it says | Model |
|---|---|---|
| **fit** | the share of intents served: Match, Partial, Miss, Unknown; silence is not a Match | Loop |
| **signals** | where it sticks: Corrected, Rephrased, Reverted, Reworked, Wrong place | Loop |
| **cycle time** | time from intent to first change, then to result | Loop, `git log` |
| **closed lessons** | the share of learnings that became a change to the system (a rule, a skill, the doctrine) | Loop, Agreements |
| **evidence** | goals with "how we'll know", hypotheses with a result | Goals, Loop |
| **alignment** | the share of work whose `serves` chain goes up to a goal | Work, Goals |
| **drift** | the gap, over time, between what a goal says and what recent work serves; it is returned as a question to the person, not as a score | Work, Goals, Loop |
| **autonomy** | the share of work done by routines, without a request, and the accuracy of what they inferred | Loop, `git log`, the trace |
| **gates** | approval requests per session, and gaps between the written agreement and actual access | Agreements (to instrument) |
| **capital** | how a person's signals evolve, branch by branch | Capital, private |

**The thesis reads in five curves**: reuse, fit and anchoring go up; corrections and human time per intent go down. That is "it compounds", and "you do less, and get more", measured.

**Between spaces**, on agreement only: the emergence of local types and corrections by type, aggregated, tell the standard library which questions are ambiguous and which models are missing.

The hypotheses of this space are read against their measures ([tests](../tests/README.md)).

## Anchoring

The share of human intent in what is produced (candidate).

Three lines of human intent can produce a thousand-line document. Without a space, it is generic. The same three lines, in a space where the organization and the person have explicit objects, are less so. Each human iteration on the document makes more of it specific. A line ratio is not the measure: three lines for a thousand is leverage, not genericity. What counts is what each produced element goes back to.

How to measure it, on a product (a document, an object, an answer):
1. split it into claims;
2. label each claim: **said** (it repeats or rephrases the person's words, `from-me`), **anchored** (it follows from a space object, which it cites) or **generic** (it goes back to nothing);
3. **the swap test** finds the generic: replace the organization with another; if the claim still holds, it is generic;
4. **anchoring** is the share of said or anchored claims; **genericity** is its complement.

| Companion measure | What it says |
|---|---|
| **leverage** | volume produced per line of human intent; high leverage with low anchoring is the generic document |
| **iterations** | human passes on a product, and anchoring after each |

- **Review**: what to read first is the generic and the inferred; the anchored shows its source. Review load is measured with anchoring.
- **Who labels**: an agent that has the space, and cites its sources; a second agent without the space runs the swap test; the person checks a sample. A measure without a target: [trial 13](../tests/trials/13-genericity.md) says what the system does with it.
- **With the [trace](trace.md)**, the label is born with the object: said if the claim draws on the intent, anchored on a space object, sourced on a Pointer. The swap test only covers what rests on nothing. The trace also separates two axes the label mixed: specificity (what holds only for this organization) and traceability (what goes back to something). A sourced claim can be generic, a fact true for everyone, without being invented.

Open: [anchoring definition](../objects/questions/anchoring-definition.md), [sourced in anchoring](../objects/questions/sourced-in-anchoring.md).

## Balance and yield (candidate)

Two ways to say whether the system is worth what it costs, both in human time, the scarce resource. Compute is counted separately, in money. ([decision](../objects/decisions/yield.md))

**Balance**, or net gain: what the person no longer does, minus what they do in addition.

```
balance(n) = sum of saving(i) - upkeep(n) - setup
saving(i)  = time without the system - time with it, for intent i
```

| For one intent | Without the structure | With it |
|---|---|---|
| say | re-explain the context | a few lines: the context is in the space |
| review | the whole product | what was inferred |
| correct | back and forth, mistakes found late | the faulty object, with its why |
| search | find what was said, and where | follow the links |

What the system adds: **upkeep**, which grows with the space (the upkeep measure), and **setup**, paid once.

- **Break-even** is the number of intents from which the balance turns positive: setup divided by what one intent brings, its saving minus its share of upkeep. This reasoning made structure look heavy for small teams: when a human wrote it, upkeep exceeded the saving below a certain size. When the agent writes it, human upkeep drops, and break-even can go down to a single person. That is the hypothesis; the trials check it.
- **"It compounds", in the formula**: the saving per intent grows if each reused object shortens the next ones. If it stays flat, the system does not compound; if upkeep grows faster than it, the balance ends up falling.
- **Yield** is a ratio, not a difference: intents served (fit: Match) per hour of the person. Balance says whether it is worth it; yield says how well each hour is used.

How it is measured: the "without" can no longer be observed for an intent already done. Two means: trials with two conditions ([10](../tests/trials/10-commit-or-ask.md), [13](../tests/trials/13-genericity.md), [14](../tests/trials/14-review.md)), which measure both times on the same intents; and, day to day, indicators the dashboard computes (review load, iterations and corrections per intent, the share of upkeep), which the trials tie to time.

When the balance is negative: few intents, and setup is not paid back; a placement that forces many corrections; or upkeep that grows faster than the saving. The formula says where to look.

## Signals

- A signal counts only if it says which question it answers. A signal is a result that feeds a hypothesis.
- **One object, one thread**: each object has its reaction thread (a GitHub discussion). A progress projection shows the counts, dated, against the hypotheses.
- **The strongest signal**: the agent writes "what didn't fit", filed by type, with no answer from the person, who decides whether to send it. It is exactly the list of local types.
- **Corrections are signals too**: where they recur, a model question or a line of doctrine needs revisiting.
