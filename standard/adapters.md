# Adapters

Standard 0.1 · candidate

Every tool is an adapter. All of them do the same operations:
1. read an object by its URI;
2. write it where its source is;
3. list;
4. give the history;
5. give the last change;
6. apply access.

Each one also says what it cannot do.

| Adapter | What it carries | What it cannot do |
|---|---|---|
| folder + git | objects, history, signatures, offline | fine-grained access control |
| Notion | objects, changes (the inbox included), sharing, phone | sign; keep the why natively; rate limits; 1,000 blocks for a free workspace with several members |
| GitHub | inbox (issues, discussions), access | per-object visibility |
| Discord | inbox | objects |
| Obsidian | a folder, so the same adapter as the first | sharing |

- **The agent talks to the organization, not to the tools**: it asks for `thevzion:goals/2`, and the adapter finds it.
- **AI models are adapters too**: the space declares the ones it uses, and the standard names none ([questions](questions.md#intelligence-at-several-sizes-candidate)).
- **The web is one more adapter**; a tag in a page is a projection ([trace](trace.md#beyond-the-organization)).
- Since history is append-only and authority is per type, a remote tool only needs to read the current state, write it, and give the time of the last change ([changes](changes.md#where-the-standard-departs-from-git)).

## The toolchain is optional

A CLI for people and an MCP server for agents host the adapters. They add comfort, never a requirement ([frontier](README.md#the-frontier)). See the [toolchain project](../objects/projects/toolchain.md).

## Notion, local-first

The agent writes local Markdown and commits, then pushes to Notion:
- objects go to the Objects database;
- each commit goes to the Changes database, one row per commit;
- properties flow both ways;
- page bodies flow one way until a round trip is proven;
- local Markdown stays within the common subset.

**Reconcile like git.** Notion is a remote branch:
- the merge base is the last pushed version, kept in git;
- a pull commits Notion's state on `notion/main`, then git merges;
- a conflict stops and asks;
- merge, never rebase.

The detailed feasibility notes are not published yet. Trial: [04](../tests/trials/04-notion-adapter.md).
