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
| **Augmentation** | Full Pipeline | 15.2M |
| **Optimizer** | AdamW + Cosine | 15.2M |
| **Patches** | Non-overlapping | 15.2M |
