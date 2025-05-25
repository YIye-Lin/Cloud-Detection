# 🌍 Cloud Detection using Sentinel-3 and Deep Learning

# 📋 Table of Contents

1. [About the Project](#about-the-project)  
   ├─ [Background](#background)  
   ├─ [The Sentinel-3 Satellite](#the-sentinel-3-satellite)  
   └─ [Environmental Cost Assessment](#environmental-cost-assessment)  
2. [Dataset](#dataset)  
3. [Usage](#usage)  
4. [Acknowledgments](#acknowledgments)  
5. [References](#references)  

---

## 📌 About the Project

This project is part of the final assignment for the AI4EO course at UCL, which applies artificial intelligence to Earth observation problems. It focuses on detecting cloud cover using Sentinel-3 satellite data and supervised learning models such as Convolutional Neural Networks (CNNs) and Random Forests (RFs).

By developing a classification system, we aim to generate accurate cloud masks from multispectral input imagery and evaluate model performance using confusion matrices and classification maps.

---

## 📖 Background

Cloud detection in Earth observation is crucial for atmospheric correction, climate analysis, and environmental monitoring. Clouds can obscure surface features and reduce the quality of optical satellite data.

AI models have been increasingly applied to automate cloud detection, improving speed and accuracy. This project applies two supervised models—CNN and Random Forest—on Sentinel-3 imagery to classify each pixel as cloud or clear.

---

## 🛰️ The Sentinel-3 Satellite

Sentinel-3 is a European Earth observation satellite launched under the Copernicus Programme. It provides multi-instrument measurements from a polar orbit, covering both ocean and land surfaces. 

### Instruments:
- **OLCI**: Measures water and land color, vegetation, and cloud properties.
- **SLSTR**: Records sea and land surface temperatures.
- **SRAL**: Radar altimetry for sea level and ice thickness.
- **SYNERGY**: Combines OLCI + SLSTR data for improved land monitoring.

### Orbit & Imaging:
- **Altitude**: 814.5 km  
- **Inclination**: 98.65°  
- **Revisit time**: ~2 days at equator  
- **Swath width**: ~1270 km  
- **Spectral bands**: 21 (400–1020 nm)  
- **Spatial resolution**: 300 m  

![How Sentinel-3 Observes the Earth](Image.png)  
*Figure 2. Sentinel-3 observation diagram showing orbit, instruments, and push-broom imaging.*

---

## 🌱 Environmental Cost Assessment

This project uses CNN and RF models trained on Sentinel-3 data for cloud detection. Training the CNN model in Google Colab for 10 epochs consumes about **0.05 kg CO₂e** (based on GPU runtime and electricity carbon intensity). The RF model is less accurate but requires significantly less computational power.

### Measures taken to reduce environmental impact:
- Used only a subset of the dataset
- Limited CNN training to 10 epochs
- Leveraged Colab's free tier GPU with lower-carbon infrastructure
- Minimized data I/O and storage overhead using Google Drive

This project demonstrates the importance of balancing accuracy and environmental efficiency when selecting and deploying AI models.

---

## 📂 Dataset

The Sentinel-3 OLCI L1B data used in this project was downloaded from the [Copernicus Open Access Hub](https://dataspace.copernicus.eu/). Data was processed into 21-band reflectance arrays and cloud masks labeled with IRIS.

We used a small spatial chunk for model training and evaluation, preserving general cloud features while reducing compute load.

---

## ⚙️ Usage

1. Run `preprocess.ipynb` to prepare image and mask data  
2. Use `cnn_model.ipynb` or `rf_model.ipynb` to train and evaluate  
3. Output images and confusion matrices are saved automatically  

Each model outputs a binary classification map and evaluation metrics (accuracy, confusion matrix).

---

## 🙏 Acknowledgments

This project was developed for the AI4EO module at University College London (UCL), supervised by **Dr. Michel Tsamados** and **Weibin Chen**.

---

## 📚 References

- Copernicus Sentinel-3 Overview: https://sentinels.copernicus.eu/web/sentinel/missions/sentinel-3  
- ESA Sentinel Online - OLCI Instrument: https://sentinels.copernicus.eu/web/sentinel/technical-guides/sentinel-3-olci  
- Lacoste, P., et al. (2015). The Copernicus Sentinel-3 mission. *ESA Bulletin*, 163, 26–33.  
- Strub, M., et al. (2019). Cloud masking in multispectral satellite imagery using AI. *Remote Sensing of Environment*, 231, 111251.  

---

