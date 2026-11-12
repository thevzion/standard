---
trial: 16
status: not-run
level: end-to-end
tests: [https://github.com/thevzion/source/blob/main/objects/hypotheses/structure-fixes-verbose-agents.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/structure-shrinks-the-context.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/it-compounds.md, https://github.com/thevzion/source/blob/main/objects/hypotheses/you-stop-re-explaining.md]
---

# Trial 16: the learned context

## Questions

The same task is done twice: once with the default context, once with a context built from the `draws-on` of earlier turns.

1. How does the size of the context compare?
2. How do anchoring and accuracy compare?
3. How does the person's review time compare?

## Setting

A test space with earlier turns whose `draws-on` are recorded ([trace](../../standard/trace.md)), and one task given twice.

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after.

## Expected answer

None. We record what happens.

## Measures

From [measures](../../standard/measures.md): context, anchoring, accuracy, reuse, and the person's review time.
