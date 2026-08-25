# Bavaria (BY), Germany

## Submission Details

- **Submitter (Affiliation):** Saidy Barry, moreGeo GmbH
- **Data Provider (Legal Entity):** Bayerisches Staatsministerium für Ernährung, Landwirtschaft, Forsten und Tourismus (StMELF) (Government); service operated by the Landesanstalt für Landwirtschaft (LfL)
- **Homepage:** https://www.stmelf.bayern.de

## Overview

Bavaria's Land Parcel Identification System (LPIS) is the spatial reference for area-based
agricultural payments under IACS / InVeKoS. Its unit is the field block ("Feldstück"): a contiguous
agricultural area belonging to a single farm operator, delineated by the area eligible for support.
Areas separated by roads, tracks or watercourses are not combined, and differing tenure, use or
fertiliser planning do not split one. The data is published in the "IACS in INSPIRE" (TG2) data
model and republished twice a year for the application procedure. It holds 1,692,439 field blocks
at a mean of 1.55 ha.

## Data

- **URL:** https://gdiserv.bayern.de/srv66381/services/invekos_lpis-wfs
- **Documentation:** https://geoportal.bayern.de/gdiadmin/ausgabe/ISO19139/5685adb3-8cc5-4da6-98cc-527bbe33b994 (ISO 19139)
- **File Format:** GML 3.2 via WFS 2.0, using the complex-feature schema [LPIS.xsd](https://geoportal.bayern.de/gdiadmin/schema/complex/LPIS.xsd). No GeoJSON is offered.
- **Projection:** EPSG:25832 (ETRS89 / UTM 32N); 25833, 31467, 31468, 3857 and 4258 also advertised
- **License:** [Creative Commons Namensnennung 4.0 (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/deed.de)
- **Attribution:** © Bayerisches Staatsministerium für Ernährung, Landwirtschaft, Forsten und Tourismus, CC BY 4.0

The service exposes five feature types, two of which are empty:

| Feature type                       |     Count | Content                                                             |
| ---------------------------------- | --------: | ------------------------------------------------------------------- |
| `lpis:AgriculturalArea`            | 1,692,439 | Field blocks with a land cover class                                |
| `lpis:ReferenceParcel`             | 1,692,498 | Same FLIK and near-identical geometry, but no land cover            |
| `lpis:LandscapeFeature`            |   313,284 | Eligible landscape elements (hedges, tree rows)                     |
| `lpis:EcologicalFocusArea`         |         0 | Empty                                                               |
| `lpis:NonAgriculturalEligibleArea` |         0 | Empty                                                               |

No feature type carries an area attribute; area must be computed from the geometry.

### Properties

Properties of `lpis:AgriculturalArea`, with the GML element type.

| Property                                               | Data Type          | Constraints      | Description                                                    |
| ------------------------------------------------------ | ------------------ | ---------------- | -------------------------------------------------------------- |
| `gml:id`                                               | string             | required         | Surrogate id, assigned per response and not stable             |
| `gml:identifier`                                       | string (URI)       | required         | Persistent identifier; same value as `lpis:id`                 |
| `lpis:id`                                              | string (URI)       | required, unique | The FLIK is the final segment: `…lpis.aa.DEBYLI9412000570`     |
| `lpis:agriculturalAreaType`                            | codelist reference | required         | Land cover class (values below)                                |
| `lpis:landscapeFeaturesAssociatedWithAgriculturalArea` | xlink              | 0..n             | URI reference to associated `LandscapeFeature` objects          |
| `lpis:validFrom`                                       | date               | required         | Start of validity; observed 2008-01-01 to 2026-01-01           |
| `lpis:beginLifespanVersion`                            | dateTime           | required         | Timestamp of this record version                               |
| `lpis:geometry`                                        | `gml:Polygon`      | required         | Inlined polygon in EPSG:25832, full coordinate precision       |

The FLIK derived from `lpis:id` is 16 characters, `DEBYLI` plus 10 digits, and unique.

`lpis:agriculturalAreaType` is carried as `xlink:title` and `xlink:href` **attributes** rather than
element text, so GML readers drop it unless asked for it explicitly. Values, with their code from
the `de.iacs/AgriculturalAreaTypeValue` codelist:

- `Arable land` (`AL`)
- `Permanent grassland` (`GL`)
- `Permanent crop` (`DK`)
- `Other` (`S`)

### Example

Count the features, then request one page:

    …/invekos_lpis-wfs?service=WFS&version=2.0.0&request=GetFeature&typeNames=lpis:AgriculturalArea&resultType=hits
    …/invekos_lpis-wfs?service=WFS&version=2.0.0&request=GetFeature&typeNames=lpis:AgriculturalArea&count=10000&startIndex=0

One feature, abbreviated:

```xml
<lpis:AgriculturalArea gml:id="AgriculturalArea_id_4c753ccc-4431-4be3-9f94-adc0a3593c11">
  <lpis:id>https://registry.gdi-de.org/id/de.by.inspire.invekos.lpis.aa.DEBYLI9412000570</lpis:id>
  <lpis:agriculturalAreaType xlink:title="Permanent grassland"
      xlink:href="https://registry.gdi-de.org/codelist/de.iacs/AgriculturalAreaTypeValue/GL"/>
  <lpis:geometry>
    <gml:Polygon srsName="urn:ogc:def:crs:EPSG::25832">…</gml:Polygon>
  </lpis:geometry>
  <lpis:validFrom>2025-01-01</lpis:validFrom>
</lpis:AgriculturalArea>
```

## API

| Standard      | URL                                                          | Documentation                                                                                       |
| ------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| OGC WFS 2.0.0 | https://gdiserv.bayern.de/srv66381/services/invekos_lpis-wfs | https://geoportal.bayern.de/gdiadmin/ausgabe/ISO19139/5685adb3-8cc5-4da6-98cc-527bbe33b994 |

Two quirks matter when writing a client:

- `count` is capped at 10,000 and larger values are silently reduced, so a full crawl of
  `AgriculturalArea` is 170 pages (~22 MB each).
- `numberReturned` is always reported as `0`, so the total must come from a `resultType=hits`
  request, which reports `numberMatched` correctly.
