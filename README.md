# CS3_FloodDetection
### A DS 4002 Case Study by Nehemiah Kim

---

## Overview

Can a machine look at a drone photo taken after a hurricane and automatically identify which areas are flooded? That is the question at the center of this case study. Using the FloodNet dataset — real UAV aerial imagery collected in the aftermath of Hurricane Harvey — you will train a deep learning semantic segmentation model to classify each pixel in an aerial image as either flooded or non-flooded.

This case study is targeted at second-year UVA students with some Python experience. You do not need prior experience with deep learning or computer vision. Everything you need to get started is in this repository.

---

## Hook and Rubric

The hook document and rubric for this case study are located in the root of this repository:

- [`CS3_Hook_Document.pdf`](./CS3_Hook_Document.pdf) — Read this first. It frames the problem and your mission.
- [`CS3_Rubric.pdf`](./CS3_Rubric.pdf) — Read this second. It describes exactly what you need to produce and how you will be graded.

Both documents should be referenced continuously throughout your work.

---

## Software and Platform

- **Language:** Python 3.12
- **Platform:** Google Colab (recommended) or any machine with GPU access
- **Packages required:**
  - `torch`
  - `torchvision`
  - `transformers`
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `Pillow`
  - `scikit-learn`
  - `tqdm`

Install all packages with:
```bash
pip install torch torchvision transformers numpy pandas matplotlib Pillow scikit-learn tqdm
```

---

## Repository Map

```
CS3_FloodDetection/
├── CS3_Hook_Document.pdf         # Hook document — read first
├── CS3_Rubric.pdf                # Rubric — your guide to success
├── README.md                     # This file
├── LICENSE.md                    # License terms
├── REFERENCES.md                 # All references in IEEE format
│
├── data/
│   └── data.md                   # Link to download the FloodNet dataset
│
├── scripts/            # All experiment templates — start here
│   ├── unet_exp1-4_flood_detection.ipynb # U-Net experiments 1–4
│   ├── unet_exp5-8_flood_detection.ipynb # U-Net experiments 5–8
│   ├── unet_exp9-11_flood_detection.ipynb# U-Net experiments 9–11
│   ├── unet_exp12_flood_detection.ipynb  # U-Net best configuration
│   ├── deeplabs_exp1-2_flood_detection.ipynb  # DeepLabV3+ experiments
│   ├── segformer_exp0_flood_detection.ipynb   # SegFormer baseline
│   └── segformer_exp1-4_flood_detection.ipynb # SegFormer experiments 1–4
│
├── output/
│
└── Materials/ #Blog posts that explain each architecture
```

---

## Data

The FloodNet dataset is too large to host on GitHub directly. Download it using the link in [`data/data.md`](./data/data.md).

Once downloaded, place the dataset so that your notebook can access the image and mask folders. The EDA notebook (`DS4002_EDA_Proj3.ipynb`) shows the expected folder structure.

**Dataset summary:**
- 64 labeled UAV aerial image-mask pairs (51 flooded, 13 non-flooded)
- Multi-class segmentation masks (10 classes)
- Images from Hurricane Harvey post-flood scenes
- Binary labels used for this case study: flooded (1) vs. non-flooded (0)

---

## How to Reproduce Results

1. **Download the dataset** using the link in `data/data.md` and place it in your working directory.
2. **Install the required packages** listed above.
3. **Run the notebooks** (`scripts/`) to explore the data and understand the class distribution before modeling.
4. **Run a model notebook** of your choice from the `scripts/` folder. Each notebook is self-contained and includes all preprocessing, training, and evaluation steps. Start with `unet_exp1-4_flood_detection.ipynb` if you are new to segmentation.
5. **Check your outputs** against the plots in the `output/` folder to verify your results match.

> **Note:** All notebooks were developed and tested on Google Colab with a T4 GPU. Training a single experiment takes approximately 5–15 minutes on Colab depending on the number of epochs.

---

## Reference Materials

Three reference articles are provided in the `Materials/` folder

All full citations are in [`REFERENCES.md`](./REFERENCES.md).

