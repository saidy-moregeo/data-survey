# Vlaanderen, Belgium

## Submission Details

- **Submitter (Affiliation):** Matthias Mohr
- **Data Provider (Legal Entity):** Agentschap Landbouw & Zeevisserij (Government)
- **Homepage:** https://landbouwcijfers.vlaanderen.be/open-geodata-landbouwgebruikspercelen

## Overview

Since 2020, the Flemish Department of Agriculture and Fisheries has been publishing an extensive set of agricultural
use plot data ("Landbouwgebruikspercelen") going back to the 2008 campaign. The dataset is the Flemish region's
contribution to the EU Common Agricultural Policy (CAP) under the Integrated Administration and Control System
(IACS), recording the parcels declared by farmers for area-based subsidies.

From 2023 onward, the downloadable dataset also includes the company typology (economic specialisation): each farm is
classified annually using a European method into one of four major specialisations (arable farming, horticulture,
livestock farming, mixed farms) based on the standard output of its agricultural productions. The typology is then
applied to each of the company's plots.

## Data

- **URL:** Per-year GeoPackage downloads under `https://www.landbouwvlaanderen.be/bestanden/gis/`, e.g.
  - 2025: `Landbouwgebruikspercelen_2025_-_Voorlopig_(extractie_02-06-2025)_GPKG.zip`
  - 2024: `Landbouwgebruikspercelen_2024_-_Definitief_(extractie_27-03-2025)_GPKG.zip`
  - 2023: `Landbouwgebruikspercelen_2023_-_Definitief_(extractie_28-03-2024)_GPKG.zip`
  - 2022: `Landbouwgebruikspercelen_2022_-_Definitief_(extractie_26-06-2023)_GPKG.zip`
  - 2021: `Landbouwgebruikspercelen_2021_-_Definitief_(extractie_15-03-2022)_GPKG.zip`
  - 2020: `Landbouwgebruikspercelen_2020_uitgebreid_toestand_19-03-2021_GPKG.zip`
  - 2019: `Landbouwgebruikspercelen_2019_-_Definitief_(extractie_20-03-2020)_GPKG.zip`
  - 2018: `Landbouwgebruikspercelen_2018_-_Definitief_(extractie_23-03-2022)_GPKG.zip`
- **Documentation:** https://landbouwcijfers.vlaanderen.be/open-geodata-landbouwgebruikspercelen (PDF documentation is included in each ZIP package)
- **File Format:** GeoPackage (zipped)
- **Projection:** EPSG:31370 (Belgian Lambert 72)
- **License:** [Modellicentie gratis hergebruik v1.0](https://data.vlaanderen.be/id/licentie/modellicentie-gratis-hergebruik/v1.0)
- **Attribution:** "Bron: Dept. LV"

### Properties

Some of the documented fields are missing in the GeoPackage. These are marked with "(missing)".

| Property              | **Data Type** | Constraints                | Description                                                                                  |
|-----------------------|---------------|----------------------------|----------------------------------------------------------------------------------------------|
| fid                   | integer       |                            | Identifier                                                                                   |
| BT_OMSCH              | string        | 200 chars                  | Business type (economic specialization)                                                      |
| BT_BRON               | string        | 50 chars                   | Source of the business type  (year of calculation or specialization indicated)               |
| GRAF_OPP              | number        |                            | Area (ha, accurate to 1m²)                                                                   |
| REF_ID                | integer       |                            | Unique identification number for the field.                                                  |
| GWSCOD_V              | string        | 5 chars (digits), nullable | Pre-cultivation code                                                                         |
| GWSNAM_V              | string        | 90 chars, nullable         | Pre-cultivation name                                                                         |
| GWSCOD_H              | string        | 5 chars (digits), nullable | Main cultivation/crop code                                                                   |
| GWSNAM_H              | string        | 90 chars, nullable         | Main cultivation/crop name                                                                   |
| GWSGRPH_LB            | string        | 150 chars, nullable        | Main cultivation/crop group name                                                             |
| GWSCOD_N              | string        | 5 chars (digits), nullable | First cultivation/crop code                                                                  |
| CWSNAM_N              | string        | 90 chars, nullable         | First cultivation/crop name                                                                  |
| GWSCOD_N2             | string        | 5 chars (digits), nullable | Second cultivation/crop code                                                                 |
| GWSNAM_N2             | string        | 90 chars, nullable         | Second cultivation/crop name                                                                 |
| AMKM (missing)        | string        |                            | Agri-environment code                                                                        |
| AMKM_LB (missing)     | string        |                            | Agri-environment name                                                                        |
| ECOREGELING (missing) | string        |                            | Eco-regulation code                                                                          |
| ECOR_LB (missing)     | string        |                            | Eco-regulation name                                                                          |
| BLS (missing)         | string        |                            | Planting subsidy code (forest farming systems)                                               |
| BLS_LB (missing)      | string        |                            | Planting subsidy name (forest farming systems)                                               |
| GESP_PM               | string        | 11 chars, nullable         | Specialized production method                                                                |
| GESP_PM_LB            | string        | 150 chars, nullable        | Description of specialized production method                                                 |
| BIOCERT (missing)     | string        | `J` or `N`                 | Plot under bio-control with a bio-control body.                                              |
| ERO_NAM               | string        | 20 chars,                  | Erosion color code for the field                                                             |
| STAT_BGV              | string        | 2 chars, nullable          | Status Permanent Grassland under greening (BG)                                               |
| MEERJARIG_GRASLAND    | string        |                            | Status Perennial Grassland (MG6 or higher). Example: MG16 = 16th year grassland              |
| LANDBSTR              | string        | 2 chars, nullable          | Agricultural region in which the center of the field is located                              |
| STAT_AAR              | string        | 10 chars, nullable         | Status Potatoes, follow up rotation duty                                                     |
| PCT_EKBG              | string        | 10 chars, nullable         | Percentage range of field that is ecologically sensitive permanent pasture. Example: `0-10%` |
| PCT_WETVEEN           | string        | 10 chars, nullable         | Percentage range of field that is wetland and/or peatland. Example: `0-10%`                  |
| PRC_GEM               | string        | 30 chars                   | Municipality in which the center of the field is located                                     |
| PRC_NIS               | string        | 5 chars (digits)           | NIS code of the municipality in which the center of the field is located                     |
| X_REF                 | number        |                            | X coordinate of the center of the field (Lambert)                                            |
| Y_REF                 | number        |                            | Y coordinate of the center of the field (Lambert)                                            |
| WGS84_LG              | string        | 11 chars                   | Longitude of the center of the field (WGS84). Example: `3°21'44"`                            |
| WGS84_BG              | string        | 11 chars                   | Latitude of the center of the field (WGS84). Example: `51°11'39"`                            |

Note: Many integer-like numbers are encoded as strings.

## API

The open data viewer https://geopunt.be/ shows the data (search term: landbouwgebruikspercelen).
See https://www.vlaanderen.be/datavindplaats/catalogus/landbouwgebruikspercelen-lv-2022 for more info.

| Standard     | URL                                                         | Documentation                                                                                        |
|--------------|-------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| OGC WFS      | https://geo.api.vlaanderen.be/Landbgebrperc/wfs             | https://www.vlaanderen.be/datavindplaats/catalogus/wfs-landbouwgebruikspercelen                      |
| OGC Features | https://geo.api.vlaanderen.be/Landbgebrperc/ogc/features/v1 | https://metadata.vlaanderen.be/srv/dut/catalog.search#/metadata/01f408db-df8a-49a2-8ce4-0f66b8efe17b |
| OGC WMS      | https://geo.api.vlaanderen.be/ALV/wms                       | https://www.vlaanderen.be/datavindplaats/catalogus/wms-departement-landbouw-en-visserij              |
