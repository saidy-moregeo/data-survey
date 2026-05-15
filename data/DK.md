# Denmark

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Danish Agricultural Agency (Landbrugsstyrelsen, under the Ministry of Food, Agriculture and Fisheries of Denmark) (Government)
- **Homepage:** https://lbst.dk/

## Overview

The Danish Ministry of Food, Agriculture and Fisheries publishes annual Crop Fields ("Marker") covering the parcels
that farmers declare under the EU Common Agricultural Policy (CAP) within the Integrated Administration and Control
System (IACS). The dataset is available from 2008 onwards and is typically released as preliminary data at the start
of a year and updated through the season.

## Data

- **URL:** Per-year ZIP downloads at `https://landbrugsgeodata.fvm.dk/Download/Marker/Marker_<YEAR>.zip` for years 2008–2024 (e.g. https://landbrugsgeodata.fvm.dk/Download/Marker/Marker_2024.zip)
- **Documentation:** https://geodata-info.dk/srv/eng/catalog.search#/metadata/d91b2c99-d9b0-4e6d-b323-20ac80548186
- **File Format:** Shapefile (zipped)
- **Projection:** EPSG:25832 (ETRS89 / UTM zone 32N)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)

### Properties

| Property  | Data Type | Constraints   | Description                         |
|-----------|-----------|---------------|-------------------------------------|
| Marknr    | string    | max 200 chars | Identifier                          |
| IMK_areal | number    |               | Geometry Area                       |
| Journalnr | string    |               | Journal Number                      |
| CVR       | string    |               | Requester identifier (farmer)       |
| Afgkode   | integer   |               | Crop identifier                     |
| Afgroede  | string    |               | Crop description                    |
| GB        | number    | 0 or 1        | 1 indicates basic payment Requested |
| GBanmeldt | number    |               | Declared Area                       |
| Markblok  | string    |               | Field block identifier              |

## API

| Standard | URL                                                                                           |
|----------|-----------------------------------------------------------------------------------------------|
| OGC WFS  | https://geodata.fvm.dk/geoserver/Marker/wfs?request=GetCapabilities&service=WFS&version=1.1.0 |
| OGC WMS  | https://geodata.fvm.dk/geoserver/Marker/wms?request=GetCapabilities&service=WMS&version=1.1.0 |

### Example

See https://miljoegis.mim.dk/spatialmap?profile=lbst
