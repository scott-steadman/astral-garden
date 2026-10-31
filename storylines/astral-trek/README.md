# Astral Trek

Star Trek-style episodes in the Astral Garden. The storyline's rules, ship and crew are in `storyline.md`; the prompt for the next episode is `prompt.md`.

## Generating an episode

Paste this into an AI chat that can open web links:

```
Read this file and follow its instructions exactly. It links to three more files: read those completely too before you start writing.

https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md
```

If the AI can't open links, attach or paste the prompt and the three files it links to instead (listed below).

Save the AI's whole reply as `drafts/new.md` and tell Claude "add draft". The rest of the process is in `../../workflow.md`.

## GitHub URLs

AIs read the files straight from GitHub, so pushing to `main` is what publishes a change:

- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md (give this one to the AI)
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/bible.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/storyline.md

## Files

| Path | What it is |
| --- | --- |
| `storyline.md` | Format, timeline, tone, ship, captain's habits, Kono, episodes, arcs, end-of-episode sections. |
| `prompt.md` | The prompt for the next episode. Holds only what is specific to that episode. |
| `drafts/` | Candidate drafts, one per AI run: `new.md` until Claude renames it `NN-model.md`. A kept draft is a symlink into `episodes/`. |
| `episodes/` | Episodes Scott keeps, named `NN-title-slug.md`. |
