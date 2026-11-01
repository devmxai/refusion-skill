# The engine, as it is now

Written by `rpro skill-reference --write` from catalog version 2, fingerprint `dd84c704678e786c`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

| what | how many |
|---|---|
| tools offered to an agent | 175 (direct 22 · read 36 · edit 117; direct tools that also go in a batch: 1) |
| tools withheld from an agent, each with its reason | 57 |
| library: effect | 24 |
| library: look | 6 |
| library: transition | 20 |
| library: layer_motion | 29 |
| library: text_motion | 38 |
| recipes that were run and looked at | 30 |

## Where to look

| to find | read |
|---|---|
| a tool, by what it does | `tools.md` (grouped by family; a tool's full page is `guide.read` with `tool:<name>`) |
| an effect and its settings | `effects.md` |
| a ready-made chain of effects | `looks.md` |
| a transition | `transitions.md` |
| how a layer or a text comes in, goes out or loops | `motion.md` |
| a batch that was run and looked at | `recipes.md` |

## How an item is read

- **Use** of a tool: `call` is a tool you call by itself; `read` reads and changes nothing; `edit` is an edit that goes in a `session.batch` item; `call · edit` is both (a tool you call by itself that is also valid as a batch item).
- **Target** of a tool: what it names: a `layer`, a `scene` (a composition), `inside a scene` (a tool that works in the scene that holds its layer), or `-` (the project, a source, a key).
- A library item's **id** is what the engine calls it and never changes; its **Add** line is the tool that adds it.
- **cost** is `unmeasured` until a phone has measured it: it is not a promise of speed.

## The guide's pages

Read with `guide.read` (no topic lists them). They are the engine's own text for the build that answers.

- `workflow`: How to work on a project: read, check, apply, look, mend; and the rules that keep an edit safe.
- `time`: How a time is written, and how to place things in time.
- `layers`: The kinds of layer and the tools that make, place and arrange them.
- `units`: When a group of layers is a design unit (a scene), how to build one in one batch, where its motion lives, and what the engine says of a flat build.
- `animation`: Keyframes, property paths and how a value moves.
- `formulas`: A number that follows time, another layer, the size of a text or the beat: the language, how to bind, read, drag, cut and check one.
- `rhythm`: A scene's beat grid and markers, what a formula reads from them, and how to make things land on the beat.
- `text`: Text layers, fonts and captions.
- `paths`: Drawing a path layer node by node, and changing the parts of a vector layer (an icon, an imported drawing).
- `state`: Reading how the project stands: the engine's handshake and what it can do on this device, the history, the transport and the sound.
- `checks`: What the layout checks of `scene.layout` mean, and the numbers they use.
- `motion`: How to make a movement read as smooth in the file: speed, motion blur, easing, and what a video encoder keeps.
- `pool`: The designer's material: the pictures, sounds, drawings and clips in the project's library, how they are named and found, how to place them by name, and what to do when one is missing.
- `recipes`: Batches that were run and looked at: a follow banner, a title a line reveals, a magnifier icon, a lower third, a group moved by a null, a pulse on the beat, a card as big as its text, a wheel that follows a car, a parallax; read one with `recipes:<name>`.
- `recipes:<name>`: one recipe's batch, e.g. `recipes:follow-banner`.
- `tool:<name>`: one tool's parameters, its reasons for refusal and an example, e.g. `tool:session.batch`.

Start with `workflow`.

## Tools no page describes
You are offered these and no page above names them; `tool:<name>` gives each one's parameters.
- `library.catalog`: Read what the engine offers to add, as one list whatever the kind: the effects, the looks (ready-made chains of effects), the transitions, and the ready-made…
- `library.look`: Look at what the library's cards show: the engine draws a page of its effects (`kind` 1) or its transitions (`kind` 2) on one sheet, a JPEG for you to look at…
