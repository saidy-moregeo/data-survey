# Estonia

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Põllumajanduse Registrite ja Informatsiooni Amet (ARIB / PRIA, Government)
- **Homepage:** http://data.europa.eu/88u/dataset/pria-pollud

## Overview

ARIB / PRIA publishes Geospatial Aid Application Estonia (GSAA) agricultural
parcels as an INSPIRE theme. The "Fields and Eco Areas (GSAA)" layer is the
authoritative crop-field dataset that farmers submit annually under the Common
Agricultural Policy. Data is available year by year and is served through ARIB's
INSPIRE WFS endpoint.

For a multi-year bulk download in shapefile format, see also the
[EuroCrops Estonia](EU-EuroCrops.md) dataset.

## Data

- **URL:** https://kls.pria.ee/geoserver/inspire_gsaa/wfs (per-year layer `inspire_gsaa:LU.GSAA.AGRICULTURAL_PARCELS_{year}`, 2010 – present)
- **Documentation:** http://data.europa.eu/88u/dataset/pria-pollud
- **File Format:** GML (WFS 2.0.0)
- **Projection:** EPSG:3301 (Estonian Coordinate System of 1997)
- **License:** CC-BY-SA-3.0
- **Attribution:** © Põllumajanduse Registrite ja Informatsiooni Amet

### Properties

| Property            | Data Type | Constraints  | Description                              |
|---------------------|-----------|--------------|------------------------------------------|
| pollu_id            | string    |              | Field identifier                         |
| taotlusaasta        | integer   | year         | Application year                         |
| pindala_ha          | number    | hectares     | Field area                               |
| taotletud_kultuur   | string    | crop name    | Requested crop culture                   |
| geom                | Polygon   | EPSG:3301    | Field geometry                           |

The EuroCrops shapefile snapshot exposes additional per-year columns
(`taotletud_maakasutus`, `taotletud_toetus`, `niitmise_tuvastamise_staatus`,
`niitmise_tuvast_ajavahemik`, `viimase_muutmise_aeg`, `taotleja_nimi`,
`taotleja_registrikood`) — see `ec_ee` and the EuroCrops page.

### Example

Use the WFS endpoint, e.g.:

```
https://kls.pria.ee/geoserver/inspire_gsaa/wfs
  ?service=WFS&version=2.0.0&request=GetFeature
  &typeName=inspire_gsaa:LU.GSAA.AGRICULTURAL_PARCELS_2024
  &count=10
```

## API

| Standard | URL                                                            |
|----------|----------------------------------------------------------------|
| OGC WFS  | https://kls.pria.ee/geoserver/inspire_gsaa/wfs                 |
