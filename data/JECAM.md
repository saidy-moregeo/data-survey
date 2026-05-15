# JECAM (Tropical Countries)

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** CIRAD (research) — published on the CIRAD Dataverse
- **Homepage:** https://dataverse.cirad.fr/dataset.xhtml?persistentId=doi:10.18167/DVN1/P7OLAP

## Overview

Harmonized in-situ JECAM datasets for agricultural land use mapping and monitoring
in tropical countries. The database aggregates nine land-use / land-cover datasets
collected in a standardized manner between 2013 and 2022 across seven tropical
countries within the JECAM (Joint Experiment for Crop Assessment and Monitoring)
initiative:

- Burkina Faso (Koumbia)
- Madagascar (Antsirabe)
- Brazil (São Paulo, Tocantins)
- Senegal (Nioro, Niakhar, Mboro, Tattaguine, Koussanar)
- Kenya (Muranga)
- Cambodia (Kandal)
- South Africa (Mpumalanga)

The dataset contains 31,879 records (24,287 crop and 7,592 non-crop) collected at
field scale by local experts following a common protocol. GPS waypoints were
gathered along roads/tracks for homogeneous fields/entities of at least 20 × 20 m²
and recorded with VHSR imagery loaded onto GPS tablets running QGIS. For each
waypoint a set of cropping-practice attributes (crop type, cropping pattern,
management techniques) were captured.

These datasets are intended for validating cropland and crop-type maps in the
tropics and for benchmarking classification methods.

## Data

- **URL:** https://dataverse.cirad.fr/api/access/datafile/17993
- **Documentation:** https://dataverse.cirad.fr/dataset.xhtml?persistentId=doi:10.18167/DVN1/P7OLAP
- **Citation:** Jolivot, A. *et al.* (2021). Harmonized in situ JECAM datasets for agricultural land use mapping and monitoring in tropical countries. CIRAD Dataverse V4. https://doi.org/10.18167/DVN1/P7OLAP
- **File Format:** ESRI Shapefile
- **Projection:** EPSG:4326 (WGS 84)
- **License:** CC-BY-4.0
- **Attribution:** JECAM SIRAD, https://doi.org/10.18167/DVN1/P7OLAP
- **Data Creation Details:** Ground-truthed; opportunistic sampling along roads/tracks; VHSR-assisted digitisation.

### Properties

| Property             | Data Type | Constraints                | Description                                                   |
|----------------------|-----------|----------------------------|---------------------------------------------------------------|
| Id                   | string    |                            | Record identifier                                             |
| Country              | string    | country name               | Source country                                                |
| SiteName             | string    |                            | JECAM study-site name                                         |
| AcquiDate            | date      |                            | Acquisition date of the waypoint                              |
| Area_ha              | number    | hectares                   | Estimated field area (null if 0)                              |
| CropType1            | string    | JECAM crop list            | Primary crop / land-cover label                               |
| crop:code            | string    | from `jecam_crop.csv`      | Numeric crop code derived from `CropType1`                    |
| Irrigated            | boolean   |                            | Whether the field is irrigated                                |
| geometry             | Polygon   | EPSG:4326                  | Field geometry                                                |

The fiboa converter applies the `admin-division` and `crop` extensions and uses the
shared JECAM code list at https://fiboa.org/code/jecam/crop.csv.

### Example

See the supplementary `Study_sites.kml` distributed with the dataset on the CIRAD
Dataverse.

## API

No public API; downloads are provided via the CIRAD Dataverse.
