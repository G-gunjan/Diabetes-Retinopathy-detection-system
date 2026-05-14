# 🩺 Diabetic Retinopathy Detection using Deep Learning (EfficientNetB3)

## 📌 Overview

Diabetic Retinopathy (DR) is a leading cause of blindness among diabetic patients. Early detection is crucial for effective treatment. This project presents an automated deep learning-based system that detects and classifies DR severity from retinal fundus images using **EfficientNetB3**.

The model leverages **transfer learning**, advanced **image preprocessing**, and **threshold optimization** to achieve high performance.

---

## 🎯 Objectives

* Automate detection of diabetic retinopathy from retinal images
* Classify DR into severity levels (0–4)
* Reduce dependency on manual diagnosis
* Assist ophthalmologists in early screening

---

## 🗂️ Dataset

* **APTOS 2019 Blindness Detection Dataset**
* Total images: ~5,000+
* Classes:

  * 0 → No DR
  * 1 → Mild
  * 2 → Moderate
  * 3 → Severe
  * 4 → Proliferative DR

---

## ⚙️ Methodology

### 🔹 1. Preprocessing

* Circular cropping (removes black borders)
* Ben Graham preprocessing
* CLAHE (Contrast Limited Adaptive Histogram Equalization)
* Image resizing (300×300)

### 🔹 2. Data Augmentation

* Rotation
* Zoom & shift
* Horizontal flipping
* Brightness variation

### 🔹 3. Model Architecture

* Pretrained **EfficientNetB3**
* Transfer Learning:

  * Freeze base layers
  * Fine-tune top layers
* Added layers:

  * Global Average Pooling
  * Batch Normalization
  * Dense + Dropout

### 🔹 4. Training

* Optimizer: Adam
* Loss Function: Mean Squared Error (MSE)
* Metrics: MAE, QWK
* Techniques:

  * Class Weights
  * Early Stopping
  * ReduceLROnPlateau
  * Model Checkpoint

### 🔹 5. Prediction Strategy

* Regression output (0–4 scale)
* Threshold optimization using **Nelder-Mead**
* Converted to:

  * Multi-class classification
  * Binary classification (DR / No DR)

---

## 📊 Results

* **Quadratic Weighted Kappa (QWK): ~0.78**
* Strong agreement between predicted and actual labels
* Significant improvement after threshold tuning

---

## 📈 Evaluation Metrics

* Quadratic Weighted Kappa (QWK)
* Mean Absolute Error (MAE)
* Confusion Matrix

---

## 🧠 Key Features

* Transfer Learning with EfficientNetB3
* Advanced preprocessing pipeline
* Handles class imbalance effectively
* Regression + classification hybrid approach

---
