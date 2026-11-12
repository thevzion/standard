---
trial: 18
status: not-run
level: end-to-end
tests: []
---

# Trial 18: adversarial review

## Questions

1. Given to a reader who did not follow the conversation that produced it, what in the architecture does not hold?
2. What do those objections change?

## Setting

The standard and the models as written in this repository ([standard](../../standard/README.md), [models](../../models/README.md)). First an agent with no history of the conversation, then a person.

## Fixed before the trial

One instruction, the same for both readers: find what does not hold.

## Expected answer

None. We record the objections, and what they change.

## Measures

The objections, each kept as a question on the object it questions, and the changes they lead to.

## What could break

The convergence itself: no outsider has attacked it yet. The concept converged in a dialogue between a person and an agent, and an agent tends to find that what it is offered holds.
