# Refusion skill

A skill that teaches an AI assistant how to build and polish video scenes in the Refusion project that is open on your phone: titles, captions, backgrounds, shapes and animated motion, in Arabic or any language Refusion shapes. It is the way of working. The tools themselves come from the Refusion connector, and the engine teaches the assistant each tool through the connector's own guide, so new features reach the assistant without this skill changing.

The skill is one folder, `refusion-build-scene/`, in the open [Agent Skills](https://agentskills.io/specification) format.

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

The skill stays short on purpose: it holds the way of working and quality rules, never the list of tools, so a new feature in Refusion does not need a new skill. It changes when a new craft needs explaining, and each change is a new release. To update, download the new zip and upload it again.

## What it sends

See [PRIVACY.md](PRIVACY.md).
