{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyPWyFa1UM4ftoZWJBi6JOjR",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/shreyasnagooor/Voice-Based-Biometric-System-One-Shot-Learning-for-Unseen-Speaker-Generalization/blob/main/Readme.md\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "j1yeYDluHRvS"
      },
      "outputs": [],
      "source": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "\n",
        "# **Voice-Based Biometric System: One-Shot Learning for Unseen Speaker Generalization**\n",
        "\n",
        "## **Introduction**\n",
        "This repository contains the implementation of a voice authentication system using **one-shot learning** for generalizing to unseen speakers. The system utilizes a custom **Siamese network architecture**, combining **ResNet-18** for feature extraction, **GRU** layers for sequential modeling, and an **attention mechanism** for refining speaker embeddings. The system is evaluated on the **LibriSpeech dataset** and is ideal for **financial transactions** and **secure communications**.\n",
        "\n",
        "---\n",
        "\n",
        "## **Features**\n",
        "\n",
        "- **One-Shot Learning**: Authenticate new speakers with just a single voice sample.\n",
        "- **Deep Learning Architecture**: Leverages **ResNet-18** for feature extraction, **GRU** for temporal modeling, and an **attention mechanism** to refine speaker embeddings.\n",
        "- **Noise Robustness**: Includes data augmentation techniques like **Gaussian noise**, **time stretching**, and **pitch shifting** for better real-world performance.\n",
        "- **Triplet Loss**: Uses **triplet margin loss** and **cosine similarity** for accurate speaker verification.\n",
        "- **High Security**: Designed for secure applications such as **financial transactions** and **confidential communications**.\n",
        "\n",
        "---\n",
        "\n",
        "## **Key Features and Architecture**\n",
        "\n",
        "### **Feature Extraction**  \n",
        "- Utilizes **MFCC (Mel-frequency cepstral coefficients)** to capture speech characteristics.\n",
        "- **ResNet-18** extracts hierarchical features from the audio.\n",
        "\n",
        "### **Sequence Modeling**  \n",
        "- Uses **GRU (Gated Recurrent Units)** to model the temporal dependencies in the speech data.\n",
        "\n",
        "### **Attention Mechanism**  \n",
        "- Focuses on important features in the audio for enhanced speaker representation.\n",
        "\n",
        "### **Loss Function**  \n",
        "- Implements **triplet margin loss** to ensure that embeddings from the same speaker are closer, while those from different speakers are farther apart.\n",
        "\n",
        "---\n",
        "\n",
        "## **Benchmark Comparison**\n",
        "\n",
        "| **Model**                      | **Enrollment Data Required** | **ROC-AUC (%)** | **Accuracy (%)** |\n",
        "|---------------------------------|-------------------------------|-----------------|------------------|\n",
        "| i-Vector + PLDA                | 5-10 minutes per speaker      | 80.00           | 82.00            |\n",
        "| Deep CNN + Attention           | 2-5 minutes per speaker       | 86.50           | 88.00            |\n",
        "| Unsupervised Speech Reps       | 1-2 minutes per speaker       | 87.00           | 89.50            |\n",
        "| **Proposed Siamese Network**   | 1 example (few seconds)       | **85.17**       | **85.47**        |\n",
        "\n",
        "**Key Insight**: The Siamese network shows competitive performance with significantly less enrollment data, making it highly efficient for real-world deployment.\n",
        "\n",
        "---\n",
        "\n",
        "## **Dataset**\n",
        "\n",
        "- **LibriSpeech Dataset**: Used **train-clean-100** subset (~100 hours of audio).\n",
        "- Preprocessed to a **16kHz** sampling rate with **MFCC extraction**.\n",
        "- Augmented with **Gaussian noise**, **pitch shifting**, and **time stretching** for robustness.\n",
        "\n",
        "---\n",
        "\n",
        "## **Installation and Setup**\n",
        "\n",
        "### **Clone the Repository**  \n",
        "```bash\n",
        "git clone https://github.com/your-username/voice-authentication-system.git\n",
        "cd voice-authentication-system\n",
        "```\n",
        "\n",
        "### **Install Dependencies**  \n",
        "```bash\n",
        "pip install -r requirements.txt\n",
        "```\n",
        "\n",
        "---\n",
        "\n",
        "## **Usage**\n",
        "\n",
        "### **Prepare the Dataset**  \n",
        "- Download **LibriSpeech** and preprocess it to extract **MFCC** features.\n",
        "\n",
        "### **Train the Model**  \n",
        "```bash\n",
        "python train.py --config config.yaml\n",
        "```\n",
        "\n",
        "### **Evaluate the Model**  \n",
        "```bash\n",
        "python evaluate.py --model-path saved_models/best_model.pth\n",
        "```\n",
        "\n",
        "---\n",
        "\n",
        "## **Performance Metrics**\n",
        "\n",
        "- **ROC-AUC**: 85.17%\n",
        "- **Accuracy**: 85.47%\n",
        "- **True Positive Rate (TPR)**: 92.18%\n",
        "- **True Negative Rate (TNR)**: 77.48%\n",
        "\n",
        "---\n",
        "\n",
        "## **Future Work**\n",
        "\n",
        "- **Advanced Augmentation**: Explore adversarial training for improved robustness.\n",
        "- **Edge Optimization**: Optimize the model for deployment on edge devices.\n",
        "- **Security Enhancements**: Implement **liveness detection** to defend against spoofing attacks.\n",
        "\n",
        "---\n",
        "\n",
        "## **Contributors**\n",
        "\n",
        "- **Shreyas Nagoor** - [shreyasnagoor@gmail.com]\n",
        "- **Garima Pandey** - [garimapandey.217cs002@nitk.edu.in]\n",
        "- **Shashidhar G. Koolagudi** - [koolagudi@nitk.edu.in]\n",
        "\n",
        "---\n"
      ],
      "metadata": {
        "id": "qCVfqiK9Hiqn"
      }
    },
    {
      "cell_type": "markdown",
      "source": [],
      "metadata": {
        "id": "SY7XXL-LHS15"
      }
    }
  ]
}