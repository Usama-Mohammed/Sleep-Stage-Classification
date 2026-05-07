<p align="center">
  <img src="images/banner.png" width="100%">
</p>

<h1 align="center">🛌 EOG Sleep Stage Classification using Deep Learning</h1>

<p align="center">
Automatic Sleep Stage Classification using EOG Signals and Deep Learning Architectures
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red?style=for-the-badge&logo=pytorch)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-SleepEDF-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-Research-green?style=for-the-badge)
![GPU](https://img.shields.io/badge/GPU-CUDA-enabled-purple?style=for-the-badge)

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
- [📉 Confusion Matrix](#-confusion-matrix)
- [📋 Evaluation Metrics](#-evaluation-metrics)
- [🎬 Demo](#-demo)
- [🛠️ Technologies Used](#️-technologies-used)
- [📁 Project Structure](#-project-structure)
- [🚀 Installation](#-installation)
- [▶️ How to Run](#️-how-to-run)
- [🔬 Future Improvements](#-future-improvements)
- [👨‍💻 Author](#-author)
- [📜 License](#-license)

---

# 📌 Overview

Sleep stage classification plays a crucial role in sleep disorder diagnosis and healthcare monitoring.

This project presents a deep learning framework for automatic sleep stage classification using Electrooculography (EOG) signals extracted from polysomnography recordings.

The proposed pipeline combines:

- Signal preprocessing
- Spectrogram generation
- Sequence learning
- Deep neural networks (CNN + LSTM)

to accurately classify sleep stages.

---

# 🧠 Problem Statement

Manual sleep stage scoring is:

- Time-consuming
- Expensive
- Expert-dependent

This project aims to automate the sleep staging process using deep learning techniques trained on EOG signals.

---

# 📂 Dataset

## Sleep-EDF Expanded Dataset

The dataset contains physiological sleep recordings including:

- EOG
- EEG
- EMG
- Sleep stage annotations

📌 Dataset Source:

https://physionet.org/content/sleep-edfx/

---

# 😴 Sleep Stages

The model predicts:

| Stage | Description |
|------|------|
| Wake | Awake state |
| N1 | Light sleep |
| N2 | Intermediate sleep |
| N3 | Deep sleep |
| REM | Rapid Eye Movement |

---

# ⚙️ Signal Processing Pipeline

## 1️⃣ Raw Signal Extraction

- Reading EDF files
- Extracting EOG channels

## 2️⃣ Preprocessing

- Signal normalization
- Noise reduction
- Epoch segmentation

## 3️⃣ Feature Representation

- Raw signal representation
- Spectrogram generation
- Sequential window creation

## 4️⃣ Subject-wise Splitting

The dataset is split subject-wise into:

- Training Set
- Validation Set
- Test Set

This prevents data leakage between subjects.

---

# 🏗️ Model Architecture

The proposed architecture combines CNN and LSTM networks.

## Architecture Components

- 1D CNN Layers
- Batch Normalization
- MaxPooling
- Dropout
- Bidirectional LSTM
- Fully Connected Layers

---

## 🧠 Architecture Diagram

<p align="center">
  <img src="images/architecture.png" width="85%">
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
| Epochs | 30 |
| Scheduler | ReduceLROnPlateau |
| Device | CUDA GPU |

---

# 📈 Results

## Training Accuracy

<p align="center">
  <img src="images/accuracy.png" width="75%">
</p>

---

## Training Loss

<p align="center">
  <img src="images/loss.png" width="75%">
</p>

---

# 📉 Confusion Matrix

<p align="center">
  <img src="images/confusion_matrix.png" width="70%">
</p>

---

# 📋 Evaluation Metrics

| Metric | Score |
|------|------|
| Accuracy | 82.4% |
| Precision | 81.7% |
| Recall | 80.9% |
| F1-Score | 81.1% |

---

# 📊 Class Distribution

<p align="center">
  <img src="images/class_distribution.png" width="70%">
</p>

---

# 🎬 Demo

<p align="center">
  <img src="images/demo.gif" width="90%">
</p>

---

# 🔬 Discussion

## Challenges

- Class imbalance
- Similarity between N1 and REM stages
- Overfitting risk
- Subject variability

## Solutions Applied

- Weighted loss function
- Dropout regularization
- Subject-wise split
- Learning rate scheduling

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
| MNE | EEG/EOG Processing |
| SciPy | Signal Processing |

---

# 📁 Project Structure

```text
EOG-Sleep-Stage-Classification/
│
├── data/
├── notebooks/
├── models/
├── images/
│   ├── banner.png
│   ├── architecture.png
│   ├── workflow.png
│   ├── accuracy.png
│   ├── loss.png
│   ├── confusion_matrix.png
│   ├── class_distribution.png
│   └── demo.gif
│
├── README.md
├── requirements.txt
└── train.py
```

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/your-username/EOG-Sleep-Stage-Classification.git
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ How to Run

## Run Training

```bash
python train.py
```

---

## Run Notebook

```bash
jupyter notebook
```

---

# 📦 Requirements

```txt
torch
numpy
pandas
matplotlib
scikit-learn
mne
scipy
tqdm
```

---

# 🌟 Key Features

✔ Subject-wise dataset splitting  
✔ Deep CNN + LSTM architecture  
✔ Spectrogram support  
✔ CUDA acceleration  
✔ Visualization tools  
✔ Automatic sleep stage prediction  
✔ Research-oriented implementation

---

# 🔬 Future Improvements

- Transformer-based architectures
- Attention mechanisms
- Real-time sleep staging
- Mobile deployment
- Multi-modal PSG integration

---

# 📚 References

1. Sleep-EDF Dataset  
https://physionet.org/content/sleep-edfx/

2. PyTorch Documentation  
https://pytorch.org/

3. MNE Documentation  
https://mne.tools/

---

# 👨‍💻 Author

## Osama Mohamed Abd El-Fattah Mohamed

🎓 Biomedical Engineering Student  
🧠 Machine Learning & Deep Learning Enthusiast  
📍 Helwan University

---

# ⭐ Support

If you found this project useful:

- Give the repository a ⭐
- Share it with others
- Fork the project

---

# 📜 License

This project is intended for educational and research purposes.
