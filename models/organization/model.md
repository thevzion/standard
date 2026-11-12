---
model: organization
version: 0.1
status: candidate
question: What do we want, explicitly enough that others can act on it?
includes: [purpose@0.1, goals@0.1, work@0.1, loop@0.1, agreements@0.1]   # knowledge@0.1 when the space needs it
---
# The Organization model

> What do we want, explicitly enough that others can act on it?

An organization is an intent made explicit enough that others, people or intelligences, act on
it. The Organization model is not the foundation: it is the first model, and the default door. The
center stays the person. An organization is a space that follows this model; the structure's rules,
written for organizations, hold for any space.

## Types

No types of its own. It takes those of the models it includes. Each type asks a question, has a
horizon, and points to what justifies it (`serves`).

| Model | Types |
|---|---|
| [Purpose](../purpose/model.md) | `problem`, `why`, `mission`, `principle`, `vision`, `philosophy` (optional) |
| [Goals](../goals/model.md) | `goal`, `strategy` |
| [Work](../work/model.md) | `project`, `schedule`, `task`, `deliverable` |
| [Loop](../loop/model.md) | `intent`, `question`, `hypothesis`, `decision`, `result`, `learning` |
| [Agreements](../agreements/model.md) | `mandate`, `rule`, `commitment`, `skill`, `agent` |
| [Knowledge](../knowledge/model.md), if needed | `document`, `material`, `source`, `person`, `journal`, `term` |

### The minimum: seven

Seven questions, from four models, are enough to start.

| Type | Question | Model |
|---|---|---|
| `problem` | What is wrong today, and for whom? | Purpose |
| `why` | Why do we exist? | Purpose |
| `vision` | What does the world look like if we succeed? | Purpose |
| `goal` | What do we want now, and how will we know? | Goals |
| `project` | What are we building for it? | Work |
| `task` | What are we doing next? | Work |
| `decision` | What did we choose, why, and who answers for it? | Loop |

"Seven questions. One folder. Then it compounds." Candidate, tested by
[trial 9](../../tests/trials/09-placement.md).

### What is not a type

| Thing | What it is |
|---|---|
| the space | described by [`space.md`](https://github.com/thevzion/source/blob/main/space.md) |
| a site | a link to another space |
| the inbox | a status of changes: the proposed ones |
| the log | the set of changes ([changes](../../standard/changes.md)) |

## Links

Those of the included models: `serves`, answers, replaces, `delivers`, contradicts, `draws on`
(candidate), and local kinds. The chain of `serves` is the organization's tree.

## Views

**The floors**: one view across the included models, from the longest horizon to the shortest.

| Floor | Type | Horizon | Model |
|---|---|---|---|
| 8 | `vision` | years | Purpose |
| 7 | `goal` | quarters | Goals |
| 6 | `mandate` | months | Agreements |
| 5 | `rule` | months | Agreements |
| 4 | `strategy` | quarters | Goals |
| 3 | `project` | weeks | Work |
| 2 | `schedule` | a week | Work |
| 1 | `task` | days | Work |
| 0 | `deliverable` | hours | Work |

Also, from the included models:

- Where is goal 2?
- What do we stand for, in one page?
- What must every agent here follow? (Projected as `AGENTS.md`.)
- What have we noticed and not filed yet?

## Checks

- Does the space have the seven minimum types? Expected: yes.
- Does every object except the problem and the why serve something? Expected: yes.
- Does every chain of `serves` reach the vision? Expected: yes.
- Plus the checks of each included model.

## Measures

Every measure the included models enable, on top of the structure measures:

| Measure | From |
|---|---|
| fit, signals, cycle time, autonomy | Loop |
| evidence | Goals, Loop |
| alignment | Work, Goals |
| drift | Work, Goals, Loop |
| closed lessons | Loop, Agreements |
| gates | Agreements |

The thesis reads in five curves: reuse, fit and anchoring rise; corrections and human time per
intent fall ([measures](../../standard/measures.md)).

## Routines

The canonical routines any organization can take. A routine is a question asked on its own, on a
trigger, under a mandate; what it does is a change, with its trace.

| Routine | Question | When | What it may do |
|---|---|---|---|
| file | What arrived and is not filed yet? | at every intent | place it, marked `inferred` |
| advance | Which goal has no next step? | every day | propose or write the next task, and do it if its mandate allows |
| check | Does this change break a check? | at every change | signal, like continuous integration |
| refresh | Which projection draws on a source that changed? | at every change | regenerate it |
| watch | Does the work still serve this goal? | every week | ask the person |
| take stock | What changed, and what waits for the person? | every day or week | a projection to read |
| learn | What did the last turns teach? | when a turn closes | propose a lesson, or a change to the system |

- **Defining is not activating**: a routine runs only if the person activates it.
- **A mandate per routine**: what it does alone, what it proposes, what it never does ([Agreements](../agreements/model.md)).
- **It advances; the person wants**: a goal a routine proposes stays proposed until the person wants it.
- **A budget, and the trace**: each routine has a measured cost, and what it does is reviewed like the rest, inferred first.
- **Stopped in one gesture**; a routine that drifts is signaled.
