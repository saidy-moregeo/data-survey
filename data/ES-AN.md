# Andalucía, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Junta de Andalucía (Government)
- **Homepage:** https://www.juntadeandalucia.es

## Overview

The dataset contains the SIGPAC (Sistema de Información Geográfica de Identificación de Parcelas Agrícolas, the Geographical Information System for Common Agricultural Policy) reference enclosures (Recintos) for the autonomous community of Andalucía. SIGPAC was created through collaboration between the Spanish Agricultural Guarantee Fund (FEGA) and the different Autonomous Communities as part of the Integrated Management and Control System for direct CAP aid. It is a public administrative register that contains up-to-date information on the parcels that may benefit from community aid related to the surface area, providing graphic support for these and their subdivisions (enclosures) with defined agricultural uses or developments.

The data is published per campaign year, with the most recent year being 2025 and historic years available back to 2017.

## Data

- **URL:** https://www.juntadeandalucia.es/organismos/agriculturapescaaguaydesarrollorural/servicios/sigpac/visor/paginas/sigpac-descarga-informacion-geografica-shapes-provincias.html (per-province ZIP archives per campaign year, e.g. `SP25_REC_PROV_{code}.zip` for 2025)
- **Documentation:** https://www.juntadeandalucia.es/organismos/agriculturapescaaguaydesarrollorural/servicios/sigpac
- **File Format:** Shapefile (per province, distributed as ZIP)
- **Projection:** EPSG:4258 (ETRS89 geographic)
- **License:** Pursuant to Law 37/2007 of 16 November on the reuse of public sector information and Law 3/2013 of 24 July approving the Statistical and Cartographic Plan of Andalusia 2013-2017, the geographic information of SIGPAC is made available to the public. See [conditions of use](https://www.juntadeandalucia.es/organismos/agriculturapescaaguaydesarrollorural/servicios/sigpac/visor/paginas/sigpac-descarga-informacion-geografica-shapes-provincias.html#toc-condiciones-de-uso-para-la-licencia-de-uso-comercial).
- **Attribution:** ©Junta de Andalucía

Surface (`NU_AREA`) is published in square metres.

### Properties

| Property   | Data Type | Constraints | Description          |
|------------|-----------|-------------|----------------------|
| ID_RECINTO | Real      |             | Identifier           |
| CD_PROV    | Integer   |             | Province code        |
| CD_MUN     | Integer   |             | Municipality code    |
| CD_AGRE    | Integer   |             |                      |
| CD_ZONA    | Integer   |             |                      |
| CD_POL     | Integer   |             |                      |
| CD_PARCELA | Integer   |             |                      |
| CD_RECINTO | Integer   |             |                      |
| CD_USO     | String    |             | Land Use Code (Crop) |
| NU_AREA    | Real      |             | Used area            |
| CSP        | Integer   |             |                      |
| COEF_REG   | Integer   |             |                      |
| PDTE_MEDIA | Real      |             |                      |
| INCIDENCIA | String    |             |                      |
| REGION     | Integer   |             |                      |
| GC         | String    |             |                      |
| VER        | String    |             |                      |


## Example

http://ws128.juntadeandalucia.es/agriculturaypesca/sigpac/index.xhtml