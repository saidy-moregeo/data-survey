# Saxony-Anhalt (ST), Germany

## Submission Details

- **Submitter (Affiliation):** Saidy Barry, moreGeo GmbH
- **Data Provider (Legal Entity):** Ministerium für Wirtschaft, Tourismus, Landwirtschaft und Forsten (MWL) Sachsen-Anhalt (Government)
- **Homepage:** https://mwl.sachsen-anhalt.de

## Overview

Saxony-Anhalt publishes its InVeKoS reference data as an INSPIRE *Land Cover* dataset, derived from
the LPIS reference parcels and the landscape elements. Two feature layers are served from one
ArcGIS MapServer: the field blocks ("Feldblöcke"), which are the reference parcels of the Land
Parcel Identification System, and the landscape elements ("Landschaftselemente"). Each field block
carries a land cover class from the national IACS code list and a FLIK.

Both layers stack **three annual snapshots in a single table**, distinguished only by an
`ID_VERSIONID` attribute. 78,714 field blocks for the most recent snapshot, covering 1,201,875 ha at
a median of 4.49 ha and a mean of 15.27 ha.

## Data

- **URL:** https://geodatenportal.sachsen-anhalt.de/arcgisinspire/rest/services/INSPIRE_MWL/DLM50_MWL_LC_INVEKOS/MapServer
- **Documentation:** https://metaver.de/csw?REQUEST=GetRecordById&SERVICE=CSW&VERSION=2.0.2&id=8EE3BF04-F131-4C48-8940-338B9C81D8C1
- **File Format:** GeoJSON and Esri JSON via ArcGIS REST; a single GML file via the INSPIRE Atom feed
- **Projection:** EPSG:4258 (ETRS89) natively; `f=geojson` without `outSR` reprojects to EPSG:4326, and `outSR` is honoured otherwise
- **License:** [Datenlizenz Deutschland Namensnennung 2.0](https://www.govdata.de/dl-de/by-2-0), stated in the dataset metadata as `{"id":"dl-by-de/2.0", … "quelle":"Ministerium für Wirtschaft, Tourismus, Landwirtschaft und Forsten des Landes Sachsen-Anhalt"}`. The service declares "Es gelten keine Zugriffsbeschränkungen" and "Es gelten keine Bedingungen"
- **Attribution:** © Ministerium für Wirtschaft, Tourismus, Landwirtschaft und Forsten des Landes Sachsen-Anhalt, dl-de/by-2-0

The MapServer publishes two layers, each holding the 2021, 2022 and 2023 snapshots:

| Layer | Name                                     | Total   | 2021.1 | 2022.1 | 2023.1 |
| ----- | ---------------------------------------- | ------: | -----: | -----: | -----: |
| 0     | `LC.LandCoverSurfaces.Feldbloecke`       | 236,125 | 78,722 | 78,689 | 78,714 |
| 1     | `LC.LandCoverSurfaces.Landschaftselemente` | 89,276 | 29,992 | 29,682 | 29,602 |

**Without a filter on `ID_VERSIONID` every parcel is returned three times.** `ID_LOCALID` is
byte-identical across the snapshots — `LCU_FB_DESTLI0509850059_955064` appears in all three — so the
snapshot attribute is the only thing separating them. The dataset metadata gives a revision date of
2023-06-11 and the Atom feed was last updated 2024-07-31, so 2023.1 is the current snapshot.

### Properties

Properties of layer 0, `LC.LandCoverSurfaces.Feldbloecke`. Layer 1 has an identical schema.

| Property                     | Data Type | Constraints            | Description                                                                        |
| ---------------------------- | --------- | ---------------------- | ---------------------------------------------------------------------------------- |
| `OBJECTID`                   | integer   | required, unique       | Esri object id, contiguous and ascending within a snapshot                          |
| `ID_LOCALID`                 | string    | required, unique       | INSPIRE local identifier, e.g. `LCU_FB_DESTLI0509850059_955064`. Contains the FLIK  |
| `ID_NAMESPACE`               | string    | constant               | `https://registry.gdi-de.org/id/de.st.mwl.lc.invekos`                               |
| `ID_VERSIONID`               | string    | required               | Snapshot, one of `2021.1`, `2022.1`, `2023.1`                                       |
| `CLASS_CODE`                 | string    | required               | Land cover class, as a bare code from the `de.iacs` code list (values below)         |
| `CLASS_LABEL`                | string    | **null in every row**  | Intended for the class label; never populated                                       |
| `CLASS_URI`                  | string    | **truncated**          | Always the literal `https://registry.gdi-de.org/codelist/de`, which resolves to the register index rather than to a code |
| `BEGINLIFESPANVERSION`       | date      | required               | Date this version of the field block was created; delivered as epoch milliseconds, always 1 January, 15 distinct years between 2005 and 2023 |
| `OBSERVATIONDATE`, `ENDLIFESPANVERSION`, `MOSAIC_VOID` | — | always null | INSPIRE Land Cover attributes, all carrying void reason 2 ("Unpopulated")   |
| `UNITID`                     | integer   | 0–999                  | Position within the response page, not an identifier                                |
| `DATASETID`                  | integer   | required               | Snapshot discriminator, equivalent to `ID_VERSIONID`                                |
| `SHAPE.AREA` / `SHAPE.LEN`   | number    | **square degrees**     | Geometric area and perimeter in the native angular units, so not usable as an area  |
| `geometry`                   | Polygon   | required               | Field block geometry; none empty. A handful are multipolygons, and a few dozen carry a ring self-intersection, all repairable |

The FLIK is the second underscore-separated segment of `ID_LOCALID`, 16 characters of `DESTLI` plus
10 digits. It is **unique** across the 2023.1 snapshot, verified over all 78,714 rows.

There is no area attribute. Computed from the geometry, the 2023.1 field blocks run from 28 m² to
776.6 ha, with a median of 4.49 ha and a mean of 15.27 ha, for 1,201,875 ha in total.

Values for `CLASS_CODE` on layer 0, from the national code list
[`de.iacs/AgriculturalAreaTypeValue`](https://registry.gdi-de.org/codelist/de.iacs/AgriculturalAreaTypeValue),
with counts for the 2023.1 snapshot:

- `AL` — Ackerland (arable land), 44,773 (56.9%)
- `GL` — Dauergrünland (permanent grassland), 32,467 (41.2%)
- `DK` — Dauerkultur (permanent crop), 1,009 (1.3%)
- `S` — Sonstiges (other), 465 (0.6%)

Layer 1 uses a different vocabulary,
[`de.iacs/LandscapeFeatureValueType`](https://registry.gdi-de.org/codelist/de.iacs/LandscapeFeatureValueType).

### Example

Count the features in one snapshot, then request one page:

    …/MapServer/0/query?where=ID_VERSIONID%3D%272023.1%27&returnCountOnly=true&f=json
    …/MapServer/0/query?where=OBJECTID%3E-1+AND+(ID_VERSIONID%3D%272023.1%27)&outFields=*&returnGeometry=true&resultRecordCount=1000&f=geojson

One feature, with the coordinate list and the unpopulated properties truncated:

```json
{
  "type": "Feature",
  "id": 246689,
  "geometry": { "type": "Polygon", "coordinates": [[[11.321874573, 52.846969779], …]] },
  "properties": {
    "OBJECTID": 246689,
    "ID_LOCALID": "LCU_FB_DESTLI0511660122_955113",
    "ID_NAMESPACE": "https://registry.gdi-de.org/id/de.st.mwl.lc.invekos",
    "ID_VERSIONID": "2023.1",
    "CLASS_CODE": "AL",
    "CLASS_LABEL": null,
    "CLASS_URI": "https://registry.gdi-de.org/codelist/de",
    "BEGINLIFESPANVERSION": 1388534400000,
    "SHAPE.AREA": 5.0735908527155e-06
  }
}
```

## API

| Standard      | URL                                                                                                                                 |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| ArcGIS REST   | https://geodatenportal.sachsen-anhalt.de/arcgisinspire/rest/services/INSPIRE_MWL/DLM50_MWL_LC_INVEKOS/MapServer                      |
| OGC WMS 1.3.0 | https://geodatenportal.sachsen-anhalt.de/ows_INSPIRE_MWL_LC?REQUEST=GetCapabilities&SERVICE=WMS                                      |
| INSPIRE Atom  | https://geodatenportal.sachsen-anhalt.de/arcgisinspire/rest/directories/web/INSPIRE_MWL/DLM50_MWL_LC_INVEKOS_MapServer/servicelc.xml |

The REST service is ArcGIS 11.5 and supports pagination, `orderBy`, `distinct` and statistics, but
`maxRecordCount` is 1000 and is a **hard cap**: requesting `resultRecordCount=2000` or `5000` still
returns 1000 features. Retrieving one snapshot of layer 0 therefore takes 79 pages. There is no WFS —
the `WFSServer` endpoint returns an ArcGIS Server error.

The Atom feed offers the whole dataset as one predefined download,
`…/DLM50_MWL_LC_INVEKOS.zip`, which is 98.7 MB compressed and contains a single GML file of roughly
1 GB covering both layers and all three snapshots.
