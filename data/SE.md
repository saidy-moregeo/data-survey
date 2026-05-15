# Sweden

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Jordbruksverket (The Swedish Board of Agriculture) (Government)
- **Homepage:** https://jordbruksverket.se

## Overview

A Swedish crop field ("Jordbruksskifte") is a contiguous area of land within a block where a farmer grows a crop or
otherwise manages the land. To receive compensation for agricultural support (EU support), farmers apply via a SAM
application — Sweden's implementation of the EU Common Agricultural Policy (CAP) declaration within the Integrated
Administration and Control System (IACS). The dataset contains parcels where the area applied for and the area
decided on are the same; it is published at the end of each year.

The Swedish crop code list is documented at
https://jordbruksverket.se/stod/jordbruk-tradgard-och-rennaring/sam-ansokan-och-allmant-om-jordbrukarstoden/grodkoder .

## Data

- **URL:** Per-year WFS shape-zip exports from the Inspire endpoint, e.g.
  - 2024: `http://epub.sjv.se/inspire/inspire/wfs?SERVICE=WFS&REQUEST=GetFeature&VERSION=1.0.0&TYPENAMES=inspire:arslager_skifte&outputFormat=shape-zip&CQL_FILTER=arslager='2024' and geom is not null&format_options=CHARSET:UTF-8`
  - 2023: same URL with `arslager='2023'`
- **Documentation:** https://inspire-geoportal.ec.europa.eu/srv/eng/catalog.search#/datasetdetails?country=se&view=IACSOverview&theme=none&resourceId=e317c48b-2a5e-4590-a2d5-c79900541d13
- **File Format:** Shapefile (zipped, returned by WFS as `shape-zip`)
- **Projection:** EPSG:3006 (SWEREF 99 TM)
- **License:** [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) (Open Data)
- **Attribution:** "Jordbruksverket"

### Properties

| Property   | Data Type | Constraints | Description           |
|------------|-----------|-------------|-----------------------|
| arslager   | integer   |             | Application year      |
| blockid    | string    |             | Block identifier      |
| skiftesbet | string    |             | Crop field identifier | 
| grdkod_mar | integer   |             | Main crop code        |
| grdkod_und | integer   |             | Sub crop code         |    
| ansokt_are | float     |             | Declared area         |
| faststalld | float     |             | Determined area       | 


## API (optional)

| Standard | URL                                                                                       | Documentation |
|----------|-------------------------------------------------------------------------------------------|---------------|
| OGC WMS  | https://epub.sjv.se/inspire/inspire/ows?request=getcapabilities&service=wms&version=1.3.0 | -             |
