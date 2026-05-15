# Comunitat Valenciana (Valencia), Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Spanish Agricultural Guarantee Fund (FEGA) of the Ministry of Agriculture, Fisheries and Food (Government)
- **Homepage:** https://www.fega.gob.es/es/PwfGcp/es/el_fega/index.jsp

## Overview

This dataset is the graphic layer of the plots and enclosures with defined agricultural uses that accompany the information of the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) in the Comunitat Valenciana. SIGPAC arises through the collaboration between the Spanish Agricultural Guarantee Fund (FEGA) and the Agriculture Councils of the autonomous communities; it is a public administrative register that contains updated information on the plots likely to benefit from community aid related to the surface area.

The Institut Cartogràfic Valencià download portal publishes the data per campaign year (2016–2024).

## Data

- **URL:** https://descargas.icv.gva.es/dcd/14_mediorural/03_pac/`<YEAR>`_SIGPAC_0050 (per-archive ZIP files matching `1403_...RECINTOS...`)
- **Documentation:** https://catalogo.icv.gva.es/geonetwork/srv/spa/catalog.search#/metadata/spaicv1403_sigpac2024
- **File Format:** Shapefile (enclosure shapefile at `*/RECINTO.shp`)
- **Projection:** EPSG:25830 (ETRS89 / UTM zone 30N)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) (see http://www.icv.gva.es/condiciones-de-uso-de-la-geoinformacion-icv)
- **Attribution:** © Institut Cartogràfic Valencià, Generalitat

The published surface (`DN_SURFACE`) is in square metres.

| Property   | Data Type | Constraints | Description     |
|------------|-----------|-------------|-----------------|
| DN_OID     | Integer   |             |                 |
| DN_SURFACE | Real      |             | Area in m^2     |
| DN_PERIMET | Real      |             | Perimeter in m  |
| PROVINCIA  | Integer   |             | Province ID     |
| MUNICIPIO  | Integer   |             | Municipality ID |
| AGREGADO   | Integer   |             |                 |
| ZONA       | Integer   |             |                 |
| POLIGONO   | Integer64 |             |                 |
| PARCELA    | Integer64 |             |                 |
| RECINTO    | Integer64 |             |                 |
| PENDIENTE_ | Integer64 |             |                 |
| ALTITUD    | Integer64 |             |                 |
| COEF_REGAD | String    |             |                 |
| USO_SIGPAC | String    |             | SIGPAC use code |
| INCIDENCIA | String    |             |                 | 
| PARCELA_AG | String    |             |                 | 
| GRUPO_CULT | String    |             |                 | 
| REGION     | Integer64 |             |                 |
| ALMENDROS  | Integer64 |             |                 |
| ALGARROBOS | Integer64 |             |                 |
| NOGALES    | Integer64 |             |                 |
| PISTACHOS  | Integer64 |             |                 |
| OTROS      | Integer64 |             |                 |
| CASTANOS   | Integer64 |             |                 |
| X_ETRS8930 | Real      |             |                 | 
| Y_ETRS8930 | Real      |             |                 |
| X_ED5030   | Real      |             |                 | 
| Y_ED5030   | Real      |             |                 |
| CAP_PREV   | Real      |             |                 |

Webviewer: https://visor.gva.es/visor/?capas=spaicv1403_sigpac2024

## API

| Standard | URL                                                                           | Documentation |
|----------|-------------------------------------------------------------------------------|---------------|
| OGC WMS  | https://terramapas.icv.gva.es/1403_SIGPAC?service=WMS&request=GetCapabilities | -             |
| OGC WFS  | https://terramapas.icv.gva.es/1403_SIGPAC?service=wfs&request=getcapabilities | -             |

### Example

Webviewer: https://visor.gva.es/visor/?capas=spaicv1403_sigpac2024
