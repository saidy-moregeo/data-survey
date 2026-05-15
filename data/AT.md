# Austria

## Submission Details

- **Submitter (Affiliation):** Matthias Mohr
- **Data Provider (Legal Entity):** Agrarmarkt Austria (Government)
- **Homepage:** https://geometadatensuche.inspire.gv.at/metadatensuche/inspire/api/records/9db8a0c3-e92a-4df4-9d55-8210e326a7ed

## Overview

Austria publishes two complementary datasets via INVEKOS (the Austrian implementation of IACS): the annual crop field
declarations ("Schläge") and the reference parcels ("Referenzen", "Referenzparzellen"). Both datasets are produced by
the paying agency Agrarmarkt Austria within the framework of the Common Agricultural Policy (CAP) and are published
as INSPIRE-compliant downloads.

- Crop fields (INVEKOS Schläge), available for the years 2018–2025
- Field blocks / reference parcels (INVEKOS Referenzen), 2021

## Crop fields (Schläge)

This layer includes all field uses recorded by the applicants, which serve as the basis for the CAP funding process.
A field ("Schlag") is a contiguous piece of land that is cultivated for a growing season with a single crop (field
use type) under uniform management requirements, or is registered as a landscape element in accordance with Annex 1
of the Horizontal CAP Regulation (BGBl. II No. 100/2015), or is maintained in good agricultural and ecological
condition under Art. 94 of Regulation (EU) No. 1306/2013. Fields are digitised in the GIS as polygons or points.

### Data

- **URL:** Per-year GeoPackage downloads, e.g.
  - 2025: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2025-1_polygon.gpkg.zip
  - 2024: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2024-2_polygon.gpkg.zip
  - 2023: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2023-2_polygon.gpkg.zip
  - 2022: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2022_polygon.gpkg.zip
  - 2021: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2021_polygon.gpkg.zip
  - 2020: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2020_polygon.gpkg.zip
  - 2019: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2019_polygon.gpkg.zip
  - 2018: https://inspire.lfrz.gv.at/009501/ds/inspire_schlaege_2018_polygon.gpkg.zip
- **Documentation:** https://geometadatensuche.inspire.gv.at/metadatensuche/inspire/api/records/9db8a0c3-e92a-4df4-9d55-8210e326a7ed
- **File Format:** GeoPackage (zipped)
- **Projection:** EPSG:31287 (MGI / Austria Lambert)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)

### Properties

| Property             | Data Type | Constraints | Description                                  |
|----------------------|-----------|-------------|----------------------------------------------|
| geometry             | Polygon   |             | Field polygon                                |
| GEO_ID               | string    |             | Unique field identifier                      |
| SNAR_CODE            | string    |             | Crop code (Austrian SNAR coding)             |
| SNAR_BEZEICHNUNG     | string    |             | Crop name in German                          |
| SL_FLAECHE_BRUTTO_HA | number    | > 0         | Gross field area in hectares                 |
| GEOM_DATE_CREATED    | datetime  |             | Determination date of the geometry           |

## Field blocks (Feldstücke / Referenzen)

The layer includes all reference parcels ("Referenzparzellen") defined by the paying agency Agrarmarkt Austria and
recorded landscape elements within the meaning of Art. 5 of Regulation (EU) No. 640/2014 and the Horizontal CAP
Regulation (BGBl. II No. 100/2015).

A reference parcel is the physical block that can be clearly delimited from the outside (e.g. forest, roads, water
bodies) and is formed by contiguous agricultural areas that are recognisable in nature.

### Data

- **URL:** https://inspire.lfrz.gv.at/009501/ds/inspire_referenzen_2021_polygon.gpkg.zip (file `INSPIRE_REFERENZEN_2021_POLYGON.gpkg`)
- **Documentation:** https://geometadatensuche.inspire.gv.at/metadatensuche/inspire/api/records/9db8a0c3-e92a-4df4-9d55-8210e326a7ed
- **File Format:** GeoPackage (zipped)
- **Projection:** EPSG:31287 (MGI / Austria Lambert)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)

### Properties

| Property             | Data Type | Constraints                          | Description |
|----------------------|-----------|--------------------------------------|-------------|
| geometry             | Polygon   |                                      | Reference parcel polygon |
| RFL_ID               | string    |                                      | Reference parcel identifier |
| REF_ART              | string    | `ALM`, `HEIM`, `HW`, `LSE_FL`, `PF`  | Reference parcel type code |
| REF_ART_BEZEICHNUNG  | string    | `Alm`, `Heimgut`, `Hutweide`, `LSE Fläche`, `Pflegefläche` | Reference parcel type in German |
| BRUTTOFLAECHE_HA     | number    |                                      | Gross area in hectares |
| INSPIRE_ID           | string    |                                      | INSPIRE identifier |
| REFERENZ_KENNUNG     | uint64    |                                      | Reference parcel reference number |
| FART_ID              | uint32    |                                      | Field type identifier |
| GEO_DATERF           | datetime  |                                      | Geometry determination datetime |

Mapping of `REF_ART` and `REF_ART_BEZEICHNUNG`:

- `ALM` = `Alm`
- `HEIM` = `Heimgut`
- `HW` = `Hutweide`
- `LSE_FL` = `LSE Fläche`
- `PF` = `Pflegefläche`

### Example

```xml
<gml:Polygon gml:id="ID0001" srsName="EPSG:3035" xmlns:gml="http://www.opengis.net/gml/3.2">
	<gml:exterior>
		<gml:LinearRing>
			<gml:posList srsDimension="2">4354889.29482811 [...] 2716301.28531537 </gml:posList>
		</gml:LinearRing>
	</gml:exterior>
	<gml:interior>
		<gml:LinearRing>
			<gml:posList srsDimension="2">4355360.7216415 [...] 2716403.23876317 </gml:posList>
		</gml:LinearRing>
	</gml:interior>
</gml:Polygon>
```

## API

No publicly documented API found.
