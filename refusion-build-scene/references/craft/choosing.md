# Choosing: from what you want to the engine's item

Look here for which item fits the job, then read its numbers in the index. The ids are the engine's and never change; the index ([engine/INDEX.md](../engine/INDEX.md)) says what each does today, and `library.catalog` (with `query`, `kind`, `layer`) is the live list for the build that answers. The choice of *when* is the judgement of this page; the *what it does* is the engine's.

Every id below is applied the same way: `inspector.add` with `item=library` and `kind` the id (`text.motion:1:1`, `layer.edge:recipe:4`, `fx.effect:blur.gaussian_blur`). It is also a batch item: name the layer with `target` or `target_from`. A motion is applied whole and takes the place of what its phase held; the reply's `replaced` names that, and `history.undo` brings it back. The motion remembers its item: `text.motion` and `layer.motion` give `phase_origin` for each phase ("Rise", or "Rise — modified" once a number was changed), and `library.restore` (`item` is text.motion for the words or layer.edge for the layer, and `phase`) puts it back as it was applied. Inside a batch a caption's motion is over every sentence of the layer, never the sentences the owner chose on the device.

## Coming in

| You want | Text (`inspector.add item=text.motion`) | Layer (`inspector.add item=layer.edge`) |
|---|---|---|
| Quiet and clean | `text.motion:1:1` Fade · `text.motion:1:4` Rise | `layer.edge:1:1` Fade · `layer.edge:recipe:4` Rise in |
| From a side, with direction | `text.motion:recipe:5` Slide in from the left · `text.motion:recipe:6` right | `layer.edge:recipe:1` left · `layer.edge:recipe:2` right |
| A drop | `text.motion:recipe:7` Drop in | `layer.edge:recipe:3` Drop in |
| Growing in | `text.motion:recipe:8` Zoom in · `text.motion:1:2` Pop | `layer.edge:recipe:5` Zoom in · `layer.edge:1:2` Pop |
| Fast and decisive (an ad) | `text.motion:recipe:14` Letters snap up from a blur · `text.motion:recipe:15` Snap in leaning from the left | `layer.edge:recipe:7` Snap in from the left · `layer.edge:recipe:8` right |
| Playful, springy (one accent) | `text.motion:recipe:16` Words bounce in | `layer.edge:recipe:9` Bounce in |
| Word by word | `text.motion:recipe:1` Words pop · `text.motion:recipe:10` Centre out | |
| Letter by letter | `text.motion:recipe:2` Letters rise · `text.motion:recipe:3` Letters fade · `text.motion:recipe:13` Letters rise from a blur | |
| Typed | `text.motion:recipe:4` Typewriter (short lines) | |
| Letter spacing opens | `text.motion:recipe:11` Track in | |
| Turning | `text.motion:recipe:9` Spin in | `layer.edge:recipe:6` Spin in |

## Going out

| You want | Text | Layer |
|---|---|---|
| Gone softly | `text.motion:2:1` Fade | `layer.edge:2:1` Fade |
| Out to a side | `text.motion:recipe:23` left · `text.motion:recipe:24` right | `layer.edge:recipe:21` left · `layer.edge:recipe:22` right |
| Gathering speed away (a release before a cut) | `text.motion:recipe:26` Gather out to the left | `layer.edge:recipe:26` Gather out to the left |
| Dropping, shrinking, turning away | `text.motion:2:2` Pop · `text.motion:recipe:25` Zoom out | `layer.edge:recipe:23` Drop out · `layer.edge:recipe:24` Zoom out · `layer.edge:recipe:25` Spin out |

## Alive while it stays

One per scene ([choreography.md](choreography.md)). Text: `text.motion:3:11` Wave, `text.motion:3:12` Wiggle, `text.motion:3:13` Pulse, `text.motion:3:14` Sway, `text.motion:3:15` Flicker, `text.motion:3:16` Jitter. Layer: `layer.edge:3:11` to `layer.edge:3:16`, the same six. A pulse that follows the music is a formula, not a loop: `recipes:pulse-on-beat`.

## Between scenes

| The cut should say | Use |
|---|---|
| It continues | `transition:1` Cross Dissolve · `transition:2` Film Dissolve (no dip of brightness) |
| A breath, then a new part | `transition:4` Dip to Black · `transition:5` Dip to White |
| The same surface moves | `transition:10` Push · `transition:20` Slide (each with its `direction`: left, right, up, down) |
| Closer, or further | `transition:30` Zoom In · `transition:31` Zoom Out |
| A turn | `transition:32` Spin |
| Energy, a camera swing | `transition:40` Whip (with its `direction`) |
| A flash of light | `transition:107` Flash · `transition:109` Light Leak (warm) · `transition:3` Additive Dissolve |
| Before and after, steps, a list | `transition:100` Wipe · `transition:103` Blinds · `transition:102` Clock Wipe |
| Into a detail, out of one | `transition:101` Iris · `transition:104` Shape Reveal (centre it on the subject) |
| Dreamy, soft | `transition:108` Blur Dissolve · `transition:105` Luma Fade · `transition:111` Swirl · `transition:112` Ripple |
| Digital, broken | `transition:110` Glitch · `transition:106` Noise Dissolve |
| Wake up | A hard cut: no transition, on a beat |

A transition is added to a cut between two layers with `transition.add`. See [choreography.md](choreography.md) for matching it to the motion that leaves.

None fits and the owner wants one of their own: [designing-a-transition.md](designing-a-transition.md).

## Looking at a picture or a layer

| You want | Use |
|---|---|
| A first grade: lift a dark shot, give a flat one punch | the layer's grade: `grade.exposure`, `grade.contrast`, the four tones ([grading.md](grading.md)) · `fx.effect:color.curves` · `fx.effect:color.levels` |
| Warmer or cooler | the layer's grade: `grade.temperature`, `grade.tint` ([grading.md](grading.md)) |
| Stronger or weaker colour | `fx.effect:color.hue_saturation` · `fx.effect:color.tint` · `fx.effect:color.black_white` |
| Soften, or a blur-in | `fx.effect:blur.gaussian_blur` (animate its radius) |
| Speed or focus | `fx.effect:blur.directional_blur` · `fx.effect:blur.zoom_blur` · `fx.effect:blur.spin_blur` |
| Lift a card off the ground | `fx.effect:stylize.drop_shadow` |
| Glow | `fx.effect:stylize.glow` (look at it: it hides faults and makes text soft) |
| Frame the eye | `fx.effect:stylize.vignette` |
| Texture or age | `fx.effect:stylize.film_grain` · `fx.look:vintage_film` |
| A hit of digital damage | `fx.effect:stylize.chromatic_aberration` · `fx.look:glitch_split` |
| Print, comic, newspaper | `fx.effect:stylize.halftone` · `fx.look:newsprint` · `fx.look:comic_print` |
| Wobble, liquid, heat | `fx.effect:stylize.wave_warp` · `fx.effect:stylize.turbulent_displace` · `fx.look:liquid_wobble` |
| Pixelation | `fx.effect:stylize.mosaic` |
| A dreamy bloom | `fx.look:dream_glow` |
| Tiled repeats | `fx.effect:stylize.motion_tile` |

Read `effect.catalog` for an effect's `suits` (the kinds of layer it is advised for) and `cost` before adding it, and `library.look` to see it drawn on a reference picture. An effect that this device cannot draw is refused with its reason. Every effect has a Mix, and it can be limited to a place with a mask in Region mode (`guide.read` topic `animation`).

## Backgrounds that live

`recipes:evolving-field` (a looping noise, cells, waves or rays), `recipes:colour-points` (free colour points that twist), `recipes:paint-drift` (stripes that drift inside a shape). A flat black ground reads as "nothing loaded".

## Building blocks that were run

The 30 recipes in [engine/recipes.md](../engine/recipes.md) are batches that were run and looked at: a follow banner (`recipes:follow-banner`), a lower third (`recipes:lower-third`), a title a line reveals (`recipes:line-title`), a card as wide as its text (`recipes:card-sized-to-text`), a parallax (`recipes:parallax`), a highlighter (`recipes:highlighter`) and the rest. Start from the one nearest the job and change its words and numbers.
