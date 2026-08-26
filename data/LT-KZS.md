# Lithuania — KŽS control land parcels (LPIS reference parcels)

## Submission Details

- **Submitter (Affiliation):** Saidy Barry, moreGeo GmbH.
- **Data Provider (Legal Entity):** VĮ Žemės ūkio duomenų centras (ŽŪDC, "Agricultural Data Centre", state enterprise), info@zudc.lt
- **Homepage:** https://www.zudc.lt (with https://www.nma.lt as the secondary)

## Overview

KŽS is Lithuania's LPIS reference-parcel database maintained for CAP/IACS; ~2.15M polygons of which 269,355 are eligible agricultural blocks (GKODAS bl1/bl1b); continuously updated snapshot (metadata record says maintenance "As needed", and DATA_NUO/DATA_IKI are null on every feature — no history is exposed)

## Data

- **URL:** https://www.geoportal.lt/arcgis/rest/services/nma/KZS5LT_kontroliniai_sklypai/MapServer (layer 0)
- **Documentation:** https://data.gov.lt/datasets/2971/?resource_version=2797
- **File Format:** Esri JSON only ("JSON, AMF"; f=geojson returns empty)
- **Geometry Format (if different from data):** Esri JSON polygon rings
- **Projection:** EPSG:3346 (LKS-94 / Lithuania TM) server reprojects on request
- **License:** No reuse licence published — copyright reserved. The geoportal.lt metadata record
  gives access and use constraints as "copyright" with no use limitation
  ([record](https://www.geoportal.lt/metadata-catalog/catalog/search/resource/details.page?uuid=%7B5266D059-0781-4650-9BF6-B2618CF2915E%7D)),
  and [data.gov.lt 2971](https://data.gov.lt/datasets/2971/) declares access rights PUBLIC without
  a `dct:license`. The service description prohibits use in other applications without consent
  (info@gis-centras.lt).
- **Data Creation Details:** Official LPIS maintenance at 1:5000 by ŽŪDC; farmers report boundary changes year-round via PPIS
- **Computer Vision / AI Details:** No
- **Attribution:** VĮ Žemės ūkio duomenų centras

### Properties

| Property        |         Data Type         | Constraints | Description |
| --------------- | ------------------------- | ----------- | ----------- |
| OBJECTID        | esriFieldTypeOID          |             |             |
| Shape           | esriFieldTypeGeometry     | Polygon     |             |
| GKODAS          | esriFieldTypeString       |             |             |
| BLOKAS_ID       | esriFieldTypeString       |             |             |
| PLOTAS_HA       | esriFieldTypeDouble       |             |             |
| PLOTAS_TINKAMAS | esriFieldTypeDouble       |             |             |
| PLOTAS_az0      | esriFieldTypeDouble       |             |             |
| PLOTAS_ds0      | esriFieldTypeDouble       |             |             |
| PLOTAS_dg0      | esriFieldTypeDouble       |             |             |
| DATA_NUO        | esriFieldTypeDate         |             |             |
| DATA_IKI        | esriFieldTypeDate         |             |             |
| Shape_Length    | esriFieldTypeDouble       | m           |             |
| Shape_Area      | esriFieldTypeDouble       | m²          |             |


## API (optional)


|  Standard   |                                         URL                                             | Documentation |
| ----------  | --------------------------------------------------------------------------------------- | ------------- |
| ESRI REST   | https://www.geoportal.lt/arcgis/rest/services/nma/KZS5LT_kontroliniai_sklypai/MapServer |               |