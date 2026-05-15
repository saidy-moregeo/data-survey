# Castilla-La Mancha, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Unidad de Cartografía. Secretaría General. Consejería de Agricultura, Ganadería y Desarrollo Rural. (Government)
- **Homepage:** https://datosabiertos.castillalamancha.es

## Overview

SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) is a geographic information system dedicated to the control of agricultural aid under the CAP. This dataset contains the SIGPAC enclosures (Recintos) for the autonomous community of Castilla-La Mancha. The data is exposed through the regional ESRI REST service. The latest year is published under `Vector/Recintos_sigpac`, while earlier years (2018–2024) are exposed as separate `Recintos_sigpac_<YEAR>` services.

## Data

- **URL:** https://geoservicios.castillalamancha.es/arcgis/rest/services/Vector (ESRI REST MapServer; layer `Recintos_sigpac` for the current year, `Recintos_sigpac_<YEAR>` for historic years)
- **Documentation:** https://datosabiertos.castillalamancha.es/dataset/sistema-de-informaci%C3%B3n-geogr%C3%A1fica-de-parcelas-agr%C3%ADcolas-de-castilla-la-mancha-sigpac
- **File Format:** ESRI REST / FeatureServer JSON (converted to GeoJSON)
- **Projection:** EPSG:4326 (REST export)
- **License:** [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/) (see [dataset page](https://datosabiertos.castillalamancha.es/dataset/sistema-de-informaci%C3%B3n-geogr%C3%A1fica-de-parcelas-agr%C3%ADcolas-de-castilla-la-mancha-sigpac))
- **Attribution:** Unidad de Cartografía. Secretaría General. Consejería de Agricultura, Ganadería y Desarrollo Rural.

The published surface (`dn_surface`) is in square metres.

### Properties

| Property         | Data Type | Constraints | Description       |
|------------------|-----------|-------------|-------------------|
| objectid_1       | Integer   |             | object_id         |
| dn_oid           | Integer   |             | identifier        |
| dn_surface       | Real      |             | area in m2        |
| dn_perimet       |           |             | perimeter in m    |
| provincia        |           |             | province code     |
| municipio        |           |             | municipality code |
| agregado         | Integer   |             |                   |
| zona             | Integer   |             |                   |
| poligono         | Integer   |             |                   |
| parcela          | Integer   |             |                   |
| recinto          | Integer   |             |                   |
| pdte_media       | Integer   |             |                   |
| coef_admis       | Integer   |             |                   |
| factor_sue       | Integer   |             |                   |
| factor_pen       | Integer   |             |                   |
| factor_veg       | Integer   |             |                   |
| porc_int_p       | Integer   |             |                   |
| cap_result       | Integer   |             |                   |
| factor_inc       | Integer   |             |                   |
| cap_resu01       | Integer   |             |                   |
| pendiente_       | Integer   |             |                   |
| altitud          | Integer   |             |                   |
| geocentro_       | Real      |             |                   |
| geocentr01       | Real      |             |                   |
| objectid         | Integer   |             |                   |
| coef_regad       | String    |             |                   |
| uso_sigpac       | String    |             |                   |
| incidencia       | String    |             |                   |
| parcela_ag       | String    |             |                   |
| region_201       | String    |             |                   |
| grupo_cult       | String    |             |                   |
| region           | Integer   |             |                   |
| tm               | String    |             |                   |
| codigo           | String    |             |                   |
| factor_v01       | Integer   |             |                   |
| porc_int_f       | Integer   |             |                   |
| porc_int_d       | Integer   |             |                   |
| porc_int01       | Integer   |             |                   |
| st_area(shape)   | Real      |             |                   |
| st_length(shape) | Real      |             |                   |

## API

Open data portal: https://datos-abiertos-castillalamancha.opendata.arcgis.com/
Web Viewer: https://datosabiertos.castillalamancha.es/dataset/sistema-de-informaci%C3%B3n-geogr%C3%A1fica-de-parcelas-agr%C3%ADcolas-de-castilla-la-mancha-sigpac-1

## API

| Standard  | URL                                                                  | Documentation |
|-----------|----------------------------------------------------------------------|---------------|
| ESRI REST | https://geoservicios.castillalamancha.es/arcgis/rest/services/Vector/Recintos_sigpac/MapServer | Latest year |
| ESRI REST | https://geoservicios.castillalamancha.es/arcgis/rest/services/Vector | Browse `Recintos_sigpac_<YEAR>` for historic years |
