# Cantabria, Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Gobierno de Cantabria (Government)
- **Homepage:** https://mapas.cantabria.es

## Overview

The dataset contains the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) reference enclosures (Recintos SIGPAC) for the autonomous community of Cantabria, published as an INSPIRE-compatible ESRI MapServer service. The data is served via the ESRI REST API, with a yearly layer (Recintos SIGPAC `<YEAR>`). Years from 2010 through 2024 are exposed.

## Data

- **URL:** https://geoservicios.cantabria.es/inspire/rest/services/SIGPAC/MapServer (ESRI REST MapServer; one layer per year, named `Recintos SIGPAC <YEAR>`)
- **Documentation:** https://www.territoriodecantabria.es/cartografia-sig/datos-abiertos-y-politica-de-licencias
- **File Format:** ESRI REST / FeatureServer JSON (converted to GeoJSON)
- **Projection:** EPSG:4326 (REST export)
- **License:** [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0/) (commercial use only on request)
- **Attribution:** ©Government of Cantabria. Free information available at https://mapas.cantabria.es

The published surface (`DN_SURFACE`) is in square metres.

### Properties

| Property   | Data Type | Constraints | Description     |
|------------|-----------|-------------|-----------------|
| OBJECTID   | Integer64 |             |                 |
| DN_OID     | Integer64 |             |                 |
| DN_SURFACE | Real      |             | Area in m^2     |
| DN_PERIMET | Real      |             | Perimeter in m  |
| PROVINCIA  | Integer64 |             | Province ID     |
| MUNICIPIO  | Integer64 |             | Municipality ID |
| POLIGONO   | Integer64 |             |                 |
| PARCELA    | Integer64 |             |                 |
| RECINTO    | Integer64 |             |                 |
| PENDIENTE_ | Integer64 |             |                 |
| COEF_REGAD | String    |             |                 |
| COEF_ADMIN | Integer64 |             |                 |
| USO_SIGPAC | String    |             | SIGPAC use code |
| INCIDENCIA | String    |             |                 | 
| MOTIVO_MOD | String    |             |                 | 
| REFERENCIA | String    |             |                 | 
| DATA       | Integer64 |             |                 |
| CERCA      | String    |             |                 | 
| ANYS       | Integer64 |             |                 |
| Shape_Leng | Real      |             |                 |
| Shape_Area | Real      |             |                 |

## API

| Standard | URL                                                                                                              | Documentation |
|----------|------------------------------------------------------------------------------------------------------------------|---------------|
| ESRI REST | https://geoservicios.cantabria.es/inspire/rest/services/SIGPAC/MapServer                                        | -             |
| OGC WMS  | https://geoservicios.cantabria.es/inspire/services/SIGPAC/MapServer/WMSServer?request=GetCapabilities&service=WMS | -           |
| OGC WFS  | https://geoservicios.cantabria.es/inspire/services/SIGPAC/MapServer/WFSServer?request=GetCapabilities&service=WFS | -           |
