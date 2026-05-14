# West Bahia, Brazil (LEM)

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Embrapa / Mendeley Data (Research / Open Data Repository)
- **Homepage:** https://data.mendeley.com/datasets/vz6d7tw87f/1

## Overview

LEM (Luís Eduardo Magalhães) is the supplementary dataset of a paper published in the
*Data in Brief* journal. It provides monthly land-use information for 1854 agricultural
fields from October 2019 through September 2020 in Luís Eduardo Magalhães and other
municipalities in the west of Bahia state, Brazil. Most of the 16 land-use classes are
related to crops; the dataset is well suited for crop-rotation studies and for training
classifiers from time series.

## Data

- **URL:** https://data.mendeley.com/public-files/datasets/vz6d7tw87f/files/57c83c3f-b5a9-45f5-94f8-ac1df8fab923/file_downloaded
- **Documentation:** https://data.mendeley.com/datasets/vz6d7tw87f/1
- **File Format:** ESRI Shapefile (zipped)
- **Projection:** EPSG:4326 (WGS 84)
- **License:** CC-BY-4.0
- **Attribution:** Copyright © 2024 Elsevier Inc., its licensors, and contributors.
- **Data Creation Details:** Manually digitised field boundaries with monthly crop labels.

### Properties

| Property            | Data Type | Constraints                            | Description                                      |
|---------------------|-----------|----------------------------------------|--------------------------------------------------|
| id                  | integer   |                                        | Field identifier                                 |
| Oct_2019 … Sep_2020 | string    | one of the 16 LEM classes (see below)  | Land use for the given month                     |
| note                | string    |                                        | Free-text note                                   |
| geometry            | Polygon   | EPSG:4326                              | Field geometry                                   |

Land-use classes (enum used for every monthly column):
`Beans`, `Brachiaria`, `Cerrado`, `Coffee`, `Conversion area`, `Corn`, `Cotton`,
`Crotalaria`, `Eucalyptus`, `Hay`, `Millet`, `Not identified`, `Pasture`, `Sorghum`,
`Soybean`, `Uncultivated soil`.

### Example

Available as the zipped shapefile linked above (`LEM_dataset.shp`).

## API

No public API; the dataset is distributed as a single archived file on Mendeley Data.
