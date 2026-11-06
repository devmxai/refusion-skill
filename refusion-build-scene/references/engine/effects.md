# Effects

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `48c2b3aacfa1e059`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

An effect is added to a layer with `effect.add`, or with `inspector.add` and the item `fx.effect`. Its settings are properties of the layer, keyed like any other (`fx.<kind>.<setting>[<id>]`), and every effect has a `mix`.

24 items. Read one with its id in `library.catalog`; `library.look` draws a page of them.

| Item | Id | Category |
|---|---|---|
| Exposure / Contrast | `fx.effect:color.exposure_contrast` | Color |
| Gaussian Blur | `fx.effect:blur.gaussian_blur` | Blur |
| Hue / Saturation | `fx.effect:color.hue_saturation` | Color |
| Temperature / Tint | `fx.effect:color.temperature_tint` | Color |
| Levels | `fx.effect:color.levels` | Color |
| Black & White | `fx.effect:color.black_white` | Color |
| Invert | `fx.effect:color.invert` | Color |
| Curves | `fx.effect:color.curves` | Color |
| Directional Blur | `fx.effect:blur.directional_blur` | Blur |
| Zoom Blur | `fx.effect:blur.zoom_blur` | Blur |
| Spin Blur | `fx.effect:blur.spin_blur` | Blur |
| Motion Tile | `fx.effect:stylize.motion_tile` | Stylize |
| Drop Shadow | `fx.effect:stylize.drop_shadow` | Stylize |
| Glow | `fx.effect:stylize.glow` | Stylize |
| Vignette | `fx.effect:stylize.vignette` | Stylize |
| Posterize | `fx.effect:color.posterize` | Color |
| Mosaic | `fx.effect:stylize.mosaic` | Stylize |
| Chromatic Aberration | `fx.effect:stylize.chromatic_aberration` | Stylize |
| Tint | `fx.effect:color.tint` | Color |
| Film Grain | `fx.effect:stylize.film_grain` | Stylize |
| Sharpen | `fx.effect:stylize.sharpen` | Stylize |
| Turbulent Displace | `fx.effect:stylize.turbulent_displace` | Stylize |
| Wave Warp | `fx.effect:stylize.wave_warp` | Stylize |
| Halftone | `fx.effect:stylize.halftone` | Stylize |

## Color

### Exposure / Contrast — `fx.effect:color.exposure_contrast`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Brightens or darkens the picture in stops, and stretches or flattens its contrast about the middle grey.

**Use:** The first grade of any picture or clip: rescue a dark shot, give a flat one punch. Animate the exposure for a flash or a fade to dark.

**Found by:** exposure, contrast, brightness, brighten, darken, grade, تعريض, تباين, سطوع, إضاءة, تفتيح, تغميق, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.exposure_contrast`

- `exposure` (number, stops): -5 to 5, default 0
- `contrast` (number, percent): -100 to 100, default 0
- `mix` (number, percent): 0 to 100, default 100

## Blur

### Gaussian Blur — `fx.effect:blur.gaussian_blur`

Blur · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Softens the picture evenly, in light, along either or both axes.

**Use:** Out-of-focus backgrounds, a soft glass behind a text (on an adjustment layer), a blur-in by animating the radius. The picture's edge grows by about three times the radius.

**Found by:** blur, gaussian, soften, defocus, focus, تمويه, ضبابية, غاوسي, نعومة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:blur.gaussian_blur`

- `radius` (number, pixels): 0 to 250, default 0
- `horizontal` (number, percent): 0 to 100, default 100
- `vertical` (number, percent): 0 to 100, default 100
- `mix` (number, percent): 0 to 100, default 100

## Color

### Hue / Saturation — `fx.effect:color.hue_saturation`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Turns the hue about the grey axis and shifts the saturation and the lightness.

**Use:** Recolour a graphic, mute a loud picture, push the colour for a poster look.

**Found by:** hue, saturation, colour, color, vibrance, تشبع, لون, صبغة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.hue_saturation`

- `hue` (number, degrees): -180 to 180, default 0
- `saturation` (number, percent): -100 to 100, default 0
- `lightness` (number, percent): -100 to 100, default 0
- `mix` (number, percent): 0 to 100, default 100

### Temperature / Tint — `fx.effect:color.temperature_tint`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

White balance: a warmer or cooler picture, a greener or more magenta one.

**Use:** Match two clips, warm up a sunset, cool a night scene.

**Found by:** temperature, tint, white balance, warm, cool, حرارة, دفء, برودة, توازن الأبيض, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.temperature_tint`

- `temperature` (number, percent): -100 to 100, default 0
- `tint` (number, percent): -100 to 100, default 0
- `mix` (number, percent): 0 to 100, default 100

### Levels — `fx.effect:color.levels`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Sets the black and white points, a gamma between them, and the output points, for all the channels or one.

**Use:** Restore a washed-out picture, or crush the blacks for a graphic look.

**Found by:** levels, gamma, black point, white point, histogram, مستويات, جاما, أسود, أبيض, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.levels`

- `input_black` (number, none): 0 to 254, default 0
- `input_white` (number, none): 1 to 255, default 255
- `gamma` (number, none): 0.1 to 10, default 1
- `output_black` (number, none): 0 to 255, default 0
- `output_white` (number, none): 0 to 255, default 255
- `mix` (number, percent): 0 to 100, default 100

### Black & White — `fx.effect:color.black_white`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Draws the picture toward its own grey.

**Use:** Noir looks, or to take the colour out before a Tint.

**Found by:** black and white, grayscale, greyscale, monochrome, desaturate, أبيض وأسود, رمادي, تدرج رمادي, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.black_white`

- `amount` (number, percent): 0 to 100, default 100
- `mix` (number, percent): 0 to 100, default 100

### Invert — `fx.effect:color.invert`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Reverses the picture's colours.

**Use:** Negative flashes, a white text made from a black one, X-ray looks.

**Found by:** invert, negative, reverse, معكوس, عكس, نيجاتيف, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.invert`

- `amount` (number, percent): 0 to 100, default 100
- `mix` (number, percent): 0 to 100, default 100

### Curves — `fx.effect:color.curves`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

A curve for each colour channel and one for all of them, each through five points.

**Use:** Fine grading: lift the shadows, roll off the highlights, cross-process the colour.

**Found by:** curves, tone, contrast, grade, منحنيات, منحنى, تدرج, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.curves`

- `master_black` (number, percent): 0 to 100, default 0
- `master_shadow` (number, percent): 0 to 100, default 25
- `master_mid` (number, percent): 0 to 100, default 50
- `master_light` (number, percent): 0 to 100, default 75
- `master_white` (number, percent): 0 to 100, default 100
- `red_black` (number, percent): 0 to 100, default 0
- `red_shadow` (number, percent): 0 to 100, default 25
- `red_mid` (number, percent): 0 to 100, default 50
- `red_light` (number, percent): 0 to 100, default 75
- `red_white` (number, percent): 0 to 100, default 100
- `green_black` (number, percent): 0 to 100, default 0
- `green_shadow` (number, percent): 0 to 100, default 25
- `green_mid` (number, percent): 0 to 100, default 50
- `green_light` (number, percent): 0 to 100, default 75
- `green_white` (number, percent): 0 to 100, default 100
- `blue_black` (number, percent): 0 to 100, default 0
- `blue_shadow` (number, percent): 0 to 100, default 25
- `blue_mid` (number, percent): 0 to 100, default 50
- `blue_light` (number, percent): 0 to 100, default 75
- `blue_white` (number, percent): 0 to 100, default 100
- `mix` (number, percent): 0 to 100, default 100

## Blur

### Directional Blur — `fx.effect:blur.directional_blur`

Blur · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Blurs along one direction, both ways from each pixel.

**Use:** Speed streaks, a whoosh, wind; animate the length for a snap. It is a look, not the layer's motion blur.

**Found by:** directional, motion blur, streak, speed, smear, تمويه اتجاهي, حركة, خطوط سرعة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:blur.directional_blur`

- `length` (number, pixels): 0 to 1000, default 0
- `angle` (number, degrees): -360 to 360, default 0
- `mix` (number, percent): 0 to 100, default 100

### Zoom Blur — `fx.effect:blur.zoom_blur`

Blur · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Blurs toward a point, as if zooming through the picture.

**Use:** Impact punches, a rush into a cut, tunnel looks.

**Found by:** zoom blur, radial blur, punch, rush, تمويه شعاعي, تكبير, اندفاع, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:blur.zoom_blur`

- `amount` (number, percent): 0 to 100, default 0
- `centre` (point, pixels): -10000 to 10000, default 0
- `mix` (number, percent): 0 to 100, default 100

### Spin Blur — `fx.effect:blur.spin_blur`

Blur · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Blurs about a point along arcs, as if the picture spun.

**Use:** Spinning wheels, whip looks, a dizzy moment.

**Found by:** spin, rotate, radial, whirl, دوران, تمويه دوّار, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:blur.spin_blur`

- `angle` (number, degrees): 0 to 360, default 0
- `centre` (point, pixels): -10000 to 10000, default 0
- `mix` (number, percent): 0 to 100, default 100

## Stylize

### Motion Tile — `fx.effect:stylize.motion_tile`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Repeats the picture in tiles over a larger or smaller output, with mirrored edges if asked.

**Use:** Patterns and wallpaper from one small picture; animate the phase to scroll them. A layer's chain holds one.

**Found by:** tile, repeat, pattern, mirror, wallpaper, تكرار, بلاط, نمط, مرآة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.motion_tile`

- `centre` (point, pixels): -10000 to 10000, default 0
- `tile_width` (number, percent): 1 to 10000, default 100
- `tile_height` (number, percent): 1 to 10000, default 100
- `output_width` (number, percent): 1 to 10000, default 100
- `output_height` (number, percent): 1 to 10000, default 100
- `mirror` (toggle, none): 0 to 1, default 0
- `phase` (number, degrees): -360 to 360, default 0
- `phase_horizontal` (toggle, none): 0 to 1, default 0
- `trim` (number, pixels): -2000 to 2000, default 0
- `mix` (number, percent): 0 to 100, default 100

### Drop Shadow — `fx.effect:stylize.drop_shadow`

Stylize · suits shape, vector, text, scene · cost unmeasured · available

A soft shadow of the picture's alpha, moved, softened and coloured, under the picture.

**Use:** Lift a cut-out, a text or a card off the page; animate the distance for a pop. It needs transparent edges: on a picture that fills the frame there is nothing to see.

**Found by:** shadow, drop shadow, depth, lift, ظل, عمق, ظل ساقط, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.drop_shadow`

- `color` (color, none): 0 to 1, default 0
- `opacity` (number, percent): 0 to 100, default 50
- `direction` (number, degrees): -360 to 360, default 135
- `distance` (number, pixels): 0 to 2000, default 5
- `softness` (number, pixels): 0 to 250, default 0
- `shadow_only` (toggle, none): 0 to 1, default 0
- `mix` (number, percent): 0 to 100, default 100

### Glow — `fx.effect:stylize.glow`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Spreads the bright parts of the picture by a pyramid of blurs and adds them back as light.

**Use:** Neon, lights, soft dreamy highlights. On a bright picture raise the threshold or the whole frame blooms white.

**Found by:** glow, bloom, neon, light, halo, توهج, نيون, ضوء, هالة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.glow`

- `threshold` (number, percent): 0 to 100, default 60
- `radius` (number, pixels): 0 to 100, default 10
- `intensity` (number, times): 0 to 10, default 1
- `colors` (choice, none): 0 to 1, default 0 [Original colors, Color]
- `color` (color, none): 0 to 1, default 0
- `operation` (choice, none): 0 to 1, default 0 [Add, Screen]
- `glow_only` (toggle, none): 0 to 1, default 0
- `mix` (number, percent): 0 to 100, default 100

### Vignette — `fx.effect:stylize.vignette`

Stylize · suits video, shape, background, scene, adjustment · cost unmeasured · available

Darkens or lightens the edges by an ellipse about a point.

**Use:** Draw the eye to the middle of a full-frame picture or clip. On a cut-out it leaves a grey halo at its rim: leave it off cut-outs.

**Found by:** vignette, edges, darken edges, focus, تعتيم, حواف, فينيت, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.vignette`

- `amount` (number, percent): -100 to 100, default 50
- `size` (number, percent): 5 to 200, default 75
- `roundness` (number, percent): 0 to 100, default 0
- `feather` (number, percent): 0 to 100, default 50
- `centre` (point, pixels): -10000 to 10000, default 0
- `mix` (number, percent): 0 to 100, default 100

## Color

### Posterize — `fx.effect:color.posterize`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Holds each colour channel to a number of levels.

**Use:** Poster, comic and retro-print looks; pair it with a Halftone.

**Found by:** posterize, levels, poster, flat colour, بوستر, مستويات, تبسيط ألوان, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.posterize`

- `levels` (number, none): 2 to 255, default 6
- `mix` (number, percent): 0 to 100, default 100

## Stylize

### Mosaic — `fx.effect:stylize.mosaic`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Draws the picture in cells of one colour each.

**Use:** Pixelate a face or a detail, retro pixel looks, a pixelate transition by animating the cell size.

**Found by:** mosaic, pixelate, pixel, censor, blocks, بكسلة, فسيفساء, تشويش, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.mosaic`

- `cell_width` (number, pixels): 1 to 1000, default 16
- `cell_height` (number, pixels): 1 to 1000, default 16
- `sharp` (toggle, none): 0 to 1, default 0
- `mix` (number, percent): 0 to 100, default 100

### Chromatic Aberration — `fx.effect:stylize.chromatic_aberration`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Moves the red and the blue of the picture apart: away from a point, or along an angle.

**Use:** Lens fringing, glitch splits, impact frames; animate the amount for a hit.

**Found by:** chromatic, aberration, rgb split, fringe, glitch, انحراف لوني, تقسيم ألوان, خلل, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.chromatic_aberration`

- `amount` (number, pixels): 0 to 200, default 4
- `mode` (choice, none): 0 to 1, default 0 [Radial, Linear]
- `angle` (number, degrees): -360 to 360, default 0
- `centre` (point, pixels): -10000 to 10000, default 0
- `mix` (number, percent): 0 to 100, default 100

## Color

### Tint — `fx.effect:color.tint`

Color · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Maps the picture's brightness between two colours.

**Use:** Duotone and sepia looks, a brand colour wash.

**Found by:** tint, duotone, sepia, gradient map, colorize, صبغة, لونين, سيبيا, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:color.tint`

- `black` (color, none): 0 to 1, default 0
- `white` (color, none): 0 to 1, default 0
- `amount` (number, percent): 0 to 100, default 100
- `mix` (number, percent): 0 to 100, default 100

## Stylize

### Film Grain — `fx.effect:stylize.film_grain`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Noise on the picture, the same for the same seed and frame, new on each frame when animated.

**Use:** Film texture, hiding banding, gluing graphics to footage.

**Found by:** grain, noise, film, texture, حبيبات, ضجيج, فيلم, خشونة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.film_grain`

- `amount` (number, percent): 0 to 100, default 20
- `size` (number, pixels): 0.5 to 20, default 1.5
- `seed` (number, none): 0 to 10000, default 0
- `animated` (toggle, none): 0 to 1, default 1
- `mix` (number, percent): 0 to 100, default 100

### Sharpen — `fx.effect:stylize.sharpen`

Stylize · suits video, shape, background, scene, adjustment · cost unmeasured · available

An unsharp mask: the picture plus the difference between it and its blur.

**Use:** Crisp a soft clip or a scaled-up picture; keep the radius small.

**Found by:** sharpen, unsharp, crisp, detail, حدة, توضيح, تفاصيل, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.sharpen`

- `amount` (number, percent): 0 to 1000, default 100
- `radius` (number, pixels): 0 to 50, default 2
- `threshold` (number, percent): 0 to 100, default 0
- `mix` (number, percent): 0 to 100, default 100

### Turbulent Displace — `fx.effect:stylize.turbulent_displace`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Moves the picture from place to place by a smooth noise; the evolution turns the noise through a third dimension.

**Use:** Liquid, heat haze, a hand-drawn wobble, torn edges; animate the evolution. On a picture that fills the frame it pulls a transparent rim in at the edge (a known defect, EM3).

**Found by:** turbulent, displace, wobble, liquid, distort, wave, heat, تشويه, اهتزاز, سائل, تموج, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.turbulent_displace`

- `amount` (number, pixels): 0 to 1000, default 20
- `size` (number, pixels): 1 to 5000, default 100
- `complexity` (number, none): 1 to 6, default 2
- `evolution` (number, degrees): -7200 to 7200, default 0
- `seed` (number, none): 0 to 10000, default 0
- `edges` (choice, none): 0 to 2, default 0 [Clear, Pin, Mirror]
- `mix` (number, percent): 0 to 100, default 100

### Wave Warp — `fx.effect:stylize.wave_warp`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Moves the picture across a wave: sine, triangle, sawtooth or square.

**Use:** Flags, water ripples, a wave through a text; animate the phase. It has the same edge defect as Turbulent Displace.

**Found by:** wave, warp, ripple, flag, water, موجة, تموج, ماء, علم, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.wave_warp`

- `wave` (choice, none): 0 to 3, default 0 [Sine, Triangle, Sawtooth, Square]
- `height` (number, pixels): 0 to 1000, default 10
- `width` (number, pixels): 1 to 5000, default 100
- `direction` (number, degrees): -360 to 360, default 0
- `phase` (number, degrees): -7200 to 7200, default 0
- `edges` (choice, none): 0 to 2, default 0 [Clear, Pin, Mirror]
- `mix` (number, percent): 0 to 100, default 100

### Halftone — `fx.effect:stylize.halftone`

Stylize · suits video, shape, vector, text, background, scene, adjustment · cost unmeasured · available

Prints the picture as dots, lines or crosses on paper, in one ink or in four at the angles of print.

**Use:** Newspaper and comic looks. The screen belongs to the layer: put the effect on an adjustment layer for a screen fixed to the canvas. Dots under 6 pixels turn grey on a phone.

**Found by:** halftone, dots, print, comic, newspaper, screen, نقاط, طباعة, نصف تدرج, كوميك, جريدة, effect, fx, تأثير, مؤثر, افكت

**Add:** `inspector.add item=library kind=fx.effect:stylize.halftone`

- `mode` (choice, none): 0 to 1, default 0 [One ink, Four inks]
- `shape` (choice, none): 0 to 2, default 0 [Dots, Lines, Crosses]
- `size` (number, pixels): 2 to 200, default 12
- `angle` (number, degrees): -360 to 360, default 45
- `softness` (number, percent): 0 to 100, default 15
- `gain` (number, percent): 25 to 200, default 100
- `ink` (color, none): 0 to 1, default 0
- `paper` (color, none): 0 to 1, default 0
- `mix` (number, percent): 0 to 100, default 100

