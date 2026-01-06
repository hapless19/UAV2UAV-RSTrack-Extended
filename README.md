# Rotated Box-Aware Segmentation for Fixed-Wing UAVs: A PCA-Enhanced SiamMask Approach

<p align="center">
  <img src="https://img.shields.io/badge/Conference-PRCV--2025-blue" alt="PRCV 2025">
  <img src="https://img.shields.io/badge/Task-UAV--Tracking-green" alt="Task">
  <img src="https://img.shields.io/badge/Task-Segmentation-red" alt="Segmentation">
</p>

---

## 📌 Abstract
本文针对复杂空中场景下**固定翼无人机（Fixed-Wing UAVs）**的分割与旋转框生成挑战，提出了 **PCA-SiamMask** 模型。由于固定翼无人机在长航时任务中具有重要地位，其姿态估计对航向判断至关重要。我们通过半自动标注方法增强了 **UAV2UAV** 数据集，提供了像素级掩码（Mask）和旋转框（Rotated Box）标注。

---

## 📂 Table of Contents
- [Introduction](#-introduction)
- [Methodology](#-methodology)
- [Dataset Download](#-dataset-download)
- [Experimental Results](#-experimental-results)
- [Citation](#-citation)

---

## 🚀 Introduction
现有的无人机追踪数据集往往缺乏**空中视角（Air-to-Air）**以及关键的**旋转标注（Rotation Annotations）**。而在空对空场景下，无人机的加速度和方向信息（Orientation）是理解飞行状态的关键。

我们的工作主要贡献包括：
- **数据集增强**：为 UAV2UAV 数据集提供了高质量的像素级 Mask 和旋转框标注。
- **角度优化策略**：结合椭圆拟合与主成分分析（PCA）优化旋转角估计。
- **性能提升**：在区域相似度上提升了 2.7%，旋转框 AUC 提升了 1.8%。

---

## 🛠 Methodology
<p align="center">
  <img src="./assets/framework.png" width="90%" alt="PCA-SiamMask Framework">
  <br>
  <em>图1：PCA-SiamMask 整体架构图。我们利用 PCA 策略精炼了目标姿态估计。</em>
</p>



---

## 📥 Dataset Download
我们提供了针对固定翼无人机优化后的数据集扩展包：
- **UAV2UAV-Extended (Masks & Rotated Boxes)**: [百度网盘](https://pan.baidu.com/s/1UZTbiseJ6IPR1oK5wJYMyg) (提取码: `75tu`)
- **基础数据集**: [UAV2UAV](https://github.com/hapless19/UAV2UAV-dataset) | [RSTrack](https://github.com/TonikLeung/RSTrack)

---

## 📊 Experimental Results
### 定量对比 (on UAV2UAV Dataset)

| Tracker | Region Similarity ($\mathcal{J}_M \uparrow$) | Overlap ($\mathcal{J}_O \uparrow$) | Decay ($\mathcal{J}_D \downarrow$) |
| :--- | :---: | :---: | :---: |
| SiamMask [2] | 45.1 | 55.9 | 72.4 |
| **Ours (FW-Optimized)** | **47.8** | **59.3** | **66.9** |

### 旋转框性能 (AUC Score)
| Algorithm | OSTrack | SiamMask | **PCA-SiamMask (Ours)** |
| :--- | :---: | :---: | :---: |
| **AUC** | 0.458 | 0.382 | **0.424** |

---

## 📜 Citation
如果您在研究中使用了本数据集或代码，请引用我们的 PRCV 2025 论文：

```bibtex
@inproceedings{li2025rotated,
  title={Rotated Box-Aware Segmentation for Fixed-Wing UAVs: A PCA-Enhanced SiamMask Approach},
  author={Li, Chengwei and Bai, Yunsong and Long, Ruhai and Wang, Yong and Wu, Shunan and Wu, Zhigang},
  booktitle={Proceedings of the 8th Chinese Conference on Pattern Recognition and Computer Vision (PRCV)},
  year={2025}
}
