# Smart Dermatology: CNN-Based Skin Disease Detection Through an Android Application

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15-FF6F00?logo=tensorflow)](https://tensorflow.org)
[![DOI](https://img.shields.io/badge/DOI-10.XXXX/XXXXXX-blue)](https://doi.org/XXXX)

**Arooj Fatima¹, Rozi Bibi²**  
¹Department of Computer Science, Government Postgraduate College for Women Haripur, KPK, Pakistan  
²Lecturer, Department of Computer Science, Government Postgraduate College for Women Haripur, KPK, Pakistan  

📧 hk.farooj738@gmail.com | rozi.mushtaq999@gmail.com

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Dataset](#-dataset)
- [Models & Results](#-models--results)
- [Android Application](#-android-application)
- [Installation](#-installation)
- [Repository Structure](#-repository-structure)
- [Results & Discussion](#-results--discussion)
- [Statistical Analysis](#-statistical-analysis)
- [Citation](#-citation)
- [License](#-license)
- [Contact](#-contact)

---

## 🔬 Overview

This repository contains the official implementation of **"Smart Dermatology: CNN-Based Skin Disease Detection Through an Android Application"** [citation:2]. The project presents a deep learning-based system for classifying eight types of skin diseases, with a focus on **mobile deployment** for low-resource healthcare settings.

**Key Contributions:**
- ✅ Development of a lightweight **Custom CNN** (98.63% accuracy)
- ✅ Comparative evaluation with **EfficientNet-B0** (95%) and **Hybrid VGG16** (66%)
- ✅ **Balanced dataset** of 8,000 images across eight disease classes
- ✅ **TensorFlow Lite** conversion and **Android app deployment** for offline diagnosis
- ✅ **Zero false negatives** on test set – critical for medical applications

---

## 📊 Dataset

| Attribute | Details |
|-----------|---------|
| **Total Images** | 8,000 (1,000 per class after augmentation) |
| **Image Format** | JPG, PNG (dermoscopic and clinical photographs) |
| **Resolution** | 160×160 pixels (after preprocessing) |
| **Source** | Curated from Kaggle repositories and dermatological databases |

### Disease Classes:
1. Actinic Keratosis 5. Melanoma
2. Basal Cell Carcinoma 6. Melanocytic Nevi
3. Benign Keratosis 7. Squamous Cell Carcinoma
4. Dermatofibroma 8. Vascular Lesions


**Data Preprocessing** [citation:10]:
- Black border removal using OpenCV
- Resizing to 160×160 pixels
- Normalization (0-255 → 0-1)
- Data augmentation: rotations (40°), flips, shifts, zoom, brightness adjustment

---

## 🧠 Models & Results

### Model Performance Comparison [citation:5]

| Model | Training Accuracy | Testing Accuracy | Training Loss | Testing Loss | Key Insight |
|-------|------------------|------------------|---------------|--------------|-------------|
| **Custom CNN (Proposed)** | **98.63%** | **98.54%** | 0.063 | 0.062 | Best performer, lightweight, mobile-ready |
| EfficientNet-B0 | 95% | 95% | 0.032 | 0.040 | Strong transfer learning baseline |
| Hybrid VGG16 | 83% | 66% | 0.470 | 1.050 | Overfitting on this dataset |

### Custom CNN Architecture
- 8 Convolutional layers (filters: 64→512)
- 3 Dense layers
- 3 Dropout layers (0.5)
- 9 Batch Normalization layers
- 4 Pooling layers
- **Total parameters:** 58.6 million

---

## 📱 Android Application

A key contribution of this work is the **real-world deployment** of the Custom CNN model.

### Features:
- 📸 **Image capture/selection** from gallery
- ⚡ **Offline inference** (<2 seconds)
- 📊 **Confidence score** for each prediction
- 💊 **Basic treatment guidance**
- 🌐 **No internet required**

### Technical Implementation:
- Model converted to **TensorFlow Lite** (`.tflite`)
- Android app developed in **Java** (Android Studio)
- Three screens: Splash, Home, Prediction

### Testing Results:
| Metric | Value |
|--------|-------|
| Test Images | 800 (unseen) |
| Correct Classifications | 796 |
| **Accuracy** | **99.5%** |
| False Negatives | 0 |
| Precision | 99.2% |
| Recall | 99.0% |

---

## 🛠 Installation

### Prerequisites
- Python 3.10+
- CUDA-compatible GPU (optional, for training)
- Android Studio (for app development)

### Setup Instructions [citation:3][citation:7]

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/Smart-Dermatology-CNN-Android.git
cd Smart-Dermatology-CNN-Android

# 2. Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run training (optional)
python src/train.py

# 5. Run prediction
python src/predict.py --image path/to/image.jpg
