Voice-Based Biometric System: One-Shot Learning for Unseen Speaker Generalization
📄 Abstract
This repository contains the implementation of a voice authentication system leveraging one-shot learning with a custom Siamese network architecture. The model integrates ResNet-18 for feature extraction, GRU layers for sequential modeling, and an attention mechanism to refine embeddings for speaker verification. By utilizing triplet margin loss, the system can generalize to unseen speakers using just a single example per speaker. Extensive data augmentation techniques ensure robustness against real-world acoustic challenges. Evaluated on the LibriSpeech dataset, the model demonstrates competitive performance for financial transactions and secure communications.

📋 Table of Contents
Abstract
Features
Architecture
Benchmark Comparison
Dataset
Installation
Usage
Results
Future Work
Contributors
License
✨ Features
One-Shot Learning: Efficiently authenticates unseen speakers with a single audio example.
Deep Learning Architecture: Uses ResNet-18 for feature extraction, GRU layers for sequence modeling, and an attention mechanism.
Robust to Noise: Data augmentation techniques like Gaussian noise, time stretching, and pitch shifting for real-world scenarios.
Efficient Verification: Utilizes triplet margin loss and cosine similarity for accurate speaker verification.
High Security: Ideal for sensitive applications such as financial transactions and secure communications.
🏗️ Architecture
Feature Extraction:
Uses Mel-Frequency Cepstral Coefficients (MFCCs) to capture spectral properties of speech.
ResNet-18: Extracts hierarchical features.
Sequence Modeling:
GRU (Gated Recurrent Units) to model temporal dependencies in speech.
Attention Mechanism:
Focuses on distinctive features for enhanced speaker representation.
Loss Function:
Triplet Margin Loss to maximize distance between different speakers while minimizing distance for the same speaker.
📊 Benchmark Comparison
Model	Enrollment Data Required	ROC-AUC (%)	Accuracy (%)
i-Vector + PLDA	5–10 minutes per speaker	80.00	82.00
Deep CNN + Attention	2–5 minutes per speaker	86.50	88.00
Unsupervised Speech Representations	1–2 minutes per speaker	87.00	89.50
Proposed Siamese Network	1 example (few seconds)	85.17	85.47
Key Insight:
The proposed Siamese network demonstrates competitive accuracy and ROC-AUC with significantly less enrollment data, making it an efficient choice for real-world deployment.

📚 Dataset
LibriSpeech Dataset:
Used train-clean-100 subset (~100 hours of audio).
Preprocessed to 16kHz sampling rate with MFCC extraction.
Data augmentation: Gaussian noise, pitch shifting, time stretching.
⚙️ Installation
1. Clone the repository:

bash
Copy
Edit
git clone https://github.com/your-username/voice-authentication-system.git
cd voice-authentication-system
2. Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
🚀 Usage
1. Prepare the dataset:

Download LibriSpeech and preprocess it to extract MFCCs.
2. Train the model:

bash
Copy
Edit
python train.py --config config.yaml
3. Evaluate the model:

bash
Copy
Edit
python evaluate.py --model-path saved_models/best_model.pth
📈 Results
ROC-AUC: 85.17%
Accuracy: 85.47%
Confusion Matrix: Indicates effective distinction between same and different speaker classes.
Key Metrics:
True Positive Rate (TPR): 92.18%
True Negative Rate (TNR): 77.48%
🔮 Future Work
Advanced Augmentation: Explore adversarial training for better robustness.
Scalability: Optimize for edge devices.
Security Enhancements: Implement liveness detection to counteract spoofing attacks.
🤝 Contributors
Shreyas Nagoor - [shreyasnagoor@gmail.com]
Garima Pandey - [garimapandey.217cs002@nitk.edu.in]
Shashidhar G. Koolagudi - [koolagudi@nitk.edu.in]
