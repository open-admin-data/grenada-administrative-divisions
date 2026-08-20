# Grenada Administrative Divisions / Grenada



## Overview

| Item | Details |
|------|---------|
| Parish | 8 |
| Locality | 279 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/gd](https://openadmindata.org/gd/) |
| API | [openadmindata.org/api/gd](https://openadmindata.org/api/gd/) |
| Flag | [PNG](https://onlygames.me/flags-png/gd/) · [SVG](https://onlygames.me/flags-svg/gd/) · [PDF](https://onlygames.me/flags-pdf/gd/) |
| National Anthem | [🎵 Listen & Download Grenada National Anthem MP3](https://onlygames.me/national-anthems/gd/) |

## Browse by Parish

| # | Parish | Localitys | Link |
|---|----|----|------|
| 1 | Carriacou | 17 | [Browse](divisions/carriacou-gd01/) |
| 2 | St. Andrew (Saint Andrew) | 68 | [Browse](divisions/saint-andrew-gd02/) |
| 3 | St. David (Saint David) | 37 | [Browse](divisions/saint-david-gd03/) |
| 4 | St. George (Saint George) | 93 | [Browse](divisions/saint-george-gd04/) |
| 5 | St. John (Saint John) | 20 | [Browse](divisions/saint-john-gd05/) |
| 6 | St. Mark (Saint Mark) | 12 | [Browse](divisions/saint-mark-gd06/) |
| 7 | St. Patrick (Saint Patrick) | 30 | [Browse](divisions/saint-patrick-gd07/) |
| 8 | Petite Martinique | 2 | [Browse](divisions/petite-martinique-gd08/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-parish.json](data/all-parish.json) | JSON | All 8 parish records |
| [all-locality.json](data/all-locality.json) | JSON | All 279 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-parish.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['locality']} localitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-parish.json", "utf-8"));
console.log(`Total: ${data.length} parishs`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=parish, 2=locality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{parish-slug}/
```

Localitys are listed inline in each parish's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-parish links
- [Per-parish data](docs/llms-full/) — Full data by parish

## Citation

```
Grenada Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/grenada-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
