# Brazil Crop Fields (CONAB)

## Submission Details

- **Submitter (Affiliation):** Tristan Grupp / Ivor Bosloper
- **Data Provider (Legal Entity):** Companhia Nacional de Abastecimento (CONAB) (Government)
- **Homepage:** https://portaldeinformacoes.conab.gov.br/mapeamentos-agricolas-downloads.html

## Overview

CONAB, Brazil's National Supply Company, is the government agency responsible for providing information on the country's agricultural harvest.

This subset of 27 mappings, after inspecting all boundaries in the CONAB public database, appears to be hand-drawn field boundaries. The dataset covers a range of crops (cotton, irrigated rice, sugar cane, coffee, summer crops) across multiple Brazilian states (GO, MS, PR, RS, SC, TO, BA, DF, MG, RJ) and harvest years.

The content of the Mappings comes from CONAB, total or partial reproduction without profit motives is authorized, as long as the source is cited and the integrity of the information is maintained.

Further information or suggestions can be sent to the email address conab.geote@conab.gov.br.

## Data

- **URL:** https://portaldeinformacoes.conab.gov.br/downloads/mapas/ (multiple ZIP archives under `Algodao/`, `Arroz_Irrigado/`, `Cana/`, `Cafe/`, `Culturas_de_Verao_1_Safra/`)
- **Documentation:** https://portaldeinformacoes.conab.gov.br/mapeamentos-agricolas-downloads.html
- **File Format:** Shapefile (ZIP-packaged)
- **Projection:** Mixed across files (commonly EPSG:4674 / SIRGAS 2000)
- **License:** [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0/)
- **Attribution:** CONAB - conab.gov.br

### Properties

CONAB shapefiles have inconsistent naming between years; variants of municipality code/name and area exist across files.

### Properties

This is the combined mix of properties of the different shapefiles

| Property   | Data Type | Constraints | Description                                |
|------------|-----------|------------|--------------------------------------------|
| id         | number    |            | Not so usefull combining multiple datasets |
| cd_mun     | number    |            | Municipality code                          |
| nm_mun     | string    |            | Municipality name                          |
| area_ha    | number    |            | Area in ha                                 |
| CD_MUN     | number    |            | Municipality code                          |
| NM_MUN     | string    |            | Municipality name                          |
| SIGLA_UF   | number    |            |                                            |
| CD_GEOCMU  | number    |            |                                            |
| OBJECTID_1 | number    |            |                                            |
| DS_USO     | number    |            |                                            |
| CD_UGT     | string    |            |                                            |
| CD_IBGE_MU | number    |            |                                            |
| NM_MUNIC   | string    |            |                                            |
| NM_MICRO_R | string    |            | Municipality name ?                        |
| Shape_Leng | number    |            | Perimeter                                  |
| Shape_Area | number    |            | Area in ..                                 |
| Hectares   | number    |            | Area in ha                                 |
| REGIAO     | string    |            |                                            |
| sigla_uf   | string    |            |                                            |
