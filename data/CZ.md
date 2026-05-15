# Czechia

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Czech Ministry of Agriculture (Ministr Zemědělství) (Government)
- **Homepage:** https://mze.gov.cz/public/portal/mze/farmar/LPIS

## Overview

Field boundaries for Czechia: the crop fields (Plodina) of the Czech Land Parcel Identification System (LPIS).

The dataset is published by the Czech Ministry of Agriculture as part of the implementation of the INSPIRE directive and the Common Agricultural Policy (CAP) / Integrated Administration and Control System (IACS) reporting obligations. It contains crop declarations within Field Blocks (Díly půdních bloků, DPB) of farmer applications.

## Data

- **URL:** https://mze.gov.cz/public/app/eagriapp/Files/geoprostor_zadosti23_2024-08-01_202409261243_epsg4258.zip
- **Documentation:** https://mze.gov.cz/public/portal/mze/farmar/LPIS
- **File Format:** Shapefile (delivered as ZIP)
- **Projection:** EPSG:4258
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)
- **Crop code list:** Mapped to EuroCrops HCAT via `cz_2023.csv`

### Properties

Crop Fields (Plodiny)

| Property   | Data Type  | Constraints | Description |
|------------|------------|-------------|-------------|
| ID_UZ      | Integer64  |             |             |
| JI         | Integer64  |             |             |
| ID_SZR     | Integer64  |             |             |
| ICO        | String     |             |             |
| DPB_ID     | Integer64  |             |             |
| DPB_CTVERE | String     |             |             |
| DPB_ZKOD   | String     |             |             |
| DPB_VYMERA | Real       |             |             |
| ROK        | Integer    |             |             |
| EKO        | String     |             |             |
| KULTURAKOD | String     |             |             |
| ZAKRES_ID  | Integer64  |             |             |
| OP_ID      | Integer64  |             |             |
| OP_KOD     | String     |             |             |
| TIT_ID     | Integer64  |             |             |
| TIT_KOD    | String     |             |             |
| PLODINA_ID | String     |             | Crop code   |
| PLOD_NAZE  | String     |             | Crop name   |
| DEKL_VYM   | Real       |             |             |
| ZAKRES_VYM | Real       |             |             |
| DATUM_REP  | String     |             | Date        |
| REGCISZAD  | String     |             |             |
| CISPREDTIS | String     |             |             |
| CISJED     | String     |             |             |
| DOPLNKOVY  | String     |             |             |
| DATUM_VYS  | String     |             |             |
| OBEC_NAZEV | String     |             |             |
| OBEC_KOD   | Integer    |             |             |
| OKRES_NAZE | String     |             |             |
| OKRES_KOD  | Integer    |             |             |

## API

https://mze.gov.cz/public/portal/mze/farmar/LPIS/ws-lpis
