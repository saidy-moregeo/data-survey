# Slovakia

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Pôdohospodárska platobná agentúra (Government)
- **Homepage:** https://www.apa.sk

## Overview

Slovakia Agricultural Land Identification System — Systém identifikácie poľnohospodárskych pozemkov (LPIS).

LPIS is an agricultural land identification system. It represents the vector boundaries of agricultural land and carries information about the unique code, acreage, culture/land use, etc., which is used as a reference for farmers' applications, for administrative and cross-checks, on-site checks and also checks using remote sensing methods. As Slovakia's LPIS it is the spatial reference for the Common Agricultural Policy (CAP) / Integrated Administration and Control System (IACS).

The dataset *Hranice užívania* contains the use declared by applicants for direct support.

## Data

- **URL:** https://data.slovensko.sk/download?id=e39ad227-1899-4cff-b7c8-734f90aa0b59&blocksize=0 (containing `HU2024_20240917shp/HU2024_20240917.shp`)
- **Documentation:** https://data.slovensko.sk/datasety/cc261225-7153-44a3-8ebf-05af207515c9
- **File Format:** Shapefile (delivered as ZIP)
- **Projection:** as published
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (published as Open Data)

### Properties

| Property   | **Data Type** | Constraints | Description     |
|------------|---------------|-------------|-----------------|
| ZKODKD     | String        |             | Identifier      |
| KODKD      | String        |             | code KD         |
| PARCELA    | String        |             | code KD         |
| PCUV       | Integer64     |             | code KD         |
| VYMERA     | Real          |             | Area            |
| Shape_Leng | Real          |             | Perimeter       |
| Shape_Area | Real          |             | Real Area       |
| LOKALITA_N | String        |             | Municipality    |
| KULTURA_SK | String        |             | Crop Group Code |
| KULTURA_NA | String        |             | Crop Group      |
| PLODINA    | String        |             | Crop Name       | 
| SUBJEKT_NA | String        |             | Applicant       |

