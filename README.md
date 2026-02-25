# Age Estimation from Speech

**Politecnico di Torino**  
Ismail Aljosevic – s337769  

---

## 📌 Project Overview

This project addresses the regression problem of estimating a speaker’s age from speech recordings.

The dataset consists of:

- Development set: 2,933 samples  
- Evaluation set: 691 samples  

The approach combines acoustic, linguistic, and newly extracted audio features, followed by feature selection, dimensionality reduction, and regression modeling.

---

## 📄 Project Files

- `report.pdf` – full lab report (readable independently of the code)
- `software.ipynb` – complete implementation of preprocessing, feature extraction, model training, and evaluation

---

## ⚙ Methodology

### Feature Engineering
- Provided acoustic and linguistic features
- Additional features extracted using **Librosa**:
  - MFCC
  - Chroma
  - Spectral contrast
  - Bandwidth
  - Roll-off
  - Tempogram
  - Tonnetz
- Summary statistics (min, max, mean, std)
- One-hot encoding for gender and ethnicity

### Feature Selection & Reduction
- Recursive Feature Elimination with Cross-Validation (RFECV)
- Principal Component Analysis (PCA)

### Models Evaluated
- Linear Regression
- Ridge Regression
- Random Forest Regressor (RFR)

Evaluation metric:

$$
RMSE = \sqrt{\frac{1}{N} \sum (y_i - \hat{y}_i)^2}
$$

---

## 📊 Results Summary

Best evaluation results:

| Model | RMSE |
|-------|------|
| Linear Regression | **9.590** |
| Ridge Regression | 9.677 |
| RFR | 10.062 |

- Linear Regression with RFECV achieved the best performance.
- PCA improved cross-validation performance but did not improve evaluation results.

---

## 🎯 Conclusion

- Speech rate–related features (e.g., silence duration) show strong correlation with age.
- Feature selection significantly reduces dimensionality without performance loss.
- Simpler linear models outperformed more complex tree-based models.
- Proper feature engineering plays a crucial role in regression performance.
