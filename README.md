# Team 0 (test): Synonym Finder

Type a word, get a list of synonyms for it.

## Status

**The synonym lookup still isn't built.** Typing a word and clicking the button echoes it straight back as `Synonyms for: <word>` — same as before. What changed in round 1 (JF) is the UI.

## What's here

One file, `index.html`. No build step, no dependencies, no server — open it directly in a browser.

The page is a rounded card floating on a pastel gradient: a bobbing 🌸, gradient-text heading, pill-shaped input with a soft focus glow, and a gradient button that lifts on hover. The results area starts as a dashed empty state ("your synonyms will bloom here 🌱") and pops into a filled chip once something is written to it. Dark mode and reduced-motion are both handled. All of it is inline `<style>` in that same file.

## Next up

`findSynonyms()` at the bottom of `index.html` is the hook — it reads `#wordInput` and writes to `#results`. Fill in the middle. Two ways to go:

- **Hardcoded synonym map** — stays a single static file, no key, works offline.
- **Thesaurus or LLM API** — needs a small server to hold the key. A static page can't call one safely: any key in client-side JS is readable in devtools, and `file://` origins get blocked by CORS. There's a `.env.example` in the repo, added for a LiteLLM proxy.

Also unwired: pressing Enter in the input does nothing, and the results pop animation only fires on the first result, not on repeat searches.
