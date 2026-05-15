# U.S. Department of Agriculture Crop Sequence Boundaries

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** United States Department of Agriculture (USDA), National Agricultural Statistics Service (NASS) (Government)
- **Homepage:** https://www.nass.usda.gov

## Overview

The Crop Sequence Boundaries (CSB), developed with USDA's Economic Research Service, produces estimates of field boundaries, crop acreage, and crop rotations across the contiguous United States. It uses satellite imagery with other public data and is open source, allowing users to conduct area and statistical analysis of planted U.S. commodities and providing insight on farmer cropping decisions.

NASS needed a representative field to predict crop planting based on common crop rotations such as corn-soy, and ERS is using this product to study changes in farm management practices like tillage or cover cropping over time.

CSB represents non-confidential single-crop field boundaries over a set time frame. It does not contain personal identifying information. The boundaries captured are of crops grown only — not ownership boundaries or tax parcels (unit of property). The data are derived from satellite imagery and publicly available data; they do not come from producers or agencies like the Farm Service Agency.

## Data

- **URL:**
  - 2024 (covering 2017-2024): https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/datasets/NationalCSB_2017-2024_rev23.zip
  - 2023 (covering 2016-2023): https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/datasets/NationalCSB_2016-2023_rev23.zip
- **Documentation:** https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/index.php and https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/metadata_Crop-Sequence-Boundaries-2023.htm
- **File Format:** ESRI File GeoDatabase (zipped)
- **Projection:** Albers Conical Equal Area (as used by mrlc.gov / NLCD)
- **License:** [License and Liability](https://gee-community-catalog.org/projects/csb/#license-and-liability) — provided as-is and considered public domain.

The CDL (Cropland Data Layer) crop codes are documented at https://www.nass.usda.gov/Research_and_Science/Cropland/docs/CDL_codes_names_colors.xls .

### Properties

| Property     | **Data Type** | Constraints | Description       |
|--------------|---------------|-------------|-------------------|
| CSBID        | String        |             | Identifier        |
| CSBYEARS     | String        |             |                   |
| CSBACRES     | Real          |             | Area in acres     |
| CDL2016      | Integer       |             | Crop code 2016    |
| CDL2017      | Integer       |             | Crop code 2017    |
| CDL2018      | Integer       |             | Crop code 2018    |
| CDL2019      | Integer       |             | Crop code 2019    |
| CDL2020      | Integer       |             | Crop code 2020    |
| CDL2021      | Integer       |             | Crop code 2021    |
| CDL2022      | Integer       |             | Crop code 2022    |
| CDL2023      | Integer       |             | Crop code 2023    |
| STATEFIPS    | String        |             | State identifier  |
| STATEASD     | String        |             | State identifier  |
| ASD          | String        |             |                   |
| CNTY         | String        |             | County            |
| CNTYFIPS     | String        |             | County identifier |
| INSIDE_X     | Real          |             |                   |
| INSIDE_Y     | Real          |             |                   |
| Shape_Length | Real          |             |                   |
| Shape_Area   | Real          |             |                   |


### Example

See https://www.nass.usda.gov/Research_and_Science/Crop-Sequence-Boundaries/Viewer/index.php.
