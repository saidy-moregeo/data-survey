# Slovenia

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Ministry of Agriculture, Forestry and Food (Ministrstvo za kmetijstvo, gozdarstvo in prehrano) (Government)
- **Homepage:** https://www.gov.si/drzavni-organi/ministrstva/ministrstvo-za-kmetijstvo-gozdarstvo-in-prehrano/

## Overview

Slovenia Crop Fields.

The Slovenian government provides slightly different, relevant open data sets called GERK, KMRS, RABA and EKRZ. The KMRS dataset includes Common Agricultural Policy (CAP) applications of the last year and discerns around 150 different crop categories. The Land Parcel Identification System (LPIS) is part of the Farm register (RKG), used under the Integrated Administration and Control System (IACS) to administer farmers' single-application aid claims.

Yearly variants from 2021 to 2024 are available.

## Data

- **URL:** Yearly variants, of the form `https://rkg.gov.si/razno/portal_analysis/KMRS_{year}.rar` (containing `KMRS_{year}.shp`); supported years: 2021, 2022, 2023, 2024
- **Documentation:** https://rkg.gov.si/vstop/ — see also the [MKGP-RKG public geographic data viewer](http://rkg.gov.si/GERK/WebViewer/)
- **File Format:** Shapefile (delivered as RAR)
- **Projection:** as published
- **License:** [Javno dostopni podatki: Publicly available data](https://rkg.gov.si/vstop/)

### Properties

| Property   | **Data Type** | Constraints | Description         |
|------------|---------------|-------------|---------------------|
| ID         | integer       |             | Internal identifier |
| GERK_PID   | integer       |             | Gerk ID             |
| SIFRA_KMRS | integer       |             | Crop code?          |
| AREA       | real          |             | Area in m^2         |
| RASTLINA   | string        |             | Crop name Slovenian |
| CROP_LAT_E | string        |             | Crop name English   |

### Example

See [example map for GERK](http://rkg.gov.si/GERK/WebViewer/)

## API

| Standard | URL                                                                                                                                                                                                                                                                         |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OGC WMS  | https://rkg.gov.si/GERK/WebViewer/gerk_viewer/wms?REQUEST=GetMap&SERVICE=WMS&VERSION=1.3.0&EXCEPTIONS=INIMAGE&LOCALE=sl&FEATURE_COUNT=1000&CRS=EPSG%3A3794&TRANSPARENT=FALSE&FORMAT=image%2Fjpeg&LAYERS=&STYLES=&&BBOX=393322%2C76822%2C396862%2C78582&WIDTH=885&HEIGHT=440 |
