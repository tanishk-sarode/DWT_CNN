# CNN Model for Heart Disease Classification using PCG Signals

## Introduction
Cardiovascular disease (CVD) is the leading cause of death worldwide, accounting for more than 17 million fatalities annually. Among various types of CVDs, heart valve diseases (HVDs) are of particular concern due to their increasing prevalence and high mortality rates. 

This project focuses on classifying different types of **HVDs** using **Phonocardiogram (PCG) signals** and a **1D Convolutional Neural Network (CNN)**. The dataset includes PCG recordings categorized into five classes:

- **Aortic Stenosis (AS)**
- **Mitral Stenosis (MS)**
- **Mitral Regurgitation (MR)**
- **Mitral Valve Prolapse (MVP)**
- **Normal (N)**

## Dataset and Preprocessing
- The dataset consists of **1000 PCG recordings** (200 per class) sampled at **4000 Hz**.
- Each signal is **zero-padded** to ensure uniform length.
- **Discrete Wavelet Transform (DWT)** is applied up to **5 levels** using the **db4 wavelet**.
- The DWT decomposition results in **6 coefficients**: **cA5, cD1, cD2, cD3, cD4, cD5**.
- Each coefficient is **Min-Max scaled** and reshaped to a uniform **(6003, 6)** format.
- The dataset is split into **training and testing sets** (using an 80-20 split).

## Model Architecture: 1D CNN
The model consists of:
- **1D Convolutional Layers** for feature extraction.
- **Batch Normalization** to stabilize training.
- **Max Pooling** layers for down-sampling.
- **Global Average Pooling (GAP)** to reduce dimensionality.
- **Dense Layers** for classification.
- **Softmax activation** for multi-class output.

## Training and Evaluation
- The model is trained using the **Categorical Cross-Entropy loss function**.
- The **Adam optimizer** is used for efficient gradient updates.
- The dataset is processed using **TensorFlow's tf.data API** to optimize data loading.

## Reference
- [Classification of Heart Sound Signals using a Novel Deep WavNet Model](https://www.researchgate.net/publication/342029150_Classification_of_heart_sound_signals_using_a_novel_deep_WavNet_model)
