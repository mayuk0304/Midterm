# Montefiore Park — Arts & Culture Initiative
### A Hyperspace-style static website generator (Python, no dependencies)

> **The problem:** Montefiore Park in the Bronx holds powerful community murals,
> yet its design treats it as a corridor — everyone walks through and no one stays.
> This site proposes targeted arts-and-culture interventions to fix that.

---

## What this repo contains

```
montefiore-park/
├── generate_site.py      ← the one script you need to run
├── assets/
│   ├── css/main.css      ← auto-generated Hyperspace-style stylesheet
│   └── js/main.js        ← auto-generated scroll + nav JS
├── index.html            ← auto-generated site (open in browser)
└── README.md
```

The Python script **generates a complete static website** — HTML, CSS, and JS —
from structured data defined at the top of `generate_site.py`.
No frameworks, no package installs, no build tools required.

---

## Quick start

```bash
git clone https://github.com/YOUR_USERNAME/montefiore-park.git
cd montefiore-park
python generate_site.py
open index.html          # macOS
# or: start index.html   (Windows)
# or: xdg-open index.html (Linux)
```

---

## Customising the content

All content is declared as plain Python dictionaries at the top of
`generate_site.py`. You never need to touch HTML directly.

| Variable    | What it controls |
|-------------|-----------------|
| `SITE`      | Site title, subtitle, nav links |
| `HERO`      | Full-screen opening section |
| `FEATURES`  | The three spotlight tiles (problem breakdown) |
| `PROPOSALS` | The six arts & culture proposal cards |
| `CONTACT`   | Get-involved section, address, social links |
| `COLORS`    | Full colour palette (accent, backgrounds, etc.) |

### Adding real mural photos

Replace the SVG gradient placeholders with real images in two steps:

1. Drop your images into `images/` (e.g. `images/mural1.jpg`)
2. In `generate_site.py`, update the `PLACEHOLDER_SRCS` dict:

```python
PLACEHOLDER_SRCS = {
    "mural_red":   "images/mural1.jpg",
    "mural_blue":  "images/mural2.jpg",
    "mural_green": "images/mural3.jpg",
}
```

3. Re-run `python generate_site.py`

---

## Site structure (Hyperspace sections)

| Section ID | Content |
|------------|---------|
| `#intro`   | Hero — full-screen headline + CTA |
| `#one`     | Spotlight tiles — the three design problems |
| `#two`     | Feature grid — six arts & culture proposals |
| `#three`   | Contact / Get Involved form + info |

---

## Design problem addressed

Montefiore Park suffers from **passive-corridor syndrome**:

- Benches face the path, not the murals
- No spatial variety — one undifferentiated throughway
- Poor evening lighting discourages lingering
- No recurring programming gives people a reason to visit

### Proposed interventions

1. **Mural-facing seating alcoves** — curved benches angled toward the art
2. **Warm uplighting + interpretive panels** — extend cultural life into the evening
3. **Live mural-making sessions** — monthly public workshops
4. **Open-air performances** — platform facing the murals
5. **Mural Cinema Nights** — films themed around the artwork
6. **Weekend Arts Market** — Bronx-based artists, stalls visible from the mural wall

---

## Deploying to GitHub Pages

```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/montefiore-park.git
git push -u origin main
```

Then in your repo → **Settings → Pages → Source: main branch / root**.
Your site will be live at `https://YOUR_USERNAME.github.io/montefiore-park/`

---

## Credits

- Template style: [Hyperspace by HTML5 UP](https://html5up.net/hyperspace) (CCA 3.0 license)
- Icons: [Font Awesome](https://fontawesome.com)
- Fonts: [Source Sans Pro — Google Fonts](https://fonts.google.com/specimen/Source+Sans+Pro)
- Initiative: Montefiore Park Community Arts Project, Bronx NY

---

*This is a community design concept — not an official NYC Parks Department project.*
