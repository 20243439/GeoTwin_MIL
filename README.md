# GeoTwin_MIL

[![ACM SIGSPATIAL 2025](https://img.shields.io/badge/ACM%20SIGSPATIAL-2025-blue)](https://sigspatial2025.sigspatial.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-green.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)](https://pytorch.org/)

> **A Novel Evaluation Framework for 15-Minute City Using Satellite Imagery**
>
> Accepted at **ACM SIGSPATIAL 2025**

---

## 📌 Overview

**GeoTwin_MIL** is a multi-modal deep learning framework for evaluating **15-Minute City (15MC)** completeness using satellite and map imagery. The framework integrates **cross-modal contrastive learning** and **Multiple Instance Learning (MIL)** to predict multi-label urban functions at the regional level.

<p align="center">
  <img src="https://github.com/user-attachments/assets/xxxxx.png" width="800"/>
</p>

---

## 🔬 Method

### 1. Cross-Modal Contrastive Learning

Aligns representations between satellite and map modalities to learn shared semantic features across different image sources.

### 2. MIL Aggregation

Aggregates patch-level features to region-level predictions for multi-label classification, enabling comprehensive urban function assessment.

---

## 📁 Repository Structure

```
GeoTwin_MIL/
├── featureExtract/                    # Feature extraction scripts
│   └── ...
├── image_geotwin_feature_1024/        # Example pre-extracted features
├── dataset.py                         # Dataset loading and preprocessing
├── model.py                           # Model architecture (contrastive + MIL)
├── main.py                            # Training and evaluation pipeline
├── train.sh                           # Example training script
├── requirements.txt                   # Python dependencies
├── LICENSE                            # MIT License
└── README.md
```

---

## ⚙️ Installation

### Prerequisites

- Python >= 3.8
- PyTorch >= 2.0
- CUDA >= 11.7 (for GPU support)

### Setup

```bash
# Clone the repository
git clone https://github.com/20243439/GeoTwin_MIL.git
cd GeoTwin_MIL

# Create virtual environment (recommended)
conda create -n geotwin python=3.8 -y
conda activate geotwin

# Install dependencies
pip install -r requirements.txt
```

---

## 🚀 Usage

### Training

```bash
# Using the training script
bash train.sh

# Or run directly
python main.py --mode train \
    --satellite_dir <satellite_path> \
    --map_dir <map_path> \
    --epochs 100 \
    --batch_size 32
```

### Evaluation

```bash
python main.py --mode eval \
    --satellite_dir <satellite_path> \
    --map_dir <map_path> \
    --checkpoint <model_checkpoint_path>
```

### Feature Extraction

```bash
cd featureExtract
python extract_features.py \
    --input_dir <image_directory> \
    --output_dir <feature_output_directory>
```

---

## 📊 Dataset

The framework supports multi-modal urban imagery datasets containing:

- **Satellite Images**: High-resolution satellite imagery
- **Map Images**: Corresponding map tile images (e.g., OpenStreetMap)

Data should be organized as follows:

```
data/
├── satellite/
│   ├── region_001.png
│   ├── region_002.png
│   └── ...
├── map/
│   ├── region_001.png
│   ├── region_002.png
│   └── ...
└── labels.csv
```

---

## 📝 Citation

If you find this work useful, please cite our paper:

```bibtex
@inproceedings{geotwin2025,
  title={A Novel Evaluation Framework for 15-Minute City Using Satellite Imagery},
  author={Chanjae Song, Seongyeub Chu, Jongwoo Kim, and Mun Yong Yi},
  booktitle={Proceedings of the 33rd ACM SIGSPATIAL International Conference on Advances in Geographic Information Systems},
  year={2025}
}
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [ACM SIGSPATIAL](https://sigspatial.org/) for accepting our work.
- ThisworkwassupportedbytheNationalResearch Foundation of Korea(NRF) grant funded by the Korea government(MSIT)(No.RS-2022-NR068758).
---

## 📧 Contact

For questions or issues, please open an [issue](https://github.com/20243439/GeoTwin_MIL/issues) or contact the authors.
