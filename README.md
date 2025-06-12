# 💳 Credit Card Fraud Detection using Anomaly Detection

## 📌 Overview
This project focuses on identifying fraudulent credit card transactions using **unsupervised anomaly detection techniques**. The dataset is highly imbalanced, making it a perfect case for anomaly detection rather than traditional supervised learning.

---

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

## 🧠 Observations

- **Isolation Forest** was the most effective in detecting fraudulent cases (~30% detection).
- **LOF** also performed reasonably but had lower recall.
- **SVM** produced too many false positives due to dataset imbalance.
- Precision-Recall Curve (PR AUC) is used instead of accuracy due to class imbalance.

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

## 📂 Project Structure

