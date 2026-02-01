# Hit Thunder

> Name origin: “Hit Thunder” is a deliberately grammar-breaking literal translation of the Korean slang “벼락치기” (cramming).

Two single-file study tools I built for my own exam prep.

I originally hacked these together in a “vibe-coding” sprint. They’re not polished, but after using them for a while I found them genuinely useful, so I’m sharing them.

The world is changing fast, but we still get judged by overfitted, old-school exams in a lot of places. This repo is my attempt to make those exams easier to *systematically* grind through: structure your study guide, practice by filters, keep memos/tags/history, and iterate.

## What’s in here

- `index.html`: a simple landing page (useful for GitHub Pages).
- `renderer.html`: a Markdown + LaTeX guide viewer with an exam-style practice mode.
- `summary.html`: the core guide-building tool that generates/refines the exact guide format `renderer.html` reads.
- `example_en.txt`, `example_ko.txt`: example guides (they auto-load based on UI language when no guide is saved).

## Quick start

### Option 0: just double-click it
You can usually run it by double-clicking `index.html` (or `renderer.html` / `summary.html`).

If your browser blocks `fetch()` on `file://`, use a local server (below).

### Option A (recommended): run a tiny local web server
Some browsers restrict `fetch()` when opening HTML files via `file://`. A local server avoids that.

```bash
cd exam-study-workbench
python -m http.server 8000
```

Then open:

- `http://localhost:8000/` (landing page)

### Option B: open the HTML directly
You can still open `renderer.html` directly and load a guide using the “Guide” button.

## Privacy & safety notes

- By default, everything is stored locally in your browser (localStorage/sessionStorage/IndexedDB).
- If you enable LLM features (in `renderer.html` / `summary.html`), the content you’re working with will be sent to the endpoint you configure. Don’t paste secrets.
- Exports can contain your notes/history. Treat exported files as sensitive if your notes are sensitive.

## License

MIT — see `LICENSE`.
