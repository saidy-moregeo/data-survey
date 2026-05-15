# Canarias (Canary Islands), Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Gobierno de Canarias - Consejería de Agricultura, Ganadería, Pesca y Soberanía Alimentaria (Government)
- **Homepage:** https://www.gobiernodecanarias.org/agpsa/

## Overview

The Canary Islands Crop Map (Mapa de cultivos de Canarias) is a cartographic dataset developed by the Department of Agriculture, Livestock, Fisheries and Water of the Government of the Canary Islands to understand the available agricultural surface of the Canary Islands. It has been developed and maintained from 1998 to the present.

There are separate crop maps for each of the islands, which together let users see the temporal and spatial evolution of the cultivated areas in recent years. The Canary Islands Crop Map is therefore a basic tool for decision-making in regional agricultural policy, as well as a base source for the preservation of agricultural land in the field of territorial planning.

Unlike the other Spanish regions in this survey, the Canary Islands publish their own crop classification (not the generic SIGPAC land-use codes).

## Data

- **URL:** https://opendata.sitcan.es/upload/medio-rural/gobcan_mapa-cultivos_`<island>`_shp.zip (per-island ZIP archives for islands `lz`, `eh`, `lp`, `lg`, `tf`, `gc`, `fv`)
- **Documentation:** https://opendata.sitcan.es/upload/medio-rural/gobcan_mapa-cultivos_metodologia.pdf
- **File Format:** Shapefile (per island, distributed as ZIP)
- **Projection:** EPSG:32628 (WGS 84 / UTM zone 28N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see https://datos.canarias.es/portal/aviso-legal-y-condiciones-de-uso)
- **Attribution:** Gobierno de Canarias

### Properties

| Property   | Data Type | Constraints | Description   |
|------------|-----------|-------------|---------------|
| ISLA_NA    | String    |             | Island name   |
| ISLA_CO    | String    |             | Island code   |
| CULTIVO_NA | String    |             | Crop name     |
| CULTIVO_CO | String    |             | Crop code     |
| BORDE_NA   | String    |             |               |
| BORDE_CO   | String    |             |               |
| DISEMI_NA  | String    |             |               |
| DISEMI_CO  | String    |             |               |
| REGADIO_NA | String    |             |               |
| REGADIO_CO | Integer   |             |               |
| TECNICA_NA | String    |             |               |
| TECNICA_CO | String    |             |               |
| ABANDON_NA | String    |             |               |
| ABANDON_CO | String    |             |               |
| AREA_M2    | Real      |             | Area in m2    |
| FECHA      | String    |             | Date of field |
