# Comparative Analysis of Machine Learning Models for Text Classification

## 📌 Overview
This project compares **RandomForest**, **XGBoost**, and **Logistic Regression** for text classification using two feature extraction methods: **Bag-of-Words (BoW)** and **TF-IDF**.  
The goal was to evaluate which combination of model and features delivers the best performance for large-scale text classification tasks.  

---

## ⚙️ Approach
1. **Dataset Preparation**
   - Collected and cleaned raw text and title data.
   - Sampled to **100k entries** for computational feasibility.
   - Preprocessed text (lowercasing, stopword removal, tokenization).

2. **Feature Extraction**
   - **Bag-of-Words (BoW):** Simple word frequency representation.
   - **TF-IDF:** Weighted frequency emphasizing unique terms.

3. **Models Used**
   - **RandomForest** (with OOB score evaluation).  
   - **XGBoost** (boosted decision trees).  
   - **Logistic Regression** (linear baseline).  

4. **Evaluation Metrics**
   - **Accuracy**  
   - **F1-score**  
   - **Out-of-Bag (OOB) Score** (only for RandomForest)  
   - Confusion Matrices for detailed error analysis.  

---

## 📊 Results Summary

| Model                | Features | Accuracy | F1-score | OOB Score |
|-----------------------|----------|----------|----------|-----------|
| RandomForest          | BoW      | 0.8608   | 0.8616   | 0.8459    |
| RandomForest          | TF-IDF   | 0.8621   | 0.8634   | 0.8469    |
| XGBoost               | BoW      | 0.8513   | 0.8526   | N/A       |
| XGBoost               | TF-IDF   | 0.8499   | 0.8507   | N/A       |
| Logistic Regression   | BoW      | **0.8776** | **0.8769** | N/A    |
| Logistic Regression   | TF-IDF   | **0.8776** | **0.8769** | N/A    |

👉 **Logistic Regression consistently outperformed RandomForest and XGBoost**, achieving ~87.8% accuracy and F1-score.  
👉 Both **BoW** and **TF-IDF** gave nearly identical results, suggesting limited benefit from TF-IDF in this dataset.  

---

## ⚠️ Challenges Faced
1. **High Dimensionality**  
   - Text features created huge sparse matrices, increasing training time and memory usage.  

2. **Label Inconsistencies**  
   - Target label mapping issues caused confusion during evaluation (especially with XGBoost).  

3. **Sampling Trade-off**  
   - Downsampling to 100k entries was necessary for speed, but may have slightly reduced performance.  

4. **Feature Similarity**  
   - BoW and TF-IDF showed very close results, limiting the expected advantage of TF-IDF.  

---

## ✅ Conclusion
- **Logistic Regression** with simple frequency-based features proved to be the most effective model.  
- **Complex ensembles (RandomForest, XGBoost)** did not outperform the linear baseline.  
- In many NLP classification problems, **simple linear models + BoW/TF-IDF** remain strong baselines before moving to deep learning approaches.  

---
