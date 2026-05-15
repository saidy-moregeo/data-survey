# Mecklenburg-Vorpommern, Germany

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Ministerium für Landwirtschaft und Umwelt Mecklenburg-Vorpommern (Government)
- **Homepage:** https://www.geodaten-mv.de/dienste/feldblock_atom

## Overview

The Mecklenburg-Vorpommern *Feldblock* register is the official Land Parcel
Identification System (LPIS / FLIK) layer used to administer IACS / CAP payments
in the German state of Mecklenburg-Western Pomerania. The dataset includes
per-block land-use class, area, perimeter and DIN 19708 erosion hazard
classifications (wind and water).

## Data

- **URL:** https://www.geodaten-mv.de/dienste/gdimv_feldblock_wfs (WFS, shape-zip output)
- **Documentation:** https://www.geodaten-mv.de/dienste/feldblock_atom?type=dataset&id=f18122c4-2585-4c22-9c48-9e960e8dhd34
- **File Format:** ESRI Shapefile (via WFS shape-zip)
- **Projection:** WFS native (German state CRS)
- **License:** No restrictions apply (see Atom feed)

### Properties

| Property   | Data Type | Constraints                                       | Description                                           |
|------------|-----------|---------------------------------------------------|-------------------------------------------------------|
| fbid       | string    | FLIK pattern `DEMVLI…`                            | Field block identifier (FLIK)                         |
| dgl_jahr   | int16     |                                                   | Permanent-grassland year (DGL Jahr)                   |
| bodennutzu | string    |                                                   | Land use / crop code (Bodennutzungsart)               |
| bez_kreis  | string    |                                                   | District name (Kreisbezeichnung)                      |
| groesse_p  | number    | hectares                                          | Productive (net) area of the block                    |
| perimeter  | number    | metres                                            | Polygon perimeter                                     |
| erwind     | string    | `0`, `1`, `-`                                     | Wind-erosion class per Direktzahlungen-Verordnung     |
| erwater    | string    | `0`, `1`, `2`, `-`                                | Water-erosion class per Direktzahlungen-Verordnung    |
| erwind_l   | string    | `Enat0…Enat5`, `Enat0-EE…Enat5-EE`, `-`           | Wind-erosion class per DIN 19708                      |
| erwater_l  | string    | `Enat0…Enat5`, `Enat0-EE…Enat5-EE`, `-`           | Water-erosion class per DIN 19708                     |
| geometry   | Polygon   |                                                   | Field block geometry                                  |

### Example

Request a small sample via the WFS endpoint above (use `MAXFEATURES=10`).

## API

| Standard | URL                                                     |
|----------|---------------------------------------------------------|
| OGC WFS  | https://www.geodaten-mv.de/dienste/gdimv_feldblock_wfs  |
