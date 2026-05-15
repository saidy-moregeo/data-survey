# Luxembourg

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Administration des services techniques de l'agriculture (ASTA) (Government)
- **Homepage:** https://asta.etat.lu/en

## Overview

The Land Parcel Identification System (LPIS) is a reference database of agricultural parcels used as the basis for
area-related payments to farmers under the EU Common Agricultural Policy (CAP). These payments are (co-)financed by
the European Agricultural Guarantee Fund (EAGF) and the European Agricultural Fund for Rural Development (EAFRD).

To ensure that payments are regular, the CAP relies on the Integrated Administration and Control System (IACS), a
set of comprehensive administrative and on-the-spot checks on subsidy applications managed by the Member States.
The LPIS is a key component of IACS: an IT system based on ortho imagery (aerial or satellite photographs) which
records all agricultural parcels. Luxembourg publishes its LPIS as the "FLIK" reference dataset.

See https://data.public.lu/en/datasets/inspire-annex-ii-theme-land-cover-landcoverunit-land-parcel-identification-system-lpis-2024-reference-data-of-agricultural-parcels/

## Data

- **URL:** https://data.public.lu/fr/datasets/r/b4ae6690-7e4c-4454-8b60-9fa33ba6a61b (saved locally as `lu.zip`)
- **Documentation:** https://geocatalogue.geoportail.lu/geonetwork/srv/api/records/f511a4ee-928a-4900-ac05-52aa0ce03bba?language=eng
- **File Format:** Shapefile (zipped). A GML variant is also available at https://data.public.lu/fr/datasets/r/622bd574-9430-4c48-80a6-110844693560
- **Projection:** EPSG:2169 (Luxembourg 1930 / Gauss)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** "Luxembourg ministry of Agriculture"

### Properties

| Property   | **Data Type** | Constraints | Description            |
|------------|---------------|-------------|------------------------|
| FLIK       | integer       |             | Identifier             |
| CODE_ELEM  | string        | D, N, P, V  |                        |
| CODE_COM   | string        | 000-999     | Region? (Municipality) |
| CODE_SECT  | string        | A-H         |                        |
| SURF_ELEM  | float         |             | Area in m^2            |
| PERIM_REEL | float         |             | Perimeter in m         |
| EXCEPTION  | float         |             |                        |
| SURFACE    | float         |             | Area in m^2            |
| PERIMETRE  | float         |             | Perimeter in m         |

### Example

See [example map](https://map.geoportail.lu/theme/agriculture?layers=1637&zoom=10&lang=en&version=3&X=667917&Y=6394482&rotation=0&opacities=1&time=&bgLayer=orthogr_2013_global)

### API

| Standard | URL                                                                                                  |
|----------|------------------------------------------------------------------------------------------------------|
| OGC WMS  | https://wms.inspire.geoportail.lu/geoserver/af/wms?service=WMS&version=1.3.0&request=GetCapabilities |
