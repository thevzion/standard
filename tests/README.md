# Tests

Status: candidate, untested. No trial has run against this version of the standard.

## A test is a question

A test is a question put to a space, with its expected answer. It runs on the sources, and what comes back is compared with what was expected. It has the same form as the rest of the standard: a question, sources, an answer ([questions](../standard/questions.md)).

| | The question | Who answers | What comes out |
|---|---|---|---|
| a check | what must be true: "Does every goal say how we will know?" | computation, or a decision model | yes or no, or a distribution |
| a measure | how much: "What share was inferred?" | computation | a number |
| a trial | a series of questions put to a test space | agents, then a judge | a distribution |

Deterministic or probabilistic, question by question. Computation answers where it is enough (a measure, a check on the structure); intelligence answers where understanding is needed. From the cheapest to the most expensive: computation, a decision model, a writing model, the person.

## Four levels

Many of these questions go to a decision model: it gets one atomic piece and a closed question, and it classifies.

| Level | The question is about | Example | Who answers | What comes out |
|---|---|---|---|---|
| unit | one object | "Does this goal say how we will know?"; "Is this a goal or a task?" | computation, or a decision model | yes or no, with a probability |
| integration | a few objects and their links | "Does this task serve a goal?"; "Does this change contradict a decision?" | computation on the links, or a decision model | yes or no, with the objects involved |
| end-to-end | a scenario, in a test space | the [trials](#index-of-trials) | agents, then a judge | a distribution |
| watch | a person or an organization, over time | "Does the work of the last three weeks still serve this goal?" | a decision model on recent work, then a pure agent if doubt remains | a question for the person |

Why this is viable now: a closed question on an atomic object is cheap and fast for a decision model. Thousands can be asked, and asked again at every change. Before, each question needed a person or a large AI model.

## Trials as automated tests

Like tests for code, but played by agents.

| Part | What it is |
|---|---|
| Setting | a test space at a given version, and intents written in advance |
| Play | an agent handles the intents; the trace keeps everything it read and wrote |
| Assertions | on objects, not on text. "This intent gives a goal that `serves` the vision, marked `inferred`" can be checked; "the document is good" cannot. Atomicity is what makes an agent's work testable. |
| Judge | first the checks and the measures, computed; then a decision model, for closed questions; then the person, on a sample. The judge is never the agent under test, and preferably not from the same provider. |
| Repetition | an agent never returns the same thing twice. Each trial runs several times, and we read a distribution, not a pass or a fail. |
| Versions | each run's trace notes the AI model, the doctrine and the versions of the models. Without them, two runs do not compare. It also notes what else the agent loaded (global instructions, memory, hooks): a run on the tester's own configuration is not a clean run. |
| Exposure | real intents go to the AI providers ([access](../standard/access.md)). Trials use fictional intents, or real ones with the person's consent. |
| Cost | a suite costs compute, and that is measured too. |

Each trial file holds its questions, its setting, the criteria fixed before it runs, its expected answer where there is one, its measures ([measures](../standard/measures.md)) and what could break. Criteria are written before the first run and not changed after. A run is recorded with its date, its versions and what happened, and the hypotheses it tests get a `test` change ([changes](../standard/changes.md)).

## Test the tester

A decision model is calibrated before anyone relies on it. On a sample labeled by the person, or by a large AI model, we measure its agreement, and from that we set the probability threshold below which it hands the question over. Open: [decision-model-threshold](../objects/questions/decision-model-threshold.md).

## The watch

Some questions are asked continuously, like monitoring in production rather than a test: "Is this person drifting from their goal?" Three rules:

- **An answer is a question, not a verdict.** "Your work has served X for three weeks, and your goal says Y. Is the goal still true, or is this drift?" Changing one's mind is legitimate. Either way, the answer updates the source: the goal is replaced, or the work is redirected.
- **A person's watch belongs to them.** It runs in their space, for them alone, like Capital. In an organization, the watch covers goals and work, never people: "Your work is shared, not you."
- **No model decides for the person.** It flags; the person says what they want.

Open: [watch-settings](../objects/questions/watch-settings.md).

## Where checks live

| Checks | Where |
|---|---|
| structure checks, on any space | [structure.md](structure.md) |
| a model's own checks, for example "Does every goal say how we will know?" | the `## Checks` section of each model, in `../models/<id>/model.md`, for example [the Goals model](../models/goals/model.md) |
| trials | the files in `trials/`, listed [below](#index-of-trials) |

Checks signal; they never block ([observe before constraining](../objects/decisions/observe-before-constraining.md)).

## What can break

The concept converged on 2026-11-12: the last four ideas added no kind of thing to the meta-model, and each piece already exists and works elsewhere. That is not evidence that the assembly works. The convergence came from a dialogue between a person and an agent, and an agent tends to find that what it is offered holds.

| What can break | Why it is plausible | Trial |
|---|---|---|
| placement | everything rests on well-typed objects; if two agents file the same intent differently, the measures measure noise | [9](trials/09-placement.md) |
| declared draws-on | an AI model can cite a source it read that does not support what it claims; the gap between `read` and `draws-on` only catches sources never read | [15](trials/15-trace.md) |
| fragmentation | small objects can read as badly as a long document: people read a story, and the views must recompose it | [14](trials/14-review.md) |
| read capture | where the adapter cannot see the agent's tool calls, `read` is missing | [15](trials/15-trace.md); N1 to N7 in [4](trials/04-notion-adapter.md) |
| the balance | reviewing, correcting and upkeep still take time; that cost is accepted against the gains ([decision](../objects/decisions/review-cost-accepted.md)), and the balance is measured: "adds no work" stays a hypothesis | [10](trials/10-commit-or-ask.md); upkeep |
| labeling | the swap test, and a label set by an agent, can be unreliable | [13](trials/13-genericity.md) |
| the convergence itself | no outsider has attacked it yet | [18](trials/18-adversarial-review.md) |
| the leak | an executable life, with clean data, is worse to lose | [19](trials/19-exposure.md); exposure |

## Index of trials

Trials write only in a test space. Trials 1, 12 and 18 also read real material, read-only.

| # | Trial | Level | Hypotheses it tests | Status |
|---|---|---|---|---|
| 0 | [the first run](trials/00-first-run.md) (proposed) | end-to-end | [your-intent-is-the-source](../objects/hypotheses/your-intent-is-the-source.md) | not-run |
| 1 | [a home and the canonical repository](trials/01-home-and-canonical-repo.md) | end-to-end | | not-run |
| 2 | [two turns, and reuse](trials/02-two-turns-reuse.md) | end-to-end | [it-compounds](../objects/hypotheses/it-compounds.md), [your-intent-is-the-source](../objects/hypotheses/your-intent-is-the-source.md) | not-run |
| 3 | [resume with another agent](trials/03-resume-with-another-agent.md) | end-to-end | [the-prompt-works-with-any-agent](../objects/hypotheses/the-prompt-works-with-any-agent.md), [it-carries-over-to-people](../objects/hypotheses/it-carries-over-to-people.md), [switch-models-keep-everything](../objects/hypotheses/switch-models-keep-everything.md), [say-it-once-every-agent-knows-it](../objects/hypotheses/say-it-once-every-agent-knows-it.md), [you-stop-re-explaining](../objects/hypotheses/you-stop-re-explaining.md) | not-run |
| 4 | [the Notion adapter](trials/04-notion-adapter.md) | end-to-end | | not-run |
| 5 | [interoperability](trials/05-interoperability.md) | end-to-end | [it-carries-over-to-people](../objects/hypotheses/it-carries-over-to-people.md) | not-run |
| 6 | [the person spots the catches](trials/06-person-spots-catches.md) | end-to-end | [work-can-train-the-person](../objects/hypotheses/work-can-train-the-person.md) | not-run |
| 7 | [the reduced tree](trials/07-reduced-tree.md) | end-to-end | [the-prompt-works-with-any-agent](../objects/hypotheses/the-prompt-works-with-any-agent.md) | not-run |
| 8 | [a second model](trials/08-second-model.md) | end-to-end | | not-run |
| 9 | [placement](trials/09-placement.md) | end-to-end | [anyone-can-start-with-seven-types](../objects/hypotheses/anyone-can-start-with-seven-types.md), [your-intent-is-the-source](../objects/hypotheses/your-intent-is-the-source.md), [you-say-it-the-source-writes-itself](../objects/hypotheses/you-say-it-the-source-writes-itself.md) | not-run |
| 10 | [commit or ask](trials/10-commit-or-ask.md) | end-to-end | [adds-no-work](../objects/hypotheses/adds-no-work.md), [saying-it-clearly-costs-less-than-fixing-it](../objects/hypotheses/saying-it-clearly-costs-less-than-fixing-it.md), [fixing-an-explicit-mistake-costs-less-than-asking-first](../objects/hypotheses/fixing-an-explicit-mistake-costs-less-than-asking-first.md), [you-stop-babysitting-your-agent](../objects/hypotheses/you-stop-babysitting-your-agent.md) | not-run |
| 11 | [the dashboard](trials/11-dashboard.md) | end-to-end | | not-run |
| 12 | [an existing workspace](trials/12-existing-workspace.md) | end-to-end | | not-run |
| 13 | [genericity](trials/13-genericity.md) | end-to-end | [adds-no-work](../objects/hypotheses/adds-no-work.md), [structure-fixes-verbose-agents](../objects/hypotheses/structure-fixes-verbose-agents.md), [your-context-makes-it-specific](../objects/hypotheses/your-context-makes-it-specific.md) | not-run |
| 14 | [review](trials/14-review.md) | end-to-end | [adds-no-work](../objects/hypotheses/adds-no-work.md), [you-review-only-what-was-inferred](../objects/hypotheses/you-review-only-what-was-inferred.md) | not-run |
| 15 | [the trace](trials/15-trace.md) | end-to-end | [structure-shrinks-the-context](../objects/hypotheses/structure-shrinks-the-context.md), [every-object-knows-where-it-came-from](../objects/hypotheses/every-object-knows-where-it-came-from.md) | not-run |
| 16 | [the learned context](trials/16-learned-context.md) | end-to-end | [structure-fixes-verbose-agents](../objects/hypotheses/structure-fixes-verbose-agents.md), [structure-shrinks-the-context](../objects/hypotheses/structure-shrinks-the-context.md), [it-compounds](../objects/hypotheses/it-compounds.md), [you-stop-re-explaining](../objects/hypotheses/you-stop-re-explaining.md) | not-run |
| 17 | [projection to PROV](trials/17-projection-to-prov.md) | end-to-end | [every-object-knows-where-it-came-from](../objects/hypotheses/every-object-knows-where-it-came-from.md) | not-run |
| 18 | [adversarial review](trials/18-adversarial-review.md) | end-to-end | | not-run |
| 19 | [exposure](trials/19-exposure.md) | end-to-end | | not-run |
| 20 | [pure projection](trials/20-pure-projection.md) | end-to-end | [ask-and-it-answers-from-your-sources](../objects/hypotheses/ask-and-it-answers-from-your-sources.md) | not-run |
| 21 | [voice](trials/21-voice.md) | end-to-end | [you-say-it-the-source-writes-itself](../objects/hypotheses/you-say-it-the-source-writes-itself.md) | not-run |
| 22 | [the watch](trials/22-watch.md) | watch | [it-keeps-moving-when-you-stop-talking](../objects/hypotheses/it-keeps-moving-when-you-stop-talking.md) | not-run |
| 23 | [a routine](trials/23-routine.md) | end-to-end | [it-keeps-moving-when-you-stop-talking](../objects/hypotheses/it-keeps-moving-when-you-stop-talking.md) | not-run |
| 24 | [elevation](trials/24-elevation.md) | end-to-end | [anyone-can-start-with-seven-types](../objects/hypotheses/anyone-can-start-with-seven-types.md), [work-can-train-the-person](../objects/hypotheses/work-can-train-the-person.md), [you-dont-need-to-know-how](../objects/hypotheses/you-dont-need-to-know-how.md) | not-run |
