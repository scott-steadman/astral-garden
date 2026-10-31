# Story workflow

How an AI draft becomes canon, for any storyline. Scott makes three decisions (the winner, which characters to keep, what becomes world canon); Claude does the rest.

Each storyline lives in `storylines/<name>/` with its `storyline.md`, its `prompt.md`, a `drafts/` folder and an `episodes/` folder (a short-form storyline just has one story, numbered `01`). The storyline's own `README.md` has the text to paste into an AI. Examples below use Astral Trek (`storylines/astral-trek/`).

## 1. Add a draft

1. Scott pastes the text from the storyline's `README.md` into an AI and saves its whole reply, end sections included, as `storylines/<name>/drafts/new.md`.
2. Scott tells Claude "add draft". Claude:
   - reads the *Metadata* table and renames the file `drafts/NN-model.md`: `NN` is the two-digit episode number (from the *Episode* row, or else from `prompt.md`), `model` is the *Model* row as a lowercase slug (`Claude Opus 5.5` → `claude-opus-5-5`). If the name is taken, it adds `-b`, `-c`. If the model is "unknown", Claude asks Scott which model it was.
   - checks the draft against the rules: length, the prompt's required characters and scenes, terminology, and the end sections the storyline file asks for. Problems are reported, not fixed.
   - commits the draft.

## 2. Choose a winner

1. With several drafts for an episode, Scott asks Claude to compare them. Claude builds a side-by-side table from the *Metadata* sections: logline, word count, point of view, new canon, open threads, and any rule problems.
2. Scott reads the ones they like and names the winner.

## 3. Keep it

Claude moves the winner to `episodes/NN-title-slug.md` (slug from its title) and leaves a relative symlink in its place, so the kept file's raw GitHub URL works (raw URLs don't follow symlinks):

```
cd storylines/astral-trek
git mv drafts/01-claude-opus-5-5.md episodes/01-the-golden-door.md
ln -s ../episodes/01-the-golden-door.md drafts/01-claude-opus-5-5.md
```

Losing drafts stay in `drafts/`, for comparing how models handle the same prompt. The kept episode keeps its end sections, as a record of where each fact came from.

## 4. Incorporate it

Claude reads the winner's end sections and gives Scott one checklist. Scott approves, edits or strikes each item before Claude changes any file.

- **`storyline.md`**
  - An *Episodes* entry: title, logline, stardates, file.
  - **Characters to keep**: Claude proposes the recurring cast; Scott picks. Kept characters get entries built from *Character details*.
  - Storyline-only canon (planar systems, villains, gadgets), each in its own section.
  - **Arcs**: Claude suggests arcs from the open threads and from plots that span episodes; Scott approves.
  - **Contradictions**: anything the draft marked as contradicting the storyline file, for Scott to rule on.
- **`storylines.md`**
  - The storyline's status line.
  - Any open world question or hook the story settled: the answer goes to the bible and the question comes off the list.
- **`bible.md`**: only items marked **world-level** that Scott declares canon. Everything else stays in the storyline file.

## 5. Prepare the next episode

Claude updates `prompt.md` for the next episode (its number, the arc it continues, required characters and scenes, anything Scott wants to steer), updates `todo.md`, and commits and pushes. Earlier prompts live on in git history.
