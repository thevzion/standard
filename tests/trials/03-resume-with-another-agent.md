---
trial: 3
status: not-run
level: end-to-end
tests: [https://github.com/thevzion/source/blob/main/objects/hypotheses/the-prompt-works-with-any-agent.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/it-carries-over-to-people.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/switch-models-keep-everything.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/say-it-once-every-agent-knows-it.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/you-stop-re-explaining.md]
---

# Trial 3: resume with another agent

## Questions

1. Can another agent, including one from another provider, pick up a space with nothing but the space, and no briefing?
2. With the space alone, does it find the problem, the first goal, the next task, and where to write a decision?
3. What does the person have to explain again?
4. Does a person who did not write the space find the same four things?

## Setting

- A space written by a first agent that followed [the setup prompt](../../setup/prompt.md).
- A second agent, from another provider, opens it with no briefing.
- Each agent runs clean, or the run notes what else it loaded.

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after.

## Expected answer

None. We record what happens.

## Measures

From [measures](../../standard/measures.md): context, reuse.

## Before this trial

Version 1 of the setup prompt was tried once, on 2026-11-11, with a fictional person: an agent from a second provider resumed a space written by the first and found the four things of question 2. That run used the version 1 layout ([from version 1 to version 2](../../setup/prompt.md#from-version-1-to-version-2)), so it does not count for this trial.
