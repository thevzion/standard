---
trial: 10
status: not-run
level: end-to-end
tests: [objects/hypotheses/adds-no-work.md, objects/hypotheses/saying-it-clearly-costs-less-than-fixing-it.md, objects/hypotheses/fixing-an-explicit-mistake-costs-less-than-asking-first.md, objects/hypotheses/you-stop-babysitting-your-agent.md]
---

# Trial 10: commit or ask

## Questions

1. With the same intents, which costs the person less time: an agent that asks before writing, or an agent that writes, marks what it inferred, and lets the person correct?
2. How many exchanges, and how many approvals, does each one ask for?
3. How accurate are the final objects in each case?

## Setting

The same intents, two agents. One asks before writing. The other writes, marks what it inferred, and then the person corrects. The rule under test is the decision [commit rather than ask](../../objects/decisions/commit-rather-than-ask.md).

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after. Among them: how the person's time is counted, and how the accuracy of an object is judged.

## Expected answer

None. We record what happens.

## Measures

From [measures](../../standard/measures.md): balance, upkeep, accuracy, gates; and the person's time, the number of exchanges, the number of approvals asked.

## What could break

The balance: reviewing, correcting and upkeep still take time. That cost is accepted against the gains ([review cost accepted](../../objects/decisions/review-cost-accepted.md)), and the balance is measured: "adds no work" stays a hypothesis.
