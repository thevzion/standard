# Setup prompt

Version 2. Candidate, untested: no run has used this version yet. Its open points are in [prompt-v2](../objects/questions/prompt-v2.md), and [trial 7](../tests/trials/07-reduced-tree.md) will test it.

Copy everything below the line and give it to an agent that works in a folder. The other ways to start are in [README.md](README.md).

---

Set up my space with the TheVZion standard, version 0.1, and the Organization model, version 0.1.

A space is what I want, written as small typed objects that people and agents can read and act on, where every change is kept with its reason. The standard is in `standard/` and the models are in `models/` of TheVZion's repository, linked from https://thevzion.com. Where this text and the standard differ, the standard wins.

## How you behave

```
Make it explicit.
1. Start from what the person wants, and find the question it answers.
2. Discern before you write: an existing object first, then a type from the
   installed models, then a local type you name by its question. Same for
   links. The person never has to name a type.
3. Say where each object and link comes from: its model and version, or
   local. Mark what you inferred.
4. Commit rather than ask or wait: a visible mistake is cheap to fix. Say
   briefly what you wrote; the person reviews when they choose.
5. Keep every change, with its reason. Correct precisely: reverse the one
   object or link that is wrong, and keep why. Nothing is rewritten.
6. Keep it small: one object per question. What won't serve again stays in
   the conversation.
7. Ask only when the answer changes what they want. Never decide what they
   want, and let nothing that reaches others rest on an inference.
```

In practice:

- Write, commit, then tell me. Ask for my approval only where a mistake cannot be corrected precisely, or reaches someone else: publishing, pushing, sending a message, making a commitment, spending money.
- Ask before reading my files, and read only what I allow: what you read goes to your AI provider.
- Never move or delete a file that has no history yet: that cannot be undone.

## 1. Ask where it should live

Your first question, and the only one before you start:

> Where should it live: a folder, your Notion, or both? If a folder, may I keep its history with git?

If both, each type has one source: ask which side is the source. The other side is a projection of it, never edited by hand.

## 2. Lay it out

In a folder:

```
<space>/
├─ space.md       the manifest: URI, standard version, models, truth, access, adapters
├─ objects/       the state: one file per object, typed by its model
│  ├─ problem.md  why.md  vision.md
│  ├─ goals/  projects/  tasks/  decisions/
│  ├─ sites/      links to other spaces
│  └─ types/      local types, each with its question
├─ spaces/        child spaces, with the same tree
├─ AGENTS.md      a projection of the doctrine and the space's mandates
├─ .git/          the changes: one commit per change
└─ .local/        specific to this machine, never committed
```

Create a folder when its first object arrives. Add `.local/` to `.gitignore`.

In Notion:

```
<Name>            the page is the space; its URL is its URI
├ Agents          a projection
├ Objects         a database: one page per object; a view per type, a Sites view
├ Changes         a database: one row per change; the "Proposed" view is the inbox
└ <Child space>   the same tree
```

Each page of Objects has the properties Type, Question, Serves, Source, Lifecycle, Evidence, Date.

## 3. Write space.md

For example:

```markdown
---
space: bike-workshop
uri: bike-workshop
standard: 0.1
models:
  - organization@0.1
adapters:
  - folder+git
---

# Bike workshop

## Truth

| Where | Role |
|---|---|
| this folder | Source |
| AGENTS.md | Projection |

## Access

| Verb | Who |
|---|---|
| read | me, my partner |
| propose | me, my partner, our agents |
| decide | me, my partner |
```

The URI comes from the path, or is the page URL in Notion. Access has three verbs: read, propose, decide. TheVZion's own `space.md` follows the same format.

## 4. Write the objects

Start from what I say. Find the question each thing answers, and write one object per question, in my words where you can.

Each object starts with a header:

```markdown
---
type: goal
model: goals@0.1
question: What do we want now, and how will we know?
serves: objects/vision.md
source: from-me
lifecycle: active
evidence: open
date: 2026-11-12
---

Repair fifty bikes a month by June. We will know when the logbook shows fifty for three months in a row.
```

| Field | What it holds |
|---|---|
| `type` | the type id: singular, lowercase |
| `model` | the model that defines the type, with its version, or `local` |
| `question` | the type's question, word for word |
| `serves` | the path of the object that justifies this one; a list if several. Only `problem` and `why` have none. |
| `draws-on` | optional, candidate: the objects this one relies on |
| `source` | `from-me` for my words or my decision; `inferred` for what you wrote, condensed, rephrased or guessed |
| `lifecycle` | `proposed`, `active`, `review`, `done` or `dropped` |
| `evidence` | how we know it holds: `by-construction`, `sourced`, `observed` (with a date), `hypothesis` or `open` |
| `date` | when it was written |

A space starts with seven types:

| Type | Model | File | Question |
|---|---|---|---|
| problem | `purpose@0.1` | `objects/problem.md` | What is wrong today, and for whom? |
| why | `purpose@0.1` | `objects/why.md` | Why do we exist? |
| vision | `purpose@0.1` | `objects/vision.md` | What does the world look like if we succeed? |
| goal | `goals@0.1` | `objects/goals/1.md` | What do we want now, and how will we know? |
| project | `work@0.1` | `objects/projects/<name>.md` | What are we building for it? |
| task | `work@0.1` | `objects/tasks/<name>.md` | What are we doing next? |
| decision | `loop@0.1` | `objects/decisions/<name>.md` | What did we choose, why, and who answers for it? |

The questions are quoted from the models; where a model's file says otherwise, the model wins.

To place something, in this order:

1. revise an existing object, or add a link to it;
2. otherwise, use a type from the installed models;
3. otherwise, use a local type already created;
4. otherwise, create a local type in `objects/types/<name>.md`, named by its question, with its horizon and its fields. Its objects say `model: local`. A local type must ask a question no installed type asks; otherwise it is a field, a link or a view.

Then:

- You may infer an object from what I said, and mark it `inferred`. You may not invent what I want: a goal I never stated is a question for me, not an object.
- The seven types do not all need an answer on the first day. When one is missing and it matters for what I am doing, ask its question, one at a time, Problem and Why first.
- A link to another space goes in `objects/sites/`: an address, no content. A child space goes in `spaces/<name>/`, with the same tree.

## 5. Keep every change

With git, one commit per change:

```
<object>(<operation>): <what changes>

Why: <the reason, one line>
Source: from-me | inferred
```

`<object>` is the type of the object that changes (`goal`, `decision`). For the manifest, it is `space`: the first commit is `space(add): set up the space`, with `space.md`, `AGENTS.md` and `.gitignore`.

| Operation | When |
|---|---|
| `add` | a new object |
| `revise` | its content changes |
| `remove` | it goes, and the change says why |
| `rename` | same object, new name |
| `split`, `merge` | one becomes two, two become one |
| `test` | a hypothesis is tried |
| `validate` | its status moves up |
| `reverse` | one object or link was wrong; it is undone, and why is kept |
| `restructure` | a type, a question or a kind of link changes |
| `migrate` | objects move to another type or model version: propose it, apply it after my yes |

- The objects keep the truth; the message helps you read them.
- A correction is a change: `reverse` or `revise` the one object or link that is wrong, and nothing else. Never rewrite history.
- Propose instead of committing to the main line when a change comes from someone else, is large (a migration), or commits other people: a branch or a pull request in git, a row in the "Proposed" view in Notion.
- Code and anything else built in the folder keep their own convention.

Without git (I said no, or your sandbox blocks it, in which case say so), keep `changes.md` at the root, append only. One entry per change:

```markdown
## 2026-11-12 goal(add): repair fifty bikes a month by June

Objects: objects/goals/1.md
Why: the first goal I named
Source: from-me
Who: me, with my agent
```

Never edit an earlier entry: a correction is a new entry. In Notion, each change is one row of the Changes database, with the same fields.

## 6. Write AGENTS.md

`AGENTS.md` is a projection: the doctrine above, what is specific to this space (its mandates: who may do what), where things are, and how to record a change. It tells the next agent how to read, update and record. Regenerate it when its sources change; do not edit it by hand.

## 7. Tell me what you wrote

After each turn, say in a few lines what you wrote: which objects, which of them are `inferred`, and any question only I can answer. I review when I choose. Ask only when the answer changes what I want, one question at a time.

## From version 1 to version 2

If this folder was set up with version 1 of this prompt:

| Version 1 | Version 2 |
|---|---|
| `organization.md` | `space.md` |
| `org/` | `objects/` |
| one file per type, plural (`org/goals.md`) | one file per object, singular type ids (`objects/goals/1.md`, `type: goal`) |
| `source: from me` | `source: from-me`; the header also gains `model`, `lifecycle`, `evidence` and `date` |
| `inbox/` | proposed changes: a branch, a pull request, a "Proposed" row |
| `sites.md` | `objects/sites/`, one link per file |
| `orgs/` | `spaces/` |
| a commit per change, with `Why:` | the same, with `Source:` too |

Propose the move as one `migrate` change, and apply it after my yes. The history stays whole.
