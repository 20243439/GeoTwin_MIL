# GeoTwin_MIL
**A Novel Evaluation Framework for 15-Minute City Using Satellite Imagery**  accepted at **ACM SIGSPATIAL 2025**

---

## Overview
GeoTwin_MIL is a multi-modal framework for evaluating 15-Minute City (15MC) completeness using **satellite** and **map imagery**.  
It integrates **cross-modal contrastive learning** and **Multiple Instance Learning (MIL)** to predict multi-label urban functions at the regional level.

---

## Method
1. **Cross-Modal Contrastive Learning**  
   Aligns representations between satellite and map modalities.  
2. **MIL Aggregation**  
   Aggregates patch-level features to region-level predictions for multi-label classification.

---

## Repository Structure
GeoTwin_MIL
├── featureExtract # Feature extraction scripts
├── image_geotwin_feature_1024 # Example pre-extracted features
├── dataset.py # Dataset loading and preprocessing
├── model.py # Model architecture (contrastive + MIL)
├── main.py # Training and evaluation pipeline
├── train.sh # Example training script
└── LICENSE # MIT License

python main.py --mode eval --satellite_dir <satellite_path> --map_dir <map_path>
