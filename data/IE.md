# Ireland: Geospatial aid application (GSAA) dataset

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Department of Agriculture, Food and the Marine (Government)
- **Homepage:** https://www.gov.ie/en/organisation/department-of-agriculture-food-and-the-marine/

## Overview

The Ireland INSPIRE Geospatial Aid Application (GSAA) dataset represents the outline shape of LPIS parcels as
claimed under area-based schemes within the EU Common Agricultural Policy (CAP) and the Integrated Administration
and Control System (IACS). It includes the crops claimed as part of the annual GSAA — yearly information collected
through the beneficiary declaration.

## Data

- **URL:** Per-year GML downloads at `https://dafm-inspire-atom.s3.eu-west-1.amazonaws.com/files/LU/GSAA_<YEAR>.zip` for years 2022–2024 (e.g. https://dafm-inspire-atom.s3.eu-west-1.amazonaws.com/files/LU/GSAA_2024.zip containing `GSAA_2024.gml`, layer `ExistingLandUseObject`)
- **Documentation:** https://inspire-geoportal.ec.europa.eu/srv/eng/catalog.search#/extenddetails?country=ie&view=priorityOverview&theme=none&resourceId=IACSdata_INSPIRE_ATOM
- **File Format:** GML (zipped), Inspire ELU theme
- **Projection:** EPSG:4258 (ETRS89)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** "Ireland Department of Agriculture, Food and the Marine"

The source `crop_name` may contain multiple comma-separated crops. Rows with `crop_name == "Void"` denote non-agricultural areas.

### Properties

| Property              | Data Type | Constraints | Description   |
|-----------------------|-----------|-------------|---------------|
| localId               | int       |             | Identifier    |
| crop_name             | string    |             | Name of crop  |
| observationDate       | datetime  |             | Date observed |
| validFrom             | datetime  |             | Date start    |
