# Extremadura, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Junta de Extremadura (Government)
- **Homepage:** https://www.juntaex.es/lajunta/consejeria-de-infraestructuras-transporte-y-vivienda

## Overview

This dataset contains the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) reference enclosures (Recintos) for the autonomous community of Extremadura. SIGPAC is a public administrative register created through collaboration between the Spanish Agricultural Guarantee Fund (FEGA) and the different Autonomous Communities that contains the parcels that may benefit from CAP aid related to the surface area, providing graphic support for the enclosures with defined agricultural uses.

The data is published on the Junta de Extremadura download portal (SITEX, subcategory 45) as one shapefile per municipality per campaign year.

## Data

- **URL:** http://sitex.gobex.es/SITEX/centrodescargas/viewsubcategoria/45 (per-municipality archives, year selectable)
- **Documentation:** http://sitex.gobex.es/SITEX/files/CondicionesUsoCICTEX.pdf
- **File Format:** Shapefile (per municipality, distributed as ZIP)
- **Projection:** EPSG:4258 (ETRS89 geographic)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see [CondicionesUsoCICTEX.pdf](http://sitex.gobex.es/SITEX/files/CondicionesUsoCICTEX.pdf))
- **Attribution:** Junta de Extremadura

The published surface (`dn_surface`) is in square metres.

### Properties

| Property    | Data Type | Constraints | Description                               |
|-------------|-----------|-------------|-------------------------------------------|
| dn_surface  | Real      |             | Area                                      |
| dn_perimet  | String    |             | Perimeter                                 |
| provincia   | Real      |             | Adminstrative subdivision Province ID     |
| municipio   | Real      |             | Adminstrative subdivision municipality ID |
| agregado    | int       |             |                                           |
| zona        | int6      |             |                                           |
| poligono    | Real      |             |                                           |
| parcela     | Real      |             |                                           |
| recinto     | Real      |             | Precinct                                  |
| pendiente   | int       |             |                                           |
| coef_regad  | int       |             |                                           |
| uso_sigpac  | String    |             | Land use code                             |
| id          | int       |             | identifier                                |
| numero      | int       |             |                                           |
| pdte_media  | Real      |             |                                           |
