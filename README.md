
# VITA: ViT Acceleration for Efficient 3D Human Mesh Recovery

## Overview

This repository contains the code and resources for the paper **"VITA: ViT Acceleration for Efficient 3D Human Mesh Recovery via Hardware-Algorithm Co-Design"**, presented at the 61st ACM/IEEE Design Automation Conference (DAC) 2024.

VITA introduces a hardware and algorithm co-design framework for accelerating Vision Transformer (ViT)-based Human Mesh Recovery (HMR) tasks. The framework achieves significant performance and energy efficiency improvements by leveraging a novel average pooling model and a tailored accelerator architecture.

## Features

- **Algorithmic Innovations**:
  - Introduction of an Average Pooling Block (APB) to replace conventional multi-head attention, optimized for data locality.
  - Dual-stream ViT architecture for balanced global and local feature extraction in 3D HMR tasks.

- **Hardware Architecture**:
  - Custom Processing Element (PE) architecture supporting efficient operations for pooling, normalization, and convolution.
  - Optimized dataflow and memory access patterns for reduced DRAM access and enhanced performance.

- **Performance**:
  - Achieves up to 5.05× and 69.12× speedups on average over the state-of-the-art GPUs and CPUs on HMR tasks.

## Repository Structure

- `/image_classification/`: Contains and insrtructions and files related to the Image Classification part of the project.
- `/human_mesh_recovery/`: Contains instructions and files related to the Human Mesh Recovery part of the project.
- `/HLS/`: Contains the FPGA implementation of the hardware design.(Compiled files are to be added soon)

## Getting Started

### Prerequisites

- Python 3.x
- PyTorch
- CUDA Toolkit (for GPU acceleration)
- Vitis-AI 3.0 (HLS)

### Experiments

To reproduce the results from the paper, run the following script:

```bash
python experiments/run_hmr.py --config configs/vita_hmr.yaml
```

## Software/Hardware Co-Design

<p align="center">
  <img src="./img/vita_algorithm.pdf">
  <img src="./img/vita_arch.pdf">  
</p>

## Visualizations

<p align="center">
  <img src="./img/vita_results">
</p>

## Citing

If our code helps your research, please consider citing the following paper:

    @inproceedings{tian2024vita,
        title={VITA: ViT Acceleration for Efficient 3D Human Mesh Recovery via Hardware-Algorithm Co-Design},
        author={Tian, Shilin and Szafranski, Chase and Zheng, Ce and Yao, Fan and Louri, Ahmed and Chen, Chen and Zheng, Hao},
        booktitle={61st ACM/IEEE Design Automation Conference (DAC)},
        year={2024},
        organization={ACM/IEEE}
}

## Contact

For For any questions or issues, please contact the owner of the Repo.