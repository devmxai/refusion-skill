# The engine, as it is now

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `9aa4256683fb9560`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

| what | how many |
|---|---|
| tools offered to an agent | 110 (direct 27 · read 48 · edit 35; direct tools that also go in a batch: 0) |
| tools withheld from an agent, each with its reason | 279 |
| library: effect | 16 |
| library: look | 5 |
| library: transition | 24 |
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
| the project as one document, to read and write a scene whole, and what it carries | `document.md` (its examples: the skill's project files `examples/*.rfp`) |

## How an item is read

- **Use** of a tool: `call` is a tool you call by itself; `read` reads and changes nothing; `edit` is an edit that goes in a `session.batch` item; `call · edit` is both (a tool you call by itself that is also valid as a batch item).
- **Target** of a tool: what it names: a `layer`, a `scene` (a composition), `inside a scene` (a tool that works in the scene that holds its layer), or `-` (the project, a source, a key).
- A library item's **id** is what the engine calls it and never changes; its **Add** line is the tool that adds it.
- **cost** is `unmeasured` until a phone has measured it: it is not a promise of speed.

## The guide's pages

Read with `guide.read` (no topic lists them). They are the engine's own text for the build that answers.

- `workflow`: The loop of the work; building by description; looking and measuring; the rules that keep an edit safe.
- `kinds`: Every value a layer of each kind the document makes has: its path, its kind of value, its range or every name a choice takes, its default; read from the engine's own schemas.
- `document`: The project's document: in the project's folder on a desktop, the file `project.rfp` you write by hand; through the connector, read with `project.file_read` and written with `project.file_write`; its form, its names, and what it carries.
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
- `craft`: The craft of the Refusion skill as this engine carries it: direction, timing, choreography, checks, styles, Arabic and text, grading, templates and recipes; `craft:<page>` reads one.
- `templates`: A scene made a template: its controls (text, font, switch, picture, colour, number), an instance's own values, its sections, and taking an instance apart.
- `recipes`: Batches that were run and looked at: a follow banner, a title a line reveals, a magnifier icon, a lower third, a group moved by a null, a pulse on the beat, a card as big as its text, a wheel that follows a car, a parallax; read one with `recipes:<name>`.
- `recipes:<name>`: one recipe's batch, e.g. `recipes:follow-banner`.
- `tool:<name>`: one tool's parameters, its reasons for refusal and an example, e.g. `tool:session.batch`.

Start with `workflow`.

## Tools no page describes
You are offered these and no page above names them; `tool:<name>` gives each one's parameters.
- `grade.paste`: Give a layer (the target: a layer's id, or `"selection"` for the layer the owner has selected), or with `every` each layer of the composition that takes a…
- `grade.curve`: Read a curve of the grade of a layer (the target) at the edit head: `curve` 0 Luma (the lightness, the colour kept), 1 red, 2 green, 3 blue, 4 Hue vs Hue, 5…
- `grade.balance_auto`: Balance a layer's picture by itself (the target): the parts of its frame of least colour among its midtones (the layer alone, with its grade, without its look…
- `grade.match`: Bring a layer (the target) near another (`reference`, a layer's id), shot in other light: the engine measures both frames (each alone, with its grade, without…
- `grade.inputs`: Read the curves a layer's clip (the target: a video, a picture or an adjustment layer) may have been shot with, as the grade's first stage reads them: 0 as the…
- `grade.input_set`: Read a layer's clip (the target) by the curve it was shot with (`curve`, a code `grade.inputs` lists; 0 as the file says): the grade's first stage turns the…
- `grade.selection_window`: Give selection `slot` (1 to 4) of a layer's grade (the target) a window, a part of the picture it holds: `shape` 1 a circle, 2 a rectangle, 0 none (it holds…
- `scope.read`: Read the picture at the edit head as a colourist reads the scopes: the project drawn as a file is drawn, counted by the scopes' own kernels on the GPU, and the…
- `slot.list`: Read every media slot of the project (its own composition and its scenes), so an agent or a person knows what a template asks for and what is still empty, as…
- `library.look`: Look at what the library's cards show: the engine draws a page of its effects (`kind` 1), its transitions (`kind` 2), its kinds of background (`kind` 3) or its…
- `morph.analyze`: Read what `morph.to` would make of a shape layer (the target: a layer's id, or `"selection"`) and an outline: a kind with its numbers, or another shape layer's…
- `addon.inspect`: Read an add-on's package and check it as `addon.install` would, installing nothing: the package whole (its framing, every entry's hash, its end record: a…
- `addon.install`: Install the add-on `addon.inspect` kept: its package is kept in the app's folder of add-ons as it was read, and what it brings is offered with the built-ins…
- `addon.list`: Read the add-ons held that are not built in, as parallel lists: each one's kind, id, version, fingerprint, name, maker, licence, where it is from (`installed`…
- `project.design_table`: Read how the open project's files are built, as numbers (REFUSION_PLAN WI-2.6): the design table of `project.rfp` and every `scenes/<name>.rfs`, or of the one…
