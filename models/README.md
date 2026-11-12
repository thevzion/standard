# Models

Status: candidate, untested. Every model here is at version `0.1`.

## What a model is

A model is a set of types, each with its question and its horizon, plus views, checks and a
version. The structure knows none of them: it only knows that an object has a type, and that a
type asks a question ([structure](../standard/structure.md)).

| Property | What it means |
|---|---|
| **Not a template** | A template is copied, then drifts. A model is declared ("conforms to `organization@0.1`") and can evolve. A copy to duplicate (in Notion, for example) is called a template. |
| **Declared** | A space declares its models in [`space.md`](https://github.com/thevzion/source/blob/main/space.md), each with its version, next to the version of the standard. |
| **Composes** | A space takes the models it needs. A model can include others, like a package depends on packages. |
| **Serves alone** | Each model answers one family of questions and works without the others: a decision log without goals, tasks without a vision. |
| **Named in full** | Always "the Organization model", "a Game model". Never "model" alone, which also means an AI model. |

A project and the model it makes do not share a name: the game project makes the Game model, the
capital project makes the Capital model.

### Everything is a question

A model carries types, views and checks. All three are questions; so are measures and routines
([questions](../standard/questions.md)).

| | The question | Who answers | What comes out |
|---|---|---|---|
| **type** | what an object answers: "What do we want now?" | the person, with their agent, which marks what it inferred | an object: the source |
| **view** | what someone needs to know: "Where is goal 2?" | a computation, or a pure agent | a projection, regenerated when a source changes |
| **check** | what should be true: "Does every goal say how we'll know?" | a computation, or a decision model | yes or no, or a distribution |
| **measure** | how much: "What share was inferred?" | a computation | a number |
| **routine** | a question asked on its own, on a trigger, under a mandate | an agent | a change, with its trace |

Answer with the cheapest thing that suffices: a computation, then a decision model, then a writing
model, then the person. Checks signal; they never block. A check is a question with its expected
answer; a trial is a series of questions asked to a test space ([tests](../tests/README.md)).

## The standard library

The models that come with the standard, as a language's standard library comes with the language.
Other models plug in the same way. The name is a candidate
([standard-library-name](https://github.com/thevzion/source/blob/main/objects/questions/standard-library-name.md)).

| Model | Its question | Types |
|---|---|---|
| [Purpose](purpose/model.md) | Why, and toward what? | `problem`, `why`, `mission`, `principle`, `vision`, `philosophy` (optional) |
| [Goals](goals/model.md) | What do we want to make true, and how will we know? | `goal`, `strategy` |
| [Work](work/model.md) | What are we doing, and what comes out of it? | `project`, `schedule`, `task`, `deliverable` |
| [Loop](loop/model.md) | What was asked, chosen, observed, learned? | `intent`, `question`, `hypothesis`, `decision`, `result`, `learning` |
| [Knowledge](knowledge/model.md) | What do we know, and what do we keep? | `document`, `material`, `source`, `person`, `journal`, `term` |
| [Agreements](agreements/model.md) | Who may do what, and what have we promised? | `mandate`, `rule`, `commitment`, `skill`, `agent` |
| [Capital](capital/model.md) | What can the person do now that they couldn't before? | `capability` (private), and a reading of the loop |

These families were first found in a real workspace built by intuition, before any of this was
written down.

## Two assemblies

| Model | Includes | For |
|---|---|---|
| [Organization](organization/model.md) | Purpose, Goals, Work, Loop, Agreements; Knowledge if needed | the default door; any group that wants something, from one human to a company |
| [Home](home/model.md) | Organization, Knowledge, Capital | a person's life: the space of an organization of one |

## Outside the library

Game describes the thing made when it is a game; a space that makes one takes Organization to make
it and Game for the thing made. Seeds are models we won't write ourselves, published as ideas.
Both are in [seeds](seeds.md).

## Local types and links

When no installed type fits, the agent creates a **local type**, named by its question, without the
person naming it. Links follow the same rule: first the existing kinds (`serves`, answers,
replaces), else a local kind with its meaning (depends on, blocks, contradicts). "Contradicts" is
precious: the explicit makes contradictions detectable.

**Placement order**, reuse before creating:

1. revise an existing object, or add a link to it;
2. else a type from the installed models;
3. else a local type already created;
4. else a new local type;
5. and if the choice changes what the person wants, one question.

| Rule | What it says |
|---|---|
| **A local type is an object** | `objects/types/supplier.md` holds its question, horizon and fields. It is versioned and kept like the rest; the structure keeps its three sets. Where local types live is open ([where-local-types-live](https://github.com/thevzion/source/blob/main/objects/questions/where-local-types-live.md)). |
| **Restraint** | A local type must ask a question no installed type asks. Otherwise it is a field, a link or a view. Maximize reuse and clarity, not the number of objects. |
| **Desire paths** | Let people walk, then pave the paths they made. Within a space, local types emerge; across spaces, the same local type often returns: it becomes a seed, then a model. The library grows from use, not from our guesses. |
| **What is shared** | Only type definitions are shared, on agreement. Never objects. |

## Migrations

A migration is a change (`migrate`), proposed by the agent and accepted by the person, because it is
wide: from `local:supplier` to `work@0.4:vendor`, twelve objects, and why.

- History stays whole; the current state lives in the new model.
- Upgrading an installed model's version takes the same path ([model-version-migration](https://github.com/thevzion/source/blob/main/objects/questions/model-version-migration.md)).
- A migration is not always one to one: it can split or merge.
- It rewrites internal links in the same change. The old URI must stay resolvable ([uri-on-type-change](https://github.com/thevzion/source/blob/main/objects/questions/uri-on-type-change.md)).

## When a type enters a model

**Entry rule** (candidate): a type answers a question no other type asks, serves in several
spaces, and has a horizon. Otherwise it is a field of an existing type, or a view. A set of types
that speaks not of what we want but of a thing made is another model (Game, for example).

| Candidate | Question | Proposed verdict |
|---|---|---|
| Philosophy | How do we see things, beyond us? | optional type of Purpose, above the why |
| Term | What do we mean by our words? | type of Knowledge |
| Question | What are we still asking? | type of Loop, before hypotheses |
| Commitment | What have we promised, and to whom? | type of Agreements, needed between organizations |
| Mechanism | What turns what into what? | to test: a type, or a field of rules; close to skills |
| Capital | What can I do now that I couldn't before? | the Capital model, private |
| Manifesto | (none) | a view, not a type |
| Rituals | When do we look at each floor again? | a field of the schedule |
| Refusals | What do we refuse? | already a field of strategy |

No inheritance between types, to start: models include each other, objects link
([type-inheritance](https://github.com/thevzion/source/blob/main/objects/questions/type-inheritance.md)).

### Find what's still implicit

To find the next ones, ask of each sentence: "Which question does this answer?" A sentence with no
answer is noise, or a missing type. This is the candidate prompt "Find what's still implicit".

Between spaces, on agreement only, the emergence of local types and corrections by type, added up,
tell the library which questions are ambiguous and which models are missing
([measures](../standard/measures.md)).

## What remains to untangle (candidates)

| Item | The tension | Proposed reading | Open question |
|---|---|---|---|
| **People** | two senses | members of a space (who reads, proposes, decides; their keys) belong to the structure, in `space.md`; the people we know are `person` objects in Knowledge | [people-members-or-contacts](https://github.com/thevzion/source/blob/main/objects/questions/people-members-or-contacts.md) |
| **Issues** | not a type | what we noticed and have not filed yet. An idea is a `material`, a friction or bug is an observed `result`, a question is a `question`, a thing to do is a `task`. "To sort" becomes a view. | [issues-type-or-view](https://github.com/thevzion/source/blob/main/objects/questions/issues-type-or-view.md) |
| **Deliverable** | maybe a link | a project `delivers` an object of any model (a document, a publication, code). A spec is a document; it becomes a deliverable because a project delivers it. | [deliverable-type-or-link](https://github.com/thevzion/source/blob/main/objects/questions/deliverable-type-or-link.md) |
| **Resources** | two senses | files belong to Knowledge; means (money, time, attention) have no model yet. Candidate: a **Means** model, "What do we have, and what does it cost?", in the library or apart. | [means-model](https://github.com/thevzion/source/blob/main/objects/questions/means-model.md) |

## Open questions on models

- Where a model lives, and how a space references it: by URI and version, copied or read online ([where-a-model-lives](https://github.com/thevzion/source/blob/main/objects/questions/where-a-model-lives.md)).
- The format of a model, and of a seed ([model-and-seed-format](https://github.com/thevzion/source/blob/main/objects/questions/model-and-seed-format.md)).
- A model included twice, in different versions: which one wins ([model-included-twice](https://github.com/thevzion/source/blob/main/objects/questions/model-included-twice.md)).
