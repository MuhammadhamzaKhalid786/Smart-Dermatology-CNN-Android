# Smart Dermatology: CNN-Based Skin Disease Detection Through an Android Application

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)]
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)]
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15-orange.svg)]

---

## 🔬 Overview

This repository presents a deep learning-based system for **skin disease classification** using a **Custom CNN model**, integrated into an **Android application** for real-time and offline diagnosis.

The system classifies **8 types of skin diseases** and is designed for **mobile deployment in low-resource environments**.

---

## 🎯 Key Contributions

- ✅ Custom CNN with **98.5% test accuracy**
- ✅ Comparison with EfficientNet-B0 and VGG16
- ✅ Dataset of **8000 balanced images**
- ✅ TensorFlow Lite model for mobile deployment
- ✅ Android application (offline prediction)
- ✅ Fast inference (<2 seconds)

---

## 📊 Dataset

**Dataset is not included in this repository due to large size.**

👉 Download Dataset: https://drive.google.com/drive/folders/1xHJxdy4-_EwwGxK8Y0Kj0FrrEDZV6K_I

| Attribute | Details |
|----------|--------|
| Total Images | 8000 |
| Classes | 8 |
| Image Size | 160×160 |
| Source | Kaggle |

### Classes:
- Actinic Keratosis  
- Basal Cell Carcinoma  
- Benign Keratosis  
- Dermatofibroma  
- Melanoma  
- Melanocytic Nevi  
- Squamous Cell Carcinoma  
- Vascular Lesions  

---

## 🧠 Models & Results

| Model | Accuracy |
|------|---------|
| **Custom CNN** | **98.5%** |
| EfficientNet-B0 | 95% |
| VGG16 (Hybrid) | 66% |

---

## 📱 Android Application

**App files are not included due to large size.**

👉 Download Android App: 
https://drive.google.com/drive/folders/1xHJxdy4-_EwwGxK8Y0Kj0FrrEDZV6K_I
### Features:
- Image capture / gallery selection  
- Offline prediction  
- Confidence score  
- Simple UI  

### Tech Stack:
- Java (Android Studio)  
- TensorFlow Lite  
---

## 🛠 Installation

```bash
git clone https://github.com/YOUR_USERNAME/Smart-Dermatology-CNN-Android.git
cd Smart-Dermatology-CNN-Android
pip install -r requirements.txt
python src/train.py
