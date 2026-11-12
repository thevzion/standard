# Structure

Standard 0.1 · candidate

Level 1 of the standard: independent of any domain. Four words, on three sets.

| Word | What it is |
|---|---|
| **Object** | an explicit thing, of one type, that answers a question |
| **URI** | its stable address |
| **Truth** | where it lives: local or remote, once, with a role ([truth](truth.md)) |
| **Access** | who reads it, who proposes, who decides ([access](access.md)) |

A space is the unit: a folder or a page, with its `space.md`. An organization is a space that follows the Organization model, the most common case. Structure rules written for the organization hold for any space.

## The closest parallel: the web

| Web | Here |
|---|---|
| a resource | an object |
| a URI | a URI |
| a representation (HTML, JSON) | a projection (a file, a Notion page, a site) |
| each server is the authority on its resources | each organization is the authority on its objects |
| links | links: `serves`, replaces, sites |
| a shared vocabulary (schema.org) | a model |
| GET, POST | read, propose, decide |
| the browser | the agent |
| the W3C | TheVZion, which holds the protocol, not the network |

What it adds to the web: **meaning** (types that each ask a question), **time** (a loop, and changes that carry a why) and **the human** (who wants, who answers, and what stays with the person).

## Three sets

| Set | What it is | Rule |
|---|---|---|
| **Objects** | the state: what is true now | one object per URI |
| **Links** | relations between objects: `serves` (what justifies it), answers, replaces, points to another space | a link is carried by the object that declares it |
| **Changes** | the events: what happened to objects | temporal and append-only; each change says when, who, which objects, which operation, why, and its status: proposed, accepted, refused |

- State is derived from accepted changes: history can be replayed.
- A change is never rewritten: another change reverses it, with its why.
- Measures are computed from objects and changes; the doctrine tells intelligence how to write them.

Changes in detail: [changes.md](changes.md).

## The meta-model: six kinds

Everything else is an instance of one of them: Organization and Game are models, TheVZion is a space, "goal 2" is an object.

| Kind | What it is | Its relations |
|---|---|---|
| **Space** | `space.md`, a URI, an authority, its members and its adapters | declares models with their version; contains child spaces; points to other spaces (sites); holds objects; defines its local types |
| **Model** | a set of types, with their views, checks and a version | includes other models; defines types |
| **Type** | a question, a horizon, fields | defined by a model, or locally by a space |
| **Object** | an explicit thing with a URI; a file or a page | typed by a type; carries its provenance (model and version, or local; said or inferred) |
| **Link** | a relation of a given kind: `serves`, answers, replaces, `delivers`, contradicts, `draws on` (candidate), or a local kind | joins two objects, including across spaces |
| **Change** | an event: when, who, why, source, status; a commit or a row of the Changes database | touches objects and links; serves an intent; read objects at a version (`read`, candidate) |

**Organization and Game are models, not levels.** The Organization model includes others; the Game model describes the thing made. Neither owns the other: a game can be designed without an organization, and an organization can run without a game.

- **Compose rather than own.** A model includes others, as a package depends on packages, and a space declares the ones it takes. If a domain always wants the pair, a Studio model can include Organization and Game.
- **Links are the glue.** In a game's space, a mechanic (Game) serves a goal (Goals), a playtest (Game) produces a result (Loop), and a decision (Loop) revises the mechanic.
- **Game includes Loop** (candidate): a playtest is an experiment, and its results are Loop results. A model included twice, by Organization and by Game, is installed once ([question](../objects/questions/model-included-twice.md)).
- **No inheritance between types**, to start. A type does not extend another; models include each other, and objects link to each other. A measure may later show it is needed ([question](../objects/questions/type-inheritance.md)).

## Local types and local links

When no installed type fits, the agent creates a **local type**, named by its question, without the person naming it. Links follow the same rule: existing kinds first (`serves`, answers, replaces), otherwise a local kind with its meaning (depends on, blocks, contradicts). "Contradicts" is precious: explicit content makes contradictions detectable.

Placement order:
1. revise an existing object, or add a link to it;
2. a type from the installed models;
3. a local type already created;
4. a new local type;
5. if the choice changes what the person wants, one question.

- **A local type is an object**: `objects/types/supplier.md` carries its question, horizon and fields, versioned like the rest.
- **Restraint**: a local type must ask a question no installed type asks. Otherwise it is a field, a link or a view. The aim is reuse and clarity, not the number of objects.
- **Desire paths**: let people walk, then pave the paths they made. Local types emerge within a space; the same local type often returns across spaces: it becomes a seed, then a model. Only type definitions are shared, on agreement, never objects.
- **Migrations**: a large change (`migrate`), proposed by the agent and accepted by the person, for example from `local:supplier` to `work@0.2:vendor`, twelve objects, and the why. History stays whole. Upgrading an installed model follows the same path. A migration can split or merge, and rewrites internal links in the same change. The old URI must stay resolvable ([question](../objects/questions/uri-on-type-change.md)).

Detail on models, seeds and local types: [models](../models/README.md), [seeds](../models/seeds.md), [where local types live](../objects/questions/where-local-types-live.md).

## Layout: one object, one file, one page

What can change status or be cited alone has its own file and its own page.

| Nature | Folder | Notion |
|---|---|---|
| a single object (the vision) | a file: `vision.md` | a page, a row of type Vision |
| a set (the projects) | a folder, one file per item | a view of the Objects database, one page per item |
| a child space | a folder with the same tree, in `spaces/` | a child page with the same shape |

The reduced tree: a manifest, the two sets, and nothing else ([trial 07](../tests/trials/07-reduced-tree.md)).

```
<space>/
├─ space.md              the manifest: URI, standard version, models, truth, access, adapters
├─ objects/              the state, one file per object, typed by its model
│  ├─ problem.md  why.md  vision.md ...
│  ├─ goals/  projects/  tasks/  decisions/ ...
│  ├─ sites/             links to other spaces
│  └─ types/             local types, each with its question
├─ spaces/               child spaces, same tree
├─ AGENTS.md             a projection of the doctrine and the mandates
├─ .git/                 the changes: one commit per change, sealed
└─ .local/               machine-specific, never committed
```

```
<Name>                   the page is the space (URI, standard, models); its URL is the URI
├ Agents                 a projection
├ Objects                a database: one page per object; one view per type, a Sites view
├ Changes                a database: one row per commit; the "Proposed" view is the inbox
└ <Child space>          same tree
```

- `space.md` maps to the space page; an object file to a page of the Objects database (Type, Question, Serves, Source, Lifecycle, Evidence, Date); a commit to a row of the Changes database. For each type, one side is the Source and the other a Projection.
- The URI is derived from the path, or is the Notion page URL. The folder is the index; nothing is kept by hand.
- `space.md` declares the root URI, the standard version, the models and their versions, truth, access and adapters.
- The local path of a URI lives in a machine-specific map, outside commits.

## The object header

Each object file starts with a header. A link also carries its provenance.

```yaml
---
type: hypothesis                 # singular type id, lowercase
model: loop@0.1                  # the model and version that define the type, or `local`
question: What do we think is true, and how will we know?   # the type's question, verbatim
serves: objects/goals/1.md       # what justifies it; a list if several
draws-on: [standard/measures.md] # optional (candidate): what it rests on
source: inferred                 # from-me | inferred
lifecycle: active                # proposed | active | review | done | dropped
evidence: hypothesis             # by-construction | sourced | observed | hypothesis | open
date: 2026-11-12
---
```

An adapter may add its sync identifiers.

## Two status axes

| Axis | Values |
|---|---|
| **lifecycle** | `proposed`, `active`, `review`, `done`, `dropped` |
| **evidence** | `by-construction`, `sourced`, `observed` (dated), `hypothesis`, `open` |

## Recursion

- **There is always a center: a person**, where someone wants and answers. Their home is their life: an organization of one, the root of their tree.
- **A project becomes a space** when it has its own why and goals, measured differently. It keeps a `serves` link to its parent, and often takes one more model (the Game model for a game). The tree is the chain of `serves`.
- **Containing is not pointing.** What is yours is a child (a folder in `spaces/`, a child page). What is shared is a site: a pointer to a space with its own centers. The graph is a tree only when seen from one person.
- **Same shape at any size**: a person alone, without a legal form; a team or an association; a company and the organizations of its employees. "Same structure, any size. And they connect."

| Seen from | TheVZion is |
|---|---|
| its own `space.md` | the root of its space, with the Organization model |
| the home of a member | a site: a shared organization that serves one of their goals |

### Organization of one

An organization of one is an organization whose intent is that of a single human. The term stays in English, like "organization". ([decision](../objects/decisions/organization-of-one.md))

- **"One" counts those who want, not those who work.** An organization of one is not alone: agents act in it as much as needed, but one human wants and answers for it. The [invariant](doctrine.md#the-invariant) defines it.
- **"Human" rather than "person"**: a company is also a person, in law. "Human" removes the ambiguity.
- **You become one**: a person becomes an organization of one when their intent is explicit enough to be acted on. "Everyone can be an organization now", not "everyone is".

The organization of one is the person as an organization; their home is its space (`space.md`, `objects/`, the history).

"One human who wants. As many agents as it takes."

"Company of One" (Paul Jarvis, 2019) and the one-person billion-dollar company talk about the size and revenue of a business. This is not a business: it is a structure, that of what one human wants, and it connects to others.

### The network, by wills

An organization is made of organizations of one, plugged into it by `serves` links: a person's goal serves a goal of the organization. Each will passes through the system and can feed a larger one. Nothing is taken from the person; what is shared is shared by pointer ("Your work is shared, not you."). Each person has more reach alone, so an organization whose members are organizations of one gains as much. Organizations link to each other (sites), and organizations of one link directly to each other too. The same structure, at every size, up to the scale of the planet.
