---
trial: 9
status: not-run
level: end-to-end
tests: [objects/hypotheses/anyone-can-start-with-seven-types.md, objects/hypotheses/your-intent-is-the-source.md, objects/hypotheses/you-say-it-the-source-writes-itself.md]
---

# Trial 9: placement

This trial tests the [doctrine](../../standard/doctrine.md): discern before you write.

## Questions

1. Placement: in a new space with the Organization model, where do raw intents go?
2. Restraint: does any local type double an installed type?
3. Consistency: do two agents, or two sessions, file the same intents in the same types?
4. Migration: when a model that covers a local type is installed, what does the agent do?

## Setting

A new test space with the Organization model ([organization](../../models/organization/model.md)), ten raw intents written in advance, and two agents or two sessions.

## Fixed before the trial

| Criterion | What must hold |
|---|---|
| placement | of ten raw intents, at least eight go into types of the model; the others go into local types, each with its question, marked `local` and `inferred` |
| restraint | no local type doubles an installed type |
| consistency | two agents, or two sessions, file the same intents in the same types at least eight times out of ten |
| migration | when a model that covers a local type is installed, the agent proposes the migration, applies nothing before the person agrees, and the links still resolve |

## Expected answer

Each criterion above holds.

## Measures

From [measures](../../standard/measures.md): placement; and the `local-double` check of the [structure checks](../structure.md).

## What could break

Placement: everything rests on well-typed objects. If two agents file the same intent differently, the measures measure noise.
