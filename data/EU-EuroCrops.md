# EuroCrops

## Submission Details

- **Submitter (Affiliation):** Matthias Mohr
- **Data Provider (Legal Entity):** Maja Schneider, Technical University of Munich (TUM) (Research / Individual)
- **Homepage:** https://www.eurocrops.tum.de

## Overview

EuroCrops is a dataset collection combining all publicly available self-declared crop reporting datasets from countries of the European Union. The following countries are covered:

- [Austria](https://github.com/maja601/EuroCrops/wiki/Austria)
- [Belgium](https://github.com/maja601/EuroCrops/wiki/Belgium)
- [Czechia](https://github.com/maja601/EuroCrops/wiki/Czechia)
- [Germany](https://github.com/maja601/EuroCrops/wiki/Germany)
- [Denmark](https://github.com/maja601/EuroCrops/wiki/Denmark)
- [Estonia](https://github.com/maja601/EuroCrops/wiki/Estonia)
- [Spain](https://github.com/maja601/EuroCrops/wiki/Spain)
- [France](https://github.com/maja601/EuroCrops/wiki/France)
- [Croatia](https://github.com/maja601/EuroCrops/wiki/Croatia)
- [Lithuania](https://github.com/maja601/EuroCrops/wiki/Lithuania)
- [Latvia](https://github.com/maja601/EuroCrops/wiki/Latvia)
- [Netherlands](https://github.com/maja601/EuroCrops/wiki/Netherlands)
- [Portugal](https://github.com/maja601/EuroCrops/wiki/Portugal)
- [Romania](https://github.com/maja601/EuroCrops/wiki/Romania)
- [Sweden](https://github.com/maja601/EuroCrops/wiki/Sweden)
- [Slovenia](https://github.com/maja601/EuroCrops/wiki/Slovenia)
- [Slovakia](https://github.com/maja601/EuroCrops/wiki/Slovakia)

National-level FIBOA pages (where they exist) describe the underlying source datasets in more detail — this page focuses on the EuroCrops-harmonised variants and the per-country HCAT crop mapping files.

The shared HCAT columns each variant adds are:

| Property | Data Type | Constraints | Description |
| -------- | --------- | ----------- | ----------- |
| EC_trans_n | string | see HCAT | The original crop name translated into English |
| EC_hcat_n  | string | see HCAT | Machine-readable HCAT name of the crop |
| EC_hcat_c  | string | 10 digits | 10-digit HCAT code indicating the crop hierarchy |

Country mapping CSVs are hosted at https://github.com/maja601/EuroCrops/tree/main/csvs/country_mappings.

## Data

- **Project URL:** https://github.com/maja601/EuroCrops
- **Cloud-Native variant:** https://beta.source.coop/repositories/cholmes/eurocrops/
- **Metadata catalogue:** https://zenodo.org/communities/eurocrops
- **License:** [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)

## Country variants

### Belgium — Flanders

- **Year:** 2021
- **Source ZIP:** https://zenodo.org/records/10118572/files/BE_VLG_2021.zip?download=1 -> `BE_VLG_2021/BE_VLG_2021_EC21.shp`
- **License:** CC-BY-SA-4.0
- **National page:** [BE-VLG.md](BE-VLG.md)

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| REF_ID | string | unique | Field identifier |
| GRAF_OPP | number | | Area in hectares |
| GWSCOD_H | string | | Main-crop code |
| GWSNAM_H | string | | Main-crop name |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Estonia

- **Year:** 2021
- **Source ZIP:** https://zenodo.org/records/14094196/files/EE_2021.zip?download=1
- **License:** CC-BY-SA-4.0 (original attribution: © Põllumajanduse Registrite ja Informatsiooni Amet)
- **National page:** [EE.md](EE.md)

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| pollu_id | string | unique | Field identifier |
| taotlusaas | integer | year | Year |
| pindala_ha | number | ha | Area in hectares |
| taotletud_ | string | | Requested crop culture |
| taotletu_1 | string | | Requested land use |
| taotletu_2 | string | | Requested support |
| niitmise_t | string | | Mowing-detection status |
| niitmise_1 | string | | Mowing-detection period |
| viimase_mu | string | date | Last edit time |
| taotleja_n | string | | Applicant name |
| taotleja_r | string | | Applicant's registration code |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Lithuania

- **Year:** 2021
- **Source ZIP:** https://zenodo.org/records/6868143/files/LT_2021.zip -> `LT/LT_2021_EC.shp`
- **License:** CC-BY-SA-4.0
- **National page:** [LT.md](LT.md)

The source `Shape_Area` is in square metres. The `GRUPE` field covers crop classes including Vegetables, Buckwheat, Pulse cereals, Oats, Winter cereals, Summer cereals, Spring cereals, Sugar beet, Berries, Maize.

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| NMA_ID | string | unique | Field identifier |
| GRUPE | string | | Crop name |
| Shape_Leng | number | m | Perimeter |
| Shape_Area | number | m^2 | Area in square metres |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Latvia

- **Year:** 2021
- **Source ZIP:** https://zenodo.org/records/8229128/files/LV_2021.zip -> `LV_2021/LV_2021_EC21.shp`
- **License:** CC-BY-SA-4.0 (original attribution: Lauku atbalsta dienests)
- **National page:** [LV.md](LV.md)

The source ZIP already contains HCAT columns from EuroCrops.

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| OBJECTID | string | unique | Field identifier |
| AREA_DECLA | number | ha | Declared area |
| DATA_CHANG | datetime | | Last change date |
| PERIOD_COD | integer | year | Period code |
| PARCEL_ID | integer | | Parcel identifier |
| PRODUCT_CO | string | | Crop product code |
| AID_FORMS | string | | Subsidy type |
| EC_NUTS3 | string | NUTS 3 | NUTS-3 region |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Netherlands (Crops)

- **Year:** Per-year (2009-2025 in the base BRP dataset)
- **Source URL:** yearly files at `https://service.pdok.nl/rvo/brpgewaspercelen/atom/v1_0/downloads/` (e.g. `brpgewaspercelen_definitief_2024.gpkg`)
- **License:** CC-BY-SA-4.0 (original BRP licence is CC0-1.0)
- **National page:** [NL.md](NL.md)

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| id | string | unique | BRP identifier |
| area | number | ha | Area in hectares |
| category | string | Grasland / Bouwland | Grass- or arable-land category |
| gewascode | string | | Crop code |
| gewas | string | | Crop name |
| jaar | integer | year | Year |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Romania

- **Year:** Cross-border project (no year set; 2017-01-01 used as the reference date)
- **Source ZIP:** https://zenodo.org/records/14094196/files/RO_ny.zip?download=1 -> `RO/*.shp`
- **License:** CC-BY-SA-4.0 (original licence: CC0-1.0)

The `LC_MAPCODE` field covers agricultural classes including A (Arable Land), CAG (Covered Agricultural Land), G/N (Grassland), P/T (Trees), R (Rice).

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | WGS 84 / UTM 35N | Field-boundary geometry |
| AREA_HA | number | m^2 | Area |
| SOURCE | string | | Source dataset reference |
| LC_MAPCODE | string | | Land-cover code |
| LC_CLASS_N | string | | Land-cover class name |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

### Slovenia

- **Year:** 2021
- **Source ZIP:** https://zenodo.org/records/10118572/files/SI_2021.zip?download=1 -> `SI_2021_EC21.shp`
- **License:** CC-BY-SA-4.0 (original attribution: Ministrstvo za kmetijstvo, gozdarstvo in prehrano)
- **National page:** [SI.md](SI.md)

`AREA` is in square metres. The source ZIP already contains HCAT columns from EuroCrops.

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon | | Field-boundary geometry |
| ID | string | unique | Field identifier |
| AREA | number | m^2 | Area |
| GERK_PID | integer | | Slovenian GERK parcel id |
| SIFRA_KMRS | string | | Crop-type class |
| RASTLINA | string | | Plant |
| CROP_LAT_E | string | | English Latin crop name |
| COLOR | string | | Display colour |
| EC_NUTS3 | string | NUTS 3 | NUTS-3 region |
| EC_trans_n / EC_hcat_n / EC_hcat_c | string | | HCAT columns added by EuroCrops |

## API

EuroCrops is made available by multiple third-parties through their APIs, e.g. Sentinel Hub and Euro Data Cube. The harmonised cloud-native variant is also browsable on [Source Cooperative](https://beta.source.coop/repositories/cholmes/eurocrops/).
