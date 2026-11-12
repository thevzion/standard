# Structure checks

Status: candidate, untested.

These checks run on any space, whatever models it declares. Each one is a question with its expected answer. An unexpected answer is a smell, signaled with where it was found. A check never blocks a change ([observe before constraining](../objects/decisions/observe-before-constraining.md)).

Who answers:

- **computation**, when reading the files, their headers and the history is enough;
- **a decision model**, when the question needs understanding. It gets one atomic piece and a closed question, and returns yes or no with a probability. Below its calibrated threshold, it hands the question over ([test the tester](README.md#test-the-tester)).

A model adds its own checks in the `## Checks` section of its `model.md` (for example, "Does every goal say how we will know?" in [the Goals model](../models/goals/model.md)). The rules these checks read are in [structure](../standard/structure.md), [changes](../standard/changes.md), [truth](../standard/truth.md) and [access](../standard/access.md).

## Objects

| Check | Question | Expected answer | Who answers |
|---|---|---|---|
| `type` | Does every object have a type? | yes | computation |
| `model` | Does every object name the model that defines its type, with a version (`goals@0.1`), or `local`? | yes | computation |
| `model-declared` | Is every model an object names declared in `space.md`, or included by a declared model? | yes | computation |
| `type-defined` | Does the named model define that type, or, for `local`, does `objects/types/` define it? | yes | computation |
| `question` | Is every object's `question` its type's question, word for word? | yes | computation |
| `source` | Is every object's `source` either `from-me` or `inferred`? | yes | computation |
| `status` | Is every `lifecycle` one of proposed, active, review, done, dropped, and every `evidence` one of by-construction, sourced, observed, hypothesis, open? | yes | computation |
| `observed-dated` | Does every object with `evidence: observed` carry a date? | yes | computation |
| `one-uri` | Does each URI hold exactly one object? | yes | computation |
| `one-question` | Does each object answer one question? | yes; an object that answers several is flagged | decision model |

## Links

| Check | Question | Expected answer | Who answers |
|---|---|---|---|
| `serves` | Does every `serves` resolve to an object of this space, or through a site to an object of another space? | yes | computation |
| `draws-on` | Does every `draws-on` resolve? | yes | computation |
| `roots` | Are the roots (`problem`, `why`) the only objects without `serves`? | yes | computation |

## Local types

| Check | Question | Expected answer | Who answers |
|---|---|---|---|
| `local-question` | Does every local type in `objects/types/` state its question? | yes | computation |
| `local-double` | Does a local type ask a question that an installed type already asks? | no; if it does, it should be a field, a link or a view | decision model, one closed question per pair of a local type and an installed type |

## Changes

| Check | Question | Expected answer | Who answers |
|---|---|---|---|
| `subject` | Does every change subject follow `<object>(<operation>): <what changes>`, with a known operation? | yes | computation |
| `trailers` | Does every change carry a `Why:` trailer and a `Source:` trailer, `from-me` or `inferred`? | yes | computation |
| `append-only` | Was any accepted change rewritten? With git, the hash chain shows it; with `changes.md`, any edit to an earlier entry does. | no | computation |

Known operations: `add`, `revise`, `remove`, `rename`, `split`, `merge`, `test`, `validate`, `reverse`, `restructure`, `migrate`, and, as a candidate, `redact`.

## Space, truth and access

| Check | Question | Expected answer | Who answers |
|---|---|---|---|
| `manifest` | Does `space.md` declare the URI, the standard version, the models with their versions, the truth, the access and the adapters? | yes | computation |
| `one-source` | Does each type have one Source, every other place being a Projection, a Pointer or an Inbox? | yes | computation, on `space.md` |
| `reaches-others` | Does anything that reaches others (a publication, a message, a commitment, an expense) rest on an object still marked `inferred`? | no | computation along `serves` and `draws-on`; a decision model when it is unclear whether something reaches others |
| `access-match` | Does the written access agreement (who reads, proposes, decides, in `space.md` and the mandates) match the access the tool grants (repository rights, page sharing)? | yes | computation, through each adapter |
| `projection-by-hand` | Was any projection edited by hand, that is, changed by a change that neither touches its sources nor regenerates it? | no | computation, on the changes. How a regeneration is marked is open: [projection-definition](../objects/questions/projection-definition.md) |
| `local-committed` | Is anything under `.local/` committed? | no | computation |

## What a run returns

For each check: its id, where the unexpected answer was found (an object, a link or a change), and the answer, with its probability when a decision model gave it. Also: how many objects and changes were checked, and the version of the standard and of each model the run used.
