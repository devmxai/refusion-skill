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
| `lift_master` and the other three | Each wheel's lightness: lift lowers or raises the black end, gamma the middle, gain the white end, offset everything. | -100 to 100, 0 |

Each number's property path is the layer's, then grade, then the number (the layer 5's exposure is layer.5.grade.exposure). A layer has no grade until one of its numbers is set; a grade at its defaults draws nothing and costs nothing.

## The order

The engine runs a grade in one pass, in this order: white balance (temperature, tint), exposure, then contrast and the four tones in a log scale (ACEScct), then vibrance and saturation. That is why contrast behaves as it does in DaVinci Resolve: it turns about mid grey, so it adds punch without darkening the picture or blowing the sky.

A wheel is subtle: a puck a tenth of the way out is a visible tint. Push the shadows a little toward blue and the highlights a little toward orange for the classic split; keep the middle (gamma) for skin.

## Grading as a colourist does

1. **Balance first.** Make white white and skin skin: temperature and tint on the shot as it is. A warm or cold look is made later, on top of a picture that is right.
2. **Set the light.** Exposure for the face or the subject, not for the sky. Then whites and blacks to set where the picture ends, then highlights and shadows to shape the inside.
3. **Contrast after the light.** A little goes a long way: 10 to 25 is a lot on a phone screen.
4. **Colour last.** Vibrance before saturation: it fills dull colours and leaves skin alone. Saturation above 30 makes skin orange and skies electric.
5. **Match the shots.** Shots of one scene should look like one place: grade one, then bring the others to it with the same numbers moved a little, not with new looks.
6. **One look for a scene:** an adjustment layer over its shots, graded once, rather than the same numbers on every clip.
7. **Match by copying.** `grade.paste` gives one clip's grade to another (`every`: to every clip), keys and all, in one step; the owner copies with `grade.copy` from the colour sheet. Then adjust what differs.

## What not to do

- Fix a dark shot with contrast. Raise exposure; contrast only spreads what is there.
- Push highlights down to save a sky, then forget the face went grey. Look at the subject after every change.
- Grade by the numbers without looking: `render.look` shows the frame; the numbers are not the picture.
- Re-grade a shot the person already graded without being asked: their grade is theirs.
