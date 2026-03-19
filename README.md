# Musiki

An interactive map of music genres and how they evolved -- from blues and classical roots to trap metal and bedroom pop.

Live at [musiki.tiessen.me](https://musiki.tiessen.me)

---

## What It Is

Musiki is a static reference site that visualizes 80 music genres as a force-directed graph, showing parent-child relationships across 300+ years of music history. Click any node to open a wiki-style panel with description, key artists, notable tracks, and a Spotify embed.

## Features

- **D3.js force graph** -- 80 genre nodes with era-based coloring, zoom/pan, and drag
- **Genre panels** -- full description, parent genres, sub-genres, key artists, key tracks, Spotify embed
- **Era filter** -- highlight genres by decade from Pre-1900 through the 2020s
- **Real-time search** -- filter and navigate to any genre instantly
- **Static** -- no server, no build step, loads directly from GitHub Pages

## Tech

- Vanilla HTML/CSS/JS
- [D3.js v7](https://d3js.org) via CDN
- GitHub Pages (served from `docs/`)
- Genre data: `docs/data/genres.json` (80 genres, hand-curated)

## Genre Data Schema

```json
{
  "id": "blues",
  "name": "Blues",
  "parent_ids": [],
  "origin_year": 1900,
  "origin_decade": "1900s",
  "region": "United States",
  "description": "...",
  "key_artists": ["Robert Johnson", "Muddy Waters"],
  "key_tracks": ["Cross Road Blues"],
  "spotify_track_id": "4gphxUgq0JSFv2BCLhNDiE",
  "tags": ["root", "acoustic", "american"]
}
```

## Development

No build step needed. Open `docs/index.html` in a browser, or serve locally:

```bash
cd docs
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## CI

GitHub Actions validates `genres.json` on every push -- checks valid JSON, required fields, unique IDs, and valid parent references.
