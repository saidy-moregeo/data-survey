# 10,000 Crop Field Boundaries across India

## Submission Details

- **Submitter (Affiliation):** Snehal Chaudhari, ASU
- **Data Provider (Legal Entity):** Zenodo / Sherrie Wang, Francois Waldner, David B. Lobell (Research)
- **Homepage:** https://zenodo.org/records/7315090

## Overview

Release of dataset and neural network weights accompanying the paper "Unlocking large-scale crop field delineation in smallholder farming systems with transfer learning and weak supervision" (published in Remote Sensing). Ten thousand crop fields in India were delineated manually through inspection of high-resolution satellite imagery (Airbus SPOT). The publication also provides the weights of the highest performing neural network (FracTAL ResUNet architecture) pre-trained in France and fine-tuned on Airbus SPOT images in India. The model was trained in MXNet 1.6.0 and can be loaded with the `model.load_parameters()` function.

## Data

- **URL:** https://zenodo.org/api/records/7315090/files-archive (downloaded as `india_10k.zip`)
- **Documentation:** https://www.mdpi.com/2072-4292/14/22/5738
- **File Format:** Shapefile (inside ZIP)
- **Projection:** EPSG:4326 (WGS 84)
- **License:** [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** https://doi.org/10.5281/zenodo.7315090
- **Citation:** Wang, S., Waldner, F., & Lobell, D. B. (2022). Unlocking large-scale crop field delineation in smallholder farming systems with transfer learning and weak supervision. *Remote Sensing*. https://doi.org/10.5281/zenodo.7315090

### Properties

The source dataset is sparsely attributed; only geometry and area are provided.

| Property | Data Type | Constraints | Description |
|----------|-----------|-------------|-------------|
| geometry | Polygon   | EPSG:4326   | Field boundary geometry |
| area     | number    | square metres | Pre-computed area in m² |

### Example

| Property | Example Value |
| -------- | ------------- |
| area     | 15182.634905182778 |
| sample   | sample |

## API

No publicly documented API; data is distributed via the Zenodo archive.
