# EuroCropsV2

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Joint Research Centre, European Commission; EUROSTAT; Technical University of Munich
- **Homepage:** https://data.jrc.ec.europa.eu/dataset/b9fb9e67-78a9-4327-9d59-39a928d812d3
- **Source code:** https://github.com/Martincccc/EuroCropsV2/
- **Citation:** European Commission, Joint Research Centre (2026): *EuroCropsV2*. Dataset.
  doi:10.2905/JRC.FX0BVKR; doi:10.2905/b9fb9e67-78a9-4327-9d59-39a928d812d3

## Overview

EuroCropsV2 is a harmonised, multi-annual collection of parcel-level crop declarations (Geo-Spatial Application, GSA)
from EU paying agencies. It builds on the original [EuroCrops](EU-EuroCrops.md) initiative by Technical University of
Munich and is now jointly maintained with the JRC and EUROSTAT. The published v2 release covers **18 NUTS regions
across 16 EU Member States** with at least three years per region, totalling ~47 million agricultural parcels and
~21 million hectares. Each record carries the original-source crop code; HCAT v4 names and codes are joined in via
the per-NUTS mapping CSVs (see below).

Compared to v1, the v2 release:

- Adds new countries / sub-regions: Bulgaria, Finland, Ireland, Italy (Tuscany), Germany (Brandenburg + North
  Rhine-Westphalia), and extends Belgium with both Flanders and Wallonia.
- Extends the temporal range — some NUTS regions go back to 2008 (Flanders) — and covers all years through 2023.
- Adopts the new **HCAT v4** taxonomy (replacing HCAT v3 from v1).
- Is distributed as **GeoParquet** (one file per NUTS region per year, plus a multi-year *stack* file per region),
  re-projected to **EPSG:3035** (LAEA Europe).
- Adds a stack layer per region that links the same parcel ("cropfield") across years for time-series analysis.
- Provides four mapping CSVs covering HCAT4, the original-to-HCAT mapping per NUTS region, links to agricultural
  products (Eurostat / IFS-FSS) and links to the Copernicus HRL Crop Types layer.

The dataset supports CAP monitoring, comparative spatio-temporal analyses across the EU, and interoperability with
LUCAS, IFS/FSS, FADN, EUCropMap and the Copernicus HRL Crop Types layer.

National-level survey pages (where they exist) describe the underlying source datasets in more detail; this page
focuses on the EuroCropsV2-harmonised variants.

## Data

- **Primary download (v2):** https://jeodpp.jrc.ec.europa.eu/ftp/jrc-opendata/DRLL/EuroCropsV2/gpqtv2/
- **Patch release (v2.0.1):** https://jeodpp.jrc.ec.europa.eu/ftp/jrc-opendata/DRLL/EuroCropsV2/gpqtv201/
  (v2.0.1 re-processes a number of regions; the BG stack file is not yet republished in v2.0.1, the BG yearly
  files are.)
- **Code & mapping tables:** https://github.com/Martincccc/EuroCropsV2 (especially
  [`data/cropcodemapping/`](https://github.com/Martincccc/EuroCropsV2/tree/main/data/cropcodemapping))
- **JRC catalogue entry:** https://data.jrc.ec.europa.eu/dataset/b9fb9e67-78a9-4327-9d59-39a928d812d3
- **File Format:** GeoParquet (one yearly file `<nuts>_<year>.parquet` per region per year, plus
  `<nuts>_stack.parquet` per region linking the same parcel across years). The JRC catalogue also offers a
  consolidated Esri File Geodatabase and a CSV export.
- **Projection:** EPSG:3035 (ETRS89-extended / LAEA Europe)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (the JRC catalogue entry; individual
  national source datasets may carry stricter terms — see per-country survey pages)
- **Naming convention:** lowercase NUTS code (national or sub-national; see "Country variants" below) +
  `_<year>` for yearly files or `_stack` for the multi-year stack.

### Yearly file columns

Per the [EuroCropsV2 README](https://github.com/Martincccc/EuroCropsV2):

| Property        | Data Type | Description                                                                       |
|-----------------|-----------|-----------------------------------------------------------------------------------|
| geom            | Polygon   | Parcel geometry in EPSG:3035                                                      |
| cropfield       | string    | Unique parcel identifier (primary key within the region/year)                     |
| original_code   | string    | Crop code as published in the source national dataset                             |
| off_area        | number    | Officially reported parcel area (units as published nationally; usually ha)       |
| area_ha         | number    | Parcel area in hectares, computed from `geom` (`ST_Area(geom)/10000`)             |

HCAT v4 names and codes are obtained by joining against `Eurocrops.csv` on `(nuts, original_code)` — they're not
embedded in every yearly file to keep the per-file footprint small.

### Stack file columns

The per-region `<nuts>_stack.parquet` links the same cropfield (parcel) across years for time-series analyses:

| Property   | Data Type | Description                                                                |
|------------|-----------|----------------------------------------------------------------------------|
| geom       | Polygon   | Parcel geometry (EPSG:3035)                                                |
| cropfield  | string    | Stable parcel identifier across years                                      |
| area_ha    | number    | Area in hectares                                                           |
| cf<year>   | string    | Cropfield identifier in the yearly file for `<year>` (one column per year) |
| c<year>    | string    | Crop code in the yearly file for `<year>` (one column per year)            |

### Mapping CSVs

| File | Purpose |
|---|---|
| [`hcat4.csv`](https://github.com/Martincccc/EuroCropsV2/blob/main/data/cropcodemapping/hcat4.csv) | HCAT v4 hierarchy (crop codes + names + seasonality) |
| [`Eurocrops.csv`](https://github.com/Martincccc/EuroCropsV2/blob/main/data/cropcodemapping/Eurocrops.csv) | Per-NUTS mapping from `original_code` → HCAT4 (columns: `nuts`, `original_code`, `original_name`, `translated_name`, `hcat4_code`, `hcat4_name`, `usage_code`, `usage_name`) |
| `hcat4_agriprod_mapping.csv` | HCAT4 → Eurostat / IFS-FSS agricultural products |
| `hcat4_hrl_mapping.csv` | HCAT4 → Copernicus High Resolution Layer (HRL) Crop Types |

## Country variants

The 18 NUTS regions are distributed as separate GeoParquet files per year. Year ranges below come directly from the
v2 FTP listing.

| NUTS  | Country / region                       | Years available   | National page |
|-------|----------------------------------------|-------------------|---------------|
| at    | Austria                                | 2015–2023         | [AT.md](AT.md) |
| be2   | Belgium — Flanders (NUTS-1)            | 2008–2023         | [BE-VLG.md](BE-VLG.md) |
| be3   | Belgium — Wallonia (NUTS-1)            | 2015–2023         | [BE-WAL.md](BE-WAL.md) |
| bg    | Bulgaria                               | 2014–2023         | [BG.md](BG.md) |
| cz    | Czechia                                | 2021–2023         | [CZ.md](CZ.md) |
| de4   | Germany — Brandenburg (NUTS-1, DE4)    | 2010–2023         | [DE-BB.md](DE-BB.md) |
| dea   | Germany — North Rhine-Westphalia (DEA) | 2019–2023         | [DE-NRW.md](DE-NRW.md) |
| dk    | Denmark                                | 2010–2023         | [DK.md](DK.md) |
| ee    | Estonia                                | 2015–2023         | [EE.md](EE.md) |
| es    | Spain                                  | 2021–2023         | [ES.md](ES.md) |
| fi    | Finland                                | 2020–2023         | [FI.md](FI.md) |
| fr    | France                                 | 2015–2023         | [FR.md](FR.md) |
| ie    | Ireland                                | 2017–2023         | [IE.md](IE.md) |
| iti1  | Italy — Tuscany (NUTS-2, ITI1)         | 2016–2023         | — |
| nl    | Netherlands                            | 2009–2023         | [NL.md](NL.md) |
| pt    | Portugal                               | 2017–2023         | [PT.md](PT.md) |
| si    | Slovenia                               | 2019–2023         | [SI.md](SI.md) |
| sk    | Slovakia                               | 2018–2023         | [SK.md](SK.md) |

Total v2: 153 yearly GeoParquet files + 18 per-region stack files. v2.0.1 patch updates a subset; the BG stack file
is not present in v2.0.1 (yearly BG files are).

## API

EuroCropsV2 is distributed as static GeoParquet files via the JRC's OpenData FTP. No live API is provided. The
repository includes scripts (`code/import_db/`) that ingest the GeoParquet files plus mapping tables into PostGIS or
DuckDB for querying.

## Example

```bash
# Stream a single yearly slice with DuckDB (no full download needed)
duckdb -c "
  INSTALL spatial; LOAD spatial; INSTALL httpfs; LOAD httpfs;
  SELECT cropfield, original_code, area_ha
  FROM read_parquet('https://jeodpp.jrc.ec.europa.eu/ftp/jrc-opendata/DRLL/EuroCropsV2/gpqtv201/nl_2023.parquet')
  LIMIT 5;
"
```
