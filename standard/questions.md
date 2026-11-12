# Questions

Standard 0.1 · candidate

## Everything is a question

One shape: a question, sources, an answer. A model carries types, views and checks ([structure](structure.md#the-meta-model-six-kinds)). They are all questions.

| | The question | Who answers | What comes out |
|---|---|---|---|
| **a type** | what an object answers: "What do we want?" | the person, with their agent, which marks the inferred | an object: the source |
| **a view** | what one needs to know: "Where is goal 2?" | compute, or a pure agent | a projection, regenerated when a source changes |
| **a check** | what must be true: "Does every goal say how we'll know?" | compute, or a decision model | yes or no, or a distribution |
| **a measure** | how much: "What share was inferred?" | compute | a number |

## The pure projection

The agent you talk to can write objects itself. When a request is clear and calls for a projection, it launches an agent without its context, a pure agent, which answers from the linked sources and the intent it is given. Objects can be noisy; this produces, from them, what a person reads. A document is a question, answered from the sources, their state and their links.

- **Pure**: it receives only the view's question, the sources the view links (at a version), the doctrine, and who the view is for. Nothing from the main agent's conversation. Its trace (`read`) must stay within its sources: any other read shows.
- **Anchored by construction**: it can only draw on its sources. Anything else it says is generic, and can be spotted.
- **When the sources do not say**, the answer is a question for the person, not a generic page.
- **Regenerated, never edited**: when a source it draws on changes, it is stale, like a materialized view to refresh. A correction goes back to the sources, or to the view's question ([truth](truth.md)).
- **Promoted, if decided**: part of a projection can become an object, marked `inferred`, with what it draws on.
- **For an audience**: a view for a partner reads only what is shared with them. This is also an exposure rule ([access](access.md)).

Open: [what a projection is](../objects/questions/projection-definition.md). Trial: [20](../tests/trials/20-pure-projection.md).

**The final loop.** Objects are made for precision and for machines; projections, for people. The person reads a projection, says what they want, it becomes objects, and the projections that drew on them become stale. Views recompose a narrative from small objects.

**A test is a question.** A check is a question with its expected answer: run it on the sources, and compare. A trial is a series of questions asked of a test space ([tests](../tests/README.md)).

**Deterministic or probabilistic, by choice.** Determinism still has its place. It dominated because nothing understood an intent; now each question chooses. Compute answers when it is enough (a measure, a check on the structure); intelligence when something must be understood. From cheapest to most expensive:

| Answerer | For |
|---|---|
| compute | measures, structural checks |
| a decision model | closed questions: a choice, a score, yes or no |
| a writing model | open questions: discern, write, link, explain |
| the person | what they want |

What intelligence returns is tested as a distribution.

Prior art: database views and materialized views, pure functions, `make`, documentation generated from code, test assertions. What is specific here: the answer is written by an intelligence, from typed sources, and the trace says what it draws on.

## The loop

```
Intent → Questions → Objects → Intelligence → Deliverable → Check → Decision → Result
  ↑                                                                              │
  └── Returns: Learning (revises what is above) · Resources (files) · Capital (the person)
```

| Step | What happens |
|---|---|
| Intent | an intent in human words, even a fifteen-second voice note |
| Questions → Objects | one question per type makes it explicit |
| Intelligence | it reads the chain of `serves` and acts under a mandate |
| Deliverable → Check | what comes out, compared with "how we'll know" |
| Decision | who chooses, who answers, who is concerned, and why |
| Result | what happened, dated |
| Returns | what the turn leaves |

- **To compound** is when a turn's returns make the next one cheaper or better: fewer follow-ups, less human time, more reuse. It is measurable, and it is a hypothesis ([it compounds](../objects/hypotheses/it-compounds.md), [trial 02](../tests/trials/02-two-turns-reuse.md)).
- **The loop closes on its input** (candidate): each change keeps what the agent read, and each object what it draws on. What one turn drew on becomes the next turn's context ([trace](trace.md)).
- **The human loop**: want, say, (do), see, choose, learn. Only the first cannot be delegated: wanting, and answering for it. Saying, seeing, choosing and learning are shared: intelligence does them too (it discerns, chooses within its mandate, learns from corrections), and the person does them when they want. "Intelligence can. Only people want, and answer for it."

Open: [who owns the loop](../objects/questions/who-owns-the-loop.md).

### The loop in one view (candidate)

1. **You say** what you want, in your words: by voice, in a few lines, when you want.
2. **Your agent places it**: it discerns, types, links and marks what it inferred. The source writes itself.
3. **The system answers** from the source: views, checks, measures, through compute, a decision model or a pure agent.
4. **You read and decide**: projections, what was inferred, and the questions the sources cannot answer. What you want next goes back to step 1.

**The source writes itself.** The person only gives the intent; the agent writes the source, and the person corrects when they choose. They remain the author of what they want. This already works in part in existing systems built by intuition, without this standard: a person speaks in intents, and an agent writes into databases and repositories. Not yet reliably: that is what the trials measure.

### What compounds

The more you give the system, the more it serves. Everything human that enters it comes from the person; even if it does not serve right away, it is an asset for later. Three precisions:
- **a possible asset becomes real when an answer draws on it**: the trace says so (`draws on`), and the use measure counts it. An object nothing reads is asleep;
- **an asset is one only if it is filed**: a catch-all page that receives everything serves badly. Placement turns an input into an asset;
- **what changes replaces**: an intent that contradicts an older one replaces it (`replaces`), and is not added to it. And the more assets there are, the more there is to protect ([access](access.md)).

### Voice: yield at the input

Dictating brings intent in much faster than typing: people speak roughly three times faster than they type, and the keyboard becomes the limiting factor. But voice gives more, denser and more scattered; it pays only if something discerns behind it. Without structure, dictation makes pages grow; with it, it makes objects ([trial 21](../tests/trials/21-voice.md)).

Further out, an interface that reads thought would meet two limits already in the standard: it is the extreme of exposure, and saying is the gesture that turns a thought into an intent. A thought read is an intent only once the person says it is what they want.

## Routines: the loop that runs alone (candidate)

**The inversion.** A program runs without being spoken to: a service, a scheduled job. With an agent, until now, nothing runs until the person wakes it: they pull. With the source, an intent lasts: a goal with "how we'll know" stays true until it is reached or replaced. The loop can run against it with no new request, like a controller that brings the real state back toward the wanted state. What is executable runs.

**A routine is a question, asked alone**: a question asked of the sources on a trigger (a time, a change, an event), with a mandate on what it may do with the answer. Like views and checks, it is defined in a model or in a space; no kind is added to the meta-model. What it does is a change, with its trace.

| Routine | The question | When | What it may do |
|---|---|---|---|
| **file** | "What arrived and is not filed yet?" | at each intent | place it, marked `inferred` |
| **advance** | "Which goal has no next step?" | daily | propose or write the next task, and do it if the mandate allows |
| **check** | "Does this change break a check?" | at each change | flag it, like continuous integration |
| **refresh** | "Which projection draws on a source that changed?" | at each change | regenerate it |
| **watch** | "Does the work still serve this goal?" | weekly | ask the person |
| **take stock** | "What changed, and what is waiting for the person?" | daily or weekly | a projection to read |
| **learn** | "What did the last turns teach?" | when a turn closes | propose a learning, or a change to the system |

What stays true:
- **defining is not activating**: a written routine runs only if the person activates it, since they commit the compute and let it act without them;
- **one mandate per routine**: what it does alone (write objects marked `inferred`, regenerate, flag), what it proposes (what comes from elsewhere, what is large, what engages other people), and what it never does (spend, send outside, decide in the person's place). These are the doctrine's [gates](doctrine.md#gates), nothing more;
- **it moves things forward, the person wants**: a routine can fill in tasks, goals and projects, and surface new things; a goal it proposes stays proposed until the person wants it. "Intelligence can. Only people want.";
- **a budget, and the trace**: each routine has a measured cost (the balance), and what it does is reviewed like the rest, inferred first;
- **it stops with one gesture**, and watch applies to it too: a routine that drifts is flagged.

**A library of routines**, like the library of models: a few canonical routines any space can take, and those each space writes. What local routines have in common across spaces says which ones the library lacks, as with local types.

Prior art: scheduled jobs (cron), controllers that reconcile a wanted state (Kubernetes), continuous integration, the scheduled agents of current tools. What is specific here: the routine starts from a lasting intent written in the source, and acts under a written mandate, with a trace.

Open: [routine mandates](../objects/questions/routine-mandates.md), [watch settings](../objects/questions/watch-settings.md). Trials: [22](../tests/trials/22-watch.md), [23](../tests/trials/23-routine.md).

## Intelligence at several sizes (candidate)

Objects are atomic, so a task can be broken down to its minimum. A large AI model is not needed everywhere: a fast one can validate, refuse or categorize, quickly or in bulk. Mixing both can make the whole more reliable.

Two kinds of AI model, named by role, never by product:
- **a writing model**: it discerns, splits an intent, chooses a type, writes an object, links, explains;
- **a decision model**: it does not write; it returns a typed answer (a choice, a score, yes or no) and its probability. Such AI models exist as of 2026.

**Why the structure suits it.** A type asks a question. When the answer is closed, the question is a decision: a decision model can answer it, and its probability says when to hand over.

| Task | Its answer | Who |
|---|---|---|
| discern an intent, split it, choose a new type | text, objects | a writing model |
| file into an installed type | a choice among types | a decision model, then a writing model if the probability is low |
| label a claim: said, anchored, sourced, generic | a choice | a decision model |
| the swap test | yes or no | a decision model |
| check a change against a model's checks | yes or no, and which one fails | a decision model, like continuous integration |
| flag stale objects, in bulk | yes or no, per object | a decision model |
| the fit of an intent | Match, Partial, Miss, Unknown | a decision model, then the person |
| adversarial review | objections | a large AI model, without the history |

What stays true:
- **no AI model decides in the person's place**: a decision model answers closed questions about objects, like a check; what the person wants stays theirs;
- **the probability is a signal**: below a threshold, the task goes to a writing model, then to the person; the threshold is set from measures, not in advance ([question](../objects/questions/decision-model-threshold.md));
- **each AI model is an adapter**: the space declares those it uses, and the standard names none ([adapters](adapters.md)).

**Routing, learned from the trace.** The trace already says who wrote each change (`Co-Authored-By` names the AI model). With the measures (accuracy, cost, time) per AI model and per task, one sees which size is enough for what, and routing follows, like learned context. AI model cascades already exist (FrugalGPT, 2023); what is specific here is atomic, typed tasks, and a trace that measures each choice.
