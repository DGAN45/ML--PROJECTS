# Prediction of Post-Translational Modification (PTM) Sites at Cysteine Residues Using Machine Learning

## A Computational Biology Approach to Sequence-Based PTM Site Classification

---

## 📌 Project Overview

Post-Translational Modifications (PTMs) are chemical modifications that occur after protein synthesis and play an important role in regulating protein function, stability, localization, and interactions.

This project develops a Machine Learning-based prediction system to identify whether a **Cysteine residue** in a protein sequence is **Modified** or **Unmodified** using only the surrounding amino acid sequence.

Instead of expensive laboratory experiments, this computational approach provides a fast and cost-effective solution for PTM site prediction.

---

## 🎯 Objectives

- Predict PTM sites at Cysteine residues.
- Encode protein sequences using the **BLOSUM62 substitution matrix**.
- Handle imbalanced biological datasets using **SMOTE**.
- Compare multiple Machine Learning algorithms.
- Select the best-performing model based on ROC-AUC and classification metrics.

---

## 🧬 Dataset

The dataset contains two classes:

- Positive samples (Modified Cysteine)
- Negative samples (Unmodified Cysteine)

Dataset Statistics

| Class | Samples |
|--------|---------|
| Modified | 1,870 |
| Unmodified | 9,279 |
| Total | 11,149 |

---

## 🛠 Technologies Used

- Python 3
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)

---

## 📂 Project Workflow

```
Protein Sequence
        │
        ▼
Extract Cysteine Window
        │
        ▼
BLOSUM62 Encoding
        │
        ▼
Feature Vector Generation
        │
        ▼
SMOTE (Class Balancing)
        │
        ▼
Train-Test Split
        │
        ▼
Train Models
   ├── SVM
   ├── Random Forest
   └── XGBoost
        │
        ▼
Performance Evaluation
        │
        ▼
Best Model Selection
```

---

## ⚙ Feature Engineering

Protein sequence windows centered on each cysteine residue are transformed into numerical vectors using the **BLOSUM62 substitution matrix**.

This representation captures:

- Evolutionary similarity
- Biochemical similarity
- Amino acid substitution scores

---

## 🤖 Machine Learning Models

Three supervised learning algorithms were compared:

### 1. Support Vector Machine (Linear Kernel)

- StandardScaler Pipeline
- Linear Decision Boundary

### 2. Random Forest

- 100 Decision Trees
- Maximum Depth = 12

### 3. XGBoost

- 100 Estimators
- Learning Rate = 0.1
- Maximum Depth = 6

---

## 📈 Model Performance

| Model | ROC-AUC | Training Time |
|--------|----------|---------------|
| SVM | 0.6167 | ~259 sec |
| Random Forest | 0.9516 | ~4 sec |
| XGBoost | 0.9514 | ~0.8 sec |

---

## 🏆 Final Model

**XGBoost** was selected because it achieved:

- High ROC-AUC
- Fastest training time
- Excellent classification performance

---

## 📊 Final Results

Overall Accuracy

**91%**

Classification Metrics

| Metric | Score |
|---------|--------|
| Accuracy | 0.91 |
| Precision | 0.91 |
| Recall | 0.91 |
| F1 Score | 0.91 |

Highlights

- High Precision for Modified Class (0.99)
- High Recall for Unmodified Class (0.99)
- ROC-AUC > 0.95

---

## 📁 Project Structure

```
PTM-Cysteine-Prediction/
│
├── dataset/
│   ├── cystein_pos.txt
│   └── cystein_neg.txt
│
├── notebooks/
│   └── PTM_Prediction.ipynb
│
├── models/
│
├── images/
│   ├── roc_curve.png
│   ├── confusion_matrix.png
│   └── workflow.png
│
├── README.md
│
└── requirements.txt
```

---

## ▶ How to Run

### Clone Repository

```bash
git clone https://github.com/yourusername/PTM-Cysteine-Prediction.git
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Notebook

```bash
jupyter notebook
```

or

Open the notebook directly in **Google Colab**.

---

## 📌 Applications

- Protein Function Prediction
- Computational Biology
- Bioinformatics Research
- Drug Discovery
- Disease Biomarker Identification
- PTM Site Screening
- Protein Engineering

---

## 🚀 Future Scope

- Deep Learning (LSTM, Transformers)
- AlphaFold Structural Features
- Physicochemical Feature Integration
- Independent Dataset Validation
- Multi-Class PTM Prediction
- Larger Protein Databases

---

## 👨‍💻 Authors

- Debangan Halder
- Shreya Banerjee
- Sathi Das
- Radheshyam Singh

Department of Computer Science & Technology

A.P.C. Ray Polytechnic

Academic Year: 2025–2026

---

## 📚 References

- Scikit-learn Documentation
- XGBoost Documentation
- Pandas Documentation
- NumPy Documentation
- Matplotlib Documentation
- PTM Research Articles
- BLOSUM62 Matrix Documentation

---

## ⭐ Conclusion

This project demonstrates that machine learning models can effectively predict Post-Translational Modification (PTM) sites at Cysteine residues using sequence-based information. Among the evaluated models, **XGBoost** achieved the best balance of predictive accuracy and computational efficiency, reaching approximately **91% accuracy** and an **ROC-AUC greater than 0.95**. The proposed framework provides a fast, reliable, and cost-effective computational tool that can support experimental protein research and future developments in bioinformatics.