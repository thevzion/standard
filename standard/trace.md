# The trace

Standard 0.1 · candidate

Context becomes links. Everything here is candidate; [trial 15](../tests/trials/15-trace.md) decides.

## What is missing

The structure makes explicit what is written: the object, its type, its links, the change and its why. What the agent had in front of it while writing stays implicit: it was in a conversation, and it is lost with it. The output is explicit; the input is not.

## What an agent's context holds, and what the trace keeps

| In the context | What the trace keeps | Already in the structure |
|---|---|---|
| the person's words | an intent object, `from-me`, served by the change | the intent type (Loop model), the `Intent:` trailer |
| the space objects it read | their URI, and the version read (the commit) | URIs, history |
| the model and type it used | `model@version`, in the header | the [object header](structure.md#the-object-header) |
| the doctrine it followed | the version of the projection read (`AGENTS.md`) | the [doctrine](doctrine.md) and its projections |
| what it read outside: a page, documentation | a Pointer: the address and the date | the Pointer role ([truth](truth.md)) |
| the conversation | nothing: the trace points, it does not copy; what counts in the person's words is already the intent | |

## Two links, and no new kind

The Change gains one relation, and the Link one kind.

| Link | Carried by | How it is obtained | Quality |
|---|---|---|---|
| **`read`**: what the agent read | the change, with the version read | **observed**: the agent's adapter records it from its tool calls (files opened, pages read) | complete and free, but noisy: an agent reads more than it uses |
| **`draws on`**: what the object rests on | the object, like `serves` | **declared** by the agent | precise, and fallible |

**The gap between the two is a signal.**
- Read without being drawn on: context that did not serve.
- Drawn on without being read: a source cited that the agent did not open. Check those first.

## Where it lives (candidate)

| Adapter | `read` |
|---|---|
| git | a note attached to the commit (`git notes`), which does not change the commit, or a `Read:` trailer |
| Notion | a "Read" relation from the Changes database to the Objects database |

Open: [where `read` lives](https://github.com/thevzion/source/blob/main/objects/questions/where-read-lives.md), [the unit of `draws on`](https://github.com/thevzion/source/blob/main/objects/questions/draws-on-unit.md).

## What it closes

- **The loop, on its input.** Each object knows where it comes from, and what comes from it. The chain of `serves` says why an object exists; the chain of `draws on` says what it is made of.
- **Anchoring, at birth.** A claim that draws on the intent is said; on a space object, anchored; on a Pointer, sourced. Only a claim that rests on nothing goes to the swap test ([measures](measures.md#anchoring)). The measure becomes a by-product of writing, and a declared `draws on` is checked against what was read.
- **Review.** The person reads what was inferred and, next to it, what it was inferred from. If the adapter also records what the person saw, what is left to review can be counted. Seen is not validated: silence is not a Match.
- **Correction, propagated.** When an object is revised or reversed, those that drew on its previous version are flagged stale, as a build system knows what to rebuild when a dependency changes. They are flagged, not rewritten: a signal, not a rule.
- **Context, learned.** For a kind of task, past `draws on` links say what to load next time. Context is built from the trace instead of being rewritten by hand in each tool (prompts, skills, memory). It lives in the space, and any agent picks it up ([trial 16](../tests/trials/16-learned-context.md)).
- **Continuity.** An agent that takes over reads the last changes, and what they had read ([trial 03](../tests/trials/03-resume-with-another-agent.md)).

## Why it costs almost nothing

The semantic web failed because humans had to write the links. Here, intelligence writes them. And `read` links are not even written: they are observed.

## Beyond the organization

The standard (levels 0 and 1) has no domain: Organization is the first model, not the foundation. The trace is at level 1. It holds for anything written with an agent: a document, code, a web page, a game. It could become a standard beyond the organization, implemented elsewhere, as a tag, even for websites ([question](https://github.com/thevzion/source/blob/main/objects/questions/trace-beyond-organization.md)).

### What already exists

The pieces exist, each in its own domain (checked on 2026-11-12).

| Domain | What exists | What it keeps | What it lacks, for us |
|---|---|---|---|
| linked data | PROV, from the W3C (2013) | who did what, from what: `used`, `wasDerivedFrom`, `wasAttributedTo` | use: it stayed niche, because humans wrote the provenance |
| web pages | schema.org in JSON-LD: `isBasedOn`, `citation` | a tag in the page: what the work is based on | what was inferred; the measure |
| media | C2PA, Content Credentials | a signed manifest in the file: actions, ingredients (including a generation's prompt), the AI share | text and objects; it covers what is produced, not what the agent read |
| software | SLSA, in-toto, SBOMs | the materials of a build, and what it produces | the why, and the intent |
| science | nanopublications | a claim, its provenance, its publication | the organization, and time |
| knowledge | Wikidata | each claim has references: source, address, date retrieved | what a person wants |
| sovereignty | Solid; the W3C Linked Web Storage group standardizes part of it, and its schedule slipped in 2026 | pods: one authority per person | meaning (types that ask a question), and time |
| agents | 2026 preprints (ContextNest) and vendor proposals | what an agent read, with a fingerprint | a ratified standard: we found none |
| law | Article 50 of the EU AI Act, applicable since 2026-08-02, and its voluntary code of practice of 2026-06-10 | generated content, marked in a machine-readable format | what comes from the person: the law marks the inferred, not the anchored |
| the ancestor | Vannevar Bush's Memex (1945) | trails: the sequence of what one consulted, kept and shareable | a machine to write them: that is the agent |

### What does not exist yet, to our knowledge

- the trace applied to intent: what a person wants, decides and knows, not only files, media or builds;
- input that is observed rather than declared: `read`, recorded by the adapter;
- the measure, anchoring, and a loop that learns from the trace;
- the assembly: one structure, from the person to the organization and the web.

No piece is new; the assembly is.

### Reuse the vocabularies, and project them (candidate)

The trace can already be said in existing vocabularies. The standard reuses them rather than inventing one, and each adapter projects them: PROV for linked data, schema.org for a page, C2PA for a media file.

| In the standard | PROV | schema.org | C2PA |
|---|---|---|---|
| a change | an activity (`Activity`) | | an action |
| `read` | `used` | | an ingredient, `inputTo` |
| `draws on` | `wasDerivedFrom` | `isBasedOn`, `citation` | an ingredient |
| `from-me` | `wasAttributedTo` a person | `author` | |
| `inferred` | `wasGeneratedBy` an agent's activity | to be found | `c2pa.ai-disclosure` |

These mappings are to verify against each specification ([trial 17](../tests/trials/17-projection-to-prov.md)).

### The tag, for a web page (hypothetical use)

A page declares what it draws on, in JSON-LD, as schema.org already allows:

```html
<script type="application/ld+json">
{ "@context": "https://schema.org", "@type": "Article",
  "isBasedOn": ["https://example.org/goals/2", "https://example.org/results/12"] }
</script>
```

What was inferred has no schema.org property yet: an extension, or C2PA for media. Both directions meet: the page writes its provenance, the agent that reads it picks it up, and its own trace keeps a Pointer to it.

### How a standard spreads

When the one who reads it rewards the one who writes it. schema.org took hold because search engines rewarded sites; C2PA advances through platforms and the law; SLSA through software supply chain security. Here the reader is the agent, and it rewards at once: the trace shortens its next context. The law adds a demand, marking what was generated, and the trace answers it more finely: what is said, anchored, sourced or inferred.

What it changes for the planned path: nothing. The person and the organization first; the web is one more adapter, and the tag a projection.
