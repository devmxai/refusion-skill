# Directions to start from

A direction makes type, colour, motion and transitions agree. Pick one, or name your own in two lines, before you choose a preset. These are starting points for judgement, not finished looks the owner has approved: build, look, and adjust. The ids are the engine's (see [choosing.md](choosing.md) and [engine/INDEX.md](../engine/INDEX.md)); numbers tagged as in [timing.md](timing.md).

## 1. Calm product interface

- **For:** a product tour, a feature walkthrough, an explainer for a service.
- **Type and colour:** one family, two weights; a calm ground, one accent used for the thing being explained; generous margins.
- **Motion:** unhurried, with a soft landing. Entrances 0.35 s to 0.6 s [start]; ease out for arrivals, ease in for leaves; little or no overshoot; stagger of a few frames; one slow ambient motion at most.
- **Means:** `layer.edge:recipe:4` (Rise in), `text.motion:1:4` (Rise), `text.motion:recipe:8` (Zoom in) for a title; `fx.effect:stylize.drop_shadow` to lift a card; `fx.effect:blur.gaussian_blur` on an adjustment layer for a glass behind text.
- **Transitions:** `transition:1` (Cross Dissolve) for continuity, `transition:20` (Slide Left) between steps of a flow.
- **Avoid:** bounce and spring on content, glitch, heavy grain, more than one accent.

## 2. Bold kinetic type

- **For:** a feed ad, a launch, a hook; the text is the picture.
- **Type and colour:** a heavy display face at a size that fills the frame (the hero text fills much of its width); two or three colours at most, one of them loud.
- **Motion:** fast hit, long settle, deliberate hold, hard release ([timing.md](timing.md): hit, settle, hold, release). Entrances 0.15 s to 0.5 s; the hold is the longest part; cuts on beats.
- **Means:** `text.motion:recipe:14` (Letters snap up from a blur), `text.motion:recipe:15` (Snap in leaning from the left), `text.motion:recipe:10` (Centre out), `text.motion:recipe:1` (Words pop); exits `text.motion:recipe:26` (Gather out to the left).
- **Transitions:** hard cuts on the beat, `transition:40` (Whip Left) at the hero moment.
- **Edge:** `fx.effect:stylize.chromatic_aberration` for a short hit; `fx.look:glitch_split` once, not throughout.
- **Avoid:** the same entrance for every line, a soft dissolve between loud scenes, glow on the text.

## 3. Editorial information

- **For:** news, a figure with context, a quote, a data point.
- **Type and colour:** a serif or a restrained sans, a strong typographic hierarchy, mostly neutral with one accent for the figure that matters.
- **Motion:** restrained; reveal by line or by a marker rather than by bounce. `recipes:line-title` reveals a title with a line; `recipes:highlighter` sweeps a marker over a word; `text.motion:recipe:11` (Track in) opens letter spacing.
- **Means:** `text.motion:1:1` (Fade), `text.motion:recipe:4` (Typewriter) for a short line only; the holds are long because the text is long.
- **Transitions:** `transition:2` (Film Dissolve), `transition:4` (Dip to Black) between sections.
- **Edge:** `fx.look:vintage_film` or `fx.effect:stylize.film_grain` lightly, if the subject asks for a period feel.
- **Avoid:** kinetic effects on body text, more than one highlight in view.

## 4. Geometric brand motion

- **For:** a logo, a brand sting, an icon sequence, a clean explainer built from shapes.
- **Type and colour:** the brand's; flat fills, hard edges, a grid.
- **Motion:** precise and rhythmic; shapes draw on, grow from a point, lock into place. Mechanical, not organic: `layer.edge:recipe:5` (Zoom in), `layer.edge:recipe:9` (Bounce in) for a single accent, `recipes:draw-on`, `recipes:magnifier`, `recipes:null-group` (a group moved by one null).
- **Transitions:** `transition:10` (Push Left), `transition:30` (Zoom In).
- **Edge:** `fx.effect:stylize.halftone` for a print edge on a flat colour.
- **Avoid:** randomness, loops that wobble, gradients on every shape.

## 5. Hand-made and organic

- **For:** a playful piece, a story, a poster that moves; a feel of cut paper or a hand-drawn boil.
- **Type and colour:** warm, textured, imperfect; a limited palette.
- **Motion:** stepped and slightly unsteady. `recipes:boil` and `recipes:cutout-boil` give the boil; the jitter loop (`layer.edge:3:16`) keeps an entrance smooth and then boils; living grounds with `recipes:evolving-field` or `recipes:colour-points`.
- **Looks:** `fx.look:newsprint`, `fx.look:comic_print`, `fx.look:liquid_wobble`.
- **Transitions:** `transition:12` (Push Up), a hard cut.
- **Avoid:** perfect alignment everywhere, a crisp digital ease on a hand-made element.

## Mixing

One direction per piece. A piece may borrow one move from another (a single chromatic hit in a calm interface piece), never its whole manner. When the brief names a mood the five do not cover, write your own two lines (type, colour, motion character, transitions) and keep to them.
