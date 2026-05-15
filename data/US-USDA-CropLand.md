# U.S. Department of Agriculture Crop Sequence Boundaries

## Submission Details

- **Submitter (Affiliation):** Eddie Choi (Washington University in St. Louis); Ivor Bosloper
- **Data Provider (Legal Entity):** United States Department of Agriculture (USDA), National Agricultural Statistics Service (NASS) (Government)
- **Homepage:** https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/

## Overview

The Crop Sequence Boundaries (CSB), developed with USDA's Economic Research Service, produces estimates of field
boundaries, crop acreage, and crop rotations across the contiguous United States. It uses satellite imagery with
other public data and is open source, allowing users to conduct area and statistical analysis of planted U.S.
commodities and providing insight on farmer cropping decisions.

NASS needed a representative field to predict crop planting based on common crop rotations such as corn-soy, and
ERS is using this product to study changes in farm management practices like tillage or cover cropping over time.

CSB represents non-confidential single-crop field boundaries over a set time frame. It does not contain personal
identifying information. The boundaries captured are of crops grown only — not ownership boundaries or tax parcels
(unit of property). The data are derived from satellite imagery and publicly available data; they do not come from
producers or agencies like the Farm Service Agency. The CSB is created based on the
[Cropland Data Layer (CDL)](https://www.nass.usda.gov/Research_and_Science/Cropland/SARS1a.php).

Annual datasets are available from 2015 onward; each release covers a rolling multi-year window
(e.g. the 2025 release covers 2017–2024), and previously published years are revised to reflect methodology
updates.

## Data

- **URL:**
  - 2025 (covering 2018–2028): https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/datasets/NationalCSB_2018-2025_rev23.zip
  - 2024 (covering 2017–2024): https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/datasets/NationalCSB_2017-2024_rev23.zip
  - 2023 (covering 2016–2023): https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/datasets/NationalCSB_2016-2023_rev23.zip
- **Documentation:**
  - https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/index.php
  - Per-release metadata, e.g. https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/metadata_Crop-Sequence-Boundaries-2023.htm
  - Source code used to create the dataset:
    https://github.com/USDA-REE-NASS/crop-sequence-boundaries/tree/main/csb-project
- **File Format:** ESRI File Geodatabase (`.gdb`, distributed as ZIP); geometry as MultiPolygon
- **Metadata Format:** HTML, XML
- **Projection:** Albers Conical Equal Area (as used by mrlc.gov / NLCD); EPSG:9822 (planar map projection)
  with the EPSG:4269 (NAD83) geodetic datum
- **License:** [License and Liability](https://gee-community-catalog.org/projects/csb/#license-and-liability) —
  U.S. Public Domain, provided as-is.

The CDL (Cropland Data Layer) crop codes are documented at
https://www.nass.usda.gov/Research_and_Science/Cropland/docs/CDL_codes_names_colors.xls.

### Properties

The CSB encodes the dominant CDL crop class for each year of the rolling window as a separate column
(`CDL{YEAR}`). Older releases used `R{YY}` (e.g. `R15`–`R22`) for the same purpose; the current
releases use the four-digit year naming.

| Property         | Data Type    | Constraints | Description                                                                                                                                                                                                                                                              |
|------------------|--------------|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SHAPE (geometry) | MultiPolygon |             | Feature geometry                                                                                                                                                                                                                                                       |
| CSBID            | String       | 15 digits   | CSB identifier: places 1–2 are the State FIPS code; places 3–4 are the last two digits of the starting year of the rolling window; places 5–6 are the last two digits of the ending year; the remaining places are assigned sequentially within the state/year window. |
| CSBYEARS         | String       | 4 digits    | Corresponds to places 3–6 of `CSBID` (start year + end year, two digits each).                                                                                                                                                                                         |
| CSBACRES         | Real         |             | Area of the polygon in acres                                                                                                                                                                                                                                           |
| CDL2016 … CDL2024 | Integer     |             | Majority CDL crop code within the CSB polygon for each year of the rolling window. Older releases use `R15` … `R22` for the same data.                                                                                                                                 |
| STATEFIPS        | String       |             | U.S. state FIPS code                                                                                                                                                                                                                                                   |
| STATEASD         | String       |             | State FIPS + USDA NASS Agricultural Statistics District (ASD)                                                                                                                                                                                                          |
| ASD              | String       |             | USDA NASS Agricultural Statistics District (ASD)                                                                                                                                                                                                                       |
| CNTY             | String       |             | U.S. county name                                                                                                                                                                                                                                                       |
| CNTYFIPS         | String       |             | U.S. county FIPS code                                                                                                                                                                                                                                                  |
| INSIDE_X         | Real         |             | Center X coordinate of the CSB polygon                                                                                                                                                                                                                                 |
| INSIDE_Y         | Real         |             | Center Y coordinate of the CSB polygon                                                                                                                                                                                                                                 |
| Shape_Length    | Real         |             | Shape length (m)                                                                                                                                                                                                                                                       |
| Shape_Area      | Real         |             | Shape area (m²)                                                                                                                                                                                                                                                        |

More information about which crop the values of the `CDL{YEAR}` / `R{YY}` columns denote can be found in the
per-release metadata.

### Example

A single CSB record (from the 2015–2022 release):

| Property     | Example value   |
|--------------|-----------------|
| CSBID        | 271522000000003 |
| CSBYEARS     | 1522            |
| CSBACRES     | 2.853923        |
| R15          | 121             |
| R16          | 121             |
| R17          | 121             |
| R18          | 121             |
| R19          | 23              |
| R20          | 23              |
| R21          | 5               |
| R22          | 23              |
| STATEFIPS    | 27              |
| STATEASD     | 2710            |
| ASD          | 10              |
| CNTY         | Marshall        |
| CNTYFIPS     | 089             |
| INSIDE_X     | -65686.929489   |
| INSIDE_Y     | 2799947.170035  |
| Shape_Length | 1644.136416     |
| Shape_Area   | 11549.418442    |

Web viewer: https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/Viewer/index.php

## API

No publicly documented API found.
