# AI4SmallFarms: Field boundaries for Cambodia and Vietnam

## Submission Details

- **Submitter (Affiliation):** Snehal Chaudhari, ASU
- **Data Provider (Legal Entity):** DATA Archiving and Networked Services (DANS) / Persello et al., University of Twente ITC, TU Delft, DLR (Research)
- **Homepage:** https://research.tudelft.nl/en/publications/ai4smallfarms-a-dataset-for-crop-field-delineation-in-southeast-a

## Overview

Agricultural field polygons within smallholder farming systems are essential to facilitate the collection of geo-spatial data useful for farmers, managers, and policymakers. However, the limited availability of training labels poses a challenge in developing supervised methods to accurately delineate field boundaries using Earth Observation (EO) data.

This data set allows researchers to test and benchmark machine-learning methods to delineate agricultural field boundaries in polygon format. The large-scale data set consists of 439,001 field polygons divided into 62 tiles of approximately 5×5 km distributed across Vietnam and Cambodia, covering a range of fields and diverse landscape types. The field polygons have been meticulously digitized from satellite images, following a rigorous multi-step quality control process and topological consistency checks. Multi-temporal composites of Sentinel-2 (S2) images are provided to ensure cloud-free data.

## Data

- **URL:** Per-tile GeoPackages hosted on the DANS data station (https://phys-techsciences.datastations.nl), one file per tile (e.g. `2_cambodia_areas.gpkg`, `0_vietnam_areas.gpkg`). 33 Cambodia tiles and 29 Vietnam tiles are available.
- **Documentation:** https://research.tudelft.nl/en/publications/ai4smallfarms-a-dataset-for-crop-field-delineation-in-southeast-a
- **File Format:** GeoPackage
- **Projection:** EPSG:32648 (UTM 48N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution / Citation:** Persello, C., Grift, J., Fan, X., Paris, C., Hansch, R., Koeva, M., & Nelson, A. (2023). AI4SmallFarms: A Dataset for Crop Field Delineation in Southeast Asian Smallholder Farms. *IEEE Geoscience and Remote Sensing Letters*, 20, 1-5. Article 2505705. https://doi.org/10.1109/LGRS.2023.3323095

### Properties

Fields in tiles_asia.gpkg
| Property    | Data Type | Constraints | Description                     |
| ----------- | --------- | ----------- | ------------------------------- |
| id          | int64     |             | Tile Identifier                 |
| country     | string    |             | Country Name                    |
| split       | string    |             | 'train', 'test', 'validate'     |
| month       | int64     |             | Recored Month                   |
| year        | int64     |             | Recored Year                    |
| month_text  | string    |             | Month in text                   |
| end_day     | int64     |             |                                 |


Fields in [tile_id]_[country_name]_areas.gpkg

| Property    | Data Type | Constraints | Description                                                                                             |
| ----------- | --------- | ----------- | ------------------------------------------------------------------------------------------------------- |
| id          | int64     |             | Tile Identifier                                                                                         |
| country     | string    |             | Country Name                                                                                            |
| _predicate  | string    |             | No official description but looks like this check is the geometry in withi or intersectiong the parcels |

Valid values for _predicate are : INTERSECTS and WITHIN

### Example

- tiles_asia.gpkg

   | Property    | Example Value | 
   | ----------- | ------------- | 
   | id          | 0             |
   | country     | vietnam       |
   | split       | train         |
   | month       | 01            |
   | year        | 2021          |
   | month_text  | Jan           |
   | end_day     | 31            |


- [tile_id]_[country_name]_areas.gpkg

   | Property    | Example Value | 
   | ----------- | ------------- | 
   | id          | 0             |
   | country     | vietnam       |
   | _predicate  | INTERSECTS    |

