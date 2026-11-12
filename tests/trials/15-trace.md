---
trial: 15
status: not-run
level: end-to-end
tests: [https://github.com/thevzion/source/blob/main/objects/hypotheses/structure-shrinks-the-context.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/every-object-knows-where-it-came-from.md]
---

# Trial 15: the trace

## Questions

On each change:

1. What share of what the agent read serves as a declared `draws-on`?
2. Which `draws-on` have no read behind them?
3. Does the anchoring derived from the `draws-on` agree with the labeling of [trial 13](13-genericity.md)?

After an object is revised:

4. Which objects are flagged stale, and which does the person actually change?

## Setting

In a test space, the agent's adapter records what the agent reads (a hook on its tool calls), and the agent declares what it draws on ([trace](../../standard/trace.md)).

## Fixed before the trial

- How reads are captured.
- The unit: the object.
- The version: the commit.

## Expected answer

None. We record what happens.

## Measures

From [measures](../../standard/measures.md): use, context, stale.

## What could break

- Declared draws-on: an AI model can cite a source it read that does not support what it claims. The gap between `read` and `draws-on` only catches sources never read.
- Read capture: where the adapter cannot see the agent's tool calls, `read` is missing (see also [trial 4](04-notion-adapter.md)).

Open: [where-read-lives](https://github.com/thevzion/source/blob/main/objects/questions/where-read-lives.md), [draws-on-unit](https://github.com/thevzion/source/blob/main/objects/questions/draws-on-unit.md).
