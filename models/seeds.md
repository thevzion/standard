# Game and seeds

Status: candidate, untested. Outside the [standard library](README.md).

## Game

Game describes the thing made, when it is a game. It is not part of the standard library: not
every space makes a game. A space that makes one takes the Organization model to make it, and the
Game model for the thing made. Neither owns the other: a game can be designed without an
organization, and an organization can exist without a game.

| Type | Question (proposed) |
|---|---|
| `premise` | What is the game about, in one sentence? |
| `core-loop` | What does the player do, again and again? |
| `mechanic` | Which rule turns a player's choice into a consequence? |
| `playtest` | What did we try with players, and what happened? |

"Core loop", so as not to clash with the [Loop](loop/model.md) model. The questions above are
proposed, not settled.

- **Game includes Loop** (candidate): a playtest is an experiment; its results are `result` objects of the Loop model. A model included twice, by Organization and by Game, is installed once ([model-included-twice](../objects/questions/model-included-twice.md)).
- **Links are the glue**: in a game's space, a mechanic serves a goal (Goals), a playtest produces a result (Loop), and a decision (Loop) revises the mechanic.
- **No inheritance**: a playtest does not extend a result; they link ([type-inheritance](../objects/questions/type-inheritance.md)).
- **A Studio model** could include Organization and Game, if a domain always wants the pair.

## Seeds

A seed is a model we won't write ourselves, published as an idea and open to contribution. Make it
explicit once, and everyone benefits. The library is a means; the goal is that the approach spreads
beyond us.

Seed ideas, nothing written yet:

- Recipe
- Trip
- Course
- Research
- Album
- Club
- Household

Seeds also come from use: when the same local type returns from one space to another, it is a seed,
then a model ([local types](README.md#local-types-and-links)).

## Propose one

Open an issue with the [type or model template](../.github/ISSUE_TEMPLATE/propose-a-type-or-model.md).
Give the model's question, its types each with a question and a horizon, and a space where it
serves. The entry rule applies ([models](README.md#when-a-type-enters-a-model)). The format of a
seed is open ([model-and-seed-format](../objects/questions/model-and-seed-format.md)).
