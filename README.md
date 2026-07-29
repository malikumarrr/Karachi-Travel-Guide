[README.md](https://github.com/user-attachments/files/30511265/README.md)
# Karachi — A Curated City Guide

An interactive, single-file travel guide to Karachi, focused on **food, cafés, and heritage**.
33 hand-picked places on a live map, with filters, search, and a personal itinerary builder.

**Live site:** https://malikumarrr.github.io/Karachi-Travel-Guide/

## Features

- 🗺 **Interactive map** — colour-coded markers by category (Leaflet + OpenStreetMap)
- 🔎 **Filter & search** — Food · Cafés · Heritage · Museums · Bazaars · Beach · Parks, plus live text search
- 📋 **Itinerary builder** — add places to a personal list that **persists across page refreshes** (browser `localStorage`)
- 📍 **One-tap directions** — every place links straight to Google Maps
- ⭐ **Tiered picks** — must-do / highly recommended / worth-it, shown by card colour
- 📱 **Responsive** — map-on-top layout on phones, side-by-side on desktop

## How it's built

A single self-contained `index.html` — no build step, no framework, no backend, no API keys.

| Layer | Tool |
|---|---|
| Map | [Leaflet 1.9.4](https://leafletjs.com) (CDN) |
| Map tiles | CARTO Voyager basemap (free, keyless) |
| Fonts | Google Fonts — Playfair Display + Inter |
| Logic | Vanilla JavaScript (ES6) |
| Data | A hardcoded `activities` array inside the file |
| Hosting | GitHub Pages (static) |

## Editing the guide

All content lives in the `activities` array near the top of the `<script>` block in `index.html`.
Each entry looks like this:

```javascript
{id:1, tier:1, name:"Burns Road Food Street", neighborhood:"Saddar",
 lat:24.8607, lng:67.0227, category:["food","heritage"],
 description:"…", mustOrder:"…", tip:"…",
 duration:"1–2 hrs", price:"Rs", mapsQuery:"Burns Road Food Street Karachi"}
```

- **Coordinates:** right-click a spot in Google Maps — the first two numbers are `lat, lng`.
- **Categories** must match the filter buttons. To add a new category, add a button in the
  `.filter-tags` HTML *and* a matching colour in both the CSS filter list and the `CAT_COLORS` object.
- The **Essentials** strip at the top is a separate `musts` array — each item links to a place by `id`.

## Run locally

Just open `index.html` in any browser. (An internet connection is needed for the map tiles and fonts.)

## Notes

- Place coordinates are close approximations — spot-check the pins before relying on them for navigation.
- The itinerary is stored per-browser, per-device; it is not shared between visitors.

---

Built as a single static HTML file. Content is a personal curation and may go out of date — verify opening hours and prices before you visit.
