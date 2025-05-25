# 🌍 Cloud Detection using Sentinel-3 and Deep Learning

## 📑 Table of Contents
1. [About The Project](#about-the-project)  
   ├─ [Background](#background)  
   ├─ [The Sentinel-3 Satellite](#the-sentinel-3-satellite)  
   ├─ [Environmental Cost Assessment](#environmental-cost-assessment)  
2. [Dataset](#dataset)  
3. [Usage](#usage)  
4. [Acknowledgments](#acknowledgments)  
5. [References](#references)  

---

## 📌 About The Project

This project is part of the final assignment for the AI4EO course at UCL, which applies artificial intelligence to Earth observation problems. It focuses on detecting cloud cover using Sentinel-3 satellite data and supervised learning models such as Convolutional Neural Networks (CNNs) and Random Forests (RFs). 

By developing a classification system, we aim to generate accurate cloud masks from multispectral input imagery and evaluate model performance using confusion matrices and classification maps.

---

## 🌐 Background

Cloud detection is a fundamental preprocessing step in many satellite remote sensing applications, including land cover classification and climate monitoring. Sentinel-3 OLCI (Ocean and Land Colour Instrument) provides 21 spectral bands that are suitable for distinguishing clouds from other atmospheric or surface features.

Recent advances in machine learning and AI have enabled more accurate, scalable, and automatic cloud masking. This project compares traditional ensemble learning (RF) with deep learning (CNN) approaches to assess accuracy and spatial pattern fidelity using real Sentinel-3 imagery.

---

## 🛰️ The Sentinel-3 Satellite

Sentinel-3 is part of the Copernicus Programme by ESA and is equipped with the OLCI sensor, offering 21 bands of reflectance data at 300m resolution. This satellite monitors land and ocean colour, sea surface temperature, and atmospheric parameters.

The OLCI push-broom sensor captures Earth’s reflectance by sweeping across track with a wide field of view, enabling consistent multi-band observations.

![How Sentinel-3 Works](An_educational_infographic_titled_"How_Does_Sentin.png)

---

## 🌱 Environmental Cost Assessment

This research prioritizes environmental sustainability through:

- **Use of open-access data** (Copernicus Sentinel-3) instead of bespoke missions, minimizing emissions.
- **Minimal computational footprint** by running models on Google Colab, which utilizes shared cloud resources.
- **Efficient models**: Random Forest is lightweight; CNN training was limited to a small patch set with early stopping to reduce unnecessary computation.
- **Digital-only outputs**: all results are shared via GitHub, avoiding material waste.

Overall, the project demonstrates how AI and EO can be combined responsibly with minimal carbon overhead.

---

## 🗂 Dataset

We used OLCI Level-1B Top-of-Atmosphere reflectance data from Sentinel-3, extracted over cloud-covered regions using manual labels from IRIS.

- **Input:** 21-band reflectance arrays from `.npy` files  
- **Target:** Hand-labeled binary masks (Cloud = 1, Clear = 0)  
- **Preprocessing:** Patch extraction (3x3 spatial window × 21 bands)

Two chunk files were used, spanning ~4,000×1,000 pixels each. Data was balanced and split 90/10 for training/testing.

---

## ▶️ Usage

Please see the `notebook.ipynb` file for full code.  
Run in Google Colab or locally with Python 3.8+ and the following packages:

```bash
pip install numpy matplotlib tensorflow scikit-learn opencv-python netCDF4
