# Astral Trek

Star Trek-style episodes in the Astral Garden. The storyline's rules, ship and crew are in `storyline.md`; the prompt for the next episode is `prompt.md`.

## Generating an episode

Paste this into an AI chat that can open web links and, ideally, generate images:

```
Read this file and follow its instructions exactly. It links to three more files: read those completely too before you start writing.

https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md
```

If the AI can't open links, attach or paste the prompt and the three files it links to instead (listed below).

Save the AI's `new.tar` in `drafts/`, unpack it there with `tar xf new.tar`, and tell Claude "add draft". If the AI can't make a tar file, save its whole reply as `drafts/new.md` and its images in `drafts/new-images/` instead. The rest of the process is in `../../workflow.md`.

## GitHub URLs

AIs read the files straight from GitHub, so pushing to `main` is what publishes a change:

- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/prompt.md (give this one to the AI)
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/bible.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines.md
- https://raw.githubusercontent.com/scott-steadman/astral-garden/main/storylines/astral-trek/storyline.md

## Files

| Path | What it is |
| --- | --- |
| `storyline.md` | Format, timeline, tone, what people know, ship, captain and mascot traits, episodes, arcs, required images, the writer's self-check, end-of-episode sections. |
| `prompt.md` | The prompt for the next episode. Holds only what is specific to that episode. |
| `drafts/` | Candidate drafts, one per AI run: `new.md` until Claude renames it `NN-model.md`, with its images in `NN-model-images/` and a reading copy in `NN-model.pdf`. A kept draft is a symlink into `episodes/`. A losing draft normally keeps only its PDF, not its images folder. |
| `episodes/` | Episodes Scott keeps, named `NN-title-slug.md`, with images in `NN-title-slug-images/` and a reading copy in `NN-title-slug.pdf`. |
