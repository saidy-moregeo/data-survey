# Croatia

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Agencija za plaćanja u poljoprivredi, ribarstvu i ruralnom razvoju (Government)
- **Homepage:** https://www.apprrr.hr/prostorni-podaci-servisi/

## Overview

Croatian Field Boundaries: field boundary data for Croatia, provided as part of national agricultural datasets.

This dataset contains spatial data related to agricultural land use in Croatia, including ARKOD parcel information, environmentally sensitive areas, High Nature Value Grasslands, protective buffer strips around watercourses, and vineyard classifications. The data is crucial for managing agricultural activities, ensuring compliance with environmental regulations, and supporting sustainable land use practices.

ARKOD parcels are maintained by the Paying Agency in support of the Common Agricultural Policy (CAP) and the Integrated Administration and Control System (IACS), and represent the spatial reference for farmers' single-application aid claims.

## Data

- **URL:** https://www.apprrr.hr/wp-content/uploads/nipp/land_parcels.gpkg
- **Documentation:** https://www.apprrr.hr/prostorni-podaci-servisi/
- **File Format:** GeoPackage
- **Projection:** as published
- **License:** [Prostorni podaci i servisi](https://www.apprrr.hr/prostorni-podaci-servisi/)
- **Attribution:** copyright © 2024. Agencija za plaćanja u poljoprivredi, ribarstvu i ruralnom razvoju
- **Crop code list:** Mapped to EuroCrops HCAT via `hr_2020.csv`

### Properties

| Property                 | Data Type | Constraints | Description |
|--------------------------|-----------|-------------|-------------|
| geometry                 | geometry  | Polygon / MultiPolygon | Field boundary geometry |
| id                       | integer   |             | Feature identifier (taken from the file index) |
| land_use_id              | integer   |             | Land use / crop code |
| area                     | number    | square meters | Surface area in m² (converted to hectares) |
| home_name                | string    |             | Locality / home name |
| perim                    | number    |             | Parcel perimeter |
| slope                    | number    |             | Average slope |
| z_avg                    | number    |             | Average elevation (mapped to `height`) |
| eligibility_coef         | number    |             | Eligibility coefficient |
| mines_status             | string    | `N`, `M`, `R` | Mine contamination status |
| mines_year_removed       | integer   |             | Year mines were removed |
| water_protect_zone       | string    | required    | Water protection zone code |
| natura2000               | number    |             | Natura 2000 overlap area |
| natura2000_ok            | string    |             | Natura 2000 status |
| natura2000_pop           | number    |             | Natura 2000 POP overlap |
| natura2000_povs          | number    |             | Natura 2000 POVS overlap |
| anc                      | integer   |             | Area with Natural Constraints flag |
| anc_area                 | number    |             | ANC area |
| rp                       | integer   |             | RP flag |
| sanitary_protection_zone | string    | required    | Sanitary protection zone code |
| tvpv                     | integer   |             | TVPV flag |
| ot_nat                   | integer   |             | Other nature flag |
| ot_nat_area              | number    |             | Other nature area |
| irrigation               | integer   | required    | Irrigation flag |
| irrigation_source        | integer   |             | Irrigation source code |
| irrigation_type          | integer   |             | Irrigation type code |
| jpaid                    | string    | required    | Unique single application identifier |

## API

| Standard | URL                                                                     | Documentation |
|----------|-------------------------------------------------------------------------|---------------|
| OGC WFS  | https://servisi.apprrr.hr/NIPP/wfs?request=getCapabilities              | -             |
| OGC WMS  | https://servisi.apprrr.hr/NIPP/wms?service=WMS&request=GetCapabilities  | -             |
