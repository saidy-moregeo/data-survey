# Comunidad de Madrid, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Comunidad de Madrid (Government)
- **Homepage:** https://www.comunidad.madrid

## Overview

SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) is the Agricultural Parcel Identification System implemented throughout the European Union for the application of CAP aid to farmers and ranchers. SIGPAC is configured as a database containing digitised cartographic images of the entire national territory (aerial orthoimages) and a geographic delimitation of each plot of land with its individual reference and the attributes corresponding to its geometry and agricultural use.

This dataset contains the SIGPAC enclosures (RECINTO) for the Comunidad de Madrid for the 2024 campaign, distributed as a single regional shapefile bundle.

## Data

- **URL:** https://idem.comunidad.madrid/recursos_cat_geo/Catalogo/recursos/UsoDelSuelo/spacm_sigpac.cm.zip (single regional ZIP containing `2024_SIGPAC_shape_toda_la_com/RECINTO.shp`)
- **Documentation:** https://www.comunidad.madrid/servicios/medio-rural/sigpac
- **File Format:** Shapefile (distributed as ZIP)
- **Projection:** EPSG:4258 (ETRS89 geographic)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (No limitations to public access; see https://idem.comunidad.madrid/catalogocartografia/srv/spa/catalog.search#/metadata/spacm_sigpac)

The published surface (`DN_SURFACE`) is in square metres.

### Properties

| Property   | Data Type | Constraints | Description       |
|------------|-----------|-------------|-------------------|
| DN_OID     | Real      |             | Identifier        | 
| DN_SURFACE | Real      |             | Area in m^2       | 
| PROVINCIA  | Integer   |             | Province code     | 
| MUNICIPIO  | Integer   |             | Municipality code | 
| AGREGADO   | Integer   |             |                   |
| ZONA       | Integer   |             |                   |
| POLIGONO   | Integer   |             |                   | 
| PARCELA    | Integer64 |             |                   |
| RECINTO    | Integer64 |             |                   |
| FACTOR_SUE | Integer64 |             |                   |
| FACTOR_PEN | Integer64 |             |                   |
| FACTOR_VEG | Integer64 |             |                   |
| CAP_RESU01 | Integer64 |             |                   |
| PENDIENTE_ | Integer   |             |                   |
| FACTOR_V01 | Integer64 |             |                   |
| ALTITUD    | Integer64 |             |                   |
| COEF_REGAD | Integer   |             |                   |
| USO_SIGPAC | String    |             | Crop code         |
| INCIDENCIA | String    |             |                   |
| PARCELA_AG | String    |             |                   |
| REGION_201 | String    |             |                   |
| GRUPO_CULT | String    |             | Crop Group        |
| REGION     | Integer   |             |                   |

