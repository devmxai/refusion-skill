# Refusion skill

A skill that teaches an AI assistant to design, build and polish video in the Refusion project that is open on your phone: titles, captions, ads and motion graphics, backgrounds, shapes and text (Arabic included), entrances and exits, timing and rhythm, effects, looks and transitions. The tools themselves come from the Refusion engine, through its connector or its local `rpro-mcp` and CLI; the engine teaches the assistant each tool through its own guide.

## Install

| You use | How |
|---|---|
| **Claude on the web or the desktop app** | Download [`refusion-build-scene.zip`](https://github.com/devmxai/refusion-skill/releases/latest/download/refusion-build-scene.zip) from the latest release. In Claude: **Customize > Skills**, upload the zip and turn the skill on. Skills need a paid plan and **Code execution and file creation** turned on under **Settings > Capabilities**. |
| **Claude Code** | Copy the folder `refusion-build-scene/` into `~/.claude/skills/` (for every project) or into `.claude/skills/` of a project. No zip is needed. |
| **Another assistant** | `refusion-build-scene/SKILL.md` is plain Markdown; where an assistant has a place for custom instructions, give it that text and the files it links. |

Then connect the assistant to Refusion:

1. In Refusion, open the account screen and turn on **Agent link** (the connector). The app shows the connector's address and the link to this page.
2. In Claude on the web or the desktop app: **Customize > Connectors > Add custom connector**, paste the address (`https://relay.fusionlab.pro/mcp`) and sign in with the Google account Refusion uses.
3. Ask for something, for example: "Make a six second title card with a gradient background and an animated entrance."

The connector works with any assistant that can add a remote MCP server. ChatGPT and Gemini have not been tried yet.

## What is inside

```
refusion-build-scene/
  SKILL.md                 the way of working, loaded when the skill is used
  references/craft/        how a piece is directed, timed, choreographed and judged;
                           which preset, recipe, effect or transition fits which job;
                           the defaults an assistant falls into; how to look at the result
  references/engine/       an index of the engine (tools, effects, looks, transitions,
                           ready-made motion, recipes), written by the Refusion build
  examples/                three worked plans
```

- **The craft** (`SKILL.md`, `references/craft/`, `examples/`) is written by people. It is guidance: it does not give an assistant a capability the tools lack.
- **The index of the engine** (`references/engine/`) is written by the Refusion build from the engine itself, and each file carries the catalog version it was written from. The engine is the truth: when a file and a reply of the engine differ, the reply is right. The build refuses to be saved while the index is not what the engine says.

## Keeping it current

A new feature in Refusion reaches this skill with the same change, as a new release. See [CHANGELOG.md](CHANGELOG.md). To update, download the new zip and upload it again (Claude Code: replace the folder).

## What it sends

See [PRIVACY.md](PRIVACY.md).

## License

Apache License 2.0, see [LICENSE](LICENSE). It covers the files of this repository.
