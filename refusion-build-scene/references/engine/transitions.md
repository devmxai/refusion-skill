# Transitions

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `f03794740415ddf2`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

A transition lies on a cut between two layers: `transition.add` with the kind's code. The settings are besides the length and the curve every transition has.

24 items. Read one with its id in `library.catalog`; `library.look` draws a page of them.

| Item | Id | Category |
|---|---|---|
| Cross Dissolve | `transition:1` | Dissolve |
| Film Dissolve | `transition:2` | Dissolve |
| Additive Dissolve | `transition:3` | Dissolve |
| Dip to Black | `transition:4` | Dissolve |
| Dip to White | `transition:5` | Dissolve |
| Push | `transition:10` | Push |
| Slide | `transition:20` | Slide |
| Zoom In | `transition:30` | Zoom |
| Zoom Out | `transition:31` | Zoom |
| Spin | `transition:32` | Spin |
| Whip | `transition:40` | Whip |
| Wipe | `transition:100` | Wipe |
| Clock Wipe | `transition:102` | Wipe |
| Blinds | `transition:103` | Wipe |
| Iris | `transition:101` | Shape |
| Shape Reveal | `transition:104` | Shape |
| Luma Fade | `transition:105` | Dissolve |
| Noise Dissolve | `transition:106` | Dissolve |
| Blur Dissolve | `transition:108` | Dissolve |
| Flash | `transition:107` | Light |
| Light Leak | `transition:109` | Light |
| Glitch | `transition:110` | Glitch |
| Swirl | `transition:111` | Warp |
| Ripple | `transition:112` | Warp |

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

### Push — `transition:10`

Push · cost unmeasured · available

It shows both pictures at once with no mix, takes the outgoing picture to -1 canvas widths across and 0 heights down, brings the incoming one from 1 canvas widths across and -0 heights down to rest, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.5 s.

**Use:** The whole frame is pushed off by the next picture: a clean sports, news or slideshow change for items in order, steps and places. The direction chooses the way it travels.

**Found by:** push, push left, shove, shift, scroll, pan, next, left, push right, right, push up, up, push down, down, دفع, دفع لليسار, يسار, إزاحة, تمرير, التالي, دفع لليمين, يمين, دفع للأعلى, أعلى, دفع للأسفل, أسفل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=10 (on a cut between two layers)`

- `blur` (number, degrees): 0 to 720, default 180
- `direction` (choice, none): 0 to 3, default 0 [Left, Right, Up, Down]

## Slide

### Slide — `transition:20`

Slide · cost unmeasured · available

It shows both pictures at once with no mix, leaves the outgoing picture still, brings the incoming one from 1 canvas widths across and -0 heights down to rest, blurs the motion with a 180 degree shutter and shows nothing past the edge. A new one lasts 0.5 s.

**Use:** One picture slides over the other, which stays still: lighter than a push, for card-like reveals and layered stories. The direction chooses the way it travels.

**Found by:** slide, slide left, swipe, cover, reveal, glide, card, left, slide right, right, slide up, up, slide down, down, انزلاق, انزلاق لليسار, سحب, تغطية, كشف, يسار, انزلاق لليمين, يمين, انزلاق للأعلى, أعلى, انزلاق للأسفل, أسفل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=20 (on a cut between two layers)`

- `blur` (number, degrees): 0 to 720, default 180
- `direction` (choice, none): 0 to 3, default 0 [Left, Right, Up, Down]

## Zoom

### Zoom In — `transition:30`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, takes the outgoing picture to scaled by 4, brings the incoming one from scaled by 4 to rest, blurs the motion with a 900 degree shutter and mirrors the picture past its edge. A new one lasts 0.5 s.

**Use:** The picture rushes toward you and the next shot comes out of the blur: an energetic jump, a reveal of a detail, a hype cut. The cut is hidden at the fastest instant. The next shot opens from the middle outward, an edge the blur's streaks cross, so the first shot's colours are dragged into it.

**Found by:** zoom, zoom in, rush, punch in, closer, scale up, dolly, تكبير, تقريب, اقتراب, زووم, اندفاع, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=30 (on a cut between two layers)`

- `strength` (number, times): 1.25 to 16, default 4
- `blur` (number, degrees): 0 to 1440, default 900
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 2, default 0 [Mirror, Clamp, Transparent]
- `flash` (number, none): 0 to 2, default 0.4
- `split` (number, percent): 0 to 5, default 0.8
- `seam` (choice, none): 0 to 2, default 0 [Iris out, Iris in, Mix]
- `softness` (number, percent): 2 to 40, default 12

### Zoom Out — `transition:31`

Zoom · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, takes the outgoing picture to scaled by 0.25, brings the incoming one from scaled by 0.25 to rest, blurs the motion with a 900 degree shutter and mirrors the picture past its edge. A new one lasts 0.5 s.

**Use:** The picture pulls away and the next shot comes out of the blur: a reveal of the whole after a detail, a change of scale. The cut is hidden at the fastest instant. The next shot closes in from the edges toward the middle, an edge the blur's streaks cross, so the first shot's colours are dragged into it.

**Found by:** zoom, zoom out, pull back, away, scale down, reveal, wide, تصغير, ابتعاد, زووم, كشف, سحب للخلف, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=31 (on a cut between two layers)`

- `strength` (number, times): 1.25 to 16, default 4
- `blur` (number, degrees): 0 to 1440, default 900
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 2, default 0 [Mirror, Clamp, Transparent]
- `flash` (number, none): 0 to 2, default 0.4
- `split` (number, percent): 0 to 5, default 0.8
- `seam` (choice, none): 0 to 2, default 1 [Iris out, Iris in, Mix]
- `softness` (number, percent): 2 to 40, default 12

## Spin

### Spin — `transition:32`

Spin · cost unmeasured · available

It shows one picture at a time, cut at the fastest instant of the motion, which the blur hides, takes the outgoing picture to turned 180 degrees clockwise and scaled by 1.08, brings the incoming one from turned -180 degrees clockwise and scaled by 1.08 to rest, blurs the motion with a 720 degree shutter and mirrors the picture past its edge. A new one lasts 0.7 s.

**Use:** The picture turns in one continuous camera move (a full circle unless the turn is set to another angle, from 45 degrees), blurred like a real shutter, and the next one is already in the turn: the two pictures dissolve in its middle and share one blur. Playful and loud, for fun, kids and social content; too much for serious pieces. The change runs along a fan that opens from one side, so the blur drags the first shot's colours into the next across it.

**Found by:** spin, rotate, turn, twirl, whirl, swirl, circle, دوران, تدوير, لف, دوامة, دائرة, يدور, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=32 (on a cut between two layers)`

- `strength` (number, degrees): 45 to 1440, default 360
- `blur` (number, degrees): 0 to 1440, default 720
- `pulse` (number, percent): 0 to 60, default 8
- `pivot_x` (number, percent): 0 to 100, default 50
- `pivot_y` (number, percent): 0 to 100, default 50
- `edge` (choice, none): 0 to 3, default 0 [Mirror, Clamp, Cover, Transparent]
- `direction` (choice, none): 0 to 1, default 0 [Clockwise, Counter-clockwise]
- `flash` (number, none): 0 to 2, default 0.4
- `seam` (choice, none): 0 to 1, default 0 [Fan, Mix]
- `softness` (number, percent): 2 to 40, default 12
- `seam_angle` (number, degrees): 0 to 360, default 270

## Whip

### Whip — `transition:40`

Whip · cost unmeasured · available

It shows both pictures at once with no mix, takes the outgoing picture to -1 canvas widths across and 0 heights down, brings the incoming one from 1 canvas widths across and -0 heights down to rest, blurs the motion with a 720 degree shutter and shows nothing past the edge. A new one lasts 0.4 s.

**Use:** A fast camera swing: the two pictures sit side by side and the frame pans across them with a long blur, so half of one and half of the other are on screen at the middle. Energy for sport, tech, ads and beat cuts.

**Found by:** whip, whip pan, swish, swish pan, fast, quick, speed, pan, left, right, tilt, up, down, سريع, خاطف, سحب سريع, سرعة, بان, يسار, يمين, تيلت, أعلى, أسفل, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=40 (on a cut between two layers)`

- `strength` (number, times): 1 to 2.5, default 1.15
- `blur` (number, degrees): 0 to 1440, default 720
- `direction` (choice, none): 0 to 3, default 0 [Left, Right, Up, Down]

## Wipe

### Wipe — `transition:100`

Wipe · cost unmeasured · available

Changes from the first picture to the second along an edge that crosses the canvas in a straight line; the change's edge is soft, and may glow. A new one lasts 0.7 s.

**Use:** The next shot slides over the first behind a straight edge that crosses the frame: a clean, graphic change for lists, before and after, and steps of a story. A soft edge feels calm; a hard one with a glow feels energetic.

**Found by:** wipe, linear wipe, slide in, reveal, edge, line, مسح, مسح خطي, كشف, حافة, خط, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=100 (on a cut between two layers)`

- `angle` (number, degrees): 0 to 345, default 0
- `softness` (number, percent): 0 to 50, default 6
- `glow` (number, percent): 0 to 100, default 0

### Clock Wipe — `transition:102`

Wipe · cost unmeasured · available

Changes from the first picture to the second along a hand that turns once round a point, as a clock's does; the change's edge is soft, and may glow. A new one lasts 0.7 s.

**Use:** A hand sweeps once round a point like a clock's, the next shot behind it: for time passing, countdowns and steps. Start it where the eye rests; a hard edge reads as a timer, a soft one as a gentle turn.

**Found by:** clock, clock wipe, radial wipe, sweep, timer, countdown, hand, ساعة, مسح دائري, عقرب, عد تنازلي, مؤقت, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=102 (on a cut between two layers)`

- `start` (number, degrees): 0 to 345, default 270
- `direction` (choice, none): 0 to 1, default 0 [Clockwise, Counter-clockwise]
- `centre_x` (number, percent): 0 to 100, default 50
- `centre_y` (number, percent): 0 to 100, default 50
- `softness` (number, percent): 0 to 50, default 3
- `glow` (number, percent): 0 to 100, default 0

### Blinds — `transition:103`

Wipe · cost unmeasured · available

Changes from the first picture to the second along bands across the canvas, each crossed at once; the change's edge is soft, and may glow. A new one lasts 0.7 s.

**Use:** The next shot shows through bands that each open at once, like blinds: a rhythmic, graphic change for upbeat edits and product shots. More bands feel faster.

**Found by:** blinds, venetian blinds, stripes, bands, slats, shutters, ستائر, شرائح, خطوط, أشرطة, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=103 (on a cut between two layers)`

- `angle` (number, degrees): 0 to 345, default 0
- `count` (number, none): 2 to 40, default 8
- `softness` (number, percent): 0 to 50, default 4
- `glow` (number, percent): 0 to 100, default 0

## Shape

### Iris — `transition:101`

Shape · cost unmeasured · available

Changes from the first picture to the second along a circle that opens from a point, or closes to it; the change's edge is soft, and may glow. A new one lasts 0.7 s.

**Use:** A circle opens from a point to show the next shot, or closes to it on the first: the classic iris of silent films, playful today. Put the centre on what the next shot is about.

**Found by:** iris, circle, circle wipe, open, close, spotlight, round, قزحية, دائرة, فتح, إغلاق, بقعة ضوء, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=101 (on a cut between two layers)`

- `direction` (choice, none): 0 to 1, default 0 [Open, Close]
- `centre_x` (number, percent): 0 to 100, default 50
- `centre_y` (number, percent): 0 to 100, default 50
- `softness` (number, percent): 0 to 50, default 4
- `glow` (number, percent): 0 to 100, default 0

### Shape Reveal — `transition:104`

Shape · cost unmeasured · available

Changes from the first picture to the second along a shape that grows from a point until it covers the canvas; the change's edge is soft, and may glow. A new one lasts 0.7 s.

**Use:** A shape grows from a point until the next shot fills the frame: a star for a celebration, a diamond or a hexagon for a brand, a square for a clean tech look. Turn it and place it on the subject.

**Found by:** shape, shape reveal, star, diamond, square, hexagon, circle, mask, grow, شكل, كشف, نجمة, معين, مربع, سداسي, دائرة, قناع, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=104 (on a cut between two layers)`

- `shape` (choice, none): 0 to 4, default 3 [Circle, Square, Diamond, Star, Hexagon]
- `rotation` (number, degrees): -180 to 180, default 0
- `centre_x` (number, percent): 0 to 100, default 50
- `centre_y` (number, percent): 0 to 100, default 50
- `softness` (number, percent): 0 to 50, default 3
- `glow` (number, percent): 0 to 100, default 0

## Dissolve

### Luma Fade — `transition:105`

Dissolve · cost unmeasured · available

Changes from the first picture to the second along the brightness of a picture, its brightest places first; the change's edge is soft, and may glow. A new one lasts 1 s.

**Use:** The next shot appears first in its brightest places and last in its shadows (or the other way): a dreamy, organic dissolve that follows the light of the picture. Best on shots with clear light and dark.

**Found by:** luma, luma fade, luminance, brightness, light, dreamy, fade, إضاءة, سطوع, ضوء, تلاشي, حالم, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=105 (on a cut between two layers)`

- `order` (choice, none): 0 to 1, default 0 [Bright first, Dark first]
- `softness` (number, percent): 0 to 50, default 20

### Noise Dissolve — `transition:106`

Dissolve · cost unmeasured · available

Changes from the first picture to the second along grains of noise, each changing at its own moment; the change's edge is soft, and may glow. A new one lasts 0.9 s.

**Use:** The next shot appears in grains scattered over the frame, each at its own moment: a textured, slightly gritty dissolve for music, fashion and retro edits. Larger grains read as blotches, small ones as dust.

**Found by:** noise, noise dissolve, grain, pixel dissolve, particles, organic, texture, حبيبات, ضجيج, تلاشي, ملمس, جزيئات, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=106 (on a cut between two layers)`

- `grain` (number, percent): 0.5 to 20, default 3
- `softness` (number, percent): 0 to 50, default 10

### Blur Dissolve — `transition:108`

Dissolve · cost unmeasured · available

Mixes the two pictures in light-linear values, so there is no dip of brightness in the middle, blurring them as they cross. A new one lasts 0.9 s.

**Use:** The two shots blur as they dissolve and sharpen again: a soft, dreamy change, as if the lens lost focus and found it on the next shot. For calm edits, memories and changes of place.

**Found by:** blur, blur dissolve, defocus, soft, dreamy, out of focus, fade, ضبابي, تشويش, تلاشي, حالم, ناعم, خارج التركيز, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=108 (on a cut between two layers)`

- `blur` (number, percent): 0.5 to 10, default 3

## Light

### Flash — `transition:107`

Light · cost unmeasured · available

Mixes the two pictures in light-linear values, so there is no dip of brightness in the middle, with a burst of light at the change. A new one lasts 0.6 s.

**Use:** A burst of light hides the change: the first shot brightens to white, the next one comes out of it. For beats, reveals and energetic cuts; a short one reads as a camera flash.

**Found by:** flash, white flash, camera flash, burst, bright, light, pop, وميض, فلاش, ومضة, ضوء, سطوع, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=107 (on a cut between two layers)`

- `strength` (number, none): 0 to 6, default 3
- `cut` (number, percent): 2 to 100, default 20

### Light Leak — `transition:109`

Light · cost unmeasured · available

Dissolves the two pictures in light under a warm light that sweeps across the frame. A new one lasts 1.2 s.

**Use:** A warm light sweeps across the frame as the shots dissolve, like light leaking into a film camera: nostalgic, warm and cinematic. For travel, weddings, music and memories.

**Found by:** light leak, leak, film, warm, glow, flare, vintage, analog, تسرب ضوئي, ضوء, فيلم, دافئ, توهج, كلاسيكي, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=109 (on a cut between two layers)`

- `strength` (number, percent): 0 to 300, default 180

## Glitch

### Glitch — `transition:110`

Glitch · cost unmeasured · available

Tears the change into slices that jump sideways, the colours read apart, then settles on the second picture. A new one lasts 0.5 s.

**Use:** The picture tears into slices that jump sideways with its colours read apart, then lands on the next shot: a digital, edgy change for tech, gaming, music and fast edits. Keep it short.

**Found by:** glitch, digital, rgb split, error, tear, distortion, cyber, tech, تشويش رقمي, خلل, رقمي, تمزق, تقني, سايبر, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=110 (on a cut between two layers)`

- `strength` (number, percent): 0 to 100, default 70
- `split` (number, percent): 0 to 100, default 50

## Warp

### Swirl — `transition:111`

Warp · cost unmeasured · available

Twists or ripples both pictures about a point as they dissolve into each other, then lets them settle. A new one lasts 0.9 s.

**Use:** Both shots twist into a whirl about a point as they dissolve, then untwist: a playful, magical change for fun, kids and dream sequences.

**Found by:** swirl, twirl, twist, vortex, spiral, whirlpool, warp, دوامة, التواء, لف, حلزون, إعصار, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=111 (on a cut between two layers)`

- `twist` (number, degrees): 0 to 1440, default 540
- `centre_x` (number, percent): 0 to 100, default 50
- `centre_y` (number, percent): 0 to 100, default 50

### Ripple — `transition:112`

Warp · cost unmeasured · available

Twists or ripples both pictures about a point as they dissolve into each other, then lets them settle. A new one lasts 1 s.

**Use:** Rings run out from a point like a stone dropped in water, carrying the change: a soft, liquid transition for dreams, flashbacks and calm reveals.

**Found by:** ripple, wave, water, liquid, rings, dream, warp, تموج, موجة, ماء, سائل, حلقات, حلم, transition, cut, between clips, انتقال, انتقالات, قطع, بين المقاطع

**Add:** `transition.add kind=112 (on a cut between two layers)`

- `height` (number, percent): 0 to 10, default 2.5
- `centre_x` (number, percent): 0 to 100, default 50
- `centre_y` (number, percent): 0 to 100, default 50

