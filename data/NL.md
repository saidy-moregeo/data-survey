# The Netherlands

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Rijksdienst voor Ondernemend Nederland (RVO) (Government) — published through PDOK
- **Homepage:** https://www.pdok.nl/introductie/-/article/referentiepercelen (reference parcels) and https://www.pdok.nl/introductie/-/article/basisregistratie-gewaspercelen-brp- (crop fields)

## Overview

Since 2011, the Netherlands' Ministry of Agriculture and associated government bodies have been publishing both
Field Blocks (reference parcels) and Crop Fields as open data (public domain). The data is used in the Dutch
implementation of the Integrated Administration and Control System (IACS): farmers and advisors register their
crop fields each year to apply for the EU Common Agricultural Policy (CAP) subsidy scheme. The data is also used
for agricultural statistics and policymaking.

Crop field data is available from 2009 onward and is typically published in July of a current year as a
preliminary ("voorlopig") dataset, followed up in the next year by a permanent ("definitief") dataset.
Crop field boundaries are supposed to fit within the reference parcels.

The datasets are shared as downloadable files (per-year ZIP/GeoPackage), and the most recent ones also via OGC WMS
and WFS services.

Two Dutch datasets are described here:

- BRP Crop Fields ("Basisregistratie Gewaspercelen") for 2009–2025
- Reference parcels / Field blocks ("Referentiepercelen", formerly AAN)

The same BRP source is also exposed via the EuroCrops project. See [EU-EuroCrops.md](EU-EuroCrops.md) for the cross-country aggregate.

## Crop fields (BRP)

BasisRegistratie Gewaspercelen (BRP) combines the location of agricultural plots with the crop grown. The dataset
is published by RVO and PDOK. Boundaries of agricultural plots are drawn within the reference parcels. Each
applicant annually registers their crop fields to apply for the CAP scheme; a dataset is generated for each year
with reference date 15 May.

The used crop classification is a mix of pure crops, crop categories, land cover types and attributes used for
specific subsidy requirements. The publishing organisation currently labels the attribute as "land cover" rather
than "crop".

### Data

- **URL:** Per-year downloads via the PDOK Atom feed (https://service.pdok.nl/rvo/brpgewaspercelen/atom/v1_0/index.xml):
  - 2025 (concept): https://service.pdok.nl/rvo/brpgewaspercelen/atom/v1_0/downloads/brpgewaspercelen_concept_2025.gpkg
  - 2021–2024 (definitief, GeoPackage): `https://service.pdok.nl/rvo/brpgewaspercelen/atom/v1_0/downloads/brpgewaspercelen_definitief_<YEAR>.gpkg`
  - 2009–2020 (definitief, GeoPackage in ZIP): `https://service.pdok.nl/rvo/brpgewaspercelen/atom/v1_0/downloads/brpgewaspercelen_definitief_<YEAR>.zip`
- **Documentation:** https://www.pdok.nl/introductie/-/article/basisregistratie-gewaspercelen-brp- and https://data.overheid.nl/dataset/10674-basisregistratie-gewaspercelen--brp-
- **File Format:** GeoPackage (some older years zipped)
- **Projection:** EPSG:28992 (RD-New)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (public domain)

### Properties

| Property  | Data Type | Constraints                                          | Description |
|-----------|-----------|------------------------------------------------------|-------------|
| geometry  | Polygon   |                                                      | Field polygon |
| id        | integer   |                                                      | Source identifier |
| area      | number    |                                                      | Area in m² |
| category  | string    | `Grasland`, `Bouwland`, `Sloot`, `Landschapselement` | Land-cover category (Grass land, Arable field, Ditch, Landscape element) |
| gewascode | integer   |                                                      | Crop code |
| gewas     | string    |                                                      | Crop name (Dutch) |
| jaar      | integer   | year                                                 | Reference year (reference date is 15 May) |

## Reference parcels / Field blocks

A field block (Dutch: "Referentieperceel"), formerly known as "AAN" (Agrarisch Areaal Nederland), is a contiguous
agricultural area surrounded by permanent boundaries, which is cultivated by one or more farmers with one or more
crops, is fully or partially set aside, or is fully or partially taken out of production.

The dataset includes the following parcel types: Wood (Hout), Agricultural area (Landbouwgrond), Other (Overig), and
Water (Water). For crop data, see the BRP section above.

### Data

- **URL:** https://service.pdok.nl/rvo/referentiepercelen/atom/downloads/referentiepercelen.gpkg
- **Documentation:** https://www.pdok.nl/introductie/-/article/referentiepercelen
- **File Format:** GeoPackage
- **Projection:** EPSG:28992 (RD-New)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (public domain)

### Properties

| Property                | Data Type | Constraints                                          | Description |
|-------------------------|-----------|------------------------------------------------------|-------------|
| geometry                | Polygon   |                                                      | Parcel polygon |
| id                      | integer   |                                                      | Source identifier |
| area                    | number    |                                                      | Area in m² |
| versiebron              | string    |                                                      | Source identification (digital source, e.g. aerial photo) |
| type                    | string    | `Hout`, `Landbouwgrond`, `Overig`, `Water`           | Parcel type |

### Example

See [example map](https://app.pdok.nl/viewer/#x=159472.96&y=491852.09&z=9.5964&background=BRT-A%20standaard&layers=34026fa9-603d-4511-998c-810c88cd968c;referentiepercelen,1f7d475c-179d-4c71-89ca-4b5fd210ec18;BrpGewas)

## API

Reference Parcels documentation: https://www.pdok.nl/ogc-webservices/-/article/referentiepercelen

| Standard | URL                                                     |
|----------|---------------------------------------------------------|
| OGC WMS  | https://service.pdok.nl/rvo/referentiepercelen/wms/v1_0 |
| OGC WFS  | https://service.pdok.nl/rvo/referentiepercelen/wfs/v1_0 |

Crop Field documentation: https://www.pdok.nl/ogc-webservices/-/article/basisregistratie-gewaspercelen-brp-

| Standard | URL                                                   |
|----------|-------------------------------------------------------|
| OGC WMS  | https://service.pdok.nl/rvo/brpgewaspercelen/wms/v1_0 |
| OGC WFS  | https://service.pdok.nl/rvo/brpgewaspercelen/wfs/v1_0 |
