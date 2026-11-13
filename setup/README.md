# Start

Three doors, one standard. Each ends in the same thing: a space, written as typed objects, where every change keeps its reason.

| Door | When | What to do |
|---|---|---|
| A folder, with an agent | you work with an agent that can read and write files | copy [prompt.md](prompt.md) and give it to the agent |
| Notion | you live in Notion | duplicate the template: not public yet ([public-template-and-counting](https://github.com/thevzion/source/blob/main/objects/questions/public-template-and-counting.md)) |
| Just talk | you want to talk it through first | give any chat agent the instruction below, and say you just want to talk. It asks the questions of the seven starting types together, in one message, keeps your words, and gives you the result as one file. |

## The one instruction

For any agent that can read a web page:

```
Read https://thevzion.com/llms.txt and set up my organization. First ask me, in one message, everything you need to start: its name, where it should live, what I already have that you may look at, and what I want. Then start at once, and keep every change with its reason.
```

`llms.txt` is meant to become a projection of [prompt.md](prompt.md): generated from it, never edited by hand. Until then the two can differ, and `prompt.md` is the source.

## Required, default, optional

| | What | Why |
|---|---|---|
| Required | the [standard](../standard/README.md), one model ([the Organization model](../models/organization/model.md) by default), the prompt and `llms.txt`, and a folder or a Notion page | it is text that any agent can follow |
| Default | git, installed once with your consent; where it cannot be, an append-only `changes.md`, without a seal | the agent carries it entirely, it is open and universal, and it works without an account or a network |
| Optional | the toolchain (a command line, an MCP server, sync, checks) and the plugins of a client; an MCP server comes before a plugin | comfort |

Status: version 2.1 of the prompt, candidate, untested ([trial 7](../tests/trials/07-reduced-tree.md)). The live `llms.txt` keeps the version 2 opening until it is regenerated.
