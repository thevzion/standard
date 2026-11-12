---
trial: 0
status: not-run
level: end-to-end
tests: [objects/hypotheses/your-intent-is-the-source.md]
---

# Trial 0: the first run

The first trial, proposed. At a small scale, it exercises placement ([trial 9](09-placement.md)), genericity ([trial 13](13-genericity.md)), review ([trial 14](14-review.md)) and the trace ([trial 15](15-trace.md)), with the criteria of those trials.

## Questions

1. When real intents are filed by an agent that follows the standard, where does each one go, and is it marked as it should be?
2. How anchored, and how generic, are the objects it writes?
3. How long does the person take to find what was inferred, and what is wrong?
4. Of what the agent read, what serves as a declared `draws-on`, and which `draws-on` have no read behind them?
5. On the second turn, what is reused from the first?

## Setting

- A test space with the Organization model ([organization](../../models/organization/model.md)).
- The intents: the real messages that produced the architecture in this repository, about fifteen, used with their author's consent. The messages themselves are not in this repository.
- Two turns.
- Read capture on: the agent's adapter records what it reads.
- Those messages already produced a long document, written without the standard. It is the long-document condition of [trial 14](14-review.md), on real data.

## Fixed before the trial

The criteria of trials 9, 13, 14 and 15, as written in their files, fixed before the run and not changed after.

## Expected answer

For placement, the expected answer of [trial 9](09-placement.md). For anchoring, review and the trace: none. We record what happens.

## Measures

Placement, against the criteria of [trial 9](09-placement.md). From [measures](../../standard/measures.md): anchoring, genericity (swap test), leverage, left to review, use, context, reuse.

## What could break

The rows of [what can break](../README.md#what-can-break) for placement (9), labeling (13), fragmentation (14), declared draws-on and read capture (15).
