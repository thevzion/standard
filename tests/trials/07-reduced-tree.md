---
trial: 7
status: not-run
level: end-to-end
tests: [https://github.com/thevzion/source/blob/main/objects/hypotheses/the-prompt-works-with-any-agent.md]
---

# Trial 7: the reduced tree

## Questions

1. Given [the setup prompt](../../setup/prompt.md), does an agent write the reduced tree: `space.md`, `objects/`, `objects/types/`, `objects/sites/`, `spaces/`, `AGENTS.md` as a projection, and `.local/` never committed?
2. Is every commit a change, with a subject `<object>(<operation>): …` and the trailers `Why:` and `Source:`?
3. Can each object's history be read with `git log --follow -- <path>`?
4. Does the Changes database in Notion receive one row per commit?

## Setting

- A new folder, and agents from at least two providers, each given the setup prompt.
- Without git, `changes.md` takes the place of the commits for questions 2 and 3.
- A Notion test space for question 4.

## Fixed before the trial

Not fixed yet. They are written here before the first run, and not changed after.

## Expected answer

Yes to each question. These are the properties the reduced tree claims ([structure](../../standard/structure.md), [changes](../../standard/changes.md)).

## Measures

From [measures](../../standard/measures.md); and the [structure checks](../structure.md), run on each space.

## Before this trial

Version 1 of the setup prompt was tried on 2026-11-11 with a fictional person. Agents from two providers wrote the same files. One provider's sandbox blocked git, and no rule said how to name a change that touches no object. Version 2 answers both: `changes.md` when git is blocked, and `space(<operation>)` for the setup files. Neither answer has run. Open: [prompt-v2](https://github.com/thevzion/source/blob/main/objects/questions/prompt-v2.md), [commit-trailers](https://github.com/thevzion/source/blob/main/objects/questions/commit-trailers.md).
