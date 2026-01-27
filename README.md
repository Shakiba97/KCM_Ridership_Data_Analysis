# 🚌 King County Metro Ridership Data Analysis

**Transit Ridership Recovery & SmartCard Analysis in King County, Washington**

This repository contains data processing, analysis, and visualization tools for studying **King County Metro (KCM) ridership patterns** using transit SmartCard (ORCA) data and supporting datasets. The project focuses on understanding temporal and spatial ridership trends and comparing ridership statistics across data sources.

---

## 📌 Project Overview

This project analyzes public transit ridership in King County using SmartCard transaction data and geographic information. It supports exploratory analysis of ridership recovery trends, origin–destination flows, and spatial distribution of transit usage.

The analysis is intended for **transportation researchers, planners, and data analysts** interested in transit performance evaluation and ridership behavior.

### Key Objectives

- Preprocess and analyze ORCA SmartCard ridership data  
- Compare ridership trends across datasets (e.g., ORCA vs. PSRC)  
- Analyze spatial and temporal ridership patterns  
- Visualize ridership flows and geographic distributions using interactive maps  

---

## 📁 Repository Structure

KCM_Ridership_Data_Analysis/
├── notebooks/                     # Jupyter notebooks for analysis
│   ├── Comparison (ORCA vs PSRC).ipynb
│   ├── flows.ipynb
│   └── Untitled_*.ipynb
├── data/                          # Input and processed datasets
│   ├── TAZ.csv
│   ├── output.csv
│   └── output.json
├── maps/                          # Interactive HTML visualizations
│   ├── map2023-04-01.html
│   ├── map2023-04-02.html
│   └── map2023-04-03.html
├── README.md
└── LICENSE (optional)

## 🛠️ Requirements

This project is implemented in **Python** using common data analysis and visualization libraries.

Typical dependencies include:
- `pandas`
- `numpy`
- `geopandas`
- `matplotlib`
- `folium`
- `jupyter`

Install dependencies with:

```bash
pip install pandas numpy geopandas matplotlib folium jupyter
