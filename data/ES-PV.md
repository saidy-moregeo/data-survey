# País Vasco (Basque Country), Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Gobierno Vasco (Government)
- **Homepage:** https://www.euskadi.eus/web01-tramite/es/contenidos/tramite_servicio/datos_geograficos_sigpac/es_def/index.shtml

## Overview

SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) is the system that farmers and ranchers must use to apply for community aid related to the surface area. Its introduction was a requirement imposed by the European Union on all Member States, and SIGPAC began to be used from February 1, 2005, together with the beginning of the 2005 community aid application period.

This dataset contains the Basque Country SIGPAC enclosures, published per municipality per campaign year (2016–2025).

## Data

- **URL:** https://www.geo.euskadi.eus/cartografia/DatosDescarga/Agricultura/SIGPAC/SIGPAC_CAMPA%C3%91A_`<YEAR>`_V1/ (per-municipality ZIP archives)
- **Documentation:** https://www.geo.euskadi.eus/cartografia/DatosDescarga/Documentacion/SIGPAC/20180608_NNGG_SISTEMA_DE_INFORMACION_GEOGRAFICA_VF.pdf
- **File Format:** Shapefile (per municipality, distributed as ZIP)
- **Projection:** EPSG:25830 (ETRS89 / UTM zone 30N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** Basque Government / Gobierno Vasco

### Properties

| Property   | Data Type | Constraints | Description                               |
|------------|-----------|-------------|-------------------------------------------|
| DN_SURFACE | Real      |             | Area                                      |
| DN_PERIMET | String    |             | Perimeter                                 |
| AGREGADO   | int64     |             |                                           |
| ZONA       | int64     |             |                                           |
| PROVINCIA  | Real      |             | Adminstrative subdivision Province ID     |
| MUNICIPIO  | Real      |             | Adminstrative subdivision municipality ID |
| POLIGONO   | Real      |             |                                           |
| PARCELA    | Real      |             |                                           |
| RECINTO    | Real      |             | Precinct                                  |
| USO        | String    |             | Land use code                             |
| PTE        | Real      |             | Some identifier? Not crop                 |
| REGION     | Real      |             |                                           |
| CAP        | Real      |             |                                           |
| CAMPANA    | Integer   |             | campaign year                             |


## API

| Standard | URL                                                                              | Documentation |
|----------|----------------------------------------------------------------------------------|---------------|
| OGC WMS  | https://www.geo.euskadi.eus/WMS_NEKAZARITZA?request=getcapabilities&SERVICE=WMS  | -             |

### Example

https://www.geo.euskadi.eus/geobisorea/?lang=eu&extent=-277973.5727,5288315.52,-274916.0916,5290393.6517,102100&layers=AGRICULTURA_EUS_3611_94,AGRICULTURA_EUS_3611_95,AGRICULTURA_EUS_3611_96,AGRICULTURA_EUS_3611_97,AGRICULTURA_EUS_3611_98,AGRICULTURA_EUS_3611_99,AGRICULTURA_EUS_3611_100,AGRICULTURA_EUS_3611_101
