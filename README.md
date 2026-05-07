<p align="center">
  <img src="images/banner.png" width="100%">
</p>

<h1 align="center">🛌 Sleep Stage Classification using EOG-R and CNN-LSTM</h1>

<p align="center">
Automatic Sleep Stage Classification using EOG-R Signals and Deep Learning
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red?style=for-the-badge&logo=pytorch)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-SleepEDF-orange?style=for-the-badge)

</p>

---

# 📑 Table of Contents

- [📌 Overview](#-overview)
- [🧠 Problem Statement](#-problem-statement)
- [📂 Dataset](#-dataset)
- [⚙️ Signal Processing Pipeline](#️-signal-processing-pipeline)
- [🏗️ Model Architecture](#️-model-architecture)
- [🔄 Workflow](#-workflow)
- [📊 Experimental Setup](#-experimental-setup)
- [📈 Results](#-results)
- [🛠️ Technologies Used](#️-technologies-used)
- [🔬 Future Improvements](#-future-improvements)
- [📚 References](#-references)
- [👨‍💻 Author](#-author)

---

# 📌 Overview

This project presents a deep learning framework for automatic sleep stage classification using EOG-R signals extracted from the Sleep-EDF dataset.

The implemented pipeline includes:

- EOG signal extraction
- Bandpass filtering (0.3–35 Hz)
- Epoch segmentation (30 seconds)
- Subject-wise sequence generation
- CNN-LSTM deep learning architecture
- Sleep stage prediction

The model learns temporal sleep patterns directly from EOG signals and predicts the corresponding sleep stage.

---

# 🧠 Problem Statement

Manual sleep stage scoring is:

- Time-consuming
- Expert-dependent
- Computationally expensive

This project aims to automate the sleep staging process using deep learning techniques trained on EOG-R signals.

---

# 📂 Dataset

## Sleep-EDF Expanded Dataset

The dataset contains polysomnography sleep recordings with annotated sleep stages.

📌 Dataset Source:

https://sleepdata.org/datasets/mesa

---

# 😴 Sleep Stages

The model predicts the following sleep stages:

| Stage | Description |
|------|------|
| Wake | Awake state |
| Stage 1 | Light sleep |
| Stage 2 | Intermediate sleep |
| Stage 3/4 | Deep sleep |
| REM | Rapid Eye Movement |

---

# ⚙️ Signal Processing Pipeline

## 1️⃣ Signal Extraction

- Reading EDF files
- Extracting EOG-R channel

---

## 2️⃣ Filtering

Bandpass filtering applied using:

- Low cutoff: 0.3 Hz
- High cutoff: 35 Hz

---

## 3️⃣ Epoch Segmentation

- Signals segmented into 30-second epochs

---

## 4️⃣ Normalization

- Subject-wise normalization applied to EOG signals

---

## 5️⃣ Sequence Generation

- Sequential windows generated independently inside each subject

---

## 6️⃣ Subject-wise Splitting

Dataset split into:

- Training Set
- Validation Set
- Test Set

This prevents data leakage between subjects.

---

# 🏗️ Model Architecture

The proposed deep learning architecture combines:

- 1D CNN layers for local feature extraction
- LSTM layers for temporal sequence learning
- Fully connected layers for final classification

---

## 🧠 Architecture Diagram

<p align="center">
  <img src="images/architecture.png" width="80%">
</p>


---

# 🔄 Workflow

<p align="center">
  <img src="images/workflow.png" width="90%">
</p>

---

# 📊 Experimental Setup

| Parameter | Value |
|------|------|
| Framework | PyTorch |
| Optimizer | Adam |
| Loss Function | CrossEntropyLoss |
| Batch Size | 32 |
| Epochs | 25 |
| Scheduler | ReduceLROnPlateau |
| Device | CUDA GPU |

---

# 📈 Results

The CNN-LSTM model achieved strong performance on the Sleep-EDF dataset using EOG-R signals.

---

# 📊 Overall Performance

| Metric | Score |
|------|------|
| Accuracy | 80.0% |
| Macro F1-Score | 69.6% |
| Weighted F1-Score | 81.0% |
| Cohen’s Kappa | 0.715 |

---

# 📋 Classification Report

| Sleep Stage | Precision | Recall | F1-Score | Support |
|------|------|------|------|------|
| Wake | 1.00 | 0.84 | 0.91 | 475 |
| Stage 1 | 0.36 | 0.44 | 0.39 | 70 |
| Stage 2 | 0.85 | 0.79 | 0.82 | 373 |
| Stage 3/4 | 0.49 | 1.00 | 0.66 | 62 |
| REM | 0.66 | 0.74 | 0.70 | 149 |

---

# 📊 Training Performance

The following plots show the training and validation performance across epochs.

---

## Accuracy Curve

<p align="center">
  <img src="images/accuracy_curve.png" width="80%">
</p>

### Observations

- Training accuracy gradually increased to approximately **78%**
- Validation accuracy stabilized around **54–62%**
- Mild overfitting observed during training

---

## Loss Curve

<p align="center">
  <img src="images/loss_curve.png" width="80%">
</p>

### Observations

- Training loss consistently decreased
- Validation loss fluctuated due to class imbalance and subject variability
- The model maintained relatively stable convergence

---

# 📉 Confusion Matrix

## Raw Count Confusion Matrix

<p align="center">
  <img src="images/confusion_matrix_raw.png" width="85%">
</p>

---

## Normalized Confusion Matrix (Recall)

<p align="center">
  <img src="images/confusion_matrix_normalized.png" width="85%">
</p>

---

# 🔍 Results Analysis

## Strongly Classified Stages

### Wake
- Best overall classification performance
- Precision reached **1.00**
- F1-score reached **0.91**

---

### Stage 2
- Strong classification capability
- F1-score reached **0.82**

---

### REM
- Good REM detection performance
- Recall reached **0.74**

---

## Challenging Stages

### Stage 1
- Most difficult stage to classify
- F1-score reached **0.39**
- Frequently confused with:
  - REM
  - Stage 2

This behavior is expected due to transitional sleep characteristics.

---

## Stage 3/4 Performance

- Recall achieved **1.00**
- Deep sleep patterns successfully captured
- Precision remained moderate due to false positives

---

# 🧠 Key Findings

✔ CNN layers extracted local EOG signal patterns effectively  
✔ LSTM layers improved temporal learning  
✔ Subject-wise splitting reduced data leakage  
✔ Weighted loss improved minority class learning  
✔ The model generalized reasonably well despite class imbalance

---

# ⚠️ Limitations

- Stage 1 classification remains challenging
- Mild overfitting observed
- Validation performance fluctuated due to subject variability

---

# 🛠️ Technologies Used

| Tool | Purpose |
|------|------|
| Python | Programming Language |
| PyTorch | Deep Learning |
| NumPy | Numerical Processing |
| Pandas | Data Handling |
| Matplotlib | Visualization |
| Scikit-learn | Metrics |
| MNE | Signal Processing |
| SciPy | Filtering & Processing |

---

# 🌟 Key Features

✔ Subject-wise dataset splitting  
✔ CNN-LSTM architecture  
✔ EOG-R based sleep staging  
✔ CUDA acceleration  
✔ Visualization tools  
✔ Deep learning sequence modeling

---

# 🔬 Future Improvements

- Attention mechanisms
- Transformer architectures
- Data augmentation
- Focal loss
- Real-time sleep staging

---

# 📚 References

https://pubmed.ncbi.nlm.nih.gov/29860441/

https://www.medrxiv.org/content/10.1101/2024.08.02.24311417

https://pubmed.ncbi.nlm.nih.gov/25409106/

---

# 👨‍💻 Authors

## Osama Mohamed Abd El-Fattah Mohamed  

🎓 Biomedical Engineering Student   
📍 Helwan University

## Mohamed Hazem Mohamed Al-Halafawi

🎓 Biomedical Engineering Student   
📍 Helwan University

## Mohamed Osama Mohamed Abdul Moneim

🎓 Biomedical Engineering Student   
📍 Helwan University
