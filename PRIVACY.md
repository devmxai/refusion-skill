# Refusion connector: what is sent, and where

This page describes the Refusion connector (the Agent link in the app, the relay at `relay.fusionlab.pro`, and the Refusion skill) as it is built on 2026-10-25. It says what leaves your phone, who handles it, what is kept, and how to stop it.

## What it does

When you turn on **Agent link** in the Refusion app, your phone opens one outgoing connection to the Refusion relay. An agent app you connected (today, Claude) can then reach the project that is open on your phone through that relay. The relay is a pipe and an identity check: it does not edit, and it does not understand your project.

Nothing is reachable while Agent link is off.

## What leaves your phone

Only while Agent link is on, and only as answers to what the agent asks:

- **Descriptions of your project:** its size and length, the layers with their names, kinds, times and texts, tracks, scenes and the names of the media in your library.
- **Pictures of your project** drawn by Refusion at the times the agent asks. A picture of a scene that shows your footage shows frames of your footage.
- **Results of edits** the agent makes, and the reasons when an edit is refused.
- **When the connection starts:** the name and build number of the app, the platform, and the list of tools your phone offers.

The connector has no tool that reads a file from your phone by its path, uploads a file, deletes a project, or exports. It does not send your media files.

## Who handles it

- **Anthropic** receives what the tools return as part of your conversation with Claude, under your Claude plan's terms and your settings there.
- **The Refusion relay** runs on Cloudflare. Your agent's messages pass through it in memory while they wait for your phone's answer.
- **Sign-in** uses your Refusion (Fusionlab) account through Google. The relay learns your account id; it does not keep your Google or account tokens.

## What the relay keeps

- The sign-in records the connector needs to stay signed in: its registration, grants and tokens (tokens as hashes), under your account id.
- The last list of tools your phone offered, so Claude can list them while your phone is away.
- One log line for each call with its status and duration, and one line with only an error's name when the sign-in page fails. The lines have no account, no content and no project data. Cloudflare's own observability for the relay is switched off in its configuration.

It does not keep your project, the pictures, or the messages of the agent.

## Staying in control

- **Turn Agent link off** in the Refusion app: the connection closes and no agent can reach your project.
- **Cut off one assistant:** each assistant that is in is listed under Agent link with its calls; **Cut off** removes it until you turn the link off and on again.
- **Undo:** every batch of edits an agent makes is one step in Refusion's history; Undo takes it back.
- **Remove the connector in Claude** (Customize > Connectors) to stop Claude from using it. The relay does not yet have a page that lists or ends sign-ins; turning Agent link off is what makes your project unreachable.
- **What cannot be undone is not offered:** the agent is not given tools that clear the cache, close or delete a project, or export.

Questions or problems: open an issue in this repository.
