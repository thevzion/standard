---
model: loop
version: 0.1
status: candidate
question: What was asked, chosen, observed, learned?
includes: []
---
# The Loop model

> What was asked, chosen, observed, learned?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `intent` | What was asked, in the person's words, and what came of it? | until served | `as said`, `understood`, `gap`, `signals`, `lesson`, `fit` | nothing required; changes serve it |
| `question` | What are we still asking? | not set | | the object it asks about |
| `hypothesis` | What do we think is true, and how will we know? | until tested | `how we'll know` | a goal |
| `decision` | What did we choose, why, and who answers for it? | a moment | who chose, who answers for it, who is affected, why | a goal; it answers a question |
| `result` | What happened? | a moment | date | a goal; it answers a hypothesis |
| `learning` | What did we understand that changes what's above? | always | | the object it changes |

### Intent, the loop's input

| Field | What it keeps |
|---|---|
| `as said` | the request as it was said, in the person's words |
| `understood` | what the agent understood, made explicit, so it can be corrected |
| `gap` | the gap between the request and the result |
| `signals` | corrections: Corrected, Rephrased, Reverted, Reworked, Wrong place |
| `lesson` | what the system should learn from it |
| `fit` | Match, Partial, Miss, Unknown. Silence is not a Match. A decision model proposes it, then the person. |

The intent is the input trace; changes are the output trace. A commit may name the intent it
serves (an `Intent:` trailer, candidate: [intent-trailer](https://github.com/thevzion/source/blob/main/objects/questions/intent-trailer.md)).
An intent that contradicts an older one replaces it; it is not added next to it.

### The full loop

```
Intent → Questions → Objects → Intelligence → Deliverable → Check → Decision → Result
```

| Step | What happens |
|---|---|
| Intent | an intent in human words, even a fifteen-second voice note |
| Questions → Objects | one question per type makes it explicit |
| Intelligence | it reads the chain of `serves` and acts under a mandate |
| Deliverable → Check | what comes out, compared with "how we'll know" |
| Decision | who chooses, who answers for it, who is affected, and why |
| Result | what happened, dated |

The turn leaves three returns, which feed the next intent:

| Return | What it is |
|---|---|
| Learning | revises what is above |
| Resources | files, kept in Knowledge |
| Capital | what the person can now do ([Capital](../capital/model.md)) |

- **Compounding** is when the returns of one turn make the next cheaper or better: fewer follow-ups, less human time, more reuse. It is measurable, and it is a hypothesis.
- **The loop closes on its input** (candidate): each change keeps what the agent read, each object what it draws on; what one turn drew on becomes the next turn's context ([trace](../../standard/trace.md)).
- **The human loop**: want, say, (do), see, choose, learn. Only the first is not delegated: wanting, and answering for it. "Intelligence can. Only people want, and answer for it."
- Compared with the standard's earlier loop, three changes, to test: a Questions step, Decision in place of Publication, and three returns instead of Learning alone.

Whether the full loop belongs to this model, to the Organization model, or partly to the structure
is open ([who-owns-the-loop](https://github.com/thevzion/source/blob/main/objects/questions/who-owns-the-loop.md)).

## Links

| Kind | Use here |
|---|---|
| answers | a decision answers a question; a result answers a hypothesis |
| replaces | a new intent or decision replaces an older one |
| contradicts | a result that contradicts a hypothesis, an intent that contradicts another |
| `serves` | a hypothesis or a decision points to the goal it serves |
| `draws on` | a decision or a learning points to what it rests on (candidate) |

A learning ends in a `revise` change of the object above it.

## Views

- What was asked, and what came of it?
- What have we noticed and not filed yet? ("To sort", in place of an Issues type.)
- Which hypotheses are still untested?
- What did the last turns teach us?

## Checks

- Does every intent keep the request as it was said? Expected: yes.
- Is any intent counted as a Match on silence alone? Expected: no.
- Does every hypothesis say how we'll know? Expected: yes.
- Does every decision say why, and who answers for it? Expected: yes.
- Is every result dated? Expected: yes.
- Does every learning point to what it changes? Expected: yes.

## Measures

| Measure | What it says | With |
|---|---|---|
| fit | the share of intents served: Match, Partial, Miss, Unknown; silence is not a Match | |
| signals | where it sticks: Corrected, Rephrased, Reverted, Reworked, Wrong place | |
| cycle time | the time from intent to first change, then to result | `git log` |
| closed lessons | the share of lessons that became a change to the system (a rule, a skill, the doctrine) | Agreements |
| evidence | the goals with "how we'll know", the hypotheses with a result | Goals |
| drift | the gap, over time, between what a goal says and what recent work serves | Work, Goals |
| autonomy | the share of work done by routines, unasked, and the accuracy of what they inferred | `git log`, the trace |

Definitions: [measures](../../standard/measures.md).

## Routines

| Routine | Question | When | What it may do |
|---|---|---|---|
| file | What arrived and is not filed yet? | at every intent | place it, marked `inferred` |
| learn | What did the last turns teach? | when a turn closes | propose a lesson, or a change to the system |
