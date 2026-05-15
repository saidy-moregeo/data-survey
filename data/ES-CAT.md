# Cataluña (Catalonia), Spain

## Submission Details

- **Submitter (Affiliation):** Ivor Bosloper
- **Data Provider (Legal Entity):** Catalonia Department of Agriculture, Livestock, Fisheries and Food (Government)
- **Homepage:** https://agricultura.gencat.cat/ca/ambits/desenvolupament-rural/sigpac/mapa-cultius/

## Overview

The Department of Agriculture, Livestock, Fisheries and Food publishes the Catalonia crop map (Mapa de cultius), which combines data from the Agrarian Declaration (DUN) submitted to the DACC with the SIGPAC (Sistema de Información Geográfica de la Política Agrícola Común, the Geographical Information System for Common Agricultural Policy) reference parcels. The DUN is the tool used to file declarations for agricultural holdings in Catalonia and is also used to apply for grants and certain procedures with the Department of Agriculture; declarations are georeferenced on the SIGPAC base, which lets users locate the declared crops on each plot and study irrigation, second cultivations and the historical evolution of crops in the territory.

Unlike the other Spanish regions in this survey, Catalonia uses its own crop coding (not the generic SIGPAC land-use codes). The dataset is delivered per campaign, with annual variants from 2019 through 2024.

## Data

- **URL:** https://analisi.transparenciacatalunya.cat/Medi-Rural-Pesca/Mapa-de-cultius-de-Catalunya-amb-origen-DUN/e7kw-9ebb (annual archives, e.g. `Cultius_DUN2024_SHP.zip`, `Cultius_DUN2023_GPKG.zip`)
- **Documentation:** https://agricultura.gencat.cat/web/.content/09-desenvolupament-rural/comu/dades_obertes/origen-dades-mapa-cultius.pdf
- **File Format:** GeoPackage (recent years) / Shapefile (older years), distributed as ZIP
- **Projection:** EPSG:25831 (ETRS89 / UTM zone 31N)
- **License:** [The Open Information Use License - Catalonia](https://administraciodigital.gencat.cat/ca/dades/dades-obertes/informacio-practica/llicencies/)
- **Attribution:** Catalonia Department of Agriculture, Livestock, Fisheries and Food

### Properties

| Property   | Data Type | Constraints | Description                                 |
|------------|-----------|-------------|---------------------------------------------|
| Campanya   | Integer   |             | campaign year                               |
| Provincia  | String    |             | Adminstrative subdivision Province          |
| Comarca    | String    |             | Adminstrative subdivision                   | 
| Municipi   | String    |             | Adminstrative subdivision municipality      |
| IDMUN      | String    |             | Municipality ID                             |                        
| Grup       | String    |             | Crop Group                                  |             
| Cultiu     | String    |             | Crop Name                                   |
| Seca_Regad | String    | S or R      | Irrigation coefficient (S=Dry, R=Irrigated) |                
| Sist_Regad | String    |             | Irrigation system used                      |              
| Varietat   | String    |             | Crop Variety                                |     
| Producte2n | String    |             | Second cultivated product                   |                
| HA         | Real      |             | Area                                        |


## API

| Standard  | URL                                                                            | Documentation |
|-----------|--------------------------------------------------------------------------------|---------------|
| OGC WMS   | http://sig.gencat.cat/ows/AGRICULTURA/wms                                      | -             |
| OGC WFS   | https://sig.gencat.cat/ows/AGRICULTURA/wfs?request=getcapabilities&service=wfs | -             |

### Example

https://sig.gencat.cat/visors/Cultius_DUN_SIGPAC.html
https://analisi.transparenciacatalunya.cat/Medi-Rural-Pesca/Mapa-de-cultius-de-Catalunya-amb-origen-DUN/e7kw-9ebb
