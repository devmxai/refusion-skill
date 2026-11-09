# Effects

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `9511ee7fd7751931`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

An effect is added to a layer with `effect.add`, or with `inspector.add` and the item `fx.effect`. Its settings are properties of the layer, keyed like any other (`fx.<kind>.<setting>[<id>]`), and every effect has a `mix`.

16 items. Read one with its id in `library.catalog`; `library.look` draws a page of them.

| Item | Id | Category |
|---|---|---|
| Gaussian Blur | `fx.effect:blur.gaussian_blur` | Blur |
| Black & White | `fx.effect:color.black_white` | Color |
| Invert | `fx.effect:color.invert` | Color |
| Directional Blur | `fx.effect:blur.directional_blur` | Blur |
| Zoom Blur | `fx.effect:blur.zoom_blur` | Blur |
| Spin Blur | `fx.effect:blur.spin_blur` | Blur |
| Motion Tile | `fx.effect:stylize.motion_tile` | Stylize |
| Drop Shadow | `fx.effect:stylize.drop_shadow` | Stylize |
| Glow | `fx.effect:stylize.glow` | Stylize |
| Posterize | `fx.effect:color.posterize` | Color |
| Mosaic | `fx.effect:stylize.mosaic` | Stylize |
| Chromatic Aberration | `fx.effect:stylize.chromatic_aberration` | Stylize |
| Tint | `fx.effect:color.tint` | Color |
| Turbulent Displace | `fx.effect:stylize.turbulent_displace` | Stylize |
| Wave Warp | `fx.effect:stylize.wave_warp` | Stylize |
| Halftone | `fx.effect:stylize.halftone` | Stylize |

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

