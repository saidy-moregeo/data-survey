# GloCAB Cropland Field Boundary Dataset

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Joanne V. Hall, Fernanda Argueta, Louis Giglio — University of Maryland, Department of Geographical Sciences
- **Homepage:** https://doi.org/10.5281/zenodo.10479122

## Overview

The GloCAB Cropland Field Boundary Dataset is a collection of 190,832 manually-digitized cropland field boundaries
across 22 regions spanning five countries: Brazil, Ukraine, United States of America, Canada and Russia. Each
region covers between 74 km² and 38,000 km² and represents a single predominant crop type observed in a specific
month. The dataset is a byproduct of the larger GloCAB (Global Cropland Area Burned) burned-area mapping effort.

Each field boundary feature was manually digitized by a geospatial analyst from 20 m Sentinel-2 imagery and
quality-checked by a senior team member. Where fields were too small to identify individually, the analyst
digitized a larger enveloping boundary covering several small fields and flagged that polygon with `No_Area = 1`.
Users should be aware that "NoArea" polygons do not represent a true single-field boundary.

## Data

- **URL:** https://zenodo.org/records/10479122/files/GloCAB_Field_Boundaries.zip
- **Documentation:** https://zenodo.org/records/10479122 (Zenodo record, version 1.0, 10 January 2024)
- **File Format:** ESRI Shapefile
- **Projection:** EPSG:4326 (WGS84)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution / Citation:**
  > Hall, J., Argueta, F., Zubkova, M., Chen, Y., Randerson, J., & Giglio, L. (2023). GloCAB: Global Cropland
  > Burned Area from Mid-2002 to 2020. *Earth System Science Data Discussions*, 2023, 1–27.
  > https://doi.org/10.5194/essd-2023-191
- **Funding:** NASA; United States Department of the Air Force
- **Contact:** Joanne Hall (jhall1 at umd.edu)

### Properties

| Property | Data Type | Constraints                              | Description                                                                                                                                                                                       |
|----------|-----------|------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| geometry | Polygon   |                                          | Field boundary (or, where `No_Area = 1`, an envelope around a cluster of small fields)                                                                                                            |
| Area_km2 | Real      |                                          | Polygon area in km²                                                                                                                                                                               |
| Ctry_Reg | String    | e.g. `Brazil_A`, `Ukraine_H`, `USA_D`    | Country + region identifier (see regions table below)                                                                                                                                             |
| CropType | String    | `Sugarcane`, `Maize`, `Spring Wheat`, `Winter Wheat`, `Rice` | Predominant crop type observed in the region for the digitisation date                                                                                                                            |
| No_Area  | Integer   | `0` or `1`                               | NoArea flag: `1` indicates the polygon is an envelope around multiple small fields rather than a single field boundary, and should not be used for single-field area / shape analysis             |

### Regions

| Country / Region | Mapping date | Predominant crop | Field boundary count |
|------------------|--------------|------------------|---------------------:|
| Brazil_A         | Aug 2019     | Sugarcane        |                4,510 |
| Brazil_B         | Jul 2019     | Maize            |                1,218 |
| Canada_A         | May 2018     | Spring Wheat     |                  569 |
| Russia_A         | Jul 2019     | Winter Wheat     |                1,739 |
| Russia_B         | Aug 2019     | Winter Wheat     |                2,294 |
| Russia_C         | Apr 2019     | Spring Wheat     |                1,115 |
| Russia_D         | Apr 2019     | Spring Wheat     |                1,362 |
| Russia_E         | Oct 2018     | Winter Wheat     |                2,613 |
| Ukraine_A        | Mar 2017     | Maize            |                3,994 |
| Ukraine_B        | Mar 2017     | Maize            |                6,166 |
| Ukraine_C        | Jul 2017     | Winter Wheat     |                9,327 |
| Ukraine_D        | Aug 2016     | Winter Wheat     |                5,212 |
| Ukraine_E        | Jul 2017     | Winter Wheat     |                5,433 |
| Ukraine_F        | Jun 2017     | Winter Wheat     |                2,757 |
| Ukraine_G        | Jun 2017     | Winter Wheat     |               10,305 |
| Ukraine_H        | Jul 2020     | Winter Wheat     |              123,671 |
| USA_A            | Nov 2018     | Sugarcane        |                1,091 |
| USA_B            | Oct 2019     | Sugarcane        |                2,402 |
| USA_C            | Apr 2018     | Spring Wheat     |                1,342 |
| USA_D            | Sep 2020     | Rice             |                  746 |
| USA_E            | Sep 2017     | Rice             |                1,499 |
| USA_F            | Sep 2017     | Rice             |                1,467 |
| **Total**        |              |                  |          **190,832** |

## API

No publicly documented API. The dataset is distributed as a static ZIP archive on Zenodo.
