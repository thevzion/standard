---
model: knowledge
version: 0.1
status: candidate
question: What do we know, and what do we keep?
includes: []
---
# The Knowledge model

> What do we know, and what do we keep?

## Types

| Type | Question | Horizon | Fields | Serves |
|---|---|---|---|---|
| `document` | What have we written down to keep? | not set | | optional: what it was written for |
| `material` | What did we collect that might serve later? | not set | kind: idea, observation | optional |
| `source` | Where does it come from, and when did we read it? | not set | where, when read | optional |
| `person` | Who do we know, and in what role? | not set | role | optional |
| `journal` | What happened, day by day? | not set | date | optional |
| `term` | What do we mean by our words? | not set | | optional |

Horizons are not set yet for these types, though the entry rule asks for one
([models](../README.md#when-a-type-enters-a-model)).

- A `person` is a contact, not a member. Members of a space (who reads, proposes, decides) belong to the structure, in `space.md` ([people-members-or-contacts](https://github.com/thevzion/source/blob/main/objects/questions/people-members-or-contacts.md)).
- An idea noticed in passing is a `material`; there is no Issues type ([issues-type-or-view](https://github.com/thevzion/source/blob/main/objects/questions/issues-type-or-view.md)).
- Resources in the sense of files belong here; means (money, time, attention) do not ([means-model](https://github.com/thevzion/source/blob/main/objects/questions/means-model.md)).

## Links

| Kind | Use here |
|---|---|
| `draws on` | an object or a projection points to the document or source it rests on (candidate) |
| `serves` | optional: a document points to what it was written for |
| contradicts | two sources, or a source and a claim, that disagree |

## Views

- What do our sources say about this, and where?
- What did we collect on this subject that might serve now?
- What happened this month?

## Checks

- Does every source say where it comes from and when it was read? Expected: yes.
- Is any `person` a member of the space? Expected: no.
- Does any document answer more than one question? Expected: no; a growing object often hides several.

## Measures

None of its own. Three structure measures read this model well: use (the objects others draw on,
and those read but never drawn on), context (the share of what was read that is drawn on) and size
([measures](../../standard/measures.md)).

## Routines

None from the routine table.
