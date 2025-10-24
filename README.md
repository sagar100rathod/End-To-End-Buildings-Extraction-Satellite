# 🏙️ End-to-End Building Footprint Extraction from Satellite Imagery

This repository provides a **complete, reproducible workflow** for extracting **building footprints** from high-resolution **satellite imagery**.
It covers every stage — from **dataset preparation (COCO → masks)** to **training DeepLabV3+ (ResNet101)** for **semantic segmentation**, leveraging **weighted boundary masks** for improved separation of adjacent buildings.

## Project Overview

* **Goal:** Automatically segment and extract building footprints from satellite images.
* **Dataset:** [Mapping Challenge (AIcrowd)](https://www.aicrowd.com/challenges/mapping-challenge-old)
* **Model:** [DeepLabV3+](https://arxiv.org/abs/2104.01263) with **ResNet101** backbone.
* **Framework:** PyTorch
* **Key Technique:** Weighted boundary mask augmentation for better delineation of touching buildings.

## Notebook Covers entire Workflow

1. **Data Acquisition**
   * Download the dataset from [AIcrowd Mapping Challenge](https://www.aicrowd.com/challenges/mapping-challenge-old).
   * Extract the dataset into your working directory.
2. **Data Preparation**
   * Convert **COCO-style annotations** into **binary mask images** for training.
   * Each image mask represents building footprints.
3. **Model Training**
   * Train **DeepLabV3+ (ResNet101)** for building segmentation.
   * Weighted boundary loss improves model accuracy on dense urban areas.
4. **Inference**
   * Apply the trained model on unseen satellite tiles.
   * Generate predicted masks of building footprints.

## Model Details

* **Architecture:** DeepLabV3+
* **Encoder Backbone:** ResNet101 (pretrained on ImageNet)
* **Loss Function:** Dice Loss + Weighted Boundary Mask Loss
* **Optimizer:** Adam / SGD (configurable)
* **Evaluation Metrics:** Accuracy, Precision, Recall, F1 Score

> Weighted boundary mask notably improves boundary precision for densely packed urban regions.

## References

* Aatif Jiwani, et al., **“A Semantic Segmentation Network for Urban-Scale Building Footprint Extraction Using RGB Satellite Imagery,”** arXiv:2104.01263
* [AIcrowd Mapping Challenge Dataset](https://www.aicrowd.com/challenges/mapping-challenge-old)
