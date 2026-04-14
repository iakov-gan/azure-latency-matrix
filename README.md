# Azure Network Latency Matrix

Interactive viewer for Azure region-to-region network latency data.

**🔗 Live:** [iakov-gan.github.io/azure-latency-matrix](https://iakov-gan.github.io/azure-latency-matrix/)

![Screenshot](https://img.shields.io/badge/regions-51-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## Features

- **51×51 region matrix** — all Azure public regions with round-trip P50 latency in milliseconds
- **Geography filter** — scope to Americas, Europe, Asia Pacific, or Middle East & Africa
- **Searchable multi-select** — pick specific source and destination regions with built-in search
- **Sort options** — order by name (A↔Z) or average latency (low↔high)
- **Color-coded cells** — instant visual read on latency quality:

  | Color | Latency |
  |-------|---------|
  | 🟢 Green | < 40 ms |
  | 🟡 Yellow | 40–99 ms |
  | 🟠 Orange | 100–199 ms |
  | 🔴 Red | 200–299 ms |
  | 🔴 Dark red | ≥ 300 ms |

- **Bookmarkable URLs** — filter state syncs to URL query params
- **Zero dependencies** — single static HTML file, no frameworks, no build step

## URL Parameters

Share specific views via query parameters:

| Param | Example | Description |
|-------|---------|-------------|
| `geo` | `?geo=Europe` | Filter by geography |
| `source` | `?source=East+US,West+US` | Select source regions (comma-separated) |
| `dest` | `?dest=UK+South` | Select destination regions |
| `sort` | `?sort=latency` | Sort order: `name`, `name-desc`, `latency`, `latency-desc` |

Example: [Americas only, sorted by latency](https://iakov-gan.github.io/azure-latency-matrix/?geo=Americas&sort=latency)

## Data Source

Latency data is sourced from Microsoft's official documentation:
[Azure Network Latency](https://learn.microsoft.com/en-us/azure/networking/azure-network-latency)

- **Metric:** Round-trip P50 (median) latency
- **Window:** 30-day period ending June 29, 2025
- **Updates:** Microsoft refreshes this data every 6–9 months

## Running Locally

Just open the file in a browser — no server required:

```
git clone https://github.com/iakov-gan/azure-latency-matrix.git
open index.html
```

## License

MIT
