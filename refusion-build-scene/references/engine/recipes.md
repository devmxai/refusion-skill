# Recipes that were run

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `af18d4dc3cfd181b`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

Each is a batch that was run on a project and looked at before it was written. Read one with `guide.read` and the topic `recipes:<name>`; change its words and numbers, and look again.

| Recipe | What it makes |
|---|---|
| `recipes:follow-banner` | a pill with a dot and a line of text that grows in and fades out |
| `recipes:line-title` | a title a line reveals by sweeping right and hides by sweeping back, then a second title |
| `recipes:magnifier` | an icon of three shapes that draws itself, comes in with an overshoot and travels |
| `recipes:lower-third` | a name and a title beside a bar, in and out as one unit |
| `recipes:null-group` | shapes moved, turned and scaled together by a null inside a unit |
| `recipes:word-reveal` | words that rise and fade in one after the other, soft with motion blur |
| `recipes:typewriter` | letters typed one by one with a blinking caret |
| `recipes:letters-wave` | letters that go up and down in a travelling wave, for as long as the text is there |
| `recipes:pulse-colour` | words that swell one after the other and turn a colour at the peak |
| `recipes:letters-order` | letters that pop in from the end, or in a fixed shuffle |
| `recipes:slide-in-out` | a title that slides in from the left and out to the right |
| `recipes:highlighter` | a word of a sentence that a yellow marker sweeps over in half a second (`text.mark_progress` keyed on the span of its pill) |
| `recipes:painted-stroke` | a ring whose stroke is a conic gradient that turns round it (`stroke_paint.kind` 3, `stroke_paint.angle` keyed) |
| `recipes:evolving-field` | a background of evolving noise that loops exactly (`fill.kind` 8, `fill.field_phase` keyed from 0 to 1) |
| `recipes:colour-points` | a background of free colour points that twists and bends (`fill.kind` 7, `fill.points_swirl`, `fill.points_bend`) |
| `recipes:paint-drift` | stripes that drift inside a rectangle while its edges stay, by the paint mapping of the fill (`paint.offset`, `paint.extend`) |
| `recipes:draw-on` | a pen-drawn loop that is open (its end passes its start) and a curved arrow with an arrowhead on its end, each drawn on along its stroke by its trim, thinning at its ends and wavering as a hand |
| `recipes:boil` | a hand-drawn ring whose wavering edge takes a new shape eight times a second and holds it between, by the step of the layer that shows its scene (`time.step`) |
| `recipes:sentence-reveal` | a sentence of thirteen words that appears word by word in 1.6 s, on one text layer (`text.motion_set` with each word as the unit and a `span`) |
| `recipes:cutout-boil` | a shape (or a picture of the pool) that comes in smooth with the pop and then boils like a hand-made cut-out, by the jitter loop of the layer (`layer.motion_set` phase 3), whose hold steps the loop alone |
| `recipes:push-in` | a slow push-in on a shape or a picture: two keys on `transform.scale` with an ease in out, which is what a preset would be (a move no preset says is keys) |
| `recipes:halftone` | a picture, a gradient or any layer printed as dots, lines or crosses of one ink on paper, or as four inks at the angles of print, by the effect `stylize.halftone` |
| `recipes:looks` | a layer given a look: a ready-made chain of effects with its values (liquid wobble, newsprint, comic print, vintage film, glitch split, dream glow), by `effect.look` |
| `recipes:pulse-on-beat` | a shape that swells on every beat of the scene's grid and falls back before the next, by one formula on its scale (`beat`, `mod`, `pow`); change the tempo and it follows |
| `recipes:card-sized-to-text` | a card as wide and as high as the text on it, an English one and an Arabic one, by a formula on the card's size that measures the text (`measure(N)`); edit the text and the card follows |
| `recipes:wheel-follows-car` | a car that moves by two keys and two wheels that stay under it and turn as far as it has rolled, by formulas that read the car's position (`layer(N)`) |
| `recipes:parallax` | three ranges of a landscape that slide against a figure that crosses the scene, each by its own share of the figure's position (`layer(N)`) |
| `recipes:enter-on-beats` | three bars that grow in one after the other, one on each beat, by a formula on the beat (`ease(beat, ...)`) |
| `recipes:appear-from-marker` | a circle that pops in at a named marker of the scene and follows it when the marker is moved (`marker("hit")`, `scene_time`) |
| `recipes:pool-by-name` | three pictures the designer named («ميسي صغير», «ميسي أول مباراة», «ميسي كأس العالم») chosen from the library by their names and placed one after the other, one batch of `layer.insert_source` |
