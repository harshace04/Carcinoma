# Skin Cancer Detection using Deep Learning (HAM10000)

##  Project Summary
This repository implements a **multi-class skin lesion classification system** using deep learning.  
The goal is to classify dermatoscopic images into **6 diagnostic categories** using a **Convolutional Neural Network (CNN)** built with **FastAI (PyTorch backend)**.  
This was developed as part of my applied deep learning work for real-world medical imaging analysis.

---

##  Motivation
Early detection of skin cancer can save lives. Traditional methods are manual and require expert dermatologists.  
This project uses **deep learning vision models** to build an automated classifier that can help screen skin lesions faster and more objectively.

---

##  Dataset
- **Dataset Name:** HAM10000 (Human Against Machine with 10,000 images)  
- **Domain:** Dermatoscopic images of skin lesions  
- **Number of Classes:** 6 diagnostic categories  
- **Image Type:** RGB images  
- **Challenges:**
  - Intra-class similarity and inter-class overlap
  - Class imbalance  
This dataset was preprocessed and split into training and validation sets for supervised training.

---

##  Tech Stack
- **Language:** Python  
- **Frameworks:** FastAI, PyTorch  
- **Libraries:** NumPy, Pandas, Scikit-learn, Matplotlib

---

##  Model Architecture
We built a **transfer learning–based CNN** using a **pretrained backbone** (trained on ImageNet) and fine-tuned on HAM10000:

1. Load pretrained CNN backbone
2. Replace final layer for **6-class classification**
3. Train first with frozen backbone, then full fine-tuning
4. Use data augmentation (flip, rotate, zoom)

This approach reduces training time and improves generalization performance.

---

##  Training Pipeline
Training was done from **Aug 2024 to Jun 2025** with the following steps:

1. Load and preprocess images
2. Apply data augmentation
3. Train with frozen pretrained layers
4. Find optimum learning rate (FastAI learning rate finder)
5. Fine-tune the model end-to-end
6. Monitor validation metrics to avoid overfitting

---

##  Evaluation Metrics
The model is evaluated using multiple metrics:

- **Accuracy:** Model’s overall correctness
- **Precision:** True positives relative to predicted positives
- **Recall:** True positives relative to actual positives
- **F1-score:** Harmonic mean of precision and recall
- **Confusion Matrix:** Shows per-class performance

This provides better insight than accuracy alone.

**Result:** **84.8% overall accuracy**  
Detailed metrics are included in the .ipynb file.

---


