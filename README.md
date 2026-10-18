# 🌱 India's Top 20 Environment Startups & WIPO Patent Landscape Analysis (2026)

![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)
![Domain](https://img.shields.io/badge/Sector-ClimateTech%20%26%20Cleantech-forestgreen.svg)
![Data Source](https://img.shields.io/badge/IP%20Database-WIPO%20PATENTSCOPE-orange.svg)
![Entity Resolution](https://img.shields.io/badge/Matching-3--Stage%20Fuzzy%20%2B%20MCA%20CIN-brightgreen.svg)

## 📌 Executive Summary
This repository presents a rigorous empirical dataset and reproducible entity-resolution pipeline built to:
1. **Identify and Rank the Largest 20 Environment & Climate-Tech Startups in India** using a multi-dimensional composite framework combining **Commercial Scale** (cumulative equity funding, valuation, team size) and **Environmental & Deep-Tech IP Impact** (verified decarbonization/circularity metrics and WIPO Green IPC patent intensity).
2. **Extract, Clean, and Merge Patent Filings from WIPO PATENTSCOPE**, solving the critical **Brand-to-Legal Entity Discrepancy** (e.g., *Phool.co* filing patents under *Kanpur Flowercycling Pvt Ltd*; *Battery Smart* under *Upgrid Solutions Pvt Ltd*; *Recykal* under *Rapidue Technologies Pvt Ltd*) via a 3-stage deterministic + MCA CIN alias + fuzzy string-matching pipeline in Python.

---

## 📂 Repository Structure
```text
├── README.md                                   # Complete methodology, matching architecture & results
├── indian_environment_startups_wipo_master.xlsx# Multi-tab Excel workbook (Startups, Raw WIPO, Merged Data)
├── top_20_environment_startups_india.csv       # Deliverable 1(a)(iii): Startup-level details & rankings
├── wipo_patentscope_raw_data.csv               # Deliverable 2(a)(i): Raw patent records exported from WIPO
├── wipo_merged_patent_startup_dataset.csv      # Deliverable 2(a)(ii): Matched & merged WIPO-Startup dataset
└── wipo_patent_matcher.py                      # Reproducible Python 3 entity-resolution & matching script
```

---

## 🔬 Part 1: Identifying the Largest 20 Environment Startups in India

### 1.1 Search Methodology & Taxonomy Definition
India's climate-tech ecosystem encompasses over **1,580+ funded ventures** having raised **$12.8 Billion cumulatively** (Tracxn India Climate Tech Report 2026). To isolate true **Environment & Climate-Tech Startups** from legacy infrastructure conglomerates, I applied a strict 3-step search and screening protocol:

1. **Taxonomic Alignment with the WIPO IPC Green Inventory:**
   Included ventures operating across six core environmental verticals mapped to WIPO's IPC Green Inventory:
   * **Clean Mobility & EV Energy Storage Infrastructure** (`B60L`, `H01M`)
   * **Circular Economy, E-Waste & Battery Material Recovery** (`C22B`, `H01M 10/54`, `B29B`)
   * **Bioenergy, Compressed Biogas (CBG) & Green Hydrogen** (`C12M`, `C12P`, `C25B`)
   * **Solar Cold-Chain, Agri-Ecology & Drought Biopolymers** (`F25D`, `C08B`, `A01G`)
   * **Industrial Air Pollution Control & Carbon Capture / Synthetic Biology** (`F01N`, `C12N`)
   * **Sustainable Biomaterials & Single-Use Plastic Alternatives** (`D06N`, `C08L`)
2. **Database Triangulation:**
   Cross-referenced **Tracxn India Climate Tech 2026**, **StartupBlink Cleantech Index (Oct 2026)**, **DPIIT Startup India**, **IIMA Ventures / MUFG Climate Tech Reports**, and **Ministry of Corporate Affairs (MCA)** filings.
3. **Boundary Exclusions (Startup Purity Filter):**
   Excluded mature public utility Independent Power Producers (IPPs) and corporate spin-offs (such as *ReNew Power, Tata Power Renewable, Greenko, Adani Green, Inox Clean Energy*) where primary capital is project-finance debt for solar/wind parks rather than proprietary environmental technology startups.

---

### 1.2 Ranking Justification (Arrival at the Top 20)
To avoid biasing the ranking toward asset-heavy balance-sheet businesses over R&D-intensive deep-tech ventures, each candidate startup was evaluated on a **100-Point Composite Index**:

`Composite Score (100) = Commercial Scale Score (60 pts) + Environmental & IP Impact Score (40 pts)`

* **Commercial Scale (60 Points):** Cumulative institutional equity raised (30 pts), estimated enterprise valuation (20 pts), and active full-time employee base (10 pts).
* **Environmental & Technological Impact (40 Points):** Quantified physical unit abatement—tonnes of CO2e avoided, tonnes of e-waste/plastic/floral waste diverted, MWh of clean energy generated (25 pts)—combined with proprietary hardware/biotech/chemical patent defensibility (15 pts).

---

## 🏆 Summary Table: Top 20 Environment Startups in India & Merged WIPO
