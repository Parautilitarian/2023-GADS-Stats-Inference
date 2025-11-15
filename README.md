# 2023 NERC GADS Cause Code Report

## Overview

This repository contains aggregated 2023 **Generating Availability Data System (GADS)** data from the **North American Electric Reliability Corporation (NERC)**.  
The dataset provides an anonymized summary of **forced outage and derating events** reported by electric generating units across NERC reliability regions.

Each record represents an aggregated grouping of **similar generating units** categorized by **Cause Code**, **Region**, **Fuel Type**, **Unit Type**, **System**, and **Event Type**.  
All identifying unit‑level data is masked to maintain confidentiality.

---

## Dataset Summary

| Attribute | Description |
|------------|-------------|
| **Cause Code** | Primary identifier for the cause of an outage or derating event. Each event is assigned one primary Cause Code. |
| **Sum of Distinct Units** | Number of unique generating units contributing to the aggregated record. |
| **Sum of Event Count** | Total count of events associated with the cause code. |
| **Sum of MW Lost** | Total capacity (in megawatts) unavailable due to the associated events. |
| **Sum of MWHrs Lost** | Total energy loss (in megawatt‑hours) attributed to the events. |

Additional aggregations and filters are available to provide analysis by season, region, fuel type, unit type, system, and event classification.

---

## Event Classifications

| Category | Description |
|-----------|-------------|
| **Outages** | Full loss of generating capacity. Includes: U1 (Forced Immediate), U2 (Forced Delayed), U3 (Forced Postponed). |
| **Deratings** | Partial reduction in generating capacity. Includes: D1 (Forced Immediate), D2 (Forced Delayed), D3 (Forced Postponed). |
| **Startup Failure (SF)** | Failure to synchronize or start following a shutdown. |

Planned, maintenance, and reserve shutdown events are **excluded**.

---

## Filters and Dimensions

### Season
- **Winter** – December–February  
- **Summer** – June–September  
- **Off‑Peak** – All other months

### Region Code
- **MRO** — Midwest Reliability Organization  
- **NPCC** — Northeast Power Coordinating Council  
- **RF** — ReliabilityFirst  
- **SERC** — SERC Reliability Corporation  
- **TRE** — Texas Reliability Entity  
- **WECC** — Western Electricity Coordinating Council  

### Fuel Category
- **Coal**  
- **Gas**  
- **Hydro**  
- **Nuclear**  
- **Oil**  
- **Waste Heat**  
- **Other**  

### Unit Type
- 100 – Fossil Steam  
- 200 – Nuclear  
- 300 – Gas Turbine / Jet Engine  
- 400 – Reciprocating Engine  
- 500 – Pumped Storage / Hydro  
- 650 – Fluidized Bed  
- 800 – Miscellaneous  
- 810 – Multi‑Boiler / Multi‑Turbine  
- 850–852 – Combined Cycle Configurations  
- 860–862 – Cogeneration Units  

### System Name
- Balance of Plant  
- Boiler  
- Diesel Engine  
- External  
- Gas Turbine  
- Generator  
- HRSG Boiler  
- Hydro Turbine / Pump  
- Nuclear Reactor  
- Performance  
- Personnel Errors  
- Pollution Control Equipment  
- Regulatory / Safety / Environmental  
- Steam Turbine  

Each **System Name** is further subdivided by **Component Name**, representing specific equipment or subsystem failures.

---

## Data Usage

The dataset supports the analysis of:
- Reliability performance by technology, fuel, or region  
- Leading outage causes across generating systems  
- Seasonal variations in forced outages and deratings  
- MW and MWh loss metrics by event classification  

All data are **aggregated and anonymized** as per NERC’s confidentiality policies.

---

## Research Q1: 
### Is there a statistically significant difference in the average megawatts lost (MW Lost) across different NERC regions for forced outage events?
- Goal: To infer whether the geographical region (operational reliability area) is associated with higher or lower mean MW loss during forced outages.
- Outcome Variable (Continuous): Sum of MW Lost — total megawatts lost during events.
- Explanatory Variable: Region Code (categorical nominal: MRO, NPCC, RF, SERC, TRE, WECC).

## Research Q2: 
### Does the frequency of forced outage events (Event Count) differ among Fuel Categories (e.g., coal, gas, nuclear, hydro)?
- Goal: To infer whether certain fuel types experience more forced outage events than others.
- Outcome Variable (Count): Sum of Event Count — the number of forced outage events recorded per category.
- Explanatory Variable: Fuel Category (categorical nominal: Coal, Gas, Nuclear, Hydro, Oil, etc.).

---

## Citation

If using or referencing this dataset or derived analyses, please cite as:

> NERC (2023). *Generating Availability Data System (GADS) – Cause Code Report (Aggregated Data, 2023)*.

---

## License

This dataset and documentation are provided for informational and research purposes under NERC’s public data policies.  
Confirm applicable usage terms via [NERC GADS](https://www.nerc.com/pa/RAPA/gads/Pages/default.aspx).

---

## Repository Structure

```plaintext
├── data/
│   ├── gads_2023_causecodes.csv
│
├── analysis/
│   └── research_question_1.qmd
│   └── research_question_2.qmd
|
└── README.md
