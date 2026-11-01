# Arabic and text

Refusion shapes text itself, Arabic and other right-to-left scripts included. Your part is to give it the text as the user wrote it, choose a font that has the letters, and move the words in a way that keeps them whole.

- **Give the text as written.** Type Arabic in its normal logical order. Never reverse the letters, never insert presentation forms or invisible marks to fix the look. The engine joins the letters and orders mixed Arabic and English.
- **Choose the font from the catalog.** Read the families with `font.catalog` and a script filter for Arabic (script 2; Latin is 1). Do not name a family you have not found there. If a font has no glyph for the script, the engine substitutes one; `font.resolve` says which, and `render.look` shows it.
- **Move Arabic by word.** The letters of a joined script stay joined, so a letter-by-letter entrance moves the whole word. Use a word unit, not a letter unit, for Arabic.
- **Mixed text.** For Arabic with English words or numbers, look at the picture: the order of the pieces in the line is what the viewer reads. Fix the text, not the letters.
- **Size and room.** Arabic often needs a slightly larger size than Latin text to read as equally strong, and more room for its line. `scene.layout` reports text that is too small (`text_below_legible`), that leaves the canvas or the safe area, and two texts that overlap by the lines they ink; fix those before anything else. `guide.read` with the topic `checks` explains each check; do not guess the numbers.
- **Reading time.** A line in Arabic competes with the eye's travel from the right; give it its full reading time ([timing.md](timing.md)) and do not shorten the hold to fit more words.
- **Captions.** Captions are a layer of their own with cues of words and times (`caption.create`; `guide.read` topic `text`). Their timing belongs to the speech; do not stretch a caption to fill space.
- **Write for the viewer.** Keep on-screen Arabic short and in the register the user used. Do not translate the user's wording unless they ask.

A highlighter sweeping a word goes along the way the text reads, so an Arabic word is swept from its right (`recipes:highlighter`). A card sized to its text follows an Arabic line as it does an English one (`recipes:card-sized-to-text` has both).
