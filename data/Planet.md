# Planet Automated Field Boundaries

## Submission Details

- **Submitter (Affiliation):** Matej Batič, Planet Labs
- **Data Provider (Legal Entity):** Planet Labs PBC (Company)
- **Homepage:** https://www.planet.com

## Overview

These field boundaries are created by Planet Labs, using an automated process based on satellite imagery. The algorithm works on a monthly basis and is available for the entire globe. The data is provided in GeoPackage format. For more information, see the [field boundaries technical specification](https://planet.widen.net/s/5vq8w5wjvf/2403.08_mar-9444-field-boundaries-technical-specification-sheet-3).

## Data

- **Data access:** Data must be obtained from the Planet subscriptions API — see https://developers.planet.com/docs/planetary-variables/field-boundaries/. The output is a GeoPackage with a file name such as `FIELD_BOUNDARIES_v1.0.0_S2_P1M-20230101T000000Z_fb.gpkg`. The filename contains the acquisition timestamp (`-YYYYMMDDTHHMMSSZ_fb.gpkg`).
- **Documentation:** https://developers.planet.com/docs/planetary-variables/field-boundaries/
- **File Format:** GeoPackage
- **Projection:** EPSG:4326
- **License:** [Planet Proprietary License](https://www.planet.com/licensing-information/)
- **Attribution:** © 2024 Planet Labs, PBC

### Properties

| Property | Data Type | Constraints | Description |
| -------- | --------- | ----------- | ----------- |
| polygon_id | integer | >=0 | Each polygon in the resulting GeoPackage file has assigned a unique identification number. | 
| area_ha | number | > 0 | Polygon area in hectares. |
| micd | number | > 0 | Maximum Inscribed Circle Diameter (MICD) is an intuitive proxy for the width of a field, even in case of rotated and narrow-but-curved fields. | 
| ca_ratio | number | > 0 | Circumference-Area ratio (CA ratio) is calculated by dividing the circumference of a given polygon by the square root of its area. This ratio is then adjusted so that a circle corresponds to 0, and scaled so that a square corresponds to 1. |
| qa | integer | 0,1,2 | The Quality Assessment attribute presents three values: <ul><li>0: Polygons with high quality, i.e. with micd > 30 m.</li><li>1: Polygons with micd < 30 m. The quality for these polygons cannot be guaranteed.</li><li>2: Polygons clipped by the AOI.</li></ul> |



### Example

https://devext.sinergise.com/parcelio/
