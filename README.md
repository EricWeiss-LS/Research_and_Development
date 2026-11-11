# Luceo R&D

Hosted prototypes and embeds. Served by GitHub Pages from `docs/` on `main`.

## Classroom pages

`docs/classroom/<team>/` holds one self-contained HTML page per Classroom topic, exported from the Luceo Classroom Builder, plus:

- `index.json`: every page with its ID, file, track, module, label, title, archetype, Builds on IDs, and estimated minutes. The app reads this to build navigation.
- `index.html`: a browsable list of the pages.

Each page is an app embed: no top bar, no prev/next. Put it in an iframe. The page talks to the host:

| Message to the host | When | Payload |
|---|---|---|
| `classroom:height` | on load, and whenever content height changes (flip, reveal) | `{type, topic, height}` |
| `classroom:navigate` | a Builds on chip is tapped | `{type, from, topic}` |

Quiz and video links carry `target="_top"`, so they open the app, not the iframe. Diagrams are embedded as data URLs; the only external request is Google Fonts.

URL pattern once Pages is on: `https://<user>.github.io/Luceo-R-and-D/classroom/boylston-boys-8/t02-m2-2-superman.html`

Teams:
- `boylston-boys-8/`: Boylston Boys 8, Nashoba Rec League 7th-8th, Winter 2026-27. 34 pages. Source bundle lives in the Luceo Sports builder workspace.
