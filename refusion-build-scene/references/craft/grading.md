# Grading a picture

A layer's grade is how its picture is lit and coloured: one object on a video, a picture or an adjustment layer, drawn before the layer's effects. Its numbers are properties of the layer, so they are set, keyed and undone as any property is. There is no grading tool to call: `property.set` sets a number, keys animate it, `scene.snapshot` and the inspector read it.

## The numbers

| Path | What it does | Range, default |
|---|---|---|
| `grade.exposure` | The light, in stops: +1 doubles it. | -5 to 5, 0 |
| `grade.contrast` | Spreads the tones from the pivot (a positive value) or draws them to it. | -100 to 100, 0 |
| `grade.pivot` | Where contrast turns, in the log scale; 0.4135 is mid grey. Moves nothing alone. | 0 to 1, 0.4135 |
| `grade.highlights` | The bright tones, short of white. | -100 to 100, 0 |
| `grade.shadows` | The dark tones, short of black. | -100 to 100, 0 |
| `grade.whites` | The brightest part. | -100 to 100, 0 |
| `grade.blacks` | The darkest part. | -100 to 100, 0 |
| `grade.temperature` | Cooler (blue, negative) to warmer (yellow, positive), keeping the brightness. | -100 to 100, 0 |
| `grade.tint` | Green (negative) to magenta (positive). | -100 to 100, 0 |
| `grade.vibrance` | Saturation that lifts the dullest colours most and spares skin and saturated ones. | -100 to 100, 0 |
| `grade.saturation` | All colours toward or away from grey. | -100 to 100, 0 |

A path names the layer: `layer.<id>.grade.exposure`. A layer has no grade until one of its numbers is set; a grade at its defaults draws nothing and costs nothing.

## The order

The engine runs a grade in one pass, in this order: white balance (temperature, tint), exposure, then contrast and the four tones in a log scale (ACEScct), then vibrance and saturation. That is why contrast behaves as it does in DaVinci Resolve: it turns about mid grey, so it adds punch without darkening the picture or blowing the sky.

## Grading as a colourist does

1. **Balance first.** Make white white and skin skin: temperature and tint on the shot as it is. A warm or cold look is made later, on top of a picture that is right.
2. **Set the light.** Exposure for the face or the subject, not for the sky. Then whites and blacks to set where the picture ends, then highlights and shadows to shape the inside.
3. **Contrast after the light.** A little goes a long way: 10 to 25 is a lot on a phone screen.
4. **Colour last.** Vibrance before saturation: it fills dull colours and leaves skin alone. Saturation above 30 makes skin orange and skies electric.
5. **Match the shots.** Shots of one scene should look like one place: grade one, then bring the others to it with the same numbers moved a little, not with new looks.
6. **One look for a scene:** an adjustment layer over its shots, graded once, rather than the same numbers on every clip.

## What not to do

- Fix a dark shot with contrast. Raise exposure; contrast only spreads what is there.
- Push highlights down to save a sky, then forget the face went grey. Look at the subject after every change.
- Grade by the numbers without looking: `render.look` shows the frame; the numbers are not the picture.
- Re-grade a shot the person already graded without being asked: their grade is theirs.
