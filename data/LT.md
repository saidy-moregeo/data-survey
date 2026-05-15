# Lithuania

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Nacionalinė mokėjimo agentūra prie Žemės ūkio ministerijos (Government); harmonized dataset published by the Europe-LAND HE Project
- **Homepage:** https://www.nma.lt

## Overview

Lithuania crop fields: a collection of data on agricultural land and crop areas, including cultivated crops, in the territory of the Republic of Lithuania.

The data is collected by the Lithuanian Paying Agency (NMA) under the Common Agricultural Policy (CAP) / Integrated Administration and Control System (IACS) and was published as a harmonized GeoParquet by the Europe-LAND Horizon Europe project on Zenodo.

## Data

- **URL:** https://zenodo.org/records/14384070/files/LT_2024.zip (containing `GSA-LT-2024.geoparquet`)
- **Documentation:** https://europe-land.eu/news/harmonized-database-of-european-land-use-data-published/ — see also https://doi.org/10.5281/zenodo.14230620
- **File Format:** GeoParquet
- **Projection:** as published
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** Nacionalinė mokėjimo agentūra prie Žemės ūkio ministerijos
- **Crop code list:** Mapped to EuroCrops HCAT via `lt_2021.csv`

### Properties

| Property        | Data Type | Constraints | Description                        |
|-----------------|-----------|-------------|------------------------------------|
| geometry        | geometry  | Polygon / MultiPolygon | Field boundary geometry |
| field_id        | string    |             | Field identifier                   |
| farm_id         | string    |             | Farm identifier                    |
| crop:code_list  | string    |             | Crop code list identifier          |
| crop_code       | string    |             | Declared crop code                 |
| organic         | integer   | `0`, `1`, `2` | Organic farming status           |
| field_size      | number    | hectares    | Field area                         |
| EC_trans_n      | string    |             | EuroCrops translated name          |
| EC_hcat_n       | string    |             | EuroCrops HCAT name                |
| EC_hcat_c       | string    |             | EuroCrops HCAT code                |
