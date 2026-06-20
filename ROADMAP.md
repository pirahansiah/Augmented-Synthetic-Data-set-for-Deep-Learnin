# Roadmap — Augmented Synthetic Data-set for Deep Learning

## 12-Month Vision

Evolve the toolkit from a legacy C++11 OpenCV augmentation script into the industry-standard open-source pipeline for synthetic training data generation — supporting traditional, neural, and generative augmentation across all major hardware platforms.

---

## Quarterly Milestones

### Q1 (Months 1-3): Foundation & Migration
- [ ] Migrate C++ source to C++26 with modern CMake build system
- [ ] Create Python 3.14 bindings with type-annotated augmentation API
- [ ] Implement conda `py314` environment with OpenCV v5 and CUDA 13
- [ ] Port 8 legacy transforms to composable pipeline architecture
- [ ] Add unit tests (≥90% coverage) and CI/CD for Linux/macOS/Windows
- [ ] Benchmark baseline on M5 Max and Intel Ultra 9 Gen 2

### Q2 (Months 4-6): GPU Acceleration & Edge Optimization
- [ ] Implement CUDA 13 kernels for batched rotation, bilateral filter, affine warp
- [ ] NVIDIA Spark (128GB VRAM) optimization: Tensor Core utilization for transform batching
- [ ] Apple M5 Max Neural Engine dispatch for on-device augmentation
- [ ] Raspberry Pi 5 ARM64 lightweight routines with NEON SIMD
- [ ] Intel Ultra 9 Gen 2 AVX-512 vectorized pixel operations
- [ ] Achieve ≥10x throughput improvement over legacy baseline

### Q3 (Months 7-9): Neural & Generative Augmentation
- [ ] Integrate TrivialAugment / RandAugment learned augmentation policies
- [ ] Add Stable Diffusion XL / FLUX generative augmentation module
- [ ] Implement augmentation quality metrics (FID, LPIPS, SSIM)
- [ ] Support annotation propagation (bounding boxes, segmentation masks)
- [ ] Multi-GPU distributed augmentation for large-scale datasets
- [ ] Publish benchmarking suite with reproducible results

### Q4 (Months 10-12): Production & Ecosystem
- [ ] Docker containerization for cloud deployment (AWS, GCP, Azure)
- [ ] Web-based augmentation preview and parameter tuning UI
- [ ] YOLO/RT-DETR/EfficientNet integration examples and tutorials
- [ ] Academic paper submission on augmentation pipeline architecture
- [ ] Community contribution guidelines and plugin system
- [ ] v1.0 stable release with full documentation

---

## Technical Debt

| Item | Priority | Effort | Impact |
|---|---|---|---|
| Source file has `.txt` extension (`FarshidPirahanSiah_advanceDataAugmentation.txt`) — rename to `.cpp` | High | Low | Correctness |
| Replace `rand()` / `srand()` with `<random>` C++26 facilities | High | Low | Reproducibility |
| Eliminate raw `char*` pointers — use `std::string` throughout | Medium | Low | Safety |
| Remove duplicate includes (`<iostream>` included twice) | Low | Low | Cleanliness |
| Replace `using namespace std;` with explicit qualification | Medium | Medium | Namespace hygiene |
| Add RAII file handling for `std::ifstream` | Medium | Low | Exception safety |
| Fix `modify1()` — generates 360 variants but is never called | High | Low | Dead code removal |
| Add input validation for `argv[1]` and file path parsing | High | Medium | Robustness |
| Replace magic numbers (36, 360, 70, 15, etc.) with named constants | Medium | Low | Maintainability |
| Add multi-threaded processing for folder-level parallelism | High | Medium | Performance |

---

## Future Features

### Near-Term (3-6 months)
- **Diffusion-based augmentation**: Generate entirely new training samples using FLUX/SDXL with prompt-guided diversity control
- **AutoAugment / RandAugment integration**: Learned augmentation policies that optimize for target model performance
- **Annotation propagation**: Automatically transform bounding boxes, segmentation masks, and keypoints alongside images
- **Augmentation validation suite**: Statistical tests to verify augmented data distribution quality

### Mid-Term (6-9 months)
- **Multi-modal augmentation**: Synchronized transforms for paired image-depth, image-text, or multi-camera data
- **Hardware-aware augmentation**: Automatically select optimal backend (CPU/GPU/Neural Engine) based on input size and available hardware
- **Augmentation caching**: Deduplicate and cache frequently-used augmentation chains to eliminate redundant computation
- **Web UI**: Browser-based interface for configuring augmentation pipelines with live preview

### Long-Term (9-12 months)
- **Plugin system**: Community-contributed augmentation transforms with hot-reload
- **Federated augmentation**: Generate synthetic data across distributed nodes without centralizing raw data
- **Continuous augmentation**: Real-time augmentation during training (in-loop augmentation) for improved convergence
- **Benchmarking platform**: Public leaderboard for augmentation pipeline performance across hardware configurations
