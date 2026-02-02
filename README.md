# Hit Thunder

> Name origin: “Hit Thunder” is a deliberately grammar-breaking literal translation of the Korean slang “벼락치기” (cramming).

Two single-file study tools I built for my own exam prep.

I originally hacked these together in a “vibe-coding” sprint. They’re not polished, but after using them for a while I found them genuinely useful, so I’m sharing them.

The world is changing fast, but we still get judged by overfitted, old-school exams in a lot of places. This repo is my attempt to make those exams easier to *systematically* grind through: structure your study guide, practice by filters, keep memos/tags/history, and iterate.

## What’s in here

- `index.html`: a simple landing page (useful for GitHub Pages).
- `renderer.html` (**Hit Thunder Renderer**): a guide viewer + exam-style practice workspace.
- `guide_maker.html` (**Hit Thunder Guide Maker**): the core tool that turns exam PDFs/TXT into a renderer-readable guide (and problems JSON).
- `example_en.txt`, `example_ko.txt`: example guides (they auto-load based on UI language when no guide is saved).

## Quick start

### Option 0: just double-click it
You can usually run it by double-clicking `index.html` (or `renderer.html` / `guide_maker.html`).

If your browser blocks `fetch()` on `file://`, use a local server (below).

### Option 0.5: test via GitHub Pages
If GitHub Pages is enabled for this repo, you can also open:

https://pineapplesour.github.io/Hit-Thunder/

## Workflow (Guide Maker → Renderer)

### 1) Build a guide from exam files
Open `guide_maker.html` and just drop your past-exam files:

- PDF: runs OCR in-browser, then splits questions and builds a study guide.
- TXT: uses the text directly (no OCR).

When it finishes, download either:

- **One-file import (recommended):** a renderer save file (`.json`) you can import in one shot.
- Or download **guide** (`.txt`) and **type problems** (`.json`) separately (still supported).

### 2) Use it in the renderer
Open `renderer.html`, then choose one:

- **One-file import:** `⭱ Import` → select the save file JSON exported by the Guide Maker.
- **Separate import:** `📑 Guide` → load the guide text, then `📂 Problems` → load the problems JSON.

## Renderer buttons (high level)

- `📑 Guide`: load/replace the guide text file.
- `📂 Problems`: load the type problems JSON (for Solve/Stats).
- `🧩 Solve`: practice in an exam-like flow (sessions, grading, notes).
- `📊 Stats`: filter by tags/history and collect review sets.
- `⭳ Export` / `⭱ Import`: backup/restore everything (including guide/problems/memos/history).
- `A- / A+` and `⇔` width controls: adjust readability (useful on mobile).

### Option A (recommended): run a tiny local web server
Some browsers restrict `fetch()` when opening HTML files via `file://`. A local server avoids that.

```bash
cd Hit-Thunder
python -m http.server 8000
```

Then open:

- `http://localhost:8000/` (landing page)

### Option B: open the HTML directly
You can still open `renderer.html` directly and load a guide using the “Guide” button.

## Privacy & safety notes

- By default, everything is stored locally in your browser (localStorage/sessionStorage/IndexedDB).
- If you enable LLM features (in `renderer.html` / `guide_maker.html`), the content you’re working with will be sent to the endpoint you configure. Don’t paste secrets.
- Exports can contain your notes/history. Treat exported files as sensitive if your notes are sensitive.

## License

MIT — see `LICENSE`.
