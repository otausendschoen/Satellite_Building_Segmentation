# Satellite_Building_Segmentation

This project addresses the critical challenge of assessing disaster damage using satellite imagery, with a particular focus on detecting and classifying building damage. The approach combines deep learning, computer vision, and geospatial data analysis to enable accurate segmentation of flood-affected structures.

The implementation centers around a semantic segmentation model (UNet with a ResNet-34 encoder), trained on the xBD and ETCI-2021 datasets.

---

## Project Overview

Natural disasters such as floods frequently cause severe damage to buildings and infrastructure. This project supports emergency planning and humanitarian response efforts by:

- Detecting flood-affected regions from satellite images
- Segmenting buildings and assessing damage levels
- Producing interpretable visual outputs to guide field operations

---

## Repository Structure

| File / Folder                      | Description |
|-----------------------------------|-------------|
| `Part_I_segmentation.ipynb`       | Performs semantic segmentation using a UNet-based model with ResNet34 backbone. Predicts damage masks from satellite images and evaluates results using metrics like IoU and F1-score. |
| `Part_II_data-preparation.ipynb`  | Prepares the dataset, including downloading, preprocessing, tiling of satellite images, and generating label masks. Also includes normalization and formatting suitable for model input. |
| `Part_III_model-training.ipynb`   | Trains the UNet segmentation model on the processed dataset. Defines architecture, loss functions, augmentation strategy, training loops, and evaluation pipeline. Also includes a full design document outlining project context, goals, assumptions, risks, and metrics. |
| `data/`                           | Placeholder for input satellite images, label masks, and preprocessed tiles. |
| `README.md`                       | Project documentation (this file). |

---

## Methodology

- **Model**: UNet with ResNet34 encoder (pretrained on ImageNet)
- **Loss Function**: Weighted BCE + Dice Loss to address class imbalance
- **Evaluation**: Intersection over Union (IoU), Precision, Recall, F1-score
- **Data**: Sentinel-1 imagery (VV + VH bands) and xBD building annotations
- **Augmentations**: Random rotation, flipping, scaling using Albumentations
- **Deployment**: Containerized with Docker and deployed to AWS EC2 instance

---
