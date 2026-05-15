# Castilla y León, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Junta de Castilla y León (Government)
- **Homepage:** https://datos.jcyl.es/web/jcyl/set/es/sector-publico/sigpac/1284212629849

## Overview

This dataset is the official SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) land plan for Castilla y León. It is based on the SIGPAC (FEGA) database and includes the Land Consolidation Replacement Farms that are not always updated in the public SIGPAC viewer. The data is curated by the regional Department of Agriculture, Livestock and Rural Development and published per province, per campaign year (2019–2025).

## Data

- **URL:** http://ftp.itacyl.es/cartografia/05_SIGPAC/`<YEAR>`_ETRS89/Parcelario_SIGPAC_CyL_Provincias/ (per-province ZIP archives, e.g. `2025_ETRS89/...`)
- **Documentation:** http://ftp.itacyl.es/cartografia/05_SIGPAC/Catalogo_Metadatos/
- **File Format:** Shapefile (per province, distributed as ZIP; enclosure shapefile named `*_RECFE*.shp` / `*_BURGOS*.shp`)
- **Projection:** EPSG:4258 (ETRS89 geographic)
- **License:** CC-NC: Free use of the data is permitted, but commercial exploitation is prohibited (see [LICENCIA-IGCYL-NC-2012.pdf](http://ftp.itacyl.es/cartografia/LICENCIA-IGCYL-NC-2012.pdf))

### Properties

| Property   | Data Type | Constraints | Description     |
|------------|-----------|-------------|-----------------|
| DN_OID     | Integer64 |             |                 |
| SUPERFICIE | Real      |             | Area in m^2     |
| PERIMETRO  | Real      |             | Perimeter in m  |
| PROVINCIA  | Integer64 |             | Province ID     |
| MUNICIPIO  | Integer64 |             | Municipality ID |
| AGREGADO   | Integer64 |             |                 |
| ZONA       | Integer64 |             |                 |
| POLIGONO   | Integer64 |             |                 |
| PARCELA    | Integer64 |             |                 |
| RECINTO    | Integer64 |             |                 |
| USO_SIGPAC | String    |             | SIGPAC use code |
| COEF_REGAD | Integer64 |             |                 |
| C_REFREC   | String    |             |                 |
| Shape_Leng | Real      |             |                 |
| Shape_Area | Real      |             |                 |

