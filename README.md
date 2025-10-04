# IISC_test
This repo. contains the solutions of the questions which were asked to me by the AI&R Lab .



# Vision Transformer (ViT) for CIFAR-10

PyTorch implementation of Vision Transformer achieving maximum of **28.11%** test accuracy on CIFAR-10.

## 🚀 Run in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Harshil1010/IISC_test/blob/main/q1.ipynb)

**Quick setup:**
1. Click the Colab badge above
2. Select **Runtime → Change runtime type → T4 GPU**
3. Run all cells (**Runtime → Run all** or Ctrl+F9)
4. Training takes ~120 minutes


## 🚀 Quick Start

### Manual Setup
```python
# Run in Google Colab
!git clone https://github.com/your-username/vit-cifar10.git
%cd vit-cifar10
!python train.py
```

## 📊 Results

| Model | Accuracy | Epoch | Learning Rate |
|-------|----------|-------|---------------|
| **ViT (Ours)** | **28.11%** | **50** | **0.001** |

## 📊 Ablation Study Results

| Experiment | Best Value | Parameters |
|------------|------------|------------|
| **Patch Size** | 4×4 | 15.2M |
| **Depth/Width** | 8/512 | 15.2M |
| **Heads** | 8 | 15.2M |
| **Embed Dim** | 512 | 15.2M |
| **MLP Ratio** | 4.0 | 15.2M |
| **Dropout** | 0.1 | 15.2M |
| **Augmentation** | Full Pipeline | 15.2M |
| **Optimizer** | AdamW + Cosine | 15.2M |
| **Batch Size** | 128 | 15.2M |
| **Learning Rate** | 0.001 | 15.2M |
| **Weight Decay** | 0.05 | 15.2M |
| **Patches** | Non-overlapping | 15.2M |




# Text-Driven Image Segmentation with SAM 2

## Pipeline Description

This project implements an end-to-end pipeline for text-driven image segmentation using GroundingDINO and SAM 2:

### Pipeline Steps:

1. **Text Prompt Processing**: User provides a natural language description of the target object
2. **Object Detection**: GroundingDINO processes the image and text prompt to generate bounding boxes
3. **Mask Generation**: SAM 2 takes the bounding boxes as prompts to produce precise segmentation masks
4. **Visualization**: Results are displayed showing original image, detections, and final segmentation

### Key Components:
- **GroundingDINO**: Zero-shot object detection that links text concepts to visual regions
- **SAM 2** (Segment Anything Model 2): Foundation model for high-quality segmentation
- **Supervision**: Utilities for visualization and annotation

## Limitations

### Model Limitations:
1. **Text Understanding**: GroundingDINO may struggle with complex or abstract text descriptions
2. **Detection Accuracy**: Bounding box quality directly affects final segmentation results
3. **Multiple Instances**: Handling multiple objects of the same class can be challenging
4. **Occlusion**: Performance degrades with heavily occluded objects

### Technical Limitations:
1. **Computational Requirements**: Requires significant GPU memory for high-resolution images
2. **Inference Speed**: Not optimized for real-time applications
3. **Installation Complexity**: Multiple dependencies and model downloads required

### Domain Limitations:
1. **Fine Details**: May miss very small or thin structures
2. **Texture/Color Bias**: Performance varies with object textures and colors
3. **Boundary Precision**: Mask boundaries may not be pixel-perfect in complex scenes

## Video Extension (Bonus)

The pipeline includes experimental video object segmentation that:
- Uses first-frame text prompt for initialization
- Propagates masks across frames using SAM 2's tracking capabilities
- Maintains temporal consistency in object segmentation

**Note**: Video performance depends heavily on object consistency and motion patterns between frames.

## Setup
```bash
pip install -r requirements.txt
