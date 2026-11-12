---
model: goals
version: 0.1
status: candidate
question: What do we want to make true, and how will we know?
includes: []
---
# The Goals model

> What do we want to make true, and how will we know?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `goal` | What do we want now, and how will we know? | quarters (floor 7) | `how we'll know` (required) | the vision |
| `strategy` | What are we betting on, and what do we refuse? | quarters (floor 4) | `refusals` | a goal |

A goal is an intent that lasts: it stays true until it is reached or replaced. A goal proposed by
an agent or a routine stays `proposed` until the person wants it.

## Links

| Kind | Use here |
|---|---|
| `serves` | a goal points to the vision; a strategy to the goal it bets for |
| replaces | a new goal replaces an old one rather than adding to it |
| contradicts | two goals, or a strategy and a refusal, that pull against each other |

## Views

- Where is goal 2?
- What are we betting on this quarter, and what do we refuse?
- What serves this goal, from project to task?

## Checks

- Does every goal say how we'll know? Expected: yes.
- Does every goal serve the vision? Expected: yes.
- Does every strategy name what it refuses? Expected: yes.
- Is any goal active that the person has not wanted? Expected: no.

## Measures

| Measure | What it says | With |
|---|---|---|
| evidence | the goals with "how we'll know", the hypotheses with a result | Loop |
| alignment | the share of work whose chain of `serves` reaches a goal | Work |
| drift | the gap, over time, between what a goal says and what recent work serves; returned as a question to the person, not a grade | Work, Loop |

Definitions: [measures](../../standard/measures.md).

## Routines

| Routine | Question | When | What it may do |
|---|---|---|---|
| advance | Which goal has no next step? | every day | propose or write the next task, and do it if its mandate allows |
| watch | Does the work still serve this goal? | every week | ask the person |

Defining a routine does not activate it; each acts under its own mandate
([Agreements](../agreements/model.md)).
