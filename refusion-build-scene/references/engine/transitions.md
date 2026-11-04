# Transitions

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `4af08c00a3ffec14`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

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

**Use:** The standard, nearly invisible change between two shots: use it between scenes of one mood or place, and for a soft passing of time. A long one reads as a dream, a short one as a smooth cut.

**Found by:** dissolve, cross dissolve, crossfade, cross fade, fade, blend, mix, smooth, soft, تلاشي, تداخل, مزج, ذوبان, انتقال ناعم, تمازج, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=1 (on a cut between two layers)`

### Film Dissolve — `transition:2`

Dissolve · cost unmeasured · available

Mixes the two pictures in light-linear values, so there is no dip of brightness in the middle. A new one lasts 1 s.

**Use:** A dissolve that keeps the brightness steady in the middle (the pictures are mixed in linear light): for footage, where a plain cross dissolve dips a little dark halfway.

**Found by:** film dissolve, film, dissolve, linear light, smooth, cinematic, even, تلاشي سينمائي, فيلم, سينمائي, ثبات الإضاءة, تداخل, مزج, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=2 (on a cut between two layers)`

### Additive Dissolve — `transition:3`

Dissolve · cost unmeasured · available

Adds the light of the two pictures: each is whole until its half and the sum brightens in the middle. A new one lasts 1 s.

**Use:** Adds the light of the two shots, so the middle brightens as in a double exposure: a dreamy or glowing change, a passing flash. Bright shots blow out in the middle.

**Found by:** additive, additive dissolve, add, glow, flash, double exposure, light, bright, إضافي, جمع الضوء, وميض, توهج, تعريض مزدوج, سطوع, تداخل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=3 (on a cut between two layers)`

### Dip to Black — `transition:4`

Dissolve · cost unmeasured · available

Takes the first picture to a colour (red 0, green 0, blue 0) and the colour to the second, with a hold on the colour. A new one lasts 1 s.

**Use:** The end of a scene or a chapter: the picture goes to black and the next one comes out of it. Also the classic open and close of a piece.

**Found by:** dip to black, fade to black, fade out, black, end, chapter, close, open, تلاشي للأسود, اسوداد, أسود, ظلام, نهاية, فصل, إغلاق, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=4 (on a cut between two layers)`

- `hold` (number, percent): 0 to 60, default 12

### Dip to White — `transition:5`

Dissolve · cost unmeasured · available

Takes the first picture to a colour (red 1, green 1, blue 1) and the colour to the second, with a hold on the colour. A new one lasts 1 s.

**Use:** A bright, airy pause: a flashback, a dream, a flash between sections. The picture goes to white and the next one comes out of it.

**Found by:** dip to white, fade to white, white, flash, bright, flashback, airy, تلاشي للأبيض, أبيض, ابيضاض, وميض, سطوع, ذكرى, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=5 (on a cut between two layers)`

- `hold` (number, percent): 0 to 60, default 12

## Push

### Push Left — `transition:10`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves -1 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** The whole frame is pushed off by the next picture: a clean sports, news or slideshow change for items in order, steps and places. Left, right, up and down choose the direction of travel.

**Found by:** push, push left, shove, shift, scroll, pan, next, left, دفع, دفع لليسار, يسار, إزاحة, تمرير, التالي, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=10 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Right — `transition:11`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 1 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** The whole frame is pushed off by the next picture: a clean sports, news or slideshow change for items in order, steps and places. Left, right, up and down choose the direction of travel.

**Found by:** push, push right, shove, shift, scroll, pan, next, right, دفع, دفع لليمين, يمين, إزاحة, تمرير, التالي, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=11 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Up — `transition:12`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and -1 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** The whole frame is pushed off by the next picture: a clean sports, news or slideshow change for items in order, steps and places. Left, right, up and down choose the direction of travel.

**Found by:** push, push up, shove, shift, scroll, pan, next, up, دفع, دفع للأعلى, أعلى, إزاحة, تمرير, التالي, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=12 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Push Down — `transition:13`

Push · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and 1 heights down for each unit of motion, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** The whole frame is pushed off by the next picture: a clean sports, news or slideshow change for items in order, steps and places. Left, right, up and down choose the direction of travel.

**Found by:** push, push down, shove, shift, scroll, pan, next, down, دفع, دفع للأسفل, أسفل, إزاحة, تمرير, التالي, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=13 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

## Slide

### Slide Left — `transition:20`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves -1 canvas widths across and 0 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** One picture slides over the other, which stays still: lighter than a push, for card-like reveals and layered stories. Left, right, up and down choose the direction of travel.

**Found by:** slide, slide left, swipe, cover, reveal, glide, card, left, انزلاق, انزلاق لليسار, سحب, تغطية, كشف, يسار, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=20 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Right — `transition:21`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 1 canvas widths across and 0 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** One picture slides over the other, which stays still: lighter than a push, for card-like reveals and layered stories. Left, right, up and down choose the direction of travel.

**Found by:** slide, slide right, swipe, cover, reveal, glide, card, right, انزلاق, انزلاق لليمين, سحب, تغطية, كشف, يمين, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=21 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Up — `transition:22`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and -1 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** One picture slides over the other, which stays still: lighter than a push, for card-like reveals and layered stories. Left, right, up and down choose the direction of travel.

**Found by:** slide, slide up, swipe, cover, reveal, glide, card, up, انزلاق, انزلاق للأعلى, سحب, تغطية, كشف, أعلى, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=22 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

### Slide Down — `transition:23`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, moves 0 canvas widths across and 1 heights down for each unit of motion, leaves the outgoing picture still, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.67 s.

**Use:** One picture slides over the other, which stays still: lighter than a push, for card-like reveals and layered stories. Left, right, up and down choose the direction of travel.

**Found by:** slide, slide down, swipe, cover, reveal, glide, card, down, انزلاق, انزلاق للأسفل, سحب, تغطية, كشف, أسفل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=23 (on a cut between two layers)`

- `blur` (number, percent): 0 to 100, default 25

## Zoom

### Zoom In — `transition:30`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, scales by 4 for each unit, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.8 s.

**Use:** The picture rushes toward you and the next shot comes out of the blur: an energetic jump, a reveal of a detail, a hype cut. The cut is hidden at the fastest instant.

**Found by:** zoom, zoom in, rush, punch in, closer, scale up, dolly, تكبير, تقريب, اقتراب, زووم, اندفاع, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=30 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 2, default 0 [Mirror, Clamp, Transparent]

### Zoom Out — `transition:31`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, scales by 0.25 for each unit, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.8 s.

**Use:** The picture pulls away and the next shot comes out of the blur: a reveal of the whole after a detail, a change of scale. The cut is hidden at the fastest instant.

**Found by:** zoom, zoom out, pull back, away, scale down, reveal, wide, تصغير, ابتعاد, زووم, كشف, سحب للخلف, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

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

**Use:** The picture turns a full circle with blur and the next one appears in the turn: playful and loud, for fun, kids and social content; too much for serious pieces.

**Found by:** spin, rotate, turn, twirl, whirl, swirl, circle, دوران, تدوير, لف, دوامة, دائرة, يدور, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

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

**Use:** A very fast pan with motion blur, as if the camera whipped sideways, and the next shot arrives out of it: sports, travel and upbeat edits, matched to a beat. Left, right, up and down choose the direction.

**Found by:** whip, whip pan, swish, swish pan, fast, quick, speed, pan, left, سريع, خاطف, سحب سريع, سرعة, بان, يسار, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=40 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Right — `transition:41`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 2 canvas widths across and 0 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Use:** A very fast pan with motion blur, as if the camera whipped sideways, and the next shot arrives out of it: sports, travel and upbeat edits, matched to a beat. Left, right, up and down choose the direction.

**Found by:** whip, whip pan, swish, swish pan, fast, quick, speed, pan, right, سريع, خاطف, سحب سريع, سرعة, بان, يمين, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=41 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Up — `transition:42`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 0 canvas widths across and -2 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Use:** A very fast pan with motion blur, as if the camera whipped upward, and the next shot arrives out of it: sports, travel and upbeat edits, matched to a beat. Left, right, up and down choose the direction.

**Found by:** whip, whip pan, swish, swish pan, fast, quick, speed, tilt, up, سريع, خاطف, سحب سريع, سرعة, تيلت, أعلى, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=42 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

### Whip Down — `transition:43`

Whip · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, moves 0 canvas widths across and 2 heights down for each unit of motion, blurs the motion with a 216 degree shutter and mirrors the picture past its edge. A new one lasts 0.4 s.

**Use:** A very fast pan with motion blur, as if the camera whipped downward, and the next shot arrives out of it: sports, travel and upbeat edits, matched to a beat. Left, right, up and down choose the direction.

**Found by:** whip, whip pan, swish, swish pan, fast, quick, speed, tilt, down, سريع, خاطف, سحب سريع, سرعة, تيلت, أسفل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=43 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 50
- `blur` (number, percent): 0 to 100, default 30

