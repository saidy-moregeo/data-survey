# Aragón, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Gobierno de Aragón (Government)
- **Homepage:** https://www.aragon.es

## Overview

SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) is the reference cartography used by Spain to identify agricultural plots for CAP aid applications. This dataset contains the SIGPAC enclosures (Recintos) for the autonomous community of Aragón, distributed by the Aragonese regional government per province (codes 22 Huesca, 44 Teruel, 50 Zaragoza).

## Data

- **URL:** https://idearagon.aragon.es/descargas (per-province ZIP archives, e.g. `rec22_sigpac.shp.zip`, `rec44_sigpac.shp.zip`, `rec50_sigpac.shp.zip`)
- **Documentation:** https://idearagon.aragon.es/descargas
- **File Format:** Shapefile (per province, distributed as ZIP)
- **Projection:** EPSG:25830 (ETRS89 / UTM zone 30N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see https://idearagon.aragon.es/portal/politica-privacidad.jsp)
- **Attribution:** (c) Gobierno de Aragón

### Properties

| Property   | Data Type | Constraints | Description       |
|------------|-----------|-------------|-------------------|
| DN_OID     | Real      |             | Identifier        | 
| SUPERF.    | Real      |             | Area in m^2       | 
| PROVINCIA  | Integer   |             | Province code     | 
| MUNICIPIO  | Integer   |             | Municipality code | 
| AGREGADO   | Integer   |             |                   |
| ZONA       | Integer   |             |                   |
| POLIGONO   | Integer   |             |                   | 
| PARCELA    | Integer64 |             |                   |
| RECINTO    | Integer64 |             |                   |
| ELEGIBILID | Integer   |             |                   |
| PENDIENTE_ | Integer   |             |                   |
| COEF_REGAD | Integer   |             |                   |
| COEF_ADMIS | Integer   |             |                   |
| USO_SIGPAC | String    |             | Crop code         |
| PARCELA_AG | String    |             |                   |
| GRUPO_CULT | String    |             | Crop Group        |
| REGION     | Integer   |             |                   |

## API

See https://icearagon.aragon.es/portal/directorio_ws.jsp for Aragón web services.

### Example

https://icearagon.aragon.es/cartoteca/index.html?LOCAT=http://idearagon.aragon.es/Visor2D?&SERVICIO=Visor2D&CAPA=v_sigpac_recintos&BBOXFOTOGRAMA=649005.99350000:4581760.39700000:810495.30640000:4754860.70140000&ESCALA=5000&COLECCION=SIGPAC&ISGEORREF=false&FECHA=20240101
