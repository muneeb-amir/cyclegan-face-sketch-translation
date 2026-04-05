# CycleGAN: Face ↔ Sketch Translation

This repository implements a CycleGAN model for unpaired image-to-image translation between human face images and sketches. The entire training and inference pipeline is contained in a single script/notebook for simplicity and reproducibility.

---

## Overview

CycleGAN enables translation between two visual domains without requiring paired data. This implementation learns two mappings:

* Face → Sketch
* Sketch → Face

The model leverages adversarial training along with cycle-consistency constraints to preserve structural integrity across domains.

---

## Features

* End-to-end CycleGAN implementation in a single file
* Bidirectional translation (Face ↔ Sketch)
* Mixed precision training (AMP)
* Checkpoint saving for recovery and reuse
* Compatible with GPU training (Colab / Kaggle)

---

## Dataset

* **Person Face Sketches Dataset (Kaggle)**

### Preprocessing

* Image resizing and normalization
* Random cropping and flipping
* Domain-wise separation (Face / Sketch)

---

## Model Architecture

* **Generators**

  * G_AB: Face → Sketch
  * G_BA: Sketch → Face

* **Discriminators**

  * D_A: Face domain
  * D_B: Sketch domain

* **Loss Functions**

  * Adversarial Loss (LSGAN)
  * Cycle Consistency Loss
  * Identity Loss

---

## Training Configuration

* Framework: PyTorch
* Batch Size: 8
* Epochs: 10
* Mixed Precision: Enabled
* Hardware: GPU (T4 recommended)

Training stabilizes after early epochs with noticeable improvements in visual quality across both translation directions.

---

## Usage

### Run Training

If using Python script:

```bash
python train.py
```

If using notebook:

* Open `train.ipynb`
* Run all cells sequentially

---

## Results

* Stable adversarial training without collapse
* Consistent bidirectional translation
* Progressive quality improvement over epochs

---

## Key Concepts

* Generative Adversarial Networks (GANs)
* Cycle Consistency
* Unpaired Image Translation
* Domain Adaptation

---

## Setup

```bash
git clone <repo-url>
cd cyclegan-face-sketch-translation
pip install -r requirements.txt
```

---

## Notes

* Designed for clarity and reproducibility in a single-file workflow
* Suitable for experimentation and extension into modular pipelines

## Results
DURING TRAINING:

<img width="733" height="540" alt="image" src="https://github.com/user-attachments/assets/593172eb-1856-49f5-a8c7-c8e2cfe1792b" />

AFTER TRAINING:

<img width="378" height="379" alt="Screenshot 2025-11-20 150024" src="https://github.com/user-attachments/assets/057b61e7-4da9-4253-b23d-271467c246fa" />


