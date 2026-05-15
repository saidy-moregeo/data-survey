# Galicia, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Virtual Office for Rural Environment - Xunta de Galicia (Government)
- **Homepage:** https://ovmediorural.xunta.gal/es/consultas-publicas/sixpac

## Overview

SIXPAC (the Galician name for SIGPAC - Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) is the official reference database for the identification of agricultural plots, which is mandatory in Spain for making applications for direct CAP aid that require declaring surface areas. SIXPAC lets farmers indicate the location of the farm surfaces that may be eligible for subsidies and submit requests for changes to data related to land uses.

The Galicia data is exposed through the regional ESRI REST service. Yearly layers from 2010 through 2024 are available.

## Data

- **URL:** https://ideg.xunta.gal/servizos/rest/services/ParcelasCatastrais/SIXPAC_`<YEAR>`/MapServer (ESRI REST MapServer; layer `recintos`)
- **Documentation:** https://mapas.xunta.gal/gl/aviso-legal
- **File Format:** ESRI REST / FeatureServer JSON (converted to GeoJSON)
- **Projection:** EPSG:4326 (REST export)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see https://mapas.xunta.gal/gl/aviso-legal)
- **Attribution:** Información procedente do FOGGA

The published surface (`DN_SURFACE`) is in square metres.

### Properties

| Property                      | Data Type | Constraints | Description     |
|-------------------------------|-----------|-------------|-----------------|
| OBJECTID                      | Int       |             | Identifier      |
| CARTOGRAFIA_REFERENCIA_AUX_CP | Int       |             |                 |
| DN_OID                        | Int       |             | Identifier      |
| DN_VERSION                    | Int       |             |                 |
| DN_INITIALDATE                | Int       |             | Retrieval data  |
| DN_ENDDATE                    | Int       |             | Retrieval data  |
| DN_SURFACE                    | Real      |             | Area in m2      |
| DN_PERIMETER                  | Reak      |             | Perimeter in m  |
| PROVINCIA                     | Int       |             | Province code   |
| MUNICIPIO                     | Int       |             | Municipal code  |
| AGREGADO: 0                   | Int       |             |                 |
| ZONA                          | Int       |             |                 |
| POLIGONO                      | Int       |             |                 |
| PARC_REEMPLAZO                | Int       |             |                 |
| REGION_2015                   | String    |             |                 |
| GRUPO_CULTIVO                 | String    |             | Sigpac use code |
| NOM_ZONACP                    | String    |             |                 |
| SP_REEMPLAZO                  | int       |             |                 |
| USO_SIGPAC:                   | String    |             | Not filled?     |
| COEF_REGADIO                  |           |             |                 |
| COEF_ADMISIBILIDAD            |           |             |                 |
| INCIDENCIAS                   |           |             |                 |
| REGION                        | int       |             |                 |
| SHAPE.AREA                    | Real      |             |                 |
| SHAPE.LEN                     | Real      |             |                 |

## API

| Standard  | URL                                                              | Documentation |
|-----------|------------------------------------------------------------------|---------------|
| ESRI REST | https://ideg.xunta.gal/servizos/rest/services/ParcelasCatastrais | Browse `SIXPAC_<YEAR>` services per year |

### Example

https://mapas.xunta.gal/visores/conservaciondanatureza/
