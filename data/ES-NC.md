# Navarra, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Comunidad Foral de Navarra (Government)
- **Homepage:** https://gobiernoabierto.navarra.es

## Overview

This dataset contains the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) reference enclosures (Recintos) for the autonomous community of Navarra, updated and coordinated with the land registry. It allows the geographical identification of plots declared by farmers in any aid scheme related to the surface area. The Comunidad Foral de Navarra publishes the graphic information in ESRI Shape format (in ETRS89 UTM 30N reference system).

The Navarra SIGPAC download portal publishes per-municipality archives.

## Data

- **URL:** https://sigpac.navarra.es/descargas/ (per-municipality ZIP archives)
- **Documentation:** https://sigpac.navarra.es/descargas/
- **File Format:** Shapefile (per municipality, distributed as ZIP)
- **Projection:** EPSG:25830 (ETRS89 / UTM zone 30N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see https://sigpac.navarra.es/descargas/)
- **Attribution:** Comunidad Foral de Navarra

### Properties

| Property   | Data Type | Constraints    | Description       |
|------------|-----------|----------------|-------------------|
| FEATURE    | Integer64 |                | ID                |
| REFSIGPAC  | String    | max_length=25  | SIGPAC ID         |
| CP         | Integer64 |                |                   |
| CMUNICIPIO | Integer64 |                | Municipality code |
| MUNICIPIO  | String    | max_length=100 | Municipality name |
| POLIGONO   | Integer64 |                |                   |
| PARCELA    | Integer64 |                |                   |
| CRECINTO   | Integer64 |                |                   |
| IDUSO24    | String    | max_length=25  | USE_CODE          |
| USO24      | String    | max_length=100 | USE_CODE_NAME     |
| INCIDENCIA | String    | max_length=50  |                   |
| IDUSO03    | String    | max_length=100 |                   |
| TIPOEXPLOT | String    | max_length=50  |                   |
| CSUBVENCI  | String    | max_length=5   |                   |
| PENDIENTE  | Integer64 |                |                   |
| IDCOMARCA  | String    | max_length=25  | Comarca ID        |
| COMARCA    | String    | max_length=100 | Comarca name      |
| REGION     | String    | max_length=5   | Region ID         |
| BEGINLIFE  | String    | max_length=10  | Date DD/MM/YYYY   |
| SUPERFICIE | Real      |                |                   |
