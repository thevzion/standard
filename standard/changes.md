# Changes

Standard 0.1 · candidate

The third set of the [structure](structure.md): the events. Temporal, append-only. ([decision](https://github.com/thevzion/source/blob/main/objects/decisions/the-commit-is-the-change.md))

## The commit is the change

The Changes set is the standard's abstraction; each adapter stores it its own way.

| Where | A change is | Journal and seal |
|---|---|---|
| a folder with git | a commit | git is the journal and the seal: the hash chain and signatures prove it was not rewritten |
| Notion | a row of the Changes database | the commit fingerprint, as a property |
| a folder without git | an entry of `changes.md` | an append-only file keeps the journal, without a seal |

A `changes/` folder next to the commits doubles the work, and the two can diverge. There is none.

## Fields

Every field of a change already exists in git, except two, which become trailers (`Why:`, `Source:`). Two more are candidates (`Intent:`, `Read:`).

| Field | In git | In Notion (Changes database) |
|---|---|---|
| when | the commit date | the date |
| who | the author; `Co-Authored-By` when an agent wrote | the author |
| which objects | the files of the diff | a relation to pages of the Objects database |
| which operation | the subject: `<object>(<operation>): ...` | the operation |
| why | the `Why:` trailer | the why |
| said or inferred | the `Source: from-me` or `Source: inferred` trailer | the source |
| status | main branch: accepted; a branch or a pull request: proposed; not merged: refused | the status |
| an object's history | `git log --follow -- objects/goals/2.md` | the rows linked to the page |
| the seal | the hash chain, signatures | the commit fingerprint, a property |
| the intent served (candidate) | the `Intent:` trailer | a relation to the Intents database |
| what the agent read (candidate) | a git note, or a `Read:` trailer: the URIs and the version read | a "Read" relation to the Objects database |

Open: [commit trailers](https://github.com/thevzion/source/blob/main/objects/questions/commit-trailers.md), [the `Intent:` trailer](https://github.com/thevzion/source/blob/main/objects/questions/intent-trailer.md), [where `read` lives](https://github.com/thevzion/source/blob/main/objects/questions/where-read-lives.md).

## Convention

```
<object>(<operation>): <what changes>

Why: <the reason, one line>
Source: from-me | inferred
```

Example:

```
goal(revise): turn goal 2 into an outcome

Why: a deliverable was posing as a goal
Source: inferred
```

Operations: `add`, `revise`, `remove`, `rename`, `split`, `merge`, `test`, `validate`, `reverse`, `restructure`, `migrate` (see [local types and migrations](structure.md#local-types-and-local-links)), and, candidate, `redact`.

## Accepted by default

- **An agent's change is accepted by default**: it is committed, and marked `inferred` when the agent inferred. Better committed and engaged than nothing, silent, or waiting.
- **The inbox is the set of proposed changes**, like a pull request: what comes from elsewhere, what is large (a migration), and what engages other people. Nothing limits its size; its count and the age of its proposals are measured (waiting, in [measures](measures.md)).
- **Proposals from elsewhere** (an issue, a message, a Notion row) stay in their adapter until the agent processes them: it turns them into a commit, or a branch if they are large.

Where the line between accepted and proposed falls, beyond these three cases, is open ([question](https://github.com/thevzion/source/blob/main/objects/questions/accepted-or-proposed.md)).

## A correction is a change that teaches

A correction is precise and carries its why: `reverse` or `revise` on the wrong object or link, and nothing else. It teaches three parties:

| Who learns | What |
|---|---|
| the agent | how the person means it |
| the person | how their words were understood |
| the standard | a correction that keeps returning on a type shows an ambiguous model question; everywhere, a line of doctrine to revisit |

## Result is not Change

A **result** is a fact of the world ("What happened?"), an object of the [Loop model](../models/loop/model.md). A **change** is a fact about the organization's file.

## Double entry

The Changes are the journal; the Objects are the ledger. The state is the ledger, and it can be rebuilt from the journal.

## Where the standard departs from git

| git | The standard |
|---|---|
| history can be rewritten | history is append-only |
| lines are compared | objects are compared, field by field |
| a message can be empty | every change has an author and a why |
| anyone with access changes anything | one source and one authority per type; elsewhere, it is a proposal |
| a conflict is resolved without a trace | a conflict is settled by a decision, which becomes an object |

A remote tool therefore only needs to read the current state, write it, and give the time of the last change.

**The exception: `redact`** (candidate). It erases the past for two cases only: a secret committed by mistake, or personal data. The content is purged; the event stays ("redacted, why"). Always by decision, rare, and subject to authorization. It is the condition of the right to erasure.

## Without git

Where git cannot be installed, `changes.md` at the space root holds the journal: append-only, one entry per change, with the same fields as a commit (date, author, subject line, `Why:`, `Source:`). It has no seal.
