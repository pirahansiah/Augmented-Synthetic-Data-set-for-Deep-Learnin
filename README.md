# Augmented Synthetic Data-set for Deep Learning

[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?logo=opencv&logoColor=white)](https://opencv.org/)
[![C++](https://img.shields.io/badge/C%2B%2B-11-blue)](https://isocpp.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Advanced data augmentation pipeline for generating synthetic training datasets using OpenCV C++ transformations.

## Overview

This toolkit generates large-scale augmented datasets by combining multiple transformation techniques — rotation, scaling, contrast/brightness adjustment, bilateral filtering, blur, and morphological operations — to create diverse training data for deep learning models.

## Augmentation Techniques

| Technique | Description | Deep Learning Impact |
|-----------|-------------|---------------------|
| **Rotation** | Full 360° rotation with affine transforms | Improves rotational invariance |
| **Scaling** | Random resize with aspect preservation | Multi-scale robustness |
| **Contrast/Brightness** | Pixel-level intensity adjustment | Lighting condition generalization |
| **Bilateral Filtering** | Edge-preserving smoothing | Reduces noise while preserving structure |
| **Blur** | Gaussian/box blur with varying kernels | Simulates out-of-focus conditions |
| **Morphological** | Dilate/Erode operations | Shape variation in training data |
| **Affine Warp** | Perspective-like geometric transforms | Viewpoint augmentation |
| **AddWeighted** | Alpha-blended overlay combinations | Exposure variation simulation |

## Modern Alternatives (2025-2026)

For new projects, consider these state-of-the-art augmentation approaches:

- **[Albumentations](https://github.com/albumentations-team/albumentations)** — Fast, flexible image augmentation library with 50+ transforms, used in most modern CV pipelines
- **[Torchvision Transforms v2](https://pytorch.org/vision/stable/transforms.html)** — PyTorch-native transforms with GPU acceleration (2024+)
- **[Kornia](https://github.com/kornia/kornia)** — Differentiable computer vision library for GPU-accelerated augmentations
- **[imgaug](https://github.com/aleju/imgaug)** — Extensive augmentation library with sequence-based pipelines
- **[NVIDIA DALI](https://github.com/NVIDIA/DALI)** — GPU-accelerated data loading and augmentation for large-scale training
- **[Albucore](https://github.com/albumentations-team/albucore)** — High-performance augmentation backend written in Rust/Cython
- **Generative Augmentation** — Use diffusion models (Stable Diffusion XL, FLUX) to generate synthetic training samples
- **Neural Augmentation** — Learned augmentation policies via AutoAugment, RandAugment, or TrivialAugment

## Build & Run

### Prerequisites

- OpenCV 4.x+
- C++11 or later compiler (GCC, Clang, MSVC)

### Compilation

```bash
g++ -o augment augmentation.cpp $(pkg-config --cflags --libs opencv4)
```

### Usage

```bash
# Create a text file with image folder paths (one per line)
./augment folder_paths.txt
```

Each input folder generates up to 36 (or 360) augmented variants per image with incremental parameter changes.

## Applications

- **Object Detection** — Expand training sets for YOLO, DETR, and RT-DETR models
- **Image Classification** — Improve generalization for ResNet, EfficientNet, ConvNeXt
- **Semantic Segmentation** — Generate diverse pixel-level annotations
- **Edge AI / IoT** — Augment limited on-device datasets for deployment on Jetson, Raspberry Pi

## References

- Shorten, C. & Khoshgoftaar, T.M. (2019). A survey on Image Data Augmentation for Deep Learning. *Journal of Big Data*, 6(1).
- Cubuk, E.D. et al. (2020). AutoAugment: Learning Augmentation Strategies from Data. *CVPR*.
- Lopes, R.G. et al. (2018). A Simple Method for Data Augmentation in Deep Learning. *NeurIPS Workshop*.

## Author

**Dr. Farshid Pirahansiah** — [LinkedIn](https://linkedin.com/in/pirahansiah) | [GitHub](https://github.com/pirahansiah)
