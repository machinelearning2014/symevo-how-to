# SYMEVO Field Reference

A single-page field reference for **SYMEVO** — a Symbolic Evidence-Gated Verification Orchestrator.

It is written for someone who has to decide whether to trust the thing, so it documents the
gate conditions and the limitations as carefully as the capabilities. The final section is
the project's own documented admissions, quoted rather than paraphrased.

Published at <https://machinelearning2014.github.io/symevo-how-to/>.

## Structure

The whole site is `index.html` — one hand-authored page with its CSS and JavaScript inline.
There is no build step, no framework, and no dependency to install. GitHub Pages serves it
directly from the `main` branch root.

## Editing

Open `index.html` and edit it. The table of contents in `nav.rail` and the `<section id="...">`
elements must stay in sync: each rail link is an in-page anchor, and the scroll-spy script
marks the active section with `IntersectionObserver`.

Sections are numbered `01`–`15` and share a small set of idioms:

| Element | Purpose |
| --- | --- |
| `.masthead` | title, standfirst, and the metadata chips |
| `nav.rail` | the sticky contents index (collapses to chips under 960px) |
| `.lede` | the opening paragraph of a section |
| `.tablewrap` | horizontal-scroll wrapper for tables |
| `.codewrap` + `.codeblock` | code block with a hover copy button; `.is-accent` adds the brass left rule |
| `.note` | callout, with `.note-head` as its small caps label |
| `.gotchas` | the bordered list used for pitfalls |
| `figure svg` | inline diagrams, styled with `currentColor` so they follow the theme |

Colors are CSS custom properties on `:root`, with dark-mode overrides in both
`prefers-color-scheme` and a `[data-theme="dark"]` attribute, so the page follows the
reader's system setting by default.

## Verifying

```sh
python3 -m http.server 8000    # then open http://localhost:8000
```

The page is self-contained, so opening `index.html` directly in a browser also works.

## Accuracy

Counts, status strings, flag names, and gate conditions were read from the SYMEVO source at
the version recorded in the masthead. Where the source and the prose documentation disagree,
the source wins — and section 14 notes the specific places they disagree.
