---
model: home
version: 0.1
status: candidate
question: What do I want, what do I keep, and what can I now do?
includes: [organization@0.1, knowledge@0.1, capital@0.1]
---
# The Home model

> What do I want, what do I keep, and what can I now do?

A person's life. There is always a center: a person, where one wants and answers for it. The
organization of one is the person as an organization: one human who wants, as many agents as it
takes. The home is its space (`space.md`, `objects/`, the history), the root of the person's tree.

## Types

No types of its own. It takes those of the models it includes.

| Model | Types | Here |
|---|---|---|
| [Organization](../organization/model.md) | Purpose, Goals, Work, Loop, Agreements | what the person wants, and the work toward it |
| [Knowledge](../knowledge/model.md) | `document`, `material`, `source`, `person`, `journal`, `term` | what the person keeps |
| [Capital](../capital/model.md) | `capability` | what the person can now do; private |

### Children and sites

| Relation | What it is |
|---|---|
| child | what is the person's own: a folder in `spaces/`, a child page |
| site | what is shared: a pointer to another space, with its own centers. An organization the person joins is a site in their home, serving one of their goals. |

Containing is not pointing. The graph is a tree only seen from a person.

**Private by default, shared by pointer.** What an organization shares: aligned goals,
deliverables, decisions. What stays with the person: the home, their vision, their capital. "Your
work is shared, not you." ([access](../../standard/access.md))

## Links

Those of the included models. A person's goal can serve an organization's goal (`serves`),
across spaces: that is how organizations of one plug into larger ones.

## Views

- What changed, and what waits for me, across my spaces?
- Which of my goals does each site serve?
- The floors of my life (the Organization floors view, on the home).

## Checks

- Is the Capital model readable only by the person? Expected: yes.
- Does every site serve one of the person's goals? Expected: yes.
- Does any site expose something private? Expected: no.
- Plus the checks of each included model.

## Measures

Every measure of the [Organization](../organization/model.md) model, plus capital (private).
Exposure, a structure measure, says what leaves the home and toward whom
([measures](../../standard/measures.md)).

## Routines

| Routine | Question | When | What it may do |
|---|---|---|---|
| take stock | What changed, and what waits for the person? | every day or week | a projection to read |

And the other routines of the [Organization](../organization/model.md) model, each under its own
mandate, each active only if the person activates it.
