---
trial: 17
status: not-run
level: end-to-end
tests: [objects/hypotheses/every-object-knows-where-it-came-from.md]
---

# Trial 17: projection to PROV

## Questions

The trace of a test space is projected into PROV (JSON-LD) and into schema.org.

1. Does a tool that reads PROV read it back?
2. Does an agent that does not know the standard read it back?
3. What passes, and what is lost?

## Setting

A test space with its trace ([trace](../../standard/trace.md)), its projection into PROV and schema.org, one tool that reads PROV, and one agent that is not given the standard.

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after.

## Expected answer

None. We record what happens.

## Measures

What passes and what is lost, by field of the trace.
