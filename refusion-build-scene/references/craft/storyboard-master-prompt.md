# Writing the master prompt of a storyboard

A storyboard is many pictures of one model in one style, made from one text: the **master prompt**. You write the text; the person pastes it into the Storyboard sheet of Refusion (the section of the project's bar, beside Image and Video), puts in a reference picture, chooses the model, the size and the quality, and presses **Set**. The engine splits your text into images by fixed rules, so write it in exactly this form. Setting and generating are the person's: the storyboard's tools are not offered to an assistant, so your work is the text and nothing else.

## The form

```
<The general description: the look, the character, the colours, what to avoid.>

Image 1:
Title: <two to five words>
<The complete prompt of image 1.>
Narration: <the line of the voice-over this image illustrates>

Image 2:
Title: <two to five words>
<The complete prompt of image 2.>
Narration: <the next line of the voice-over>
```

- **Everything before `Image 1:` is the general description.** The engine puts it before every image's prompt.
- **An image begins on a line of its own** with `Image`, then its number, then a colon: `Image 7:`. The numbers run 1, 2, 3 in order with none left out; the engine refuses a text where an image is missing, so it can never lose one quietly. Do not begin any other line with the word Image, Frame, Scene or Shot followed by a number.
- **`Title:` is one line** (optional). It names the picture's file, so make it short and plain.
- **`Narration:` is optional** and may run over more than one line. It is the part of the voice-over the picture illustrates, in the voice-over's own language and in the script's order, so the pictures can later be put at the right time. Together the narration lines should cover the whole script, in order, with nothing repeated.
- Plain text only: no tables, no commentary between images, no markdown headings. Deliver the whole text in one block the person can copy.

## The general description

It is read before every image, and every image is made on its own: **the model remembers nothing from one picture to the next.** So put in it everything that must stay the same:

- the medium and the way it is drawn (a black marker line on white paper, flat colour, soft watercolour);
- the palette and the background;
- how each recurring character is drawn, in a few fixed words, and what to call it (the stickman, the king with the crown);
- what must never appear (text, letters, logos, a watermark, shading, other colours).

Keep it short, 40 to 120 words. The person's reference picture sets the look; this text says what to keep from it. Do not put the shape or size of the picture here: the sheet's size field decides it.

## Each image's prompt

Make each one complete. The model sees only the general description and this prompt.

- **One idea per image.** Subject, action, place, where the camera is, the feeling. Concrete things the model can draw: "the stickman holds a small wooden boat above his head, waves behind him", not "the struggle of man against nature".
- **Never lean on another image.** Not "the same man again", "as before", "next to the previous scene". Repeat the character's fixed words and the place every time.
- **Vary the picture, keep the look.** Change the distance (wide, close), the angle and the arrangement from image to image so the sequence does not feel like one picture repeated; do not change the style.
- **40 to 120 words** is usually right. The general description and one image's prompt are sent together, and a model takes a limited number of characters: the sheet tells the person when one image is too long, so keep every prompt well inside a few hundred words.
- **Write the prompt in English**, even when the voice-over is Arabic: models follow English most closely. Keep the `Narration:` in the voice-over's language. Never ask for words or letters inside the picture.

## How many images

One image for each beat of the script. At a normal speaking pace (about 150 words a minute, two and a half words a second) a picture that stays 5 to 8 seconds holds 12 to 20 words; a quick, busy piece changes every 3 to 4 seconds. Divide the script into beats first, one idea each, then write one image for each. Never more than 200 in one storyboard; if the script needs more, make two storyboards.

## Before you hand it over

- The general description holds the look and the fixed characters, and says what to avoid.
- The numbers run 1 to N without a gap, and each begins its own line.
- Every prompt can be understood alone, and none says "again" or "as before".
- Every narration line is the voice-over's own words, in order, and the lines cover the script.
- Nothing asks for text in the picture.

## An example

```
Hand-drawn documentary illustration: a thick black marker line on warm white paper, flat and simple, no shading, no colour except one muted red used for emphasis. The stickman has a round head, two dot eyes and no mouth; the king stickman wears a small crown. No text, no letters, no logos, no watermark.

Image 1:
Title: The lonely hill
A wide shot of a bare hill under a low sun, one stickman standing small on its top, a thin line of the horizon behind him.
Narration: In the beginning there was only one man, and a hill.

Image 2:
Title: The first boat
A close view of the stickman kneeling and fitting planks together into a small wooden boat, tools scattered on the paper around him.
Narration: He decided to build a boat.

Image 3:
Title: The king arrives
The king stickman with his small crown stands on a shore, his arm raised toward a distant sail, a few simple waves in front of him.
Narration: And one day a king saw the sail from his shore.
```
