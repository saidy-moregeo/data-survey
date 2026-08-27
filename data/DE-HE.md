# Hesse (HE), Germany

## Submission Details

- **Submitter (Affiliation):** Saidy Barry, moreGeo GmbH
- **Data Provider (Legal Entity):** Land Hessen (Government); the metadata contact is the Wirtschafts- und Infrastrukturbank Hessen (WIBank), which administers the state's agricultural funding, and the service is operated by EFTAS GmbH
- **Homepage:** https://www.geoportal.hessen.de/spatial-objects/886

## Overview

The reference parcel is the basic spatial unit for administering and geographically locating
agricultural parcels in Hesse. One may contain several parcels declared under InVeKoS and be farmed
by one or more farmers or producer associations. The data belongs to the system for identifying
agricultural parcels (LPIS), a subsystem of IACS / InVeKoS under Article 68 of Regulation (EC)
No 1306/2013. Three years are published; 618,214 parcels for 2025, at a mean of 1.22 ha.

## Data

- **URL:** https://inspire-geo.ibykus.net/geoserver/lawi/wfs
- **Documentation:** https://gdk.gdi-de.org/geonetwork/srv/api/records/0a75022a-1cbc-eb27-14cf-b66354d9f549 (GDI-DE), https://opendata.hessen.de
- **File Format:** GeoJSON (`application/json`) via WFS 2.0; GML 3.2 / 3.1.1 / 2.1.2, CSV and KML also offered
- **Projection:** EPSG:25832 (ETRS89 / UTM 32N); `srsName` is honoured and EPSG:4326 is returned at 8 decimal places
- **License:** [Creative Commons Namensnennung 4.0 (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/), with the INSPIRE constraint "Keine Beschränkungen des öffentlichen Zugangs". Note that the metadata record does not supply the source note the licence requires, stating literally "Quellenvermerk: Source note required by license, but not given!" — the exact attribution wording is therefore unconfirmed.
- **Attribution:** © Land Hessen, CC BY 4.0 (provisional, see above)

The service publishes 29 feature types across many years. The three relevant ones, for 2025:

| Feature type                             |   Count | Content                                                    |
| ---------------------------------------- | ------: | ---------------------------------------------------------- |
| `lawi:LPIS-Referenzparzellen 2025`       | 618,214 | Reference parcels with a land use class                    |
| `lawi:Landwirtschaftliche Parzellen 2025`| 618,214 | The same parcels, carrying main crop group instead         |
| `lawi:Landschaftselemente 2025`          | 137,595 | Landscape elements                                          |

The first two share the same geometry, FLIK and `declaredArea`, differing only in the thematic
attribute. Reference parcels are also published for 2024 (622,527) and 2023 (626,535).

### Properties

Properties of `lawi:LPIS-Referenzparzellen`.

| Property                                          | Data Type | Constraints      | Description                                                                     |
| -------------------------------------------------- | --------- | ---------------- | -------------------------------------------------------------------------------- |
| `id`                                              | string    | required, unique | Identifier such as `DE.HE.RP.DEHELI0004994212`. The FLIK is the final dot-segment |
| `agriculturalAreaType`                            | string    | required         | Land use class, as a code (values below)                                        |
| `agriculturalAreaType_txt`                        | string    | required         | German label for the same class                                                 |
| `declaredArea`                                    | number    | required         | Declared area **in hectares**, delivered as a JSON number                       |
| `declaredArea_uom`                                | string    | `ha`             | Unit of `declaredArea`                                                          |
| `validFrom` / `validTo`                           | string    | `DD.MM.YYYY`     | Validity period; constant within a year layer, e.g. `01.01.2025` / `31.12.2025` |
| `beginlifespanversion`                            | string    | `DD.MM.YYYY`     | Date the record version was created                                             |
| `agriculturalAreaWithinReferenceParcel`           | string    |                  | Identifier of the matching agricultural parcel, e.g. `DE.HE.AA.DEHELI…`         |
| `landscapeFeaturesAssociatedWithAgriculturalArea` | string    | nillable         | Associated landscape elements; `null` in every row sampled                      |
| `geometryType`                                    | string    | `GM_Surface`     | Geometry type                                                                   |
| `geom`                                            | Polygon   | required         | Parcel geometry                                                                 |

The FLIK taken from `id` is 16 characters, `DEHELI` plus 10 digits, and unique.

Values for `agriculturalAreaType`, with the German label and the share in a 32,000-row sample:

- `AL` — Ackerland (arable land), 40.1%
- `GL` — Dauergrünland (permanent grassland), 58.9%
- `DK` — Dauerkultur (permanent crop), 1.1%
- `S` — Sonstiges (other), 0.02%

### Example

Count the features, then request one page:

    …/lawi/wfs?service=WFS&version=2.0.0&request=GetFeature&typeNames=lawi:LPIS-Referenzparzellen%202025&resultType=hits
    …/lawi/wfs?service=WFS&version=2.0.0&request=GetFeature&typeNames=lawi:LPIS-Referenzparzellen%202025&outputFormat=application/json&count=25000&startIndex=0

One feature, with the coordinate list truncated:

```json
{
  "type": "Feature",
  "id": "LPIS-Referenzparzellen 2025.200001",
  "geometry": { "type": "Polygon", "coordinates": [[[430124.1176, 5540308.0853], …]] },
  "properties": {
    "validFrom": "01.01.2025",
    "validTo": "31.12.2025",
    "agriculturalAreaType": "DK",
    "agriculturalAreaType_txt": "Dauerkultur",
    "declaredArea": 0.0823108861267345,
    "declaredArea_uom": "ha",
    "id": "DE.HE.RP.DEHELI0004994212"
  }
}
```

## API

| Standard           | URL                                                            | Documentation                                                |
| ------------------ | -------------------------------------------------------------- | ------------------------------------------------------------ |
| OGC WFS 2.0.0      | https://inspire-geo.ibykus.net/geoserver/lawi/wfs              | https://www.geoportal.hessen.de/spatial-objects/886          |
| OGC API - Features | https://www.geoportal.hessen.de/spatial-objects/886/collections | https://www.geoportal.hessen.de/spatial-objects/886/api      |

The WFS supports paging (`startIndex`, `count`) with `CountDefault = 700000` — above any single
year — and reports `numberMatched` correctly; responses are chunked with no `Content-Length`. The
OGC API - Features endpoint caps `limit` at 10,000 and lists collections only through 2023.
