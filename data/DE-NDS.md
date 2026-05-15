# Lower Saxony, Germany

## Submission Details

- **Submitter (Affiliation):** Matthias Mohr
- **Data Provider (Legal Entity):** ML/SLA Niedersachsen (Government)
- **Homepage:** https://sla.niedersachsen.de/landentwicklung/LEA/

## Overview

Lower Saxony (also covering Bremen and Hamburg) publishes two complementary open agricultural datasets used in the Integrated Administration and Control System (IACS) of the EU Common Agricultural Policy:

- **Crop fields ("Schlaege"):** a contiguous agricultural area surrounded by permanent boundaries that is cultivated with a single crop. Data is published per application year (currently 2021 through 2025).
- **Field blocks ("Feldblock"):** a contiguous agricultural area surrounded by permanent boundaries that may be used by one or more farmers with one or more crops, may be fully or partially set aside, or may be fully or partially taken out of production.

## Data

### Crop fields (Schlaege)

- **URL (per year):** `https://sla.niedersachsen.de/mapbender_sla/download/schlaege_aktuell_{year}.zip` (`UD_{yy}_S.shp` inside; years 2021–2025). Example: https://sla.niedersachsen.de/mapbender_sla/download/schlaege_aktuell_2025.zip
- **Documentation:** https://sla.niedersachsen.de/agrarfoerderung/schlaginfo/
- **File Format:** Shapefile (ZIP)
- **Projection:** as published (EPSG:25832, UTM 32N)
- **License:** [Data licence Germany – attribution – Version 2.0](https://www.govdata.de/dl-de/by-2-0)
- **Attribution:** © ML/SLA Niedersachsen (2024), DL-DE-BY-2.0 (www.govdata.de/DL-DE-BY-2.0), Daten bearbeitet

The Lower Saxony "Nutzungscode" crop code list is published at https://www.sla.niedersachsen.de/download/141235/Verzeichnis_Nutzungscodes.xlsx . Across years some column names differ: `NC_FESTG` may appear as `KULTURARTF`, `KULTURCODE` or `KC_FESTG`; `AKTUELLEFL` may appear as `AKT_FL`. The area is in hectares.

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon / MultiPolygon | - | Crop field geometry |
| FLIK | string | 16 chars | Area identifier for the field block this field belongs to |
| SCHLAGNR | integer | - | Numeric sub-field / parcel number within the application |
| NC_FESTG (or KULTURARTF / KULTURCODE / KC_FESTG) | string | - | Crop / land-use code from the Lower Saxony "Nutzungscode" list |
| ANTRAGSJAH | integer | year | Application year |
| AKTUELLEFL (or AKT_FL) | number | > 0 | Actual area in hectares |

### Field blocks (Feldblock)

- **URL:** https://sla.niedersachsen.de/mapbender_sla/download/FB_NDS.zip
- **Documentation:** https://sla.niedersachsen.de/landentwicklung/LEA/
- **File Format:** Shapefile (ZIP)
- **Projection:** as published (EPSG:25832, UTM 32N)
- **License:** [Data licence Germany – attribution – Version 2.0](https://www.govdata.de/dl-de/by-2-0)
- **Attribution:** © ML/SLA Niedersachsen (2024), DL-DE-BY-2.0 (www.govdata.de/DL-DE-BY-2.0), Daten bearbeitet

The `FLAECHE` area is in hectares.

#### Properties

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon / MultiPolygon | - | Field block geometry |
| FLIK | string | 16 chars | Field block identifier (FLIK). Example: `DENIHB0412500015` |
| STAND | string | ISO date-time | Date of the last update of the record |
| ANT_JAHR | integer | year | Application / reference year |
| BNK | string | see below | Category of main land use, short code |
| BNK_TXT | string | see below | Textual representation of BNK in German |
| FLAECHE | number | > 0 | Area in ha |
| SHAPE_Leng | number | > 0 | Length of the boundary in meters |

Mapping between `BNK` and `BNK_TXT`:

- `AFF*` Aufforstungsfläche
- `AL` Ackerland
- `AL*` Ackerland
- `DK` Dauerkulturen
- `DK*` Dauerkulturen
- `GL` Grünland
- `GL*` Grünland
- `MB` Mischblock
- `SO` Sonstiges
- `SO*` SO nicht beihilfefähig

## API

| Standard | URL | Documentation |
| -------- | --- | ------------- |
| OGC WFS | https://sla.niedersachsen.de/agrarfoerderung/agrar_ref/wfs?service=WFS&version=2.0.0&request=GetFeature&typeName=agrar_ref:feldbloecke&count=50&outputFormat=application%2Fgml%2Bxml%3B%20version%3D3.2& | - |
