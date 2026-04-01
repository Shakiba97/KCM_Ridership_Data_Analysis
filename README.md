# 🚌 KCM Ridership Data Analysis

Analysis of King County Metro (KCM) transit ridership using ORCA SmartCard transaction data. This project explores spatial and temporal ridership patterns, origin–destination flows, and cross-source comparisons between ORCA tap data and PSRC travel survey estimates.

---

## 📋 Table of Contents

- [Background](#background)
- [Project Structure](#project-structure)
- [Notebooks](#notebooks)
- [Data](#data)
- [Setup](#setup)
- [Usage](#usage)
- [Outputs](#outputs)
- [Contributing](#contributing)

---

## Background

King County Metro is the primary public transit agency serving the Seattle metro area. This project analyzes ridership behavior using **ORCA** (One Regional Card for All), the regional SmartCard fare payment system used across King County Metro, Sound Transit, and other Puget Sound transit agencies.

The analysis focuses on:
- Comparing ORCA-derived ridership counts against **PSRC** (Puget Sound Regional Council) travel survey estimates
- Reconstructing transit **origin–destination flows** by linking tap-on and tap-off events
- Mapping ridership spatially using **TAZ** (Traffic Analysis Zone) boundaries
- Generating interactive visualizations of daily and per-card ridership patterns

---

## Project Structure

```
KCM_Ridership_Data_Analysis/
│
├── notebooks/
│   ├── 01_orca_psrc_comparison.ipynb   # ORCA vs PSRC ridership comparison
│   ├── 02_ridership_flows.ipynb        # OD flow reconstruction and mapping
│   └── scratch/                        # Exploratory/experimental notebooks
│
├── data/
│   ├── raw/
│   │   └── TAZ.csv                     # Traffic Analysis Zone reference data
│   └── processed/                      # Generated outputs (gitignored)
│
├── outputs/
│   └── maps/                           # Generated HTML map files (gitignored)
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Notebooks

| Notebook | Description |
|---|---|
| `01_orca_psrc_comparison.ipynb` | Loads ORCA SmartCard transaction data and PSRC survey estimates, aligns them by time period and geography, and produces comparison visualizations highlighting discrepancies and agreement between the two sources. |
| `02_ridership_flows.ipynb` | Reconstructs passenger origin–destination flows from sequential tap events, aggregates flows by TAZ, and generates interactive Folium maps showing ridership movement across the network. |
| `scratch/` | Exploratory notebooks used during development. Not intended for reproducibility. |

---

## Data

### Inputs

| File | Location | Description |
|---|---|---|
| `TAZ.csv` | `data/raw/` | Traffic Analysis Zone IDs and attributes for King County |
| ORCA transaction data | Not included — see below | Raw SmartCard tap events (access restricted) |

> **Note:** ORCA transaction data contains personally identifiable information and is not publicly available. Access can be requested through [King County Metro](https://kingcounty.gov/en/dept/metro) or [PSRC](https://www.psrc.org/) for research purposes.

### Outputs (generated, gitignored)

| File | Location | Description |
|---|---|---|
| `output.csv` | `data/processed/` | Processed ridership records |
| `output.json` | `data/processed/` | Flow data in JSON format |
| `output_with_counts.json` | `data/processed/` | Flow data with aggregated trip counts |
| `map_YYYY-MM-DD.html` | `outputs/maps/` | Interactive daily ridership maps |
| `map for card_id_N.html` | `outputs/maps/` | Per-card trip trajectory maps |

---

## Setup

### Prerequisites

- Python 3.9+
- pip

### Install dependencies

```bash
git clone https://github.com/Shakiba97/KCM_Ridership_Data_Analysis.git
cd KCM_Ridership_Data_Analysis
pip install -r requirements.txt
```

### requirements.txt

```
pandas>=1.5
numpy>=1.23
geopandas>=0.12
matplotlib>=3.6
folium>=0.14
jupyter>=1.0
```

---

## Usage

Launch Jupyter and run notebooks in order:

```bash
jupyter notebook
```

1. Start with `notebooks/01_orca_psrc_comparison.ipynb` to understand the data sources and their relationship.
2. Run `notebooks/02_ridership_flows.ipynb` to reconstruct OD flows and generate interactive maps.

Outputs will be saved to `data/processed/` and `outputs/maps/` automatically.

---

## Outputs

The flow analysis generates interactive HTML maps (via Folium) showing:
- **Daily ridership maps** — aggregate boardings across the network for a given date
- **Per-card maps** — individual trip trajectories for specific ORCA cards (useful for validation)

Open any `.html` file in `outputs/maps/` directly in a browser — no server required.

---

## Contributing

This is a research project. If you'd like to extend the analysis or report issues, feel free to open an issue or pull request. Please keep scratch work in `notebooks/scratch/` and avoid committing generated output files.

---

## Acknowledgements

Forked from [arsalanesmaili/kcm_ridership](https://github.com/arsalanesmaili/kcm_ridership). Data provided by King County Metro and the Puget Sound Regional Council.
