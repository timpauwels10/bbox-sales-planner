# 📦 Bbox Sales Planner

**Interactive sales planning tool for bpost Bbox parcel locker deployment across Belgium.**

Built to help field sales teams instantly see where to hunt for new locations and whom to contact.

![Status](https://img.shields.io/badge/municipalities-499-blue)
![Status](https://img.shields.io/badge/lockers-1105-orange)
![Status](https://img.shields.io/badge/swaps_pending-305-purple)

---

## What it does

| Feature | Description |
|---------|-------------|
| **Interactive map** | Dark-themed Leaflet map of Belgium with 499 municipality markers, sized and colored by door gap |
| **Hover tooltips** | Instant stats: current doors, Sc3 2026 target, gap, total demand, coverage % |
| **Dual filters** | Independent Zone (A/B/C) + Status (High/Med/Low/Swap) filters that work simultaneously |
| **Searchable sidebar** | Find any municipality by name, zip code, or zone — sorted by urgency |
| **Detail panel** | Click any municipality to see every locker's fill rate, swap status, and door count |
| **Partner suggestions** | 5 AI-generated partner leads per municipality across retail, supermarkets, hospitals, laundromats, elderly homes, and public spaces |
| **Sales playbook** | Context-aware tips based on urgency level and swap status |

## Data source

Built from `C_Lean_Lockers_Performance_SWAP.xlsx` containing:

- **17,615** current doors → **56,820** Sc3 2026 target = **39,205 door gap**
- **305** lockers flagged for swap (concentrated in Zone A)
- Fill rates, overflow counts, and demand per locker
- Three scenarios: Sc1 (fill rate-based), Sc2 (no capacity overflow), Sc3 (2026 growth forecast)

## Color coding

| Color | Meaning |
|-------|---------|
| 🔴 Red | High gap (200+ doors needed) |
| 🟡 Yellow | Medium gap (50–199 doors) |
| 🔵 Blue | Low gap (1–49 doors) |
| 🟢 Green | Target reached |
| 🟣 Purple border | Municipality has swap-pending lockers |

## Zone breakdown

| Zone | Municipalities | Door Gap | Swaps |
|------|---------------|----------|-------|
| **A** | 29 | 8,270 | 251 |
| **B** | 150 | 19,241 | 54 |
| **C** | 113 | 11,694 | 0 |

## Top priority municipalities

| Municipality | Zone | Current | Sc3 Target | Gap | Swaps |
|-------------|------|---------|-----------|-----|-------|
| Mechelen | B | 1,144 | 2,592 | 1,448 | 54 |
| Antwerpen | A | 1,001 | 2,388 | 1,387 | 44 |
| Beveren-Kruibeke-Zwijndrecht | A | 351 | 1,194 | 843 | 3 |
| Gent | A | 559 | 1,350 | 791 | 22 |
| Leuven | A | 1,092 | 1,861 | 769 | 37 |
| Vilvoorde | B | 221 | 936 | 715 | 0 |
| Sint-Niklaas | A | 286 | 984 | 698 | 17 |

## Partner segments

Each municipality gets 5 suggested partners from:

- **Retail** — Action, Kruidvat, HEMA, Zeeman, Casa
- **Supermarket** — Lidl *(active partnership)*, Colruyt, Delhaize, Carrefour, Proxy Delhaize
- **Hospital** — Regional AZ, University UZ, Polyclinics
- **Laundry** — Speed Queen, Wasbar, local laundromats
- **Elderly homes** — Armonea/Korian, Senior Living Group, Vulpia
- **Public spaces** — NMBS stations *(active partnership)*, town halls, libraries, bus hubs

## How to use

1. Open `index.html` in any modern browser
2. Use **Zone filters** (top row) to focus on A, B, or C zones
3. Use **Status filters** (second row) to show only High/Med/Low gap or Swap-pending
4. **Search** by municipality name, zip code, or zone letter
5. **Hover** markers for quick stats
6. **Click** a marker or sidebar item to open the full detail panel with lockers + partner suggestions

## Tech stack

Single HTML file, no build step. Dependencies loaded via CDN:

- [Leaflet.js](https://leafletjs.com/) — interactive map
- [CARTO Dark](https://carto.com/basemaps/) — dark tile layer
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) + [Space Mono](https://fonts.google.com/specimen/Space+Mono) — typography

## Deployment

Rename the HTML file to `index.html` and enable GitHub Pages:

```
Settings → Pages → Source: main / root → Save
```

Live at: `https://<username>.github.io/bbox-sales-planner/`

---

*Built for bpost Bbox parcel locker sales operations.*
