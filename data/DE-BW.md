# Baden-Württemberg (BW), Germany

## Submission Details

- **Submitter (Affiliation):** Saidy Barry, moreGeo GmbH
- **Data Provider (Legal Entity):** Ministerium für Ländlichen Raum und Verbraucherschutz Baden-Württemberg (MLR) (Government)
- **Homepage:** https://mlr.baden-wuerttemberg.de

## Overview

LPIS reference system for area-based agricultural payments; BW uses the cadastral parcel (Katasterflurstück) as the reference parcel, which is why there are ~5.07M polygons per year, of which ~4.36M are agricultural land, at a mean 0.35 ha; subsystem of InVeKoS under Art. 68 Reg. (EC) 1306/2013; collected under § 3(1) InVeKoS-Verordnung; maintained continuously from orthophotos and remote sensing; capture scale ~1:5,000.

## Data
- **URL:** https://owsproxy.lgl-bw.de/owsproxy/wfs/WFS_LW-BW_GISELA_landw_Parzellen
- **Documentation:** one ISO 19139 record per year, at
  `https://metadaten.geoportal-bw.de/geonetwork/srv/ger/catalog.search#/metadata/<uuid>`
  - 2018: `2485691b-415a-4f48-98c0-6a0cae5a154c`
  - 2019: `ed139dcf-c759-48df-96ce-587946a582d1`
  - 2020: `690987ca-0930-41bd-b38f-7c16ef8271b5`
  - 2021: `a66a9349-5fdc-417e-b49a-75c4e5879ecb`
  - 2022: `2a7d65fa-e222-42a0-8c4a-d3d9bd8ee4c6`
- **File Format:** GeoJSON (application/json) via WFS 2.0; GML 3.2 / 3.1.1 / 2.1.2 also offered
- **Projection:** EPSG:25832 (ETRS89 / UTM 32N)
- **License:** [Datenlizenz Deutschland – Namensnennung – Version 2.0 (dl-de/by-2-0)](<https://www.govdata.de/dl-de/by-2-0>)
- **Data Creation Details:** official LPIS maintenance by MLR at ~1:5,000, continuously updated from orthophotos and remote sensing.
- **Computer Vision / AI Details:** No
- **Attribution:** © MLR Baden-Württemberg (2026), dl-de/by-2-0


### Properties

|     Property     |        Data Type          |        Constraints       |                                     Description                        |
| ---------------- | ------------------------- | ------------------------ | ---------------------------------------------------------------------- |
| `Geo-ID`         | `xsd:string`              | required, unique         | UUID of the geometry. Stable identifier, used as fiboa `id`                                                                                   |
| `FLIK`           | `xsd:string`              | required, 16 chars       | Field block identifier (Feldblock-Identifikator) of the reference parcel. **Not unique** — one reference parcel may carry several usage types |
| `Bodenbedeckung` | `xsd:string`              | required, see list below | Land cover / usage type delineated within the reference parcel                                                                                |
| `FlaecheInHa`    | `xsd:decimal`             | required, > 0            | Maximum area **eligible for direct payments**, in hectares. Not the geometric area of the polygon                                             |
| `Antragsjahr`    | `xsd:int`                 | required                 | Application year (2018–2022). Constant within a layer                                                                                         |
| `object_id`      | `xsd:int`                 | optional                 | Row counter within the layer; not stable across publications                                                                                  |
| `geom`           | `gml:SurfacePropertyType` | optional, Polygon        | Parcel geometry. In BW the cadastral parcel (Katasterflurstück) is the reference parcel                                                       |

Values for `Bodenbedeckung` — the service abstract groups them into five classes, and notes that
one reference parcel may carry several. Counts are for 2022 (5,066,936 rows in total):

Agricultural land (4,363,087):

- `Ackerland` — arable land (1,666,841)
- `Grünland` — grassland (2,304,561)
- `Dauerkultur` — permanent crops (391,685)

Non-agricultural (18,538):

- `nicht landw. Fläche` — non-agricultural area

Landscape elements (685,311), 12 values. The suffix marks the protection status: `(CC-LE)` is
protected under Cross Compliance / GLÖZ, `(LE)` is a recorded element without that status:

- `Hecke/Knick (CC-LE)` / `(LE)` — hedge
- `Feldgehölz (CC-LE)` / `(LE)` — field copse
- `Feldrain (CC-LE)` / `(LE)` — field margin
- `Graben (LE)` — ditch
- `Feuchtgebiet (CC-LE)` — wetland
- `Baumreihe (CC-LE)` — row of trees
- `Trocken-, Natursteinmauer, Lesesteinwall (CC-LE)` — dry stone wall / stone bank
- `Fels-, Steinriegel, naturversteinte Fläche (CC-LE)` — rock or stone ridge
- `Tümpel, Söll, Doline (CC-LE)` — pond, kettle hole, doline

### Example

One page of eligible farmland in the native CRS:

    https://owsproxy.lgl-bw.de/owsproxy/wfs/WFS_LW-BW_GISELA_landw_Parzellen?service=WFS&version=2.0.0&request=GetFeature&typeNames=lw:v_gisela_landw_parzellen_2022&outputFormat=application/json&count=1000&startIndex=700000&cql_filter=Bodenbedeckung%20IN%20('Ackerland','Gr%C3%BCnland','Dauerkultur')


Replace `resultType=hits` for a count only (`numberMatched="4363087"` for the filter above).

```json
{
  "type": "Feature",
  "id": "v_gisela_landw_parzellen_2022.685312",
  "geometry": {
    "type": "Polygon",
    "coordinates": [[[488916.26, 5454734.54], [488914.45, 5454732.31],
                     [488860.97, 5454746.69], [488916.26, 5454734.54]]]
  },
  "geometry_name": "geom",
  "properties": {
    "Geo-ID": "90ccfce8-ab2e-4704-97ea-e5547b383841",
    "FLIK": "DEBWLI328202TA00",
    "Bodenbedeckung": "Ackerland",
    "FlaecheInHa": 0.0072,
    "Antragsjahr": 2022,
    "object_id": 685312
  }
}
```

## API

|    Standard   |                                     URL                                  | Documentation |
| ------------- | ------------------------------------------------------------------------ | ------------- |
| OGC WFS 2.0.0 | https://owsproxy.lgl-bw.de/owsproxy/wfs/WFS_LW-BW_GISELA_landw_Parzellen | https://metadaten.geoportal-bw.de/geonetwork/srv/ger/catalog.search#/metadata/2a7d65fa-e222-42a0-8c4a-d3d9bd8ee4c6 |
