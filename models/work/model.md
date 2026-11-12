---
model: work
version: 0.1
status: candidate
question: What are we doing, and what comes out of it?
includes: []
---
# The Work model

> What are we doing, and what comes out of it?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `project` | What are we building for it? | weeks (floor 3) | | a goal, or a strategy |
| `schedule` | Who does what, and when? | a week (floor 2) | `rituals`: When do we look at each floor again? | the projects it plans |
| `task` | What are we doing next? | days (floor 1) | | a project, or a goal |
| `deliverable` | What comes out, and is it done? | hours (floor 0) | | the project that delivers it |

Review is a ritual, not a rule: the moments when the person reads what was written go in the
schedule's `rituals` field. "Don't watch the agent work. Read what it wrote."

A deliverable may become a link rather than a type: a project `delivers` an object of any model
([deliverable-type-or-link](../../objects/questions/deliverable-type-or-link.md)).

## Links

| Kind | Use here |
|---|---|
| `serves` | a project points to a goal; a task to a project; the chain of `serves` is the tree |
| `delivers` | a project delivers an object (a document, a publication, code); candidate |
| depends on, blocks | local kinds, when one piece of work waits on another |

## Views

- Who does what this week?
- What came out this week, and is it done?
- What serves goal 2, from project to task?

## Checks

- Does every project serve a goal? Expected: yes.
- Does every task serve a project or a goal? Expected: yes.
- Does the schedule say its rituals? Expected: yes.
- Is every deliverable compared with the "how we'll know" of what it serves? Expected: yes.

## Measures

| Measure | What it says | With |
|---|---|---|
| alignment | the share of work whose chain of `serves` reaches a goal | Goals |
| drift | the gap, over time, between what a goal says and what recent work serves | Goals, Loop |

Definitions: [measures](../../standard/measures.md).

## Routines

| Routine | Question | When | What it may do |
|---|---|---|---|
| advance | Which goal has no next step? | every day | propose or write the next task, and do it if its mandate allows |
| watch | Does the work still serve this goal? | every week | ask the person |
