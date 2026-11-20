# Easing: the shape of a move

One speed from end to end is a machine's move. A move that is made starts, travels and lands, and its shape is chosen by its role. Tags as in [timing.md](timing.md).

## Where the shape is set

[engine] A move between two keyframes has a segment, and the segment has a shape. In the project's document (the file `project.rfp`, written in the folder or with `project.file_write`) the shape is the `ease` written on the key that starts the segment, one language for every key:

- `linear` (or none) and `hold`;
- a curve by its name, by the role the move plays (the industry's names, as CSS, GSAP and After Effects use them): an arrival `out_expo`, `out_quart`, `out_cubic` (quick to start, soft to land), `out_back` (lands a little past and comes back); a leaving `in_expo`, `in_cubic`, `in_back` (draws back first); a move across the frame `in_out_cubic`, `in_out_quart`, `in_out_expo`; and `smooth`, `whip`, `brake`, the others the engine's [document page](../engine/document.md) lists (an earlier name, such as `expo` or `settle`, is still read, and the reply names it now);
- a spring by its two numbers, `spring(bounce 0.2, visual 0.5)`: `bounce` how much it comes back past (0 none, up to 0.9), `visual` the share of the segment its bulk takes; also `spring_in` and `spring_in_out`. A spring whose bulk is too long for its segment is refused: shorten `visual`. (An older `spring(0.6)` is read as its two numbers.)
- a bounce or an elastic band with its liveliness from 0.05 to 1: `bounce(0.45)`, `elastic(0.5)`, each also `_in` and `_in_out` (`bounce_in_out(0.5)`);
- `cubic-bezier(x1, y1, x2, y2)`, as CSS writes it.

One segment of a layer that is there is changed by its address: `{"refusion": "patch", "set": {"@title.transform.scale.ease": "spring(bounce 0.2, visual 0.5)"}}`. The curve editor's handles (a key's speed and reach on each side, the After Effects model) are the owner's; in the file a segment's shape is its `ease` (a `cubic-bezier` for any curve), and a speed the file cannot say is counted (`speed_on_still_segment`).

[engine] A preset's channels (a phase's `channels` in the file) take their own travel and settle curves: a curve id of the motion functions, or four Bézier handles. The engine has these two vocabularies today; one ease language for both is planned (the agent plan, AB12).

## Which shape for which role

| Role | Shape | Tag |
|---|---|---|
| A word or an object that hits and settles | a strong ease out: most of the way at once, a long tail, `cubic-bezier(0.16, 1, 0.3, 1)` | [start] |
| An interface element, calm | ease in and out, `cubic-bezier(0.4, 0, 0.2, 1)` | [start] |
| Something leaving into a cut | ease in: it gathers speed and is gone | [start] |
| Something with weight that overshoots a little | back out, or a soft spring | [start] |
| A steady mechanical motion (a ticker, a turning wheel, a loop) | linear, on purpose | [start] |
| A value that jumps (a counter's digit, a stepped move) | hold | [engine] |

- **Set the shape in the description**, on the segment that starts at the keyframe: in a batch, `key_from` names the keyframe an earlier item made.
- **Linear by default is the most common lazy default** ([lazy-defaults.md](lazy-defaults.md)). [engine] The reply of an edit says how many of the keyed segments it wrote are linear (the note `linear_share`); [measured] in one agent's build 10 of 26 segments were.
- **Look at the shape, do not trust the name.** [engine] `motion.trace` draws the speed: an eased move is a bell between two keys, a linear one a flat line, a hit a tall early peak with a long fall.
