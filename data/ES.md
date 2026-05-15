# Spain Field Boundaries

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Fondo Español de Garantía Agraria (FEGA), Ministerio de Agricultura, Pesca y Alimentación (Government)
- **Homepage:** https://sigpac-hubcloud.es/

## Overview

Before 2025, Spanish official field boundaries were mostly regional, all with their specific attributes and
distribution methods (see the per-region survey files such as [Andalucía](ES-AN.md), [Castilla y León](ES-CL.md),
[Comunitat Valenciana](ES-VC.md), [La Rioja](ES-RI.md), etc.).

Since 2025, FEGA operates a unified national portal ("Servicio de Descargas SIGPAC", `sigpac-hubcloud.es`) that
publishes SIGPAC data across the country in a harmonised schema. The portal publishes three primary layers:

- **Recintos** — SIGPAC reference enclosures: a continuous, geographically defined, temporally stable, measurable
  parcel area within a SIGPAC plot, with a single use type. These serve as the reference geometry for Spain's CAP
  management and control system.
- **Cultivo Declarado** — Declaration lines (Solicitud Única / Single Application): the crops declared by farmers
  for CAP direct payments, mapped onto SIGPAC cadastral divisions.
- **Elementos del Paisaje** — Landscape features and environmental elements.

The Cultivo Declarado and Recintos layers are designated as "high-value datasets" under EU Regulation 2023/138.

## Data

- **URL:** https://sigpac-hubcloud.es/html/sdsigpac/descargas/exploradorArchivos.html — file explorer with ZIP
  archives organised by year and data type. The OGC API / WMS endpoints expose the current and previous campaign
  year.
- **Documentation:**
  - Cultivos Declarados model: https://sigpac-hubcloud.es/html/sdsigpac/modelos/cultivos-declarados-SIGPAC.html
  - Recintos model: https://sigpac-hubcloud.es/html/sdsigpac/modelos/recintos-SIGPAC.html
- **File Format:** GeoPackage (distributed as zipped archives)
- **Projection:** EPSG:4258 (ETRS89 geographic) — to be confirmed against the downloaded archive
- **License:** [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** ©FEGA / Ministerio de Agricultura, Pesca y Alimentación

### Properties — Cultivo Declarado

Each record represents a declaration line (línea de declaración) within a farmer's Single Application, mapped to
SIGPAC cadastral divisions. The geometry column is `DN_GEOM`.

| Property            | Data Type      | Constraints | Description                                                                |
|---------------------|----------------|-------------|----------------------------------------------------------------------------|
| DN_GEOM             | Geometry       | NOT NULL    | Declaration line geometry                                                  |
| DN_OID              | Integer        |             | Declaration line identifier                                                |
| PROVINCIA           | TinyInt        | NOT NULL    | Province code (INE)                                                        |
| MUNICIPIO           | SmallInt       | NOT NULL    | Cadastral municipality code                                                |
| AGREGADO            | SmallInt       | NOT NULL    | Aggregate code                                                             |
| ZONA                | TinyInt        | NOT NULL    | Zone code                                                                  |
| POLIGONO            | SmallInt       | NOT NULL    | Cadastral polygon code                                                     |
| PARCELA             | MediumInt      | NOT NULL    | Cadastral parcel code                                                      |
| RECINTO             | MediumInt      | NOT NULL    | Enclosure code within the parcel                                           |
| DN_SURFACE          | Double         | NOT NULL    | Declaration line geometry surface (m²)                                     |
| EXP_ANO             | MediumInt      |             | Application year                                                           |
| EXP_CA              | TinyInt        |             | Autonomous community code                                                  |
| EXP_NUM             | String (30)    |             | Application code                                                           |
| LD_RECINTO          | Integer64      |             | Declaration line identifier within the application                         |
| PARC_PRODUCTO       | MediumInt      |             | Declared crop / product code                                               |
| PARC_SISTEXP        | String (1)     | `S` or `R`  | Exploitation system: `S` rainfed (secano) / `R` irrigated (regadío)        |
| PARC_SUPCULT        | MediumInt      |             | Declared cultivation surface (m²)                                          |
| PARC_SIE            | String (1)     | `S` or `N`  | Ecological focus area eligibility                                          |
| PARC_AYUDASOL       | String (1000)  |             | Requested subsidy codes (comma-separated)                                  |
| PDR_REC             | String (100)   |             | Requested rural-development aid codes (comma-separated)                    |
| CULTSECUN_PRODUCTO  | MediumInt      |             | Secondary crop code                                                        |
| CULTSECUN_AYUDASOL  | String (1000)  |             | Secondary crop subsidy codes (comma-separated)                             |
| TIPO_APROVECHA      | String (20)    |             | Land use / aprovechamiento types (comma-separated)                         |

### Properties — Recintos

A Recinto (enclosure) is a continuous area within a SIGPAC parcel with a single declared use. The geometry column
is `DN_GEOM`.

| Property        | Data Type   | Constraints | Description                                       |
|-----------------|-------------|-------------|---------------------------------------------------|
| DN_GEOM         | Geometry    | NOT NULL    | Enclosure polygon                                 |
| DN_OID          | Integer     |             | Enclosure identifier                              |
| PROVINCIA       | TinyInt     |             | Province code (INE)                               |
| MUNICIPIO       | SmallInt    |             | Cadastral municipality code                       |
| AGREGADO        | SmallInt    |             | Aggregate code                                    |
| ZONA            | TinyInt     |             | Zone code                                         |
| POLIGONO        | SmallInt    |             | Cadastral polygon code                            |
| PARCELA         | MediumInt   |             | Cadastral parcel code                             |
| RECINTO         | MediumInt   |             | Enclosure code within the parcel                  |
| DN_SURFACE      | Double      |             | Surface area (m²)                                 |
| PENDIENTE_MEDIA | SmallInt    |             | Average slope                                     |
| ALTITUD         | SmallInt    |             | Altitude                                          |
| CSP             | SmallInt    |             | Permanent pasture coefficient (Coef. Superficie Pastable) |
| COEF_REGADIO    | SmallInt    |             | Irrigation coefficient                            |
| USO_SIGPAC      | String (2)  |             | SIGPAC land-use code                              |
| INCIDENCIAS     | String (50) |             | Incidence codes                                   |
| REGION          | TinyInt     |             | Region code                                       |

## API

The portal exposes the data via OGC services for the current and previous campaign year. Endpoint URLs are
listed at https://sigpac-hubcloud.es/ — confirm the current endpoints there.

| Standard           | URL                          | Documentation |
|--------------------|------------------------------|---------------|
| OGC API - Features | (see portal services page)   | https://sigpac-hubcloud.es/ogcapi |
| OGC WMS            | https://sigpac-hubcloud.es/wms?service=wms&request=getcapabilities   | - |

### Example

National SIGPAC web viewer: https://sigpac.mapama.gob.es/fega/visor/
