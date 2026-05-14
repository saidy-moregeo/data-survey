# Saarland, Germany

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Ministerium für Umwelt, Klima, Mobilität, Agrar und Verbraucherschutz, Saarland (Government)
- **Homepage:** https://geoportal.saarland.de

## Overview

The Saarland IACS / GIS subsidy application areas ("Antragsschläge") published as
INSPIRE *Existing Land Use* features. The data covers parcels declared by farmers
for agricultural-land subsidies. It is served as INSPIRE-compliant GML through a WFS
endpoint and the FLIK identifier and field size are encoded inside the INSPIRE
`description` attribute (parsed by the converter using a regular expression).

## Data

- **URL:** https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege
- **Documentation:** https://geoportal.saarland.de
- **File Format:** GML 3.2 (INSPIRE *Existing Land Use*)
- **Projection:** EPSG:4258 (ETRS89)
- **License:** CC-BY-4.0
- **Attribution:** ©GDI-SL 2024

### Properties

| Property    | Data Type | Constraints                                 | Description                                             |
|-------------|-----------|---------------------------------------------|---------------------------------------------------------|
| identifier  | string    |                                             | INSPIRE feature identifier                              |
| description | string    | `flik: DESLLI…`, `Size in ha: …`            | INSPIRE description; encodes FLIK and field size in ha  |
| flik        | string    | FLIK pattern (FLIK extension)               | Field block identifier (parsed from `description`)      |
| area        | number    | hectares (parsed)                           | Field area in hectares (parsed from `description`)      |
| name        | string    |                                             | Feature label                                           |
| geometry    | Polygon   | EPSG:4258                                   | Field geometry                                          |

### Example

Use the WFS endpoint above with a small bounding box, e.g.:

```
https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege
  ?SERVICE=WFS&REQUEST=GetFeature&VERSION=2.0.0
  &typeNames=elu:ExistingLandUseObject
  &outputFormat=application/gml%2Bxml;%20version=3.2
  &EPSG=4258&BBOX=49.1,6.5423790007724,49.332379000772,6.7747580015449
```

## API

| Standard | URL                                                                                              |
|----------|--------------------------------------------------------------------------------------------------|
| OGC WFS  | https://geoportal.saarland.de/gdi-sl/inspirewfs_Existierende_Bodennutzung_Antragsschlaege        |
