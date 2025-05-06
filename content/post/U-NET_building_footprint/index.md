---
title: "Building Footprint Extraction with U-Net"
description: "Automatic extraction of building footprints from NAIP imagery using a ResNet-50 U-Net and OpenStreetMap labels"
slug: "building-footprint-extraction"
date: 2025-05-02 07:35:00+0000
image: "building_footprint.png"
categories:
  - "Deep Learning"
  - "Remote Sensing"
  - "Building Extraction"
tags:
  - "U-Net"
  - "NAIP"
  - "OpenStreetMap"
  - "Segmentation"
weight: 1
---

This post demonstrates how we trained a U-Net (with a ResNet-50 encoder pretrained on ImageNet) to extract building footprints from high-resolution NAIP imagery using OpenStreetMap polygons as labels.

## Data

- **Input imagery**: NAIP 1 m RGB tiles over Orange County, CA  
- **Labels**: Rasterized building footprints from OpenStreetMap  

## Model & Training

- **Architecture**: U-Net with a ResNet-50 encoder, skip-connections, and sigmoid output for binary masks  
- **Loss**: Dice loss to handle class imbalance  
- **Optimizer**: Adam (lr = 1e-4) with CosineAnnealingWarmRestarts  
- **Augmentations**: Random flips, 90° rotations, affine jitter  
- **Training**: 20 epochs on 512×512 patches (10 initial + 10 resumed)  

## Convergence Curves

![Loss vs Epoch / IoU vs Epoch](loss_plot.png)

- **Left**: Dice loss decreases on both training (blue) and validation (orange).  
- **Right**: Intersection-over-Union rises from ~0.52 up to ~0.74 over 20 epochs.

## Sample Predictions

### Sample 1
![Sample 1](ep20_1.png)

### Sample 2
![Sample 2](ep20_2.png)

### Sample 3
![Sample 3](ep20_3.png)

### Sample 4
![Sample 4](ep20_4.png)

## Vectorized Footprints

After cleaning and simplifying the predicted masks, we convert them to vector polygons and overlay on the original imagery:

![Cleaned Building Footprints Overlay](building_footprint.png)

## References

- NAIP imagery: https://www.fsa.usda.gov/programs-and-services/aerial-photography/imagery-programs/naip-imagery  
- OpenStreetMap building footprints: https://download.geofabrik.de/  
- Segmentation Models PyTorch: https://github.com/qubvel/segmentation_models.pytorch  