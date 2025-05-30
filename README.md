#  Cloud Detection using Sentinel-3 and Deep Learning
Video link： https://youtu.be/Pj4nvKZaPV0
#  Table of Contents

1. [About the Project](#about-the-project)  
   ├─ [Background](#background)  
   ├─ [The Sentinel-3 Satellite](#the-sentinel-3-satellite)  
   └─ [Environmental Cost Assessment](#environmental-cost-assessment)  
2. [Dataset](#dataset)   
3. [Acknowledgments](#acknowledgments)  
4. [References](#references)  

---

##  About the Project

This project is part of the final assignment for the AI4EO course at UCL, which applies artificial intelligence to Earth observation problems. It focuses on detecting cloud cover using Sentinel-3 satellite data and supervised learning models such as Convolutional Neural Networks (CNNs) and Random Forests (RFs).

By developing a classification system, we aim to generate accurate cloud masks from multispectral input imagery and evaluate model performance using confusion matrices and classification maps.

---

##  Background

Clouds have a significant impact on the planet's energy balance, climate, and weather. They serve as the primary temperature regulator and function as a blanket to absorb thermal energy or longwave radiation (Alblooshi et al., 2023). Cloud detection in Earth observation is crucial for atmospheric correction, climate analysis, and environmental monitoring. Clouds can obscure surface features and reduce the quality of optical satellite data. 

AI models have been increasingly applied to automate cloud detection, improving speed and accuracy. This project applies two supervised models—CNN and Random Forest—on Sentinel-3 imagery to classify each pixel as cloud or clear.

---

##  The Sentinel-3 Satellite

Sentinel-3 is an Earth observation satellite constellation launched by the European Space Agency. Each satellite carries two optical multispectral instruments: the Ocean and Land Colour Instrument (OLCI) and the Sea and Land Surface Temperature Radiometer (SLSTR). OLCI and SLSTR sensors produce images covering the visible and infrared spectrum that can be collocated in order to generate synergistic products (Fernandez-Moran et al., 2021).

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

![Image](https://github.com/user-attachments/assets/ac35a764-c6ae-402b-806a-1b5f86be6aae) 
*Figure 1. Sentinel-3 observation diagram showing orbit, instruments, and push-broom imaging.*

---

## Environmental Cost Assessment

This project involves training machine learning models—**Convolutional Neural Networks (CNNs)** and **Random Forests (RFs)**—for cloud detection using Sentinel-3 OLCI data. While the environmental footprint is relatively low compared to large-scale AI applications, it is still important to consider its impact.

The CNN model was trained on **Google Colab** using a GPU for 10 epochs, which consumed approximately **0.05 kg CO₂e**. This estimate is based on runtime duration, GPU use, and average carbon intensity of cloud infrastructure. In contrast, the RF model, trained on a CPU, required significantly less computational effort and thus incurred a negligible carbon cost.

Several strategies were employed to reduce the energy and environmental impact:

- 🔹 **Subset selection**: Only a portion of the Sentinel-3 dataset was used to limit processing requirements.
- 🔹 **Efficient training**: Training epochs were kept to a minimum while maintaining model performance.
- 🔹 **Shared cloud resources**: Google Colab’s free tier was used to leverage existing infrastructure instead of dedicated GPU use.
- 🔹 **Low I/O overhead**: Preprocessing and storage were done directly in Google Drive to reduce bandwidth usage.

Although computational demands were modest, this project demonstrates the importance of **sustainable machine learning practices**. Future improvements may include applying model compression, faster architectures, or energy-aware training methods.

> **Conclusion**: This project maintains a *low environmental impact* while achieving accurate and reproducible cloud detection, balancing scientific goals with sustainability considerations.



---

##  Dataset

The Sentinel-3 OLCI L1B data used in this project was downloaded from the [Copernicus Open Access Hub](https://dataspace.copernicus.eu/). Data was processed into 21-band reflectance arrays and cloud masks labeled with IRIS.

Using a small spatial chunk for model training and evaluation, preserving general cloud features while reducing compute load.

Raw dataset from Copernicus Sentinel-3: S3A_OL_1_EFR____20230621T105847_20230621T110147_20230622T120215_0180_100_151_1980_PS1_O_NT_003.SEN3

---

##  Acknowledgments

- totony4real https://github.com/totony4real/GEOL0069-AI4EO.git
- Copernicus Sentinel-3 data used under the European Space Agency (ESA) data policy.

---

##  References

- Alblooshi, M.A.M., Kalathingal, S.H., Mirza, S.B. and Ridouane, F.L., 2023. Assessment and Classification of Cloud Coverage Using K-Means Clustering Algorithm for the Sentinel-3 LST Data: A Case Study in the Fujairah Region. American Journal of Remote Sensing, 11(2), pp.32-35.    
- Fernandez-Moran, R., Gómez-Chova, L., Alonso, L., Mateo-García, G. and López-Puigdollers, D., 2021. Towards a novel approach for Sentinel-3 synergistic OLCI/SLSTR cloud and cloud shadow detection based on stereo cloud-top height estimation. ISPRS Journal of Photogrammetry and Remote Sensing, 181, pp.238-253.

---

