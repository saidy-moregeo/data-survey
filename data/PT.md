# Portugal

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** IPAP - Instituto de Financiamento da Agricultura e Pescas (Government)
- **Homepage:** https://www.ifap.pt/isip/ows/

## Overview

Open field boundaries (identificação de parcelas) from Portugal.

Field blocks and crop fields are identified in the Portuguese Parcel Identification System (iSIP) as applied for in the Common Agricultural Policy (CAP) / Integrated Administration and Control System (IACS). The data is updated annually and published as open data via IFAP.

The crop-field level boundaries are published in `Culturas_` (crop) layers.

## Data

- **URL:** Multi-year, available via https://www.ifap.pt/isip/ows/ — yearly variants supported:
  - 2023: https://www.ifap.pt/isip/ows/resources/2023/Continente.gpkg
  - 2022: https://www.ifap.pt/isip/ows/resources/2022/2022.zip
  - 2021: https://www.ifap.pt/isip/ows/resources/2021/2021.zip
  - 2020-2017: https://www.ifap.pt/isip/ows/resources/2017-2020/{year}.zip
  - 2016-2015: https://www.ifap.pt/isip/ows/resources/2011_2016/{year}.zip
- **Documentation:** https://www.ifap.pt/isip/ows/
- **File Format:** GeoPackage (2023) / Shapefile in ZIP (other years)
- **Projection:** as published
- **License:** [No conditions apply](https://inspire.ec.europa.eu/metadata-codelist/ConditionsApplyingToAccessAndUse/noConditionsApply)

### Properties

| Property     | Data Type   | Constraints | Description                   |
|--------------|-------------|-------------|-------------------------------|
| OBJECTID     | int64       |             |                               |
| CUL_ID       | int         |             | Field block identifier        |
| CUL_CODIGO   | string      | 3 chars     | Code for crop                 |
| OSA_ID       | Integer int |             | Crop field identifier         |
| CT_português | string      | 255 chars   | Crop name (Portugese)         |
| Shape_Length | Real (0.0)  |             | Perimeter length in meters    |
| Shape_Area   | Real (0.0)  |             | Surface area in square meters |

### Example

See https://www.ifap.pt/isip/ows/resources/parcelas.pdf

## API

| Standard | URL                                                                            |
|----------|--------------------------------------------------------------------------------|
| OGC WMS  | https://www.ifap.pt/isip/ows/isip.data/wms?service=wms&request=getcapabilities |
| OGC WFS  | https://www.ifap.pt/isip/ows/isip.data/wfs?service=wfs&request=getcapabilities |
