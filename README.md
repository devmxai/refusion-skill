# Refusion skill

A skill that teaches an AI assistant to design, build and polish video in the Refusion project that is open on your phone: titles, captions, ads and motion graphics, backgrounds, shapes and text (Arabic included), entrances and exits, timing and rhythm, effects, looks and transitions. The tools themselves come from the Refusion connector (or the local `rpro-mcp` and CLI), and the engine teaches the assistant each tool through its own guide.

The skill is one folder, `refusion-build-scene/`, in the open [Agent Skills](https://agentskills.io/specification) format. It holds two kinds of file:

- **The craft** (`SKILL.md` and `references/craft/`, `examples/`), written by people: how a piece is directed, timed, choreographed and judged, which preset, recipe, effect or transition fits which job, the defaults an assistant falls into, and how to look at the result.
- **An index of the engine** (`references/engine/`), written by the Refusion build from the engine itself: the tools an assistant is offered, the effects, looks, transitions, ready-made motion and recipes, with what each does and its settings. No line of it is typed by hand.

## Use it with Claude

1. In Refusion, open the account screen and turn on **Agent link**. The app shows the connector's address and the link to this page.
2. In Claude on the web or in the desktop app: **Customize > Connectors > Add custom connector**, paste the address (`https://relay.fusionlab.pro/mcp`) and sign in with the Google account Refusion uses.
3. Download `refusion-build-scene.zip` from the [latest release](../../releases/latest).
4. In Claude on the web or in the desktop app: **Customize > Skills**, upload the zip and turn the skill on. Skills need a paid Claude plan and **Code execution and file creation** turned on under **Settings > Capabilities**.
5. Ask for something, for example: "Make a six second title card with a gradient background and an animated entrance."

Connectors and skills are managed on the web or in the desktop app. The Claude mobile app uses what is on your account; whether it loads this skill has not been checked here.

## Other assistants

The connector works with any assistant that can add a remote MCP server, and its guide carries the workflow. ChatGPT and Gemini have not been tried yet. `SKILL.md` is plain Markdown; where an assistant has a place for custom instructions, its text can be given there.

## Keeping it current

The index of the engine is rewritten by the Refusion build (`rpro skill-reference --write`), and the build refuses to be saved while the index is not what the engine says, so a tool, an effect or a preset added in Refusion reaches this skill with the same change. The craft changes when a way of working is learned, and each published change is a new release. To update, download the new zip and upload it again.

## What it sends

See [PRIVACY.md](PRIVACY.md).
