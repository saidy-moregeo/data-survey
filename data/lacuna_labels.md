# Lacuna Labels — Africa Crop Field Boundary Labels

A region-wide, multi-year set of crop field boundary labels for Africa.

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Planet Labs PBC, in collaboration with Farmerline, Spatial Collective and the Agricultural Impacts Research Group, Clark University (Research / Company)
- **Homepage:** https://github.com/agroimpacts/lacunalabels

## Overview

The [Lacunalabels](https://github.com/agroimpacts/lacunalabels/) repository hosts the analytical code and pointers to datasets resulting from a project to generate a continent-wide set of crop field labels for Africa covering the years 2017-2023. The data are intended for training and assessing machine-learning models that can be used to map agricultural fields over large areas and multiple years.

The project was funded by the [Lacuna Fund](https://lacunafund.org/), and led by [Farmerline](https://farmerline.co/), in collaboration with [Spatial Collective](https://spatialcollective.com/) and the [Agricultural Impacts Research Group](https://agroimpacts.info) at [Clark University](https://www.clarku.edu/departments/geography/).

Please refer to the [technical report](https://github.com/agroimpacts/lacunalabels/blob/main/docs/report/technical-report.pdf) for more details on the methods used to develop the dataset, an analysis of label quality, and usage guidelines.

Data is published at https://zenodo.org/records/11060871 and can be used in accordance with [Planet's participant license agreement for the NICFI contract](https://go.planet.com/nicfi-pla-2024).

## Data

- **URL:** https://africa-field-boundary-labels.s3.us-west-2.amazonaws.com/mapped_fields_final.parquet (also at https://zenodo.org/records/11060871)
- **Documentation:** https://github.com/agroimpacts/lacunalabels
- **File Format:** GeoParquet
- **Projection:** EPSG:4326
- **License:** [Planet NICFI participant license agreement](https://go.planet.com/nicfi-pla-2024)
- **Attribution:** Planet Labs Inc.
- **Citation:** Estes, L. D., Wussah, A., Asipunu, M., Gathigi, M., Kovačič, P., Muhando, J., Yeboah, B. V., Addai, F. K., Akakpo, E. S., Allotey, M. K., Amkoya, P., Amponsem, E., Donkoh, K. D., Ha, N., Heltzel, E., Juma, C., Mdawida, R., Miroyo, A., Mucha, J., Mugami, J., Mwawaza, F., Nyarko, D. A., Oduor, P., Ohemeng, K. N., Segbefia, S. I. D., Tumbula, T., Wambua, F., Xeflide, G. H., Ye, S., Yeboah, F. (2024). *A region-wide, multi-year set of crop field boundary labels for Africa.* arXiv:2412.18483.

### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | EPSG:4326 | Field-boundary geometry |
| id | string | unique | Identifier |
| name | string | | Label name |
| assignment_id | string | | Identifier for each unique mapping assignment (1 mapping by 1 labeller) |
| image_date | string | | Date of the underlying image |
| completion_time | date-time | | Date and time the labelling assignment was completed |
| category | string | `annualcropland`, `cloudshadow`, `fallow`, `treecrop`, `unsure1`, `unsure2` | Coarse land-type category |
