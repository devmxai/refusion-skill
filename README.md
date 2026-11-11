# Refusion skill

A skill that teaches an AI assistant to design, build and polish video in the Refusion project that is open on your phone: titles, captions, ads and motion graphics, backgrounds, shapes and text (Arabic included), entrances and exits, timing and rhythm, effects, looks and transitions. The tools themselves come from the Refusion engine, through its connector or its local `rpro-mcp` and CLI; the engine teaches the assistant each tool through its own guide.

## For an assistant given this link

If a person gives you this page and asks you to install the skill, do not build it from this repository's files. Take the file of the latest release, as it is: `https://github.com/devmxai/refusion-skill/releases/latest/download/refusion-build-scene.zip`. In Claude's apps, offer that file to the person to save as a skill (or tell them: **Customize > Skills**, upload it, turn it on). With a terminal, run `npx skills add devmxai/refusion-skill`. You do not need the skill to work on a Refusion project: the Refusion connector (`https://relay.fusionlab.pro/mcp`) carries the tools and the same craft (`guide.read`, topic `craft`).

## Install

| You use | How |
|---|---|
| **Claude Code** | `/plugin marketplace add devmxai/refusion-skill`, then `/plugin install refusion@refusion`. One install gives the skill and the Refusion connector; `/plugin` updates it. |
| **Any assistant with a terminal** (Claude Code, Codex, Cursor, Gemini CLI and others) | `npx skills add devmxai/refusion-skill` puts the skill where each assistant on the machine reads it. `npx skills update` keeps it current. |
| **Claude on the phone, the web or the desktop app** | Download [`refusion-build-scene.zip`](https://github.com/devmxai/refusion-skill/releases/latest/download/refusion-build-scene.zip) from the latest release. In Claude: **Customize > Skills**, upload the zip and turn the skill on. Skills need a paid plan and **Code execution and file creation** turned on under **Settings > Capabilities**. |
| **ChatGPT** | The same file: download [`refusion-build-scene.zip`](https://github.com/devmxai/refusion-skill/releases/latest/download/refusion-build-scene.zip), then in ChatGPT **Skills > Create > Upload from your computer**, where your plan has Skills. Without Skills: give a custom GPT the text of `SKILL.md` as its instructions and the pages it links as its knowledge. |
| **Another assistant** | `skills/refusion-build-scene/SKILL.md` is plain Markdown; where an assistant has a place for custom instructions, give it that text and the files it links. |

The skill is read where it is installed, never fetched from this page during a conversation: an installed skill is known to the assistant from the start and opened when it is needed, one page at a time. Each copy says its release (`Skill version` in `SKILL.md`). The engine names the release it was built with (`session.handshake`, `skill_version`), and its guide (`guide.read`, the `craft:` pages) carries the same craft, so an assistant connected to Refusion has it even before the skill is updated.

Then connect the assistant to Refusion:

1. In Refusion, open the account screen and turn on **Agent link** (the connector). The app shows the connector's address and the link to this page.
2. In Claude on the web or the desktop app: **Customize > Connectors > Add custom connector**, paste the address (`https://relay.fusionlab.pro/mcp`) and sign in with the Google account Refusion uses.
3. Ask for something, for example: "Make a six second title card with a gradient background and an animated entrance."

The connector works with any assistant that can add a remote MCP server. ChatGPT and Gemini have not been tried yet.

## What is inside

```
skills/refusion-build-scene/
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

A new feature in Refusion reaches this skill with the same change, as a new release. See [CHANGELOG.md](CHANGELOG.md). To update: `npx skills update`, or `/plugin` in Claude Code, or download the new zip and upload it again in Claude.

## What it sends

See [PRIVACY.md](PRIVACY.md).

## License

Apache License 2.0, see [LICENSE](LICENSE). It covers the files of this repository.
