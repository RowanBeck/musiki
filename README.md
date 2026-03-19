# Musiki

The complete map of music genres and how they evolved.

Live at [musiki.tiessen.me](https://musiki.tiessen.me)

## What It Is

Musiki is an interactive single-page app that visualizes the evolutionary tree of music genres, from pre-1900 roots like Blues, Classical, Folk, and Jazz through to contemporary forms like Trap, Bedroom Pop, and Afrobeats.

## Features

- Interactive D3 force-directed graph of 65+ genres
- Color-coded by era (warm tones for older genres, cool/vivid for newer)
- Click any genre to open a reference panel with description, origins, artists, tracks, and Spotify embed
- Search across all genres by name, region, or tag
- Filter by era (decade buttons)
- Smooth zoom, pan, and drag
- Mobile responsive

## Data

Genre data lives in `docs/data/genres.json`. Each genre includes:

- `id` - unique slug
- `name` - display name
- `parent_ids` - which genres it evolved from
- `origin_year`, `origin_decade` - when it emerged
- `region` - where it came from
- `description` - 2-3 paragraph human-written summary
- `key_artists` - 3-5 defining artists
- `key_tracks` - 3-5 essential tracks
- `spotify_track_id` - optional, for Spotify embed
- `tags` - searchable labels

## Root Genres (No Parents)

Blues, Folk, Classical, Jazz, Gospel, Country, Bluegrass

## Tech

Vanilla HTML/CSS/JS. D3.js v7. No build step. No framework. Deployed via GitHub Pages.

## CI

The CI workflow validates genres.json on every push: schema, required fields, duplicate IDs, and dangling parent references.
