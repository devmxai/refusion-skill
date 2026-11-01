# Checks: look, measure, judge, mend

A tool's success is not a picture, and a clean check is not a verdict on taste. After every batch that changes how something looks or moves, look at it with the engine's own eyes and read the numbers beside the picture.

## What to look at

| Moment | Why | With |
|---|---|---|
| The first frame | The still must already be designed; a piece that starts empty or off-centre has lost its first impression. | `render.look` |
| The fastest moment of each move | Blur, ghosting, a word torn from its line show here. | `render.look` at the time `motion.trace` names as the peak |
| The middle of each transition | Both pictures are on screen; this is where a mismatch of position or colour shows. | `render.look` |
| The frame where it lands | A landing that jumps or overshoots wrongly. | `render.strip` over the landing |
| The busiest moment | Overlap, clutter, text on a busy area. | `render.look` |
| The last frame | It should rest on purpose. | `render.look` |

`render.look` draws up to twelve times as one sheet, each tile marked with its time. `render.strip` draws every frame of a window as a lossless sheet, and can show a region of the canvas at its own pixels. `render.frame` is the exact picture when a pixel matters. Look at the picture; the numbers in a reply do not replace it.

## What to measure

- **`scene.survey`** counts the habits of the whole piece without drawing it: when each layer of content arrives and leaves, by what preset and on which curve, from which side, whether its start falls on the beat; the seconds between arriving and leaving (and for a text, its words and the seconds a starting-point rule says they need); which arrivals share an instant; how many curve shapes are in use and the share of the commonest; the shortest, middle and longest arrival; the first move, the end of the last move and the rest at the end. Read it after the first build and again after a fix. It judges nothing: a count says where to look with `render.look` and `motion.trace`, and a piece with a flat count can still be right (a calm piece may use one curve on purpose). It does not read what a formula adds, the layers inside a scene (ask with the scene as the target), captions, or how anything looks; its `not_measured` says so.
- **`motion.trace`** gives a layer's values, speed and acceleration per frame with a speed graph. An ease is a bell between two keys. Read it for: a stop in the middle of a travel (the speed returns to zero at a key), a landing that jumps (a spike at the end), a move that begins at full speed with no pace you intended, a long tail nobody can see. With `explain` it separates what each source gives every frame (the keys, the entrance, the exit, the loop, a formula) and says where a motion holds still and what holds it; read that before you change a number. A layer of a scene is read in the scene's own time and canvas.
- **`scene.layout`** checks the frame at a time: a layer outside the canvas, two texts over each other by the lines they ink, a text too small to read, text in the unsafe margins, and `crowded_main_timeline` (group those layers into a scene). Ask it at each of the times above.
- **`render.cost`** draws each frame of a window and says what it cost, stage by stage, with the frames that run over a frame's length. It names what it leaves out (the GPU's own timer, the display). Ask it for a scene that carries blur, many layers or several effects, and say so when the result is `unmeasured` on this device.
- **A reference to match:** `media.strip` reads a reference video's frames; `render.compare` sets your build beside it with a map of the difference.

## A critique pass before you report

Score the piece yourself on five questions, each with the evidence of a frame (which element, which time), not a feeling. A seven is "strong", not "acceptable"; if everything scores high, you are not looking.

1. **One direction.** Do type, colour, motion character and transitions all say the same thing?
2. **Hierarchy.** Can a viewer tell what is read first, second, third? Does the first mover deserve to be first?
3. **Detail.** Alignment, margins, line spacing, a landing, a hold, an ending.
4. **It does its job.** Is the text readable for as long as it needs to be, in its language, at the size it is seen? Does the piece say the one thing?
5. **One memorable move**, or honestly none (for a utility piece, none is right).

Then write two short lists: what to **keep**, and what to **fix**, ordered by how much the piece gains for the effort. Fix the first two and look again.

## Smells and their causes

| What you see | Usual cause | Fix |
|---|---|---|
| A word stops, then starts again | An ease in and out on each short segment, so the speed returns to zero at each key | Keep the speed through the key (`guide.read` topic `motion`); fewer keys |
| The landing jumps | The last key lands off the end value, or two sources both write the property | `motion.trace` with `explain`; remove one source |
| A fast move looks like separate copies | A long fast move drawn sharp | Motion blur on, or a slower move (`guide.read` topic `motion`) |
| The lean or the blur is still there when the word stops | They resolve on the wrong clock | Resolve them with the brake: `motion.channel_set` on lean and blur ([timing.md](timing.md)) |
| Everything arrives as a block | No stagger, no order | Order by importance; a delay between units; overlap |
| The text is gone before it can be read | The hold is the leftover | Give it its reading time ([timing.md](timing.md)); cut words |
| A pulse that is late or early against the music | Hand-typed times | A formula on `beat`, or a length in beats |
| The title is soft or has a halo | A glow or a look hiding the layout | Fix type and layout first; take the look off and look again |
| The owner cannot edit it | A layer per word, a flat build | Units as scenes; one text layer per sentence |

## What to tell the owner

In a sentence or two and in their words and language: what is on the timeline now, what to look at, and anything you could not do or could not check (the device, the cost, what a tool refused). Say only what a reply confirmed; if a tool was refused or did nothing, say that. The owner judges taste; you report evidence.
