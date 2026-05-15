# La Rioja, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Gobierno de La Rioja, Consejería de Agricultura, Ganadería, Mundo Rural y Medio Ambiente (Government)
- **Homepage:** https://www.larioja.org/agricultura/es/gestion-explotaciones

## Overview

This dataset contains the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical
Information System for Common Agricultural Policy) reference enclosures (Recintos) for the autonomous community of
La Rioja (province code `26`). SIGPAC was created through collaboration between the Spanish Agricultural Guarantee
Fund (FEGA) and the different Autonomous Communities as part of the Integrated Management and Control System for
direct CAP aid. It is a public administrative register that contains up-to-date information on the parcels that may
benefit from community aid related to the surface area, providing graphic support for these and their subdivisions
(enclosures) with defined agricultural uses or developments.

In addition to the enclosure / parcel layers, La Rioja publishes a number of associated SIGPAC layers (declaration
lines, permanent pastures, communal pastures, terraces, protection strips, Natura 2000, nitrate zones, disadvantaged
zones, erosion, wetlands, burned areas, repeated crops, phytosanitary information) — see
https://www.larioja.org/agricultura/es/gestion-explotaciones/sigpac/capas-datos-sigpac-asociados.

## Data

La Rioja distributes SIGPAC data through two channels:

- **Provincial-level downloads** via the SIGPAC download service at `sigpac-hubcloud.es` (province code `26`).
- **Municipal-level downloads** via the FEGA ATOM client (centralised by FEGA, mirroring the regional data per
  campaign year). The ATOM client requires the FEGA download client — see
  https://www.fega.gob.es/es/ayudas-directas-y-desarrollo-rural/aplicacion-sigpac/instalacion-cliente-atom.

- **URL:** https://www.larioja.org/agricultura/es/gestion-explotaciones/sigpac/datos-cartograficos-sigpac (entry
  point linking to both distribution channels)
- **Documentation:** https://www.larioja.org/agricultura/es/gestion-explotaciones/sigpac
- **File Format:** Shapefile and GeoPackage (Recintos, Parcelas, Líneas de declaración, Elementos del paisaje, and
  the associated SIGPAC layers — each distributed as a compressed archive)
- **Projection:** EPSG:25830 (ETRS89 / UTM zone 30N) — to be confirmed against the downloaded archive
- **License:** Use is subject to acceptance of a specific licence agreement (the wording is restrictive). See
  https://www.larioja.org/larioja-client/cm/agricultura/images?idMmedia=1377393
  (file: `20201215_Licencia_SIGPAC_Servicio_Descarga`).
- **Attribution:** ©Gobierno de La Rioja / FEGA

### Properties

SIGPAC enclosure (Recinto) attributes follow the federal FEGA schema shared across the autonomous communities.
Typical fields are listed below; the exact column set and types should be confirmed against the downloaded
shapefile / GeoPackage for the relevant campaign year (see related Spanish regions such as
[Castilla y León](ES-CL.md), [Comunitat Valenciana](ES-VC.md) and [Andalucía](ES-AN.md) for verified column lists).

| Property       | Data Type | Constraints | Description                                           |
|----------------|-----------|-------------|-------------------------------------------------------|
| geometry       | Polygon   |             | Enclosure polygon                                     |
| PROVINCIA      | Integer   | `26`        | Province code (La Rioja)                              |
| MUNICIPIO      | Integer   |             | Municipality code (INE)                               |
| AGREGADO       | Integer   |             | Aggregate code                                        |
| ZONA           | Integer   |             | Zone                                                  |
| POLIGONO       | Integer   |             | Cadastral polygon number                              |
| PARCELA        | Integer   |             | Cadastral parcel number                               |
| RECINTO        | Integer   |             | Enclosure number within the parcel                    |
| USO_SIGPAC     | String    |             | SIGPAC land-use code (see FEGA codelist)              |
| COEF_REGADIO   | Numeric   |             | Irrigation coefficient                                |
| INCIDENCIAS    | String    |             | Incidence code(s)                                     |
| PENDIENTE_MEDIA| Numeric   |             | Average slope                                         |
| SUPERFICIE     | Numeric   |             | Surface area (m²)                                     |

## Example

Public SIGPAC web viewer (national): https://sigpac.mapama.gob.es/fega/visor/

## API

No publicly documented API for La Rioja was found. The federal FEGA SIGPAC WMS may serve La Rioja coverage; see
the FEGA portal for current service endpoints.
