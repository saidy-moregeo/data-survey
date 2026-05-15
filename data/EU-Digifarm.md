# DigiFarm Automated Field Boundaries

## Submission Details

- **Submitter (Affiliation):** Santiago Nullo (Digifarm)
- **Data Provider (Legal Entity):** DigiFarm (Company)
- **Homepage:** https://digifarm.io/

## Overview

These field boundaries are created by DigiFarm using a state-of-the-art deep neural-network model for Field Delineation from super-resolved satellite imagery. The results are available through an API, covering over 200 million hectares across 30+ countries. The data is provided through the DigiFarm API at https://api-docs.digifarm.io/, as GeoJSON. For more information see https://digifarm.io/products/field-boundaries.

DigiFarm delineates field boundaries and seeded acres in the growing season based on super-resolved Sentinel-2 at 1 m per pixel using 4 bands (RGB + NIR) and serves the latest data through the API (or as Shape/KML/GeoJSON), which is crucial for in-season analysis and season planning.

## Data

- **Data access:** Data must be obtained from the DigiFarm API (see https://api-docs.digifarm.io/), either as a URL to an API request (e.g. `https://api.digifarm.io/v1/delineated-fields?token=...&bbox=11.13,60.72,11.21,60.76`) or as a local GeoJSON file.
- **Documentation:** https://api-docs.digifarm.io/ and https://digifarm.io/products/field-boundaries
- **File Format:** GeoJSON
- **Projection:** EPSG:4326
- **License:** [DigiFarm Terms and Conditions](https://digifarm.io/legal/tc)
- **Attribution:** © 2024 digifarm.io

### Properties

Some of the documented fields are missing in the GeoPackage. These are marked with "(missing)".

| Property              | **Data Type** | Constraints                | Description                                                  |
| --------------------- | ------------- | -------------------------- | ------------------------------------------------------------ |
| ID                    | integer       | not null                   | Identifier                                                   |
| AREA                  | string        | 200 chars                  | Area (ha)                                                    |
| PROPS                 | string        | json string                | Feature properties                                           |
| PERIMETER             | number        | >0                         | Perimeter (m)                                                |
| CONFIDENCE            | number        | 0-100                      | Automatic delineation confidence level                       |


## API

The API provides a GeoJSON object of delineated fields in the given bbox. Returned GeoJSON features will be limited to a max of 1000 features. If you receive 1000 features, split the querying bbox further to get complete features.

API reference: https://digifarming.readme.io/reference/get_delineated-fields
