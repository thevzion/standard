---
trial: 4
status: not-run
level: end-to-end
tests: []
---

# Trial 4: the Notion adapter

This trial runs the Notion trials N1 to N7 of a feasibility study not yet published. Their questions will be copied here when the study is published. Two questions frame them.

## Questions

1. Does Notion hold a space as the standard lays it out? The page is the space; an Objects database holds one page per object (Type, Question, Serves, Source, Lifecycle, Evidence, Date); a Changes database holds one row per change, and its "Proposed" view is the inbox; a child space is a child page of the same shape.
2. Where the Notion adapter cannot see the agent's tool calls, what is missing from `read`?

## Setting

A Notion test space, with the Organization model ([organization](../../models/organization/model.md)) and the adapter described in [adapters](../../standard/adapters.md).

## Fixed before the trial

The criteria of N1 to N7 are in the feasibility study, not published yet.

## Expected answer

None. We record what happens.

## Measures

From [measures](../../standard/measures.md); and the [structure checks](../structure.md), run on the Notion space.

## What could break

Read capture: where the adapter cannot see the agent's tool calls, `read` is missing. [Trial 15](15-trace.md) measures the same gap in a folder.
