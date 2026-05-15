# United Kingdom — UKFields (Fiboa-UK)

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Samuel Bancroft (University of Leeds) and Jake Wilkins
- **Homepage:** https://github.com/Spiruel/UKFields

## Overview

UKFields is an open dataset of automatically delineated agricultural field boundaries covering the entire United
Kingdom (England, Wales, Scotland and Northern Ireland). It is published natively as a [fiboa](https://fiboa.org/)
GeoParquet and was the first fiboa-format community dataset for the UK — distributed under the "Fiboa-UK" name in
the Google Earth Engine community catalog and on Zenodo.

The boundaries were derived by applying Meta's Segment Anything Model (SAM) to a harmonic composite of Sentinel-2
imagery for 2021, then masking the output to the 2021 Dynamic World cropland composite to retain only agricultural
parcels.

Because the dataset is derived from satellite imagery (not from declarations or cadastral registers), the polygons
represent observed field extents rather than legal or administrative parcels.

## Data

- **URL:**
  - Zenodo GeoParquet (single file `ukfields.parquet`, ~234 MB):
    https://zenodo.org/records/11110206/files/ukfields.parquet
  - Zenodo record (versions + DOI metadata): https://doi.org/10.5281/zenodo.11110206
  - Google Earth Engine FeatureCollection asset: `projects/sat-io/open-datasets/UK-FIELDS`
    (mirror of `users/spiruel/ukfields`)
  - Awesome GEE Community Catalog entry: https://gee-community-catalog.org/projects/fiboa_uk/
- **Documentation:** https://github.com/Spiruel/UKFields
- **File Format:** GeoParquet (fiboa-compliant); also available as a Google Earth Engine FeatureCollection
- **Projection:** OSGB36 / British National Grid (EPSG:27700)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) per the Zenodo deposit.
  The source code in the GitHub repository is released under CC0-1.0; the data itself follows the Zenodo licence.
- **Attribution / Citation:**
  > Bancroft, S., & Wilkins, J. (2024). UKFields (1.0.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.11110206
- **Temporal coverage:** 2021 (single snapshot derived from 2021 Sentinel-2 harmonic composites and the 2021
  Dynamic World cropland mask)
- **Method:**
  - Sentinel-2 harmonic composites for 2021 (Google Earth Engine)
  - Meta [Segment Anything Model](https://segment-anything.com/) (SAM) applied for parcel segmentation
  - Output masked to the 2021 [Dynamic World](https://dynamicworld.app/) cropland class

### Properties

| Property               | Data Type | Constraints | Description                         |
|------------------------|-----------|-------------|-------------------------------------|
| geometry               | Polygon   | NOT NULL    | Field boundary polygon              |
| id                     | string    | NOT NULL    | Unique identifier per fiboa core    |
| area                   | number    |             | Polygon area in m² (per fiboa core) |
| perimeter              | number    |             | Polygon area in m² (per fiboa core) |
| determination_method   | string    |             | Determination method                |
| determination_datetime | datetime  |             |                                     |

## API

The dataset is queryable as a FeatureCollection in Google Earth Engine. An example script is provided in the
Awesome GEE Community Catalog:
https://code.earthengine.google.com/?scriptPath=users/sat-io/awesome-gee-catalog-examples:agriculture-vegetation-forestry/FIBOA-UK-FIELDS
