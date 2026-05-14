# Saxony, Germany

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Sächsisches Landesamt für Umwelt, Landwirtschaft und Geologie (Government)
- **Homepage:** https://geoportal.sachsen.de

## Overview

"Feldblöcke und förderfähige Elemente" is the Land Parcel Identification System
(LPIS / FLIK) dataset for the German state of Saxony. It defines reference parcels
used to validate CAP / IACS subsidy applications and includes a rich set of
indicators (Natura 2000 overlap, GLOEZ-2 grassland, erosion classes, agroforestry,
agri-PV, mountain area, etc.).

## Data

- **URL:** https://www.smul.sachsen.de/gis-online/download/FBZ_ISS_Bereiche/gesamt_2024_RE.zip
- **Documentation:** https://geoportal.sachsen.de
- **File Format:** ESRI Shapefile (zipped, annual snapshot)
- **Projection:** ETRS89 / UTM zone 33N (native to the file)
- **License:** DL-DE-BY-2.0
- **Attribution:** Sächsisches Landesamt für Umwelt, Landwirtschaft und Geologie

### Properties

| Property   | Data Type | Constraints                | Description                                                 |
|------------|-----------|----------------------------|-------------------------------------------------------------|
| FB_FLIK    | string    | FLIK pattern               | Field block identifier (FLIK)                               |
| JAHR       | integer   | year                       | Reference year of the snapshot                              |
| FB_A_FLAE  | number    | hectares                   | Field block area                                            |
| FB_BN_KAT  | string    |                            | Land-use category (Bodennutzungskategorie)                  |
| FB_BEZEICH | string    |                            | Descriptive label                                           |
| ZUSTAENDIG | uint8     |                            | Responsible authority code                                  |
| FB_FFH     | boolean   | J/N                        | Inside an FFH (Natura 2000) area                            |
| FB_SPA     | boolean   | J/N                        | Inside a Special Protection Area (SPA)                      |
| FB_NB      | string    |                            | Nature-protection remarks                                   |
| NITRAT     | boolean   | J/N                        | Nitrate-vulnerable zone                                     |
| WT_WRRL    | boolean   | J/N                        | Water Framework Directive water body                        |
| NITRAT_TG  | boolean   | J/N                        | Nitrate-sensitive partial area                              |
| KWIND      | uint8     |                            | Wind-erosion class                                          |
| KWASSER    | uint8     |                            | Water-erosion class                                         |
| AGROFORST  | boolean   | J/N                        | Agroforestry registered                                     |
| AGRIPV     | boolean   | J/N                        | Agri-photovoltaic installation                              |
| GLOEZ2     | boolean   | J/N                        | GLOEZ-2 (permanent grassland) restriction                   |
| OER_UNZUL  | string    |                            | "Öko-Regelung unzulässig" remark                            |
| REG_SAAT   | string    |                            | Regional seed code                                          |
| BERG       | uint8     |                            | Mountain-area classification                                |
| geometry   | Polygon   |                            | Field block geometry                                        |

### Example

Download the latest annual ZIP from the URL above; the example test fixture is
`2024_RE_FB_33.shp`.

## API

No public OGC API; the dataset is distributed as an annual ZIP download.
