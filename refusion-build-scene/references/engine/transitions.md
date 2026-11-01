# Transitions

Written by `rpro skill-reference --write` from catalog version 2, fingerprint `18c5e4330715a936`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

A transition lies on a cut between two layers: `transition.add` with the kind's code. The settings are besides the length and the curve every transition has.

20 items. Read one with its id in `library.catalog`; `library.look` draws a page of them.

| Item | Id | Category |
|---|---|---|
| Cross Dissolve | `transition:1` | Dissolve |
| Film Dissolve | `transition:2` | Dissolve |
| Additive Dissolve | `transition:3` | Dissolve |
| Dip to Black | `transition:4` | Dissolve |
| Dip to White | `transition:5` | Dissolve |
| Push Left | `transition:10` | Push |
| Push Right | `transition:11` | Push |
| Push Up | `transition:12` | Push |
| Push Down | `transition:13` | Push |
| Slide Left | `transition:20` | Slide |
| Slide Right | `transition:21` | Slide |
| Slide Up | `transition:22` | Slide |
| Slide Down | `transition:23` | Slide |
| Zoom In | `transition:30` | Zoom |
| Zoom Out | `transition:31` | Zoom |
| Spin | `transition:32` | Spin |
| Whip Left | `transition:40` | Whip |
| Whip Right | `transition:41` | Whip |
| Whip Up | `transition:42` | Whip |
| Whip Down | `transition:43` | Whip |

## Dissolve

### Cross Dissolve — `transition:1`

Dissolve · cost unmeasured · available

Mixes the two pictures straight across, one fading into the other. A new one lasts 1 s.

**Found by:** dissolve.cross_dissolve

**Add:** `transition.add kind=1 (on a cut between two layers)`

### Film Dissolve — `transition:2`

Dissolve · cost unmeasured · available

Mixes the two pictures in light-linear values, so there is no dip of brightness in the middle. A new one lasts 1 s.

**Found by:** dissolve.film_dissolve

**Add:** `transition.add kind=2 (on a cut between two layers)`

### Additive Dissolve — `transition:3`

Dissolve · cost unmeasured · available

Adds the light of the two pictures: each is whole until its half and the sum brightens in the middle. A new one lasts 1 s.

**Found by:** dissolve.additive_dissolve

**Add:** `transition.add kind=3 (on a cut between two layers)`

### Dip to Black — `transition:4`

Dissolve · cost unmeasured · available

Takes the first picture to a colour (red 0, green 0, blue 0) and the colour to the second, with a hold on the colour. A new one lasts 1 s.

**Found by:** dissolve.dip_to_black

**Add:** `transition.add kind=4 (on a cut between two layers)`

- `hold` (number, percent): 0 to 60, default 12

### Dip to White — `transition:5`

Dissolve · cost unmeasured · available

Takes the first picture to a colour (red 1, green 1, blue 1) and the colour to the second, with a hold on the colour. A new one lasts 1 s.

**Found by:** dissolve.dip_to_white

**Add:** `transition.add kind=5 (on a cut between two layers)`

- `hold` (number, percent): 0 to 60, default 12

## Push

### Push Left — `transition:10`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves -1 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.push_left

**Add:** `transition.add kind=10 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Right — `transition:11`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 1 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.push_right

**Add:** `transition.add kind=11 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Up — `transition:12`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and -1 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.push_up

**Add:** `transition.add kind=12 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Down — `transition:13`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and 1 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.push_down

**Add:** `transition.add kind=13 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

## Slide

### Slide Left — `transition:20`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves -1 canvas widths across and 0 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.slide_left

**Add:** `transition.add kind=20 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Right — `transition:21`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 1 canvas widths across and 0 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.slide_right

**Add:** `transition.add kind=21 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Up — `transition:22`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and -1 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.slide_up

**Add:** `transition.add kind=22 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Down — `transition:23`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and 1 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Found by:** motion.slide_down

**Add:** `transition.add kind=23 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

## Zoom

### Zoom In — `transition:30`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, scales by 4 for each unit, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.8 s.

**Found by:** motion.zoom_in

**Add:** `transition.add kind=30 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 2, default 0 [Mirror, Clamp, Transparent]

### Zoom Out — `transition:31`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, scales by 0.25 for each unit, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.8 s.

**Found by:** motion.zoom_out

**Add:** `transition.add kind=31 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 2, default 0 [Mirror, Clamp, Transparent]

## Spin

### Spin — `transition:32`

Spin · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, turns 360 degrees clockwise for each unit, is 8% larger at the cut than at the ends, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 1.5 s.

**Found by:** motion.spin

**Add:** `transition.add kind=32 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30
- `pulse` (number, percent): 0 to 60, default 8
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 3, default 0 [Mirror, Clamp, Cover, Transparent]
- `direction` (choice, none): 0 to 1, default 0 [Clockwise, Counter-clockwise]

## Whip

### Whip Left — `transition:40`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves -2 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Found by:** motion.whip_left

**Add:** `transition.add kind=40 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Right — `transition:41`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 2 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Found by:** motion.whip_right

**Add:** `transition.add kind=41 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Up — `transition:42`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 0 canvas widths across and -2 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Found by:** motion.whip_up

**Add:** `transition.add kind=42 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Down — `transition:43`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 0 canvas widths across and 2 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Found by:** motion.whip_down

**Add:** `transition.add kind=43 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

