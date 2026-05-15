# Data Survey

A survey of non-standardized metadata, data and APIs that describe agricultural
fields and their boundaries.

## Data

The following data has been surveyed:

### Europe

- [Austria: INVEKOS Referenzen Österreich 2021](data/AT.md)
- [Vlaanderen, Belgium](data/BE-VLG.md)
- [Wallonia, Belgium](data/BE-WAL.md)
- [Bulgaria](data/BG.md)
- [Croatia](data/HR.md)
- [Czechia](data/CZ.md)
- [Denmark](data/DK.md)
- [Estonia](data/EE.md)
- [Finland](data/FI.md)
- [France](data/FR.md)
- [Berlin / Brandenburg, Germany](data/DE-BB.md)
- [Mecklenburg-Vorpommern, Germany](data/DE-MV.md)
- [Lower Saxony, Germany](data/DE-NDS.md)
- [North Rhine-Westphalia (NRW), Germany](data/DE-NRW.md)
- [Saarland, Germany](data/DE-SL.md)
- [Saxony, Germany](data/DE-SAX.md)
- [Schleswig-Holstein (SH), Germany](data/DE-SH.md)
- [Thuringia, Germany](data/DE-TH.md)
- [Ireland: Geospatial aid application (GSAA) dataset](data/IE.md)
- [Latvia](data/LV.md)
- [Lithuania](data/LT.md)
- [Luxembourg](data/LU.md)
- [The Netherlands](data/NL.md)
- [Norway: AR50 Agricultural land](data/NO.md)
- [Portugal](data/PT.md)
- [Romania (cross-border land cover)](data/RO.md)
- [Slovakia](data/SK.md)
- [Slovenia](data/SI.md)
- [Spain (national SIGPAC, 2025+)](data/ES.md)
- [Andalucía, Spain](data/ES-AN.md)
- [Aragón, Spain](data/ES-AR.md)
- [Canarias (Canary Islands), Spain](data/ES-CN.md)
- [Cantabria, Spain](data/ES-CB.md)
- [Castilla-La Mancha, Spain](data/ES-CM.md)
- [Castilla y León, Spain](data/ES-CL.md)
- [Cataluña (Catalonia), Spain](data/ES-CAT.md)
- [Comunidad de Madrid, Spain](data/ES-MD.md)
- [Comunitat Valenciana (Valencia), Spain](data/ES-VC.md)
- [Extremadura, Spain](data/ES-EX.md)
- [Galicia, Spain](data/ES-GA.md)
- [Islas Baleares (Balearic Islands), Spain](data/ES-PM.md)
- [La Rioja, Spain](data/ES-RI.md)
- [Navarra, Spain](data/ES-NC.md)
- [País Vasco (Basque Country), Spain](data/ES-PV.md)
- [Sweden](data/SE.md)
- [Switzerland](data/CH.md)
- [United Kingdom — UKFields (Fiboa-UK)](data/UK.md)

### Europe-wide

- [EuroCrops](data/EU-EuroCrops.md)
- [Digifarm](data/EU-Digifarm.md)

### Americas

- [West Bahia, Brazil (LEM)](data/BR-BA-LEM.md)
- [Brazil Crop Fields (CONAB)](data/BR-CONAB.md)
- [USDA Crop Sequence Boundaries](data/US-USDA-CropLand.md)
- [California (US) Statewide Crop Mapping](data/US-CA-SCM.md)

### Asia

- [India - 10k small holder](data/IN.md)
- [Japan Fude Parcels](data/JP.md)
- [AI4SmallFarms (Southeast Asia)](data/VM-KH-AI4SmallFarms.md)

### Oceania

- [New Zealand Irrigated Land Area](data/NZ.md)

### Africa

- [Lacuna Labels — Africa Crop Field Boundary Labels](data/lacuna_labels.md)

### Global / multi-region

- [AI4Boundaries](data/AI4Boundaries.md)
- [Global FieldID (Varda)](data/Global%20FieldID.md)
- [JECAM (Tropical Countries)](data/JECAM.md)
- [Open Supply Hub](data/Open-Supply-Hub.md)
- [PASTIS](data/PASTIS.md)
- [Planet](data/Planet.md)


## Data Survey Instructions

In order to help everyone get a real sense of how different field boundary datasets are structured we’ve started this survey. 
The idea is to have a page for each dataset that gives an overview of the data, includes details about it (file format, 
documentation, license, projection), and lays out the data schema / metadata. Every organization that is creating or consuming 
field boundaries should contribute to this. It is ok if it is a very simple schema, like just ID and Field. 

This should provide an easy reference during the [field boundaries workshop](https://sites.google.com/view/tge-field-boundary-initiative/) 
to ground any discussion about particular attributes, as we can easily look at to see what others did. And it should also 
serve as a continued resource to others in the future (if you don’t want to publish publicly we can also accommodate you). 

See the below for instructions if you're comfortable with GitHub or you can also just use 
[this google doc template](https://docs.google.com/document/d/1MQrVOG11bT_TbdorqxS8gL1CjJBWIkdYfok0dzTIz5Q/edit) and then 
include it in a new issue.

## Contribute

- Feel strongly encouraged to submit your information for the survey via a
  [Pull Request](https://github.com/fiboa/data-survey/pulls). 
- Please use the [template.md](template.md) to fill the survey. See the examples above for inspiration.
- Place the document with a descriptive name into the [data](data/) folder.
  If you provide more than one file, please create a folder that contains all files.
- The submission should include example data, ideally in GeoJSON format.
