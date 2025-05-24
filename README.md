# 🚨 Anomaly Detection in Network Traffic using Isolation Forest and Autoencoders

This project implements **unsupervised anomaly detection** on the **KDD Cup 1999** network intrusion dataset using two powerful techniques:

- **Isolation Forest**
- **Autoencoders (Deep Learning)**

These models are used to detect malicious network traffic without prior knowledge of attack types. It's designed as a lightweight Intrusion Detection System (IDS) for detecting novel attacks.

---

## 📂 Dataset

The dataset used is the **KDD Cup 1999 10% corrected** version, which contains a variety of simulated network traffic and attack patterns.

- 📥 Downloaded automatically using [`kagglehub`](https://github.com/kagglehub)
- Dataset source: [`galaxyh/kdd-cup-1999-data`](https://www.kaggle.com/datasets/galaxyh/kdd-cup-1999-data)
- File: `kddcup.data_10_percent_corrected`
- Binary labels: `normal.` → 0, all attack types → 1

---

## 🔍 Techniques Used

### ✅ Isolation Forest
- Unsupervised, tree-based model
- Detects anomalies by randomly partitioning data
- Works well with high-dimensional data

### ✅ Autoencoder
- Deep learning model trained to reconstruct normal traffic
- High reconstruction error implies potential anomaly
- Trained only on normal traffic samples

---

## ⚙️ Implementation Steps

1. **Dataset download** using `kagglehub`
2. **Preprocessing**:
   - Encode categorical features
   - Normalize with `MinMaxScaler`
   - Convert multi-class label to binary
3. **Train Models**:
   - Isolation Forest on entire dataset
   - Autoencoder on normal traffic only
4. **Prediction**:
   - Thresholding reconstruction error for Autoencoder
   - Direct prediction for Isolation Forest
5. **Evaluation**:
   - Accuracy
   - Confusion Matrix
   - Precision, Recall, F1-Score

---

## 📊 Results

| Model            | Accuracy | Summary                              |
|------------------|----------|--------------------------------------|
| Isolation Forest | ~85–87%  | Works well for fast unsupervised detection |
| Autoencoder      | ~93–95%  | Better performance due to deep learning |

> *Exact results may vary due to randomness and tuning.*

---

## 🛠️ Tech Stack

- Python 🐍
- Scikit-learn 📊
- TensorFlow / Keras 🤖
- Pandas, NumPy
- kagglehub for dataset management

---
