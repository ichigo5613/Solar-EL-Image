# 🚀 Solar Panel EL Defect Detection System

## 📌 Overview

This project focuses on **automating defect detection in solar panel electroluminescence (EL) images**, where defects are often **micro-level and difficult to identify manually**.

Traditional inspection requires human experts to review hundreds of EL images, making the process:

* Time-consuming
* Error-prone
* Difficult for subtle defects

This system uses **Deep Learning (CNN)** to classify EL images into:

* ✅ Good
* ❌ Defect

---

## 🎯 Problem Statement

Solar EL images often contain **very small defects** that visually resemble healthy panels. Manual inspection becomes challenging when:

* Defects are barely visible
* Large volumes of images (400–1000+) need to be reviewed
* Consistency and accuracy are required

👉 This project automates the process and improves reliability.

---

## 🧠 Solution Approach

* Built a **CNN-based classification model** using **EfficientNetV2 (transfer learning)**
* Designed a complete pipeline:

  * Data preprocessing
  * Model training
  * Evaluation
  * Inference

---

## ⚙️ Tech Stack

* **Language:** Python
* **Deep Learning:** TensorFlow / Keras
* **Model:** EfficientNetV2
* **Backend:** FastAPI
* **Cloud:** AWS EC2
* **Queue System:** AWS SQS

---

## 🏗️ System Architecture

```
User Upload → API (FastAPI) → Queue (SQS) → Model Inference → Result (Good/Defect + Confidence)
```

---

## 📊 Model Details

* Model: EfficientNetV2 (Transfer Learning)
* Dataset Size: ~2000 EL images
* Data Split: 70% Train / 15% Val / 15% Test

### Techniques Used:

* Data Augmentation
* Label Smoothing
* Cosine Learning Rate Scheduler

---

## 📈 Performance

* ✅ Accuracy: ~95–97%
* ✅ High Defect Recall (critical for real-world use)

### Evaluation Metrics:

* Confusion Matrix
* ROC-AUC Curve
* Confidence Score Distribution

---

## ⚡ Features

* Detects **micro-level defects** not easily visible to humans
* Provides **confidence score** for predictions
* Supports **bulk image processing (400–1000 images)**
* Scalable backend using **queue-based architecture**

---

## 🚀 Deployment

* Deployed using **FastAPI on AWS EC2**
* Integrated **AWS SQS** for handling large batch uploads
* Designed for **scalable, asynchronous processing**

---

## 📌 Simple Streamlit Application run
cd AI/Demo> streamlit run streamlit_app.py
Where user can maually upload files & test solar images
Which will classfiy the Uploaded solare Image is Good or Defect Image


## 📌 API Endpoint

```
POST /EL-Image-AI
```

**Input:** EL Image
**Output:**

```json
{
  "prediction": "Defect",
  "confidence": 0.94
}
```


For 