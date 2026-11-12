---
trial: 8
status: not-run
level: end-to-end
tests: []
---

# Trial 8: a second model

## Questions

1. Can the Game model be sketched (Premise, Core loop, Mechanics, Playtests) in the same form as the models of the standard library: types, each with its question?
2. Does a space that composes the Organization model and the Game model stay readable by an agent that knows only the standard?

## Setting

A test space that declares `organization@0.1` and a sketched Game model. An agent that is given only `standard/` ([standard](../../standard/README.md)). The Game model is outside the standard library ([models](../../models/README.md)).

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after.

## Expected answer

For question 2: yes, the composed space stays readable by an agent that knows only the standard. For question 1: none. We record what happens.

## Measures

From [measures](../../standard/measures.md); and the [structure checks](../structure.md), run on the composed space.
