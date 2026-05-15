# Thuringia (TH), Germany

## Submission Details

- **Submitter (Affiliation):** Matthias Mohr
- **Data Provider (Legal Entity):** Thüringer Landesamt für Landwirtschaft und Ländlichen Raum (Government)
- **Homepage:** https://geomis.geoportal-th.de/geonetwork/srv/ger/catalog.search#/metadata/D872F2D6-60BC-11D6-B67D-00E0290F5BA0

## Overview

For use in the application procedure of the Integrated Administration and Control System (IACS), digital data layers are required that represent the current situation of agricultural use with the required accuracy. The field block is a contiguous agricultural area of one or more farmers surrounded by permanent boundaries. The field block thus contains information on the geographical location of the outer boundaries of the agricultural area. Reference parcels are uniquely numbered throughout Germany (Feldblockident – FBI). They also have a field block size (maximum eligible area) and a land use category.

The following field block types exist:

- Utilized agricultural area (UAA)
- Landscape elements (LE)
- Special use areas (SF)
- Forest areas (FF)

The field blocks are classified separately according to the main land uses of arable land (`AL`), grassland (`GL`), permanent crops (`DA`, `OB`, `WB`), including agroforestry systems with an approved utilization concept and according to the BNK for no "agricultural land" (`NW`, `EF` and `PK`) and others.

Landscape elements (LE) are considered part of the eligible agricultural area under defined conditions. In Thuringia, these permanent conditional features are designated as a separate field block (FB) and are therefore part of the Thuringian area reference system (field block reference). They must have a clear reference to a UAA (agricultural land), i.e. they are located within an arable, permanent grassland or permanent crop area or border directly on it.

To produce the DGK-Lw, (official) orthophotos from the Thuringian Land Registry and Surveying Administration (TLBG) and orthophotos from the TLLLR's own aerial surveys are interpreted. The origin of this image data is 50 % of the state area each year, so that up-to-date image data is available for the entire Thuringian state area every year.

## Data

- **URL:** https://www.geoproxy.geoportal-th.de/download-service/opendata/agrar/DGK_Thue.zip
- **Documentation:** included in the ZIP file above and at the homepage
- **File Format:** Shapefile (ZIP)
- **Projection:** as published (EPSG:25832, ETRS89 / UTM 32N)
- **License:** [Data licence Germany – attribution – Version 2.0](https://www.govdata.de/dl-de/by-2-0)
- **Attribution:** © GDI-Th

Uses the FLIK extension (`https://fiboa.org/flik-extension/v0.2.0/schema.yaml`). Readers for this data should implement the following transformations:

- filters rows to only those with `LF == 'LF'` (utilized agricultural area), so the `LF` column is dropped after filtering;
- converts the `AFO` ("J"/null) and `KOND_LE` ("J"/null) flags to booleans;
- converts `AENDERUNG` from `Geaendert` → true, `Unveraendert` → false, `Neu` → null;
- splits `FBI_VJ` on commas into an array of FLIK identifiers;
- parses `GEO_UPDAT` as a UTC date (format `%d.%m.%Y`).

The `FB_FLAECHE` and `FB_FL_VJ` columns are in hectares.

### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon / MultiPolygon | - | Field block geometry |
| BEZUGSJAHR | integer (int16) | year | Reference year for which the data is valid |
| FBI | string | 16 chars | FLIK identifier Example: `DETHLIGL46281S17` |
| FBI_KURZ | string | 10 chars | FLIK identifier without the country, state and type prefix (`DETHLI`); used as the row id. Example: `GL46281S17` |
| FB_FLAECHE | number | > 0 | Area in ha |
| FBI_VJ | array of string | each 16 chars, FLIK pattern | FLIK identifier(s) of the previous year, split on `,` |
| FB_FL_VJ | number | > 0, ≤ 100000 | Area in the previous year, in ha  |
| TK10 | string | 5 chars | Sheet of the 1:10,000 topographic map covering the centroid of the field block. Example: `51334` |
| AFO | boolean | - | Whether the field block is an agroforestry system (`J` → true, otherwise false) |
| LF | string | filter only | Field block type filter; rows are kept only when `LF == 'LF'`. The column itself is not exported. |
| BNK | string | see below | Category of main land use, short code |
| KOND_LE | boolean | - | Whether the block is a conditionality landscape element (`J` → true, otherwise false) |
| AENDERUNG | boolean / null | - | Whether the field block changed since the previous update: `Geaendert` → true, `Unveraendert` → false, `Neu` → null |
| GEO_UPDAT | string | date-time | Date of the last geometry update; parsed from `%d.%m.%Y` |

Values for `LF` (rows are filtered to `LF` only):

- `LF` Agriculturally usable area
- `LE` Landscape element
- `SF` Special use area
- `FF` Forestry area

Values for `BNK`:

- `AF` Agroforestry strips on arable land
- `AL` Arable land
- `BR` Row of trees
- `DK` Permanent crops (includes the BNK DA, OB and WB valid in TH until 2023)
- `EB` Single tree (as natural monument)
- `EF` First afforestation (DZ-eligible)
- `FG` Wetland and pond
- `FH` Field copse
- `FO` Forest field block (forest, not from first afforestation)
- `FR` Field margin
- `FS` Rock and stone bar
- `GL` Grassland
- `HK` Hedge
- `NT` Stone walls, dry stone and natural stone walls
- `NW` Nature and water conservation (DZ-eligible)
- `OL` Open land conservation (KULAP-eligible)
- `TR` Terrace
- `WA` Forest from first afforestation (not DZ-eligible)

## API

| Standard | URL | Documentation |
| -------- | --- | ------------- |
| OGC WMS  | https://www.geoproxy.geoportal-th.de/geoproxy/services | - |
