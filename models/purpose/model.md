---
model: purpose
version: 0.1
status: candidate
question: Why, and toward what?
includes: []
---
# The Purpose model

> Why, and toward what?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `philosophy` (optional) | How do we see things, beyond us? | not set | | nothing; it sits above the why |
| `problem` | What is wrong today, and for whom? | until solved | | nothing |
| `why` | Why do we exist? | years | | nothing, or the philosophy if there is one |
| `mission` | What do we do, and for whom? | years | | the why |
| `principle` | How do we act, whatever happens? | years | | the why |
| `vision` | What does the world look like if we succeed? | years (floor 8) | | the why |

The problem, the why and the vision are three of the seven types an organization needs to start
([Organization](../organization/model.md)).

## Links

| Kind | Use here |
|---|---|
| `serves` | a mission, a principle or a vision points to the why |
| replaces | a new why or vision replaces the old one; the old one stays in history |
| contradicts | two principles that pull against each other; the explicit makes it visible |

## Views

- What do we stand for, in one page? (A manifesto is this view, not a type.)
- How has our why changed, and why?

## Checks

- Does the space state its problem and its why? Expected: yes.
- Does every mission, principle and vision serve the why? Expected: yes.
- Does any principle contradict another? Expected: no; if yes, it is a question for the person.

## Measures

None of its own. The structure measures apply, mostly gaps and tensions: objects without
`serves`, and "contradicts" links ([measures](../../standard/measures.md)).

## Routines

None from the routine table.
