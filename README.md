# **Voice-Based Biometric System: One-Shot Learning for Unseen Speaker Generalization**

## **Introduction**
This repository contains the implementation of a voice authentication system using **one-shot learning** for generalizing to unseen speakers. The system utilizes a custom **Siamese network architecture**, combining **ResNet-18** for feature extraction, **GRU** layers for sequential modeling, and an **attention mechanism** for refining speaker embeddings. The system is evaluated on the **LibriSpeech dataset** and is ideal for **financial transactions** and **secure communications**.

---

## **Features**

- **One-Shot Learning**: Authenticate new speakers with just a single voice sample.
- **Deep Learning Architecture**: Leverages **ResNet-18** for feature extraction, **GRU** for temporal modeling, and an **attention mechanism** to refine speaker embeddings.
- **Noise Robustness**: Includes data augmentation techniques like **Gaussian noise**, **time stretching**, and **pitch shifting** for better real-world performance.
- **Triplet Loss**: Uses **triplet margin loss** and **cosine similarity** for accurate speaker verification.
- **High Security**: Designed for secure applications such as **financial transactions** and **confidential communications**.

---
![Structure of the Librispeech Dataset](dataset.drawio (3).png)

## **Key Features and Architecture**
## **Model Architecture**
![Model Architecture](https://github.com/shreyasnagooor/Voice-Based-Biometric-System-One-Shot-Learning-for-Unseen-Speaker-Generalization/raw/main/Model%20Arch.png)


### **Feature Extraction**  
- Utilizes **MFCC (Mel-frequency cepstral coefficients)** to capture speech characteristics.
- **ResNet-18** extracts hierarchical features from the audio.

### **Sequence Modeling**  
- Uses **GRU (Gated Recurrent Units)** to model the temporal dependencies in the speech data.

### **Attention Mechanism**  
- Focuses on important features in the audio for enhanced speaker representation.

### **Loss Function**  
- Implements **triplet margin loss** to ensure that embeddings from the same speaker are closer, while those from different speakers are farther apart.

---

## **Benchmark Comparison**

| **Model**                      | **Enrollment Data Required** | **ROC-AUC (%)** | **Accuracy (%)** |
|---------------------------------|-------------------------------|-----------------|------------------|
| i-Vector + PLDA                | 5-10 minutes per speaker      | 80.00           | 82.00            |
| Deep CNN + Attention           | 2-5 minutes per speaker       | 86.50           | 88.00            |
| Unsupervised Speech Reps       | 1-2 minutes per speaker       | 87.00           | 89.50            |
| **Proposed Siamese Network**   | 1 example (few seconds)       | **85.17**       | **85.47**        |

**Key Insight**: The Siamese network shows competitive performance with significantly less enrollment data, making it highly efficient for real-world deployment.

---

## **Dataset**

- **LibriSpeech Dataset**: Used **train-clean-100** subset (~100 hours of audio).
- Preprocessed to a **16kHz** sampling rate with **MFCC extraction**.
- Augmented with **Gaussian noise**, **pitch shifting**, and **time stretching** for robustness.

---

## **Installation and Setup**

### **Clone the Repository**  
```bash
git clone https://github.com/your-username/voice-authentication-system.git
cd voice-authentication-system

