# Paralight Agent Skill

**A single-file filmmaking guide for AI agents working in [Paralight](https://paralight.ai).**

Help an agent turn a story into a coherent movie—or finish a project that already has footage—with consistent characters, deliberate coverage, readable motion, and thoughtful sound.

The complete skill is in **[SKILL.md](SKILL.md)**. The README explains how to use it; no extra reference files are required.

## What it helps with

- Develop a logline and screenplay with Guided Story Builder.
- Establish cast, props, locations, and visual continuity.
- Plan scenes and shots that cut together.
- Review generated images and video before advancing.
- Find and download finished **scene cut** videos through Make Movie Guide → Media.
- Assemble existing footage while preserving dialogue and source files.
- Add scene-aware effects, ambience, and music, including lo-fi hip-hop.
- Verify a render and prepare a clear delivery or publication handoff.

It supports both a full filmmaking workflow and narrow tasks such as “combine these four cuts.” It tells agents to continue from the actual project state instead of regenerating work that is already complete.

## Quick start

Give your agent the contents of [SKILL.md](SKILL.md), access to its supported browser-control tool, and a project link. Sign in to Paralight in that browser yourself.

Then ask:

> Use the Paralight skill to inspect this project: [project URL]. Continue from its current state, preserve approved characters and locations, and finish the missing scenes. Show me the displayed cost before any paid generation.

Or, for an existing edit:

> Open Make Movie Guide → Media. Download these finished scene cuts in story order: [scene names]. Assemble them, preserve dialogue, and add subtle location effects with a mellow lo-fi hip-hop score. Deliver an MP4 and the audio stems.

## Install as a Codex skill

Clone this repository and copy its single skill file into a skill directory:

```sh
git clone https://github.com/pdxor/paralight-agent-skill.git
mkdir -p "$HOME/.codex/skills/use-paralight"
cp paralight-agent-skill/SKILL.md "$HOME/.codex/skills/use-paralight/SKILL.md"
```

If that destination already contains a customized skill, back it up or merge changes before copying. Reload your agent's skill discovery if needed, then invoke `$use-paralight` or ask for a Paralight filmmaking task.

For other agent systems, place the file where they load skills or attach it as instructions. The workflow is portable Markdown; browser tools and installation conventions vary by agent.

## Requirements and scope

- A Paralight account and authorized access to the project.
- A browser automation tool available to the agent, or an authorized integration with equivalent capabilities.
- Optional local editing tools such as FFmpeg for exported-video assembly and audio mixing.
- Credits when the chosen Paralight actions require them.

This repository supplies guidance, **not a Paralight API client, browser extension, model, or media-generation service**. It does not bypass authentication or credit charges. Agents must inspect the live UI and follow their own tool and permission rules.

## Why this workflow

The guide combines story development with practical production discipline: lock identity and geography before coverage, review source assets before animating, repair upstream continuity problems, preserve dialogue while scoring, and verify the delivered file.

It also covers common automation traps: multiple video thumbnails on a page, media links opening instead of downloading, incomplete MP4 transfers that still expose metadata, newest-first asset lists, duplicate paid retries, and mistaking contact sheets for a full playback review.

## Example requests

**Develop a film**

> Build a restrained mystery about a vineyard caretaker who recognizes a stranger from a photograph taken fifty years earlier. Develop the screenplay first, then establish the cast and locations before planning shots.

**Review continuity**

> Audit this project's selected shots for character identity, wardrobe, eyelines, screen direction, and lighting. Return the smallest repair plan; do not regenerate anything yet.

**Finish the sound**

> Preserve all dialogue and add a warm 78 BPM lo-fi hip-hop instrumental. Keep the exterior ambience airy and the cellar quiet and resonant. Duck the score under speech and export separate music and effects stems.

**Prepare a release**

> Review the finished film, prepare a title, logline, description, and genre tags, and show me the publication package before publishing.

## Source and maintenance

Consolidated from the author's existing `use-paralight` skill and `Paralight Excellence Playbook`, with practical export, audio, verification, and recovery guidance added. The core and detailed playbook are now maintained together in one `SKILL.md`.

The Make Movie Guide → Media → Videos / The edit navigation was observed in October 2026. UI labels and product capabilities can change; the agent should always inspect current state. The whole filmmaking pipeline has not been independently tested across every account or agent host.

This is an independent community resource, not official Paralight documentation. No private project footage, screenplay, access tokens, or signed media links are included.

To contribute, describe the task, observed UI behavior, and reusable correction. Remove project identifiers and private media URLs from examples. Keep the operating instructions self-contained in `SKILL.md`.
