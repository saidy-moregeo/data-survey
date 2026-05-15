# France: Registre Parcellaire Graphique (RPG)

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Institut National de l'Information Géographique et Forestière (IGN) (Government)
- **Homepage:** https://www.data.gouv.fr/en/datasets/registre-parcellaire-graphique-rpg-contours-des-parcelles-et-ilots-culturaux-et-leur-groupe-de-cultures-majoritaire/

## Overview

France has published Crop Field data ("Registre Parcellaire Graphique" — RPG) for many years. The RPG records crop
fields declared by farmers within the EU Common Agricultural Policy (CAP) subsidy scheme as part of the Integrated
Administration and Control System (IACS).

The anonymised version, distributed as a public reference dataset, contains graphic data for plots (the basic land
unit of farmers' declarations) together with the main crop on each plot. The data has been produced by the Services
and Payment Agency (ASP) since 2007 and is published annually.

## Data

- **URL:** Per-year GeoPackage (7-Zip) downloads from data.geopf.fr:
  - 2023: https://data.geopf.fr/telechargement/download/RPG/RPG_2-2__GPKG_LAMB93_FXX_2023-01-01/RPG_2-2__GPKG_LAMB93_FXX_2023-01-01.7z (file `RPG_2-2__GPKG_LAMB93_FXX_2023-01-01.gpkg`)
  - 2022: https://data.geopf.fr/telechargement/download/RPG/RPG_2-0__GPKG_LAMB93_FXX_2022-01-01/RPG_2-0__GPKG_LAMB93_FXX_2022-01-01.7z.001 (file `PARCELLES_GRAPHIQUES.gpkg`)
  - 2021: https://data.geopf.fr/telechargement/download/RPG/RPG_2-0__GPKG_LAMB93_FXX_2021-01-01/RPG_2-0__GPKG_LAMB93_FXX_2021-01-01.7z (file `PARCELLES_GRAPHIQUES.gpkg`)
  - 2020: split download (`.7z.001` + `.7z.002`) at https://data.geopf.fr/telechargement/download/RPG/RPG_2-0__GPKG_LAMB93_FR_2020-01-01/
  - 2019: https://data.geopf.fr/telechargement/download/RPG/RPG_2-0_GPKG_LAMB93_FR-2019/RPG_2-0_GPKG_LAMB93_FR-2019.7z
  - 2018 (Shapefile): https://data.geopf.fr/telechargement/download/RPG/RPG_2-0__SHP_LAMB93_FR-2017_2017-01-01/RPG_2-0__SHP_LAMB93_FR-2017_2017-01-01.7z
- **Documentation:** https://geoservices.ign.fr/documentation/donnees/vecteur/rpg
- **File Format:** GeoPackage (for most years), Shapefile (for some older years) — all packaged as 7-Zip
- **Projection:** EPSG:2154 (RGF93 / Lambert-93) for metropolitan France. Overseas territories (outre-mer) are published in suitable UTM projections.
- **License:** [Licence Ouverte / Open Licence](https://etalab.gouv.fr/licence-ouverte-open-licence)
- **Attribution:** "IGN — Original data from https://geoservices.ign.fr/rpg"

### Properties

| Property   | Data Type | Constraints | Description               |
|------------|-----------|-------------|---------------------------|
| ID_PARCEL  | String    | 10 chars    | Identifier                |
| SURF_PARC  | Float     |             | Surface area              |
| CODE_CULTU | String    | 3 chars     | Main crop code            |
| CODE_GROUP | String    | 2 chars     | Group code of main crop   |
| CULTURE_D1 | String    | 3 chars     | Code of catch crop        |
| CULTURE_D1 | String    | 2 chars     | Code of second catch crop |

The textual descriptions of crop codes is referenced in the
[documentation](https://geoservices.ign.fr/documentation/donnees/vecteur/rpg). It's a CSV file called 
[Table référentielle des cultures et des groupes de cultures](https://geoservices.ign.fr/sites/default/files/2023-02/REF_CULTURES_GROUPES_CULTURES_2021.csv)

### Example

See an [example map at Géoportail](https://www.geoportail.gouv.fr/carte?c=4.067065654175731,49.19467447662851&z=15&l0=GEOGRAPHICALGRIDSYSTEMS.MAPS::GEOPORTAIL:OGC:WMTS(0.46)&l1=LANDUSE.AGRICULTURE2022::GEOPORTAIL:OGC:WMTS(1)&permalink=yes)

## API

| Standard | URL                                                                                               |
|----------|---------------------------------------------------------------------------------------------------|
| OGC WMTS | https://wxs.ign.fr/agriculture/geoportail/wmts?SERVICE=WMTS&VERSION=1.0.0&REQUEST=GetCapabilities |
| OGC WMS  | https://wxs.ign.fr/agriculture/geoportail/r/wms?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities |
| OGC WFS  | https://wxs.ign.fr/agriculture/geoportail/wfs?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetCapabilities   |
