# Islas Baleares (Balearic Islands), Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Govern de les Illes Balears (Government)
- **Homepage:** https://gobiernoabierto.navarra.es/

## Overview

The Geographic Information System of the Common Agricultural Policy for agricultural sites (SIGPAC - Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) allows the geographical identification of enclosures declared by farmers and farmers for any aid scheme related to the area cultivated or grazed. For the Balearic Islands the service includes protection strips on the banks of watercourses by application of BCAM 4.

The data is served through the Balearic Islands ESRI REST service, with one yearly layer named `SIGPAC ... <YEAR>`. Years from 2010 through 2024 are exposed.

## Data

- **URL:** https://ideib.caib.es/geoserveis/rest/services/public/GOIB_SIGPAC_IB/MapServer (ESRI REST MapServer; one layer per year named `SIGPAC ... <YEAR>`)
- **Documentation:** https://intranet.caib.es/opendatacataleg/dataset/sigpac-2024
- **File Format:** ESRI REST / FeatureServer JSON (converted to GeoJSON)
- **Projection:** EPSG:4326 (REST export)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see http://www.opendefinition.org/licenses/cc-by)
- **Attribution:** Govern de les Illes Balears

The published surface (`DN_SURFACE`) is in square metres.

| Property     | Data Type | Constraints | Description          |
|--------------|-----------|-------------|----------------------|
| OBJECTID     | int       |             | Identifier           |
| DN_OID       | int       |             | Identifier           |
| DN_SURFACE   | Real      |             | Area in m2           |
| DN_PERIMET   | Real      |             | Perimeter            |
| PROVINCIA    | int       |             | Province code        |
| MUNICIPIO    | int       |             | Municipality code    |
| POLIGONO     | int       |             |                      |
| PARCELA      | int       |             |                      |
| RECINTO      | int       |             |                      |
| PENDIENTE_   | int       |             |                      |
| COEF_REGAD   | int       |             |                      |
| COEF_ADMIS   | int       |             |                      |
| USO_SIGPAC   | String    |             | SIGPAC Land use code |
| INCIDENCIA   | String    |             |                      |
| MOTIVO_MOD   | int       |             |                      |
| REFERENCIA   | String    |             |                      |
| DATA         | int       |             |                      |
| CERCA        | String    |             |                      |
| ANYS         | int       |             |                      |
| Shape_Length | Real      |             |                      |
| Shape_Area   | Real      |             |                      |


## API

| Standard  | URL                                                                             | Documentation |
|-----------|---------------------------------------------------------------------------------|---------------|
| ESRI REST | https://ideib.caib.es/geoserveis/rest/services/public/GOIB_SIGPAC_IB/MapServer/ | -             |
