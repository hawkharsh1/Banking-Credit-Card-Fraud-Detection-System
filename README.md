# 💳 Banking Credit Card Fraud Detection-System

## 📌 Overview
This project focuses on identifying fraudulent credit card transactions using **unsupervised anomaly detection techniques**. The dataset is highly imbalanced, making it a perfect case for anomaly detection rather than traditional supervised learning.

---

## ❓ Why Build This Model

Credit card fraud is a growing concern in the financial sector, with attackers using sophisticated techniques to exploit systems. Fraudulent transactions not only cause financial loss but also erode customer trust. Since fraudulent transactions are extremely rare compared to legitimate ones, the dataset is highly imbalanced — making traditional classification methods less effective.

This project addresses the challenge by applying **unsupervised anomaly detection techniques**, which are well-suited for identifying rare and unusual behavior in data. By building this model, we aim to:

- Protect users from unauthorized credit card charges
- Help financial institutions detect suspicious transactions in real time
- Provide a scalable, efficient solution using Isolation Forest and other anomaly detection algorithms
- Explore effective modeling techniques for highly imbalanced datasets
------

## 📊 Dataset Summary

- **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Total transactions**: 284,807  
- **Fraudulent transactions**: 492  
- **Fraud percentage**: 0.172%
- **Features**:
  - `V1` to `V28`: PCA-transformed features
  - `Time`: Time elapsed from the first transaction
  - `Amount`: Transaction amount
  - `Class`: Target variable (1 = fraud, 0 = normal)

---

## 🤖 Algorithms Used

### 1. ✅ Isolation Forest
- **How it works**: Randomly isolates data points to identify anomalies quickly.
- **Pros**: Fast, scalable, and effective on imbalanced datasets.
- **Performance**:
  - Detected frauds: `73`
  - Accuracy: `99.74%`
  - Best in precision and recall among all methods.

---

### 2. ✅ Local Outlier Factor (LOF)
- **How it works**: Detects anomalies by comparing the **local density** of each point with its neighbors.
- **Pros**: Good for local density variations.
- **Performance**:
  - Detected frauds: `97`
  - Accuracy: `99.65%`
  - Decent performance, but lower recall than Isolation Forest.

---

### 3. ✅ One-Class SVM
- **How it works**: Learns a boundary around the normal data and flags outliers outside this region.
- **Cons**: Poor performance on this highly imbalanced data.
- **Performance**:
  - Detected frauds: `8516` (many false positives)
  - Accuracy: `70.09%`
  - Poor precision and recall.

---

## 📈 Performance Summary

| Model               | Fraud Detections | Accuracy | Notes                                 |
|---------------------|------------------|----------|---------------------------------------|
| Isolation Forest    | 73               | 99.74%   | Best precision & recall               |
| Local Outlier Factor| 97               | 99.65%   | Moderate, better in some edge cases   |
| One-Class SVM       | 8516             | 70.09%   | Too many false positives              |

---
## 🔍 Observations

- **Isolation Forest** detected `73` frauds, compared to:
  - **Local Outlier Factor (LOF)**: `97` frauds
  - **One-Class SVM**: `8516` frauds (many false positives)

- **Model Accuracy**:
  - Isolation Forest: **99.74%**
  - LOF: **99.65%**
  - SVM: **70.09%**

- **Fraud Detection Rate** (Precision & Recall):
  - **Isolation Forest** performed the best with ~**27%** fraud detection.
  - **LOF** had a lower detection rate at only ~**2%**.
  - **SVM** was ineffective with ~**0%** precision on frauds due to high false positives.

- **Conclusion**:  
  Isolation Forest significantly outperformed the other models in accurately detecting fraudulent transactions (~30% improvement). It proved more reliable for identifying rare fraud cases in an imbalanced dataset.

- **Next Steps**:
  - Consider increasing the dataset size or applying **deep learning models** (e.g., Autoencoders or LSTMs) for better performance.
  - Use **ensemble methods** or **hybrid anomaly detection systems** for improved accuracy.
  - Be cautious of **computational cost** when scaling to real-time or larger systems.

---

## 🚀 Future Improvements

- Try **deep learning** models like Autoencoders or LSTMs for better accuracy.
- Use **cost-sensitive learning** or **ensemble models**.
- Incorporate **real-time detection** pipelines.
- Explore **feature engineering** beyond PCA.

---

## 🧰 Tech Stack

- Python 3.x
- Scikit-learn
- Pandas / NumPy
- Matplotlib / Seaborn
- Jupyter Notebook

---

## 📎 References

- [Credit Card Fraud Detection Dataset - Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Scikit-learn documentation

---

