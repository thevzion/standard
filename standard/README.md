# The standard

Standard 0.1 · candidate

The standard is the doctrine and the structure: the same for everything. Models plug into it. Spaces are its instances.

Version `0.1`. Status: candidate, untested. Nothing here is a result yet; the [trials](../tests/README.md) decide.

## An organization, in one sentence

An organization is an intent made explicit enough that others, people or intelligences, can act on it, and kept alive by what they learn.

The standard writes it down without depending on any tool: tools live in the organization, not the other way round.

## The simple idea

**Your intent is the source. Intelligence runs it.**

| Software | Here |
|---|---|
| source code | what you want, decide and know, made explicit: the objects |
| the language and its types | the standard and its models: types, each one a question |
| compiling | the agent files what you say into typed objects; checks do the type checking |
| the processor | intelligence, any agent |
| electricity | compute: tokens |
| the running program | the work done, and what comes back from it |
| tests, assertions | checks (a question and its expected answer) and trials |
| a source map | the trace: what each object draws on |
| default behavior when the source says nothing | the generic |
| a view, a materialized view | a projection: a question asked of the sources, refreshed when they change |
| a pure function | a pure agent: it sees only its sources |
| `make` | regenerating the projections whose sources changed |
| a service, a scheduled job | a routine: a question asked alone, on a trigger, under a mandate |
| git | git |

Where the comparison stops:
- execution need not be deterministic, by choice: compute when it is enough, intelligence when something must be understood ([questions](questions.md));
- the executor fills gaps in the source, which a compiler never does: that is the inferred, and it is marked;
- the person writes the source and is also part of the execution: they decide, and they answer for it;
- the source is never finished: the loop rewrites it with what each turn teaches.

Why now: each time the executor grew more capable, the source moved closer to people (assembly, then higher-level languages, then declarative code such as SQL). Intelligence understands intent, so the source can be the intent itself: what you want, and why. Most organizations do not have this source. It lives in heads, chats and meetings.

## Levels

| Level | What it is | Contents |
|---|---|---|
| **0. Doctrine** (standard) | how intelligence behaves | make explicit, discern, link, commit rather than wait, mark the inferred, correct precisely |
| **1. Structure** (standard) | independent of any domain | objects, links, changes; URI, truth, access; adapters |
| **2. Models** | a pluggable, versioned library of types, each with its question | the standard library; Organization and Home, which include others; Game and seeds ([models](../models/README.md)) |
| **3. Spaces** | real spaces, each its own authority, each with its models | TheVZion, a home, a company |

- Content depends on the standard and the models, never the reverse.
- Organization is the first model and the default door, not the foundation. The center stays the person.
- A space is an instance of the standard and of the models it declares, as a database is an instance of a schema.

## The frontier

| | What | Why |
|---|---|---|
| **Required** | text any agent can follow: the standard, one model (Organization by default), the setup [prompt](../setup/prompt.md) and `llms.txt`, a folder or a Notion page | nothing else is needed to start |
| **Default** | git | it meets three conditions: the agent carries it fully, it is open and universal, it works without an account or a network. Installed once, with the person's consent. Where it cannot be installed, an append-only `changes.md` keeps the journal, without a seal |
| **Optional** | the toolchain (CLI, MCP server, sync, checks), a client's plugins | comfort. The MCP server comes before the plugin |

Three doors, one standard:
- an agent in a folder: copy the prompt;
- living in Notion: duplicate the template;
- to just talk: "Just talk".

## Files

| File | What it holds |
|---|---|
| [doctrine.md](doctrine.md) | level 0: the doctrine and its notes, the invariant, the gates |
| [structure.md](structure.md) | level 1: objects, links, changes; the meta-model; layout; header; recursion |
| [changes.md](changes.md) | the commit is the change: fields, operations, inbox, corrections |
| [trace.md](trace.md) | `read` and `draws on`: what an object comes from |
| [truth.md](truth.md) | the four roles: Source, Projection, Pointer, Inbox |
| [access.md](access.md) | read, propose, decide; exposure; federation and identity |
| [questions.md](questions.md) | everything is a question; the loop; routines; intelligence at several sizes |
| [measures.md](measures.md) | the dashboard, canonical measures, anchoring, balance and yield |
| [adapters.md](adapters.md) | tools as adapters; Notion local-first |

## Words

| Word | Meaning |
|---|---|
| **space** | the unit: a folder or a page with its `space.md`, its objects and their history |
| **standard** | the doctrine and the structure, the same for every space |
| **model** | a versioned set of types, with their views and checks (for example, the Goals model) |
| **type** | a question, a horizon, fields; defined by a model, or locally by a space |
| **object** | an explicit thing of one type that answers its question; one file or one page, one URI |
| **link** | a relation of a given kind between two objects (`serves`, answers, replaces, `draws on`) |
| **change** | an event on objects and links, with when, who, why and status; a commit |
| **trace** | what a change read (`read`) and what an object draws on (`draws on`) |
| **projection** | a copy or an answer generated from sources; regenerated, never edited |
| **site** | a link to another space |
| **organization of one** | an organization whose intent is that of a single human |
| **home** | a person's own space: the root of their tree, and the space of their organization of one |

## Prior art

No piece is new: the journal and the ledger come from Pacioli, history from git, events from event sourcing, URIs and federation from the web, objectives from OKRs, `AGENTS.md` from coding agents. The assembly is new, applied to what nobody writes yet: what we want, why, and how we will know, at every size.
