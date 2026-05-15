# Romania

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Ministry of Regional Development and Public Administration of Romania (Government)
- **Homepage:** http://spatial.mdrap.ro

## Overview

Land-cover dataset for the Romanian side of the Romania–Bulgaria cross-border area, produced within the project
"Common strategy for territorial development of the cross-border area Romania–Bulgaria" (code MIS-ETC 171),
funded by the Romania–Bulgaria Cross-Border Cooperation Programme 2007–2013. The data covers seven counties along
the Danube border: Mehedinți, Dolj, Olt, Teleorman, Giurgiu, Călărași, Constanța.

The dataset is aligned with the conceptual framework described in the Land Cover Data Specifications for the
Implementation of the INSPIRE Directive (version 3.0). It was developed by harmonising the land-cover
classification system, acquiring and processing reference data, and verifying and validating the resulting
spatial data. The dataset is published in WGS 84 / UTM zone 35N to remain compatible with the corresponding
Bulgarian-side dataset.

The dataset is also redistributed as part of the [EuroCrops](EU-EuroCrops.md) collection.

## Data

- **URL:** Original publication via data.europa.eu:
  https://data.europa.eu/data/datasets/092425a1-90c6-4461-b1a6-6f5b0f72748f?locale=ro
  EuroCrops mirror (Zenodo, file `RO_ny.zip` containing shapefiles under `RO/`):
  https://zenodo.org/records/14094196/files/RO_ny.zip
- **Documentation:** https://data.europa.eu/data/datasets/092425a1-90c6-4461-b1a6-6f5b0f72748f?locale=ro
- **File Format:** Shapefile (distributed as ZIP)
- **Projection:** EPSG:32635 (WGS 84 / UTM zone 35N)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (Public Domain Dedication)
- **Attribution:** Ministry of Regional Development and Public Administration of Romania

### Properties

| Property   | Data Type | Constraints                              | Description                                                              |
|------------|-----------|------------------------------------------|--------------------------------------------------------------------------|
| geometry   | Polygon   |                                          | Land-cover polygon                                                       |
| AREA_HA    | Real      |                                          | Polygon area in hectares                                                 |
| LC_MAPCODE | String    | e.g. `A`, `CAG`, `G`, `N`, `P`, `R`, `T` | Land-cover code (Arable, Covered Agricultural, Grassland, Trees, Rice…)  |
| LC_CLASS_N | String    |                                          | Land-cover class name                                                    |
| SOURCE     | String    |                                          | Reference data source used to derive the polygon                         |

Land-cover codes observed for agricultural classes include:

- `A` — Arable Land
- `CAG` — Covered Agricultural Land (e.g. greenhouses)
- `G`, `N` — Grassland
- `P`, `T` — Trees (orchards, plantations)
- `R` — Rice

## Example

Browse via the European Data Portal viewer:
https://data.europa.eu/data/datasets/092425a1-90c6-4461-b1a6-6f5b0f72748f?locale=ro
