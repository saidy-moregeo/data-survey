# Saarland, Germany

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper; Saidy Barry, moreGeo GmbH (reference parcels)
- **Data Provider (Legal Entity):** Ministerium für Umwelt, Klima, Mobilität, Agrar und Verbraucherschutz, Saarland (Government)
- **Homepage:** https://geoportal.saarland.de

## Overview

Saarland publishes two complementary IACS / InVeKoS datasets, both transformed into INSPIRE data
models and served through the GDI-SL geoportal:

- **Application parcels ("Antragsschläge"):** the parcels declared by farmers for agricultural-land
  subsidies, published as INSPIRE *Existing Land Use* features.
- **Reference parcels ("LPIS-Referenzschläge"):** the reference parcels of the Land Parcel
  Identification System, published as INSPIRE *Land Cover* features. 62,304 parcels, each carrying
  a land cover class from the national IACS code list.

## Data

### Application parcels (Antragsschläge)

- **URL:** https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege
- **Documentation:** https://geoportal.saarland.de
- **File Format:** GML 3.2 (INSPIRE *Existing Land Use*)
- **Projection:** EPSG:4258 (ETRS89)
- **License:** CC-BY-4.0
- **Attribution:** ©GDI-SL 2024

#### Properties

| Property    | Data Type | Constraints                                 | Description                                             |
|-------------|-----------|---------------------------------------------|---------------------------------------------------------|
| identifier  | string    |                                             | INSPIRE feature identifier                              |
| description | string    | `flik: DESLLI…`, `Size in ha: …`            | INSPIRE description; encodes FLIK and field size in ha  |
| flik        | string    | FLIK pattern                                | Field block identifier (parsed from `description`)      |
| area        | number    | hectares (parsed)                           | Field area in hectares (parsed from `description`)      |
| name        | string    |                                             | Feature label                                           |
| geometry    | Polygon   | EPSG:4258                                   | Field geometry                                          |

#### Example

Use the WFS endpoint above with a small bounding box, e.g.:

```
https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege
  ?SERVICE=WFS&REQUEST=GetFeature&VERSION=2.0.0
  &typeNames=elu:ExistingLandUseObject
  &outputFormat=application/gml%2Bxml;%20version=3.2
  &EPSG=4258&BBOX=49.1,6.5423790007724,49.332379000772,6.7747580015449
```

### Reference parcels (LPIS-Referenzschläge)

- **URL:** https://geoportal.saarland.de/gdi-sl/inspirewfs_Bodenbedeckung_LPIS
- **Documentation:** https://geoportal.saarland.de/spatial-objects/384
- **File Format:** GML 3.2 (INSPIRE *Land Cover* 5.0); GeoJSON via the OGC API - Features endpoint
- **Projection:** EPSG:4258 (ETRS89), declared per geometry as `urn:ogc:def:crs:EPSG::4258`
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/deed.de), stated in the
  dataset metadata record as *"Lizenz: cc-by/4.0 … Quellenvermerk: © GDI-SL (Jahr)"*
- **Attribution:** © GDI-SL 2026, CC BY 4.0

62,304 reference parcels. The FLIK identifier and the parcel size are encoded inside the INSPIRE
`description` attribute rather than in dedicated fields. The land cover class is carried as an
`xlink:href` into the national IACS code list
[`de.iacs/AgriculturalAreaTypeValue`](https://registry.gdi-de.org/codelist/de.iacs/AgriculturalAreaTypeValue),
the same code list Bavaria and Hesse publish:

- `GL` — Dauergrünland (permanent grassland), 61.4%
- `AL` — Ackerland (arable land), 36.6%
- `DK` — Dauerkultur (permanent crop), 1.7%
- `S` — Sonstiges (other), 0.3%

Shares are from 5,000 parcels sampled across five offsets. Note that the class is present **only in
the GML**; the GeoJSON representation of the OGC API endpoint omits the nested
`landCoverObservation` and therefore carries no class at all.

#### Properties

| Property                                          | Data Type | Constraints        | Description                                                                   |
| ------------------------------------------------- | --------- | ------------------ | ----------------------------------------------------------------------------- |
| `gml:description`                                 | string    | required           | Encodes the parcel size and the FLIK, e.g. `Size in ha: 0.11206, flik: DESLLI0000248744` |
| `gml:identifier`                                  | string    | required, unique   | INSPIRE identifier, e.g. `https://registry.gdi-de.org/id/de.sl.inspire.lc.ivs.lpis_sl/LandCoverUnit_…_DESLLI0100223113` |
| `lcv:inspireId` → `localId` / `namespace`         | string    | required           | The same identifier split into its two INSPIRE parts                          |
| `lcv:class`                                       | xlink     | required           | Land cover class, as an `xlink:href` into the `de.iacs` code list (values above) |
| `lcv:beginLifespanVersion`                        | date-time | always `xsi:nil`   | Date the record version was created; never populated                          |
| `lcv:mosaic` / `lcv:observationDate`              | —         | always `xsi:nil`   | INSPIRE Land Cover attributes; never populated                                |
| `lcv:geometry`                                    | Polygon   | required           | Parcel geometry                                                               |

The FLIK is 16 characters, `DESLLI` plus 10 digits, and unique. Parcel sizes range from 1.1 m² to
about 14 ha; small values are written in **scientific notation**, e.g. `Size in ha: 1.0999999999999999E-4`.

#### Example

Count the features, then request one page:

    …/inspirewfs_Bodenbedeckung_LPIS?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetFeature&typeNames=lcv:LandCoverUnit&resultType=hits
    …/inspirewfs_Bodenbedeckung_LPIS?SERVICE=WFS&VERSION=2.0.0&REQUEST=GetFeature&typeNames=lcv:LandCoverUnit&count=2500&startIndex=0

One feature, with the coordinate list truncated:

```xml
<lcv:LandCoverUnit gml:id="LandCoverUnit_54030be6…_DESLLI0100223113">
  <gml:description>Size in ha: 1.0999999999999999E-4, flik: DESLLI0100223113</gml:description>
  <gml:identifier codeSpace="http://inspire.ec.europa.eu/ids">https://registry.gdi-de.org/id/de.sl.inspire.lc.ivs.lpis_sl/LandCoverUnit_54030be6…_DESLLI0100223113</gml:identifier>
  <lcv:geometry>
    <gml:Polygon srsName="urn:ogc:def:crs:EPSG::4258"><gml:exterior><gml:LinearRing>
      <gml:posList>49.186863 7.302103 …</gml:posList>
    </gml:LinearRing></gml:exterior></gml:Polygon>
  </lcv:geometry>
  <lcv:landCoverObservation>
    <lcv:LandCoverObservation>
      <lcv:class xlink:href="https://registry.gdi-de.org/codelist/de.iacs/AgriculturalAreaTypeValue/GL"/>
      <lcv:mosaic xsi:nil="true"/>
      <lcv:observationDate xsi:nil="true"/>
    </lcv:LandCoverObservation>
  </lcv:landCoverObservation>
</lcv:LandCoverUnit>
```

## API

| Standard           | URL                                                                                      | Documentation                                        |
| ------------------ | ---------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| OGC WFS 2.0.0      | https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege | https://geoportal.saarland.de                        |
| OGC WFS 2.0.0      | https://geoportal.saarland.de/gdi-sl/inspirewfs_Bodenbedeckung_LPIS                      | https://geoportal.saarland.de/spatial-objects/384    |
| OGC API - Features | https://geoportal.saarland.de/spatial-objects/384/collections                            | https://geoportal.saarland.de/spatial-objects/384    |

The reference-parcel WFS supports `startIndex` / `count` paging and reports `numberMatched`
correctly, but always reports `numberReturned="0"`, so the page count has to be derived from a
`resultType=hits` request. The OGC API - Features endpoint accepts `limit` only from the fixed set
`1, 5, 10, 20, 50, 100, 200, 500, 1000, 2500`; any other value returns HTTP 200 with a plain-text
error rather than JSON. Both APIs return the parcels ordered by area, ascending.
