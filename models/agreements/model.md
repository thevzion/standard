---
model: agreements
version: 0.1
status: candidate
question: Who may do what, and what have we promised?
includes: []
---
# The Agreements model

> Who may do what, and what have we promised?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `mandate` | Who, person or intelligence, is asked to do what, within which principles, and where must they stop? | months (floor 6) | who, what, principles, where to stop | the principles or goal it acts for |
| `rule` | How is it done here? | months (floor 5) | | a mandate, or a principle |
| `commitment` | What have we promised, and to whom? | not set | to whom | the goal it serves |
| `skill` | How is this done, step by step, by whoever does it? | not set | steps | a rule, or a project |
| `agent` | Which intelligences act here, and under which mandate? | not set | mandate | its mandate |

- Each `AGENTS.md` is a projection of the doctrine and of the space's mandates: the same ground everywhere, and what is specific to each space on top ([doctrine](../../standard/doctrine.md)).
- A commitment is needed between organizations: it is what one space promises another.
- **The gates rule**: asking for agreement is justified only where a mistake cannot be corrected precisely, or reaches someone else (a publication, a message, a commitment, an expense). Elsewhere, it is a smell ([access](../../standard/access.md)).
- Candidate, to test: a `mechanism` ("What turns what into what?"), as a type or a field of rules, close to skills.

### A mandate per routine

A routine acts under a mandate that says three things (where it lives is open:
[routine-mandates](https://github.com/thevzion/source/blob/main/objects/questions/routine-mandates.md)):

| Part | Example |
|---|---|
| what it does alone | write objects marked `inferred`, regenerate, signal |
| what it proposes | what comes from elsewhere, what is wide, what engages other people |
| what it never does | spend, send outside, decide in the person's place |

## Links

| Kind | Use here |
|---|---|
| `serves` | a mandate points to the principles it acts within; an agent to its mandate; a rule to its mandate |
| contradicts | a rule that contradicts a principle, or two mandates that overlap |

## Views

- What must every agent here follow? (Projected as `AGENTS.md`.)
- What have we promised, to whom, and by when?
- Who may do what in this space?

## Checks

- Does every agent act under a mandate? Expected: yes.
- Does every mandate say where it must stop? Expected: yes.
- Does every active routine have a mandate? Expected: yes.
- Does every commitment name to whom it is made? Expected: yes.
- Does the access an agent really has match what its mandate grants? Expected: yes.

## Measures

| Measure | What it says | With |
|---|---|---|
| closed lessons | the share of lessons that became a change to the system (a rule, a skill, the doctrine) | Loop |
| gates | requests for agreement per session, and the gaps between written agreement and real access; to instrument | |

Definitions: [measures](../../standard/measures.md).

## Routines

None of its own. This model holds the mandates the routines act under.
