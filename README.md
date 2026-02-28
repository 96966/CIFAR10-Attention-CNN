[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.9+-ee4c2c.svg)](https://pytorch.org/)
[![Accuracy](https://img.shields.io/badge/Accuracy-92.47%25-brightgreen.svg)]()

# CIFAR-10 Image Classification with Channel Attention CNN

> A high-performance CNN architecture with Channel Attention for CIFAR-10 image classification. Achieves **92.47% accuracy** using advanced techniques like Mix Precision Training, Label Smoothing, and Model Ensemble. Implemented in PyTorch.

##  Project Overview
构建一个高性能的卷积神经网络（CNN），用于解决 CIFAR-10 图像分类问题。
本项目引入了**通道注意力机制 (Channel Attention)** 以增强特征提取能力，并结合了多种现代深度学习训练技巧，最终在测试集上达到了 **92.47%** 的准确率。

##  Key Highlights & Techniques
主要用到以下关键技术点：

*   **网络架构**:
    *   构建了深层卷积网络（3个卷积块，通道数递增：64->128->256）。
    *   嵌入 **Channel Attention Module**，通过全局平均池化和逐点卷积自适应地重新校准通道特征权重。
*   **数据增强 (Data Augmentation)**:
    *   几何变换：随机裁剪、水平翻转、旋转、平移。
    *   色彩变换：亮度、对比度、饱和度、色相抖动。
    *   正则化技术：**Random Erasing** (随机擦除)。
*   ** 训练策略**:
    *   **混合精度训练 (AMP)**: 加速训练并减少显存占用。
    *   **学习率调度**: Warmup (预热) + Cosine Annealing (余弦退火)，防止早期陷入局部最优并提升收敛效果。
    *   **正则化**: Label Smoothing (标签平滑), Dropout, Weight Decay, Gradient Clipping。
*   **模型集成 (Ensemble Learning)**:
    *   当单模型性能遇到瓶颈时，采用多模型概率平均策略，进一步提升鲁棒性和准确率。

## 📊 Performance Results
| Model Configuration | Test Accuracy | 
| :--- | :--- |
| **Final (All Strategies)** | **92.47%** |
<img width="150" height="144" alt="image" src="https://github.com/user-attachments/assets/76a1414c-25c7-4524-8603-e14de94869fa" />




