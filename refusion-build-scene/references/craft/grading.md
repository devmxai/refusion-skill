# Grading a picture

A layer's grade is how its picture is lit and coloured: one object on a video, a picture or an adjustment layer, drawn before the layer's effects. Its numbers are properties of the layer, so they are set, keyed and undone as any property is. There is no grading tool to call: `property.set` sets a number, keys animate it, `scene.snapshot` and the inspector read it.

## The numbers

| Number | What it does | Range, default |
|---|---|---|
| `exposure` | The light, in stops: +1 doubles it. | -5 to 5, 0 |
| `contrast` | Spreads the tones from the pivot (a positive value) or draws them to it. | -100 to 100, 0 |
| `pivot` | Where contrast turns, in the log scale; 0.4135 is mid grey. Moves nothing alone. | 0 to 1, 0.4135 |
| `highlights` | The bright tones, short of white. | -100 to 100, 0 |
| `shadows` | The dark tones, short of black. | -100 to 100, 0 |
| `whites` | The brightest part. | -100 to 100, 0 |
| `blacks` | The darkest part. | -100 to 100, 0 |
| `temperature` | Cooler (blue, negative) to warmer (yellow, positive), keeping the brightness. | -100 to 100, 0 |
| `tint` | Green (negative) to magenta (positive). | -100 to 100, 0 |
| `vibrance` | Saturation that lifts the dullest colours most and spares skin and saturated ones. | -100 to 100, 0 |
| `saturation` | All colours toward or away from grey. | -100 to 100, 0 |
| `lift`, `gamma`, `gain`, `offset` | The wheels: a pair each, where the puck is (x the blue-yellow axis, y the red-cyan one, each -1 to 1). Lift tints the shadows, gamma the middle, gain the highlights, offset everything. | (0, 0) |
| `curve_luma_0` … `curve_blue_9` | The curves: Luma (the lightness, the colour kept), red, green and blue, ten points each, a point a pair (input, output, 0 to 1; (-1, -1) out of use). Points 0 and 1 are the ends. `grade.curve` reads a curve's points and its line. | ends (0, 0) and (1, 1), the rest out of use |
| `red_hue` … `magenta_luminance` | The mixer: eight colours (red, orange, yellow, green, aqua, blue, purple, magenta), each its hue (turned a twelfth of a turn at 100), its saturation (gone at -100, doubled at 100) and its lightness. | -100 to 100, 0 |
| `skin_protect` | How much the mixer spares a colour of skin's hue and saturation. | 0 to 100, 0 |
| `lift_master` and the other three | Each wheel's lightness: lift lowers or raises the black end, gamma the middle, gain the white end, offset everything. | -100 to 100, 0 |

Each number's property path is the layer's, then grade, then the number (the layer 5's exposure is layer.5.grade.exposure). A layer has no grade until one of its numbers is set; a grade at its defaults draws nothing and costs nothing.

## The order

The engine runs a grade in one pass, in this order: white balance (temperature, tint), exposure, then contrast and the four tones in a log scale (ACEScct), then vibrance and saturation. That is why contrast behaves as it does in DaVinci Resolve: it turns about mid grey, so it adds punch without darkening the picture or blowing the sky. The wheels come after them.

A wheel is subtle: a puck a tenth of the way out is a visible tint. Push the shadows a little toward blue and the highlights a little toward orange for the classic split; keep the middle (gamma) for skin.

## Curves

The curves come after the wheels, on the colour as it is shown. A smooth line passes through the points in use and never turns back between two of them, so a tone never swaps places with another.

- **The Luma curve moves the lightness and keeps the colour.** An S on it adds contrast without making skin more orange. A few examples:
  - (0.25, 0.18) and (0.75, 0.82), with (0.5, 0.5) holding the middle: a gentle S.
  - Raising the first end: faded blacks.
  - Lowering the second end: softer highlights.
- **The red, green and blue curves each move their own channel**, as a colourist balances a shot or splits it: blue up in the shadows and down in the highlights is the classic cool-warm split.

- **The colour curves change a colour by what it is.** Each is flat at its middle, a half, where nothing changes:
  - **Hue vs Hue** turns a hue, up to a sixth of a turn.
  - **Hue vs Sat** fills or empties the colour of one hue: the classic is the blues of a sky, or a green that is too loud.
  - **Hue vs Lum** lightens or darkens one hue.
  - **Lum vs Sat** takes colour out of the shadows or the highlights: clean blacks, highlights that do not go orange.
  - **Sat vs Sat** calms only the colours that are already strong.

  A hue curve's input is the hue all the way round, as a share of a turn, read the way the wheels read colour (BT.709 YCbCr). `grade.curve` gives the colour of each input under it. To change one colour, put a point on it and a point at the middle either side, as the colour sheet does when a finger adds one.

A point is set with `property.set` on its path, and keys animate it. Points can sit in any slots, and the engine reads them in order of their input. Take a point out of use with (-1, -1).

## The mixer

The HSL mixer changes one colour by its name, as Lightroom's does. Each colour's band reaches to the colours either side of it, so a colour between two (a sky between aqua and blue) moves with both. Common uses:

- Deepen a sky: blue saturation up a little, blue luminance down.
- Calm a loud green: green saturation down.
- Warm foliage: green hue toward yellow (negative).

Skin lies between red and orange. Before pushing orange or red, set `skin_protect` (60 to 100 is safe) so faces keep their colour.

## Looks

A look sits on top of the grade, as its last stage, and `look_amount` (0 to 100) blends it in. It never changes the grade's own numbers, and taking it off (`grade.look_clear`) leaves them as they were. A grade carries one look:

- **A ready look of the library:** `grade.looks` lists thirty, in five families (Cinematic, Film, Moody, Black & White, Teal & Orange), with their ids; `grade.look_set` lays one on. Each is made of the grade's own numbers, run again on the graded picture.
- **A look-up table (`.cube`) the owner picked:** `grade.lut_set`. A creative table is usually best between 40 and 80; a table made for Log footage needs a Log shot.

Grade the shot first (balance, light), then the look on top. Applying one replaces the other. To see what a look does to the shot, lay it on and look with `render.look`.

The person's own looks are listed by `grade.looks` in family 6, My looks, and laid on with `grade.look_set` like any other. The person keeps them from the colour sheet: each holds a grade's own numbers and the look that was over them, baked into a table. They show as they were saved when laid at an amount of 100.

A look of the person's own is an add-on of the kind `look`, a `.rfl` file: `addon.list` lists it, `addon.export` writes it to share, `addon.remove` takes it off (a project that has it keeps its numbers and its table). To make a look for the owner as a file, author a folder and pack it with `rpro addon pack <folder>`, which checks it as an install would:

- The manifest, **addon.json**: `"kind": "look"`, an id in a domain of your own (not `pro.refusion.`, and not the id of a library look such as `cinematic.drama`), a version, a name in English and Arabic, a licence, `"entry": "look.json"`, and the table listed in `assets` as `text/x-cube` when there is one.
- The entry, **look.json**: `{"look": 1, "values": [[code, x, y], ...], "table": "assets/look.cube"}`. Each value is a number of the grade by its code (light, colour, the wheels, the curves, the mixer; not a selection, the look's amount or the film), named once and inside its range, `y` 0 for a number and the second axis for a wheel's puck. A table alone, or numbers alone, is a look; nothing at all is refused.

Install it with `addon.inspect` then `addon.install`, with the owner's yes: it is then in My looks (with numbers) or Imported (a table alone).

## Log footage

A clip shot in Log (Apple Log on an iPhone Pro, S-Log3, V-Log, LogC3) looks grey and flat as it is: that is the camera keeping the
light for the grade, not a fault. Read it by its curve first, with `grade.input_set` (`grade.inputs` lists the curves; 1 Apple Log,
2 S-Log3 with S-Gamut3.Cine, 3 S-Log3 with S-Gamut3, 4 V-Log, 5 LogC3). The grade then works on all the light the camera kept and
rolls the highlights off at its end, so exposure can bring a sky back that a Rec.709 clip would have lost.

- The file does not say it was shot in Log: ask the person or read `declared` (a 10-bit BT.2020 clip that is not HDR is often Log).
  Never pick a curve by guess: a wrong curve makes the picture too contrasty or too dark.
- A bought LUT made for Log footage expects the Log picture: leave the curve at 0 (as the file says) to use it.
- The curve is the clip's: `grade.paste` and the looks leave it as it is.
- A clip whose file says HLG or PQ (an iPhone's ordinary video is HLG) is already read by its own curve: `grade.input_set` refuses it
  (`source_is_hdr`), and pictures and adjustment layers take no curve (`input_needs_a_clip`).

## One colour, corrected alone

A grade has four selections (`grade.select1_…` to `grade.select4_…`): each holds one colour and corrects only it, after the mixer.

- **Its key:** `selectN_hue` (degrees round the turn) with `selectN_hue_width` (360 holds every hue) and `selectN_hue_softness`;
  `selectN_saturation_low`/`_high`/`_softness` and `selectN_lightness_low`/`_high`/`_softness` (0 to 100). Read the colour to hold
  with `scope.read` or by rendering; the hue is the angle the vectorscope shows. A narrow hue range lets greys go.
- **Its correction:** `selectN_exposure`, `_contrast`, `_temperature`, `_tint`, `_saturation`, `_hue_shift` (degrees).
- A sky deeper: hold the blue (width 40 to 60), then saturation +20 to +40, exposure -0.3, a hue shift of a few degrees. Look at the
  person after it: skin should not move.
- Prefer a selection to the mixer when one object should change and its hue is shared by others in other lightness.
- **A part of the picture:** `grade.selection_window` (`shape` 1 a circle, 2 a rectangle) limits a selection to a window on the
  content; with its colour ranges at their defaults the selection is the window alone. A face brighter: a circle over it
  (`selectN_window_x`/`_y` where the face is, `_width`/`_height` about its size, `_softness` 40 to 60), then `selectN_exposure`
  +0.3 to +0.6. For a vignette use the film's (below), not a window.

## The film

The last stage, set with `property.set` on the grade's numbers: `vignette_amount` (-15 to -35 draws the eye in; past -50 it shows), `vignette_midpoint` (where it begins),
`vignette_roundness`, `vignette_feather` (soft, 50 to 80); `grain_amount` (8 to 20 reads as film on a phone; more is a look),
`grain_size`, `grain_roughness`, `grain_colour` (0 for black and white film). The grain changes every frame and lies over everything.
Detail comes first: `clarity` +10 to +30 gives faces and landscapes body (negative softens skin, a dreamy look), `texture` +10 to +25
crisps fine detail (negative smooths skin without blurring edges); past 50 both show halos. Halation (`halation_amount` 15 to 40) puts a red rim round bright lights, as film does: for night streets, neon, sun through a window. Bloom
(`bloom_amount` 10 to 30) lets highlights glow softly; past 50 it is a dream look. Raise their thresholds to keep them on the brightest
parts only. Balance and match measure the picture without the film, so add it last.

## Grading as a colourist does

1. **Balance first.** Make white white and skin skin: temperature and tint on the shot as it is. `grade.balance_auto` does it from the picture's own near-grey parts and writes temperature and tint you can see and change. A warm or cold look is made later, on top of a picture that is right.
2. **Set the light.** Exposure for the face or the subject, not for the sky. Then whites and blacks to set where the picture ends, then highlights and shadows to shape the inside.
3. **Contrast after the light.** A little goes a long way: 10 to 25 is a lot on a phone screen.
4. **Colour last.** Vibrance before saturation: it fills dull colours and leaves skin alone. Saturation above 30 makes skin orange and skies electric.
5. **Match the shots.** Shots of one scene should look like one place: grade one, then bring the others to it with `grade.match` (`reference`: the graded layer). It measures both pictures and moves exposure, contrast, temperature, tint and saturation; the numbers it writes are ordinary numbers, so finish by hand. It matches the whole picture, not a face: two shots of different content match roughly, and a sky in one and not the other pulls the light.
6. **One look for a scene:** an adjustment layer over its shots, graded once, rather than the same numbers on every clip.
7. **Match by copying.** `grade.paste` gives one clip's grade to another (`every`: to every clip), keys and all, in one step; the owner copies with `grade.copy` from the colour sheet. Then adjust what differs.

## Reading the picture

`scope.read` measures the frame at the edit head the way a colourist reads the scopes, as numbers:

- **`black_clipped` and `white_clipped`:** the share of the picture at pure black and pure white. More than a few per cent means detail is lost: bring `whites` or `blacks` back.
- **`dark`, `middle` and `bright`:** where 1, 50 and 99 per cent of the picture lie. A picture that uses its range runs from near 0 to near 100, with the middle near 40 to 55 for daylight.
- **`saturation`:** the mean colour. Above about 25 a picture starts to look loud on a phone.
- **`skin_off`:** how many degrees skin lies from the skin line. A few degrees is natural; far off means the balance is wrong, so fix temperature and tint first.

Read it after each change that matters. `render.look` shows the picture; the numbers say what the eye misses.

## What not to do

- Fix a dark shot with contrast. Raise exposure; contrast only spreads what is there.
- Push highlights down to save a sky, then forget the face went grey. Look at the subject after every change.
- Grade by the numbers without looking: `render.look` shows the frame; the numbers are not the picture.
- Re-grade a shot the person already graded without being asked: their grade is theirs.
