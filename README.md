# My Stories: the Astral Garden

Fiction set in **the Astral Garden**, a fantasy multiverse Scott designed. It mashes up D&D 5e with the post-scarcity flavor of Iain Banks' Culture: gods are gardeners who seed planes with races, souls are sovereign, ensouled ships carry the Astral Federation's Fleet across the astral sea, and devils and demons fight an endless Blood War. The running theme is **the role of reason in a world of magic**: problems get solved by someone understanding how a thing works.

The goal of the project is for AI (Claude and others) to write stories Scott wants to read, consistent with the world as designed.

## Layout

| Path | What it is |
| --- | --- |
| `bible.md` | The world bible. World-level rules only: the astral sea, gods, souls, magic, the Federation and Fleet, fiends, known planar systems. |
| `storylines.md` | Guidance for every story, open world questions, story hooks, and the index of formats and storylines. |
| `storylines/astral-trek/storyline.md` | Astral Trek's own notes: format, ship, captain's habits, Kono, tone, arcs, end-of-episode sections. |
| `storylines/astral-trek/prompt.md` | The Episode 1 prompt. Give any AI its GitHub URL; it points the AI at the bible and storyline files and holds only what is specific to this episode. |
| `todo.md` | Scott's open decisions and review passes. |
| `memory/` | Project memory: facts and preferences a new AI session needs. Start with `memory/README.md`. |
| `CLAUDE.md` | Instructions for AI agents working in this repo. |

## Formats

Every story belongs to a **storyline**, and every storyline belongs to one of five formats:

- **Short form**: a self-contained story, up to an hour's read (about 15,000 words max).
- **Episodic**: a series of short form episodes, with plots inside each episode and arcs across them. **Astral Trek** (Star Trek in the Astral Garden) is the first.
- **Long form**: a novella or novel.
- **Adventure**: a playable D&D 5e module, 1 to 3 sessions.
- **Campaign**: a long playable D&D 5e arc.

Each storyline has its own `storylines/<name>/storyline.md` file.

## Conventions

- **The bible holds world facts only.** Character- or story-specific details go in the storyline file.
- **Canon moves up on request.** Planar systems, villains and gadgets invented for a story live in that storyline's file, and move into the bible's *Known planar systems* only once Scott declares the story canon.
- **Open questions** in `storylines.md` are left for stories to answer; when one is answered, record it in the bible.
- **Terminology**: say "whole soul", never "un-sundered". *Shifting* is an instant move between ships or planes; *teleporting* is an instant move within one plane or ship; *portaling* (dimension door) opens a walk-through passage between ships or planes.
- **Story first.** Stories may later be adapted into D&D adventures, so keep them playable where it's free, but never let playability limit the story.

## GitHub URLs

AIs read the main files straight from GitHub, so there is nothing to upload separately:

- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/bible.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/storyline.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md (give this one to the AI)

## Generating an episode

Paste this into an AI chat that can open web links:

```
Read this file and follow its instructions exactly. It links to three more files: read those completely too before you start writing.

https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md
```

If the AI can't open links, attach or paste the prompt and the three files it links to (`bible.md`, `storylines.md`, `storylines/astral-trek/storyline.md`) instead.
