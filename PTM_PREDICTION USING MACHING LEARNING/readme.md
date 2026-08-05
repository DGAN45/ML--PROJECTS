# Prediction of Post-Translational Modification (PTM) Sites at Cysteine Residues Using Machine Learning

A Computational Biology Approach to Sequence-Based PTM Site Classification

## Project Overview

This project presents a machine learning-based framework for predicting whether a cysteine residue in a protein sequence is likely to undergo a post-translational modification (PTM). The prediction is performed using only the local amino acid sequence surrounding the cysteine residue, making the approach fast, scalable, and computationally efficient.

The project was developed as a **4th Semester Minor Project** at **A.P.C. Ray Polytechnic, Department of Computer Science and Technology**.

---

## Why is this Project Important?

Post-translational modifications are chemical changes that occur in proteins after they are synthesized. These modifications play a crucial role in:

- Regulating protein function
- Cell signaling
- Enzyme activity
- Protein stability
- Disease mechanisms

Identifying PTM sites experimentally is expensive, time-consuming, and requires advanced laboratory techniques such as mass spectrometry.

### This project helps by:

- Reducing the number of experimental candidates
- Speeding up biological research
- Providing a low-cost computational screening method
- Supporting protein analysis and bioinformatics studies

---

## Real-World Applications

### Biomedical Research
Helps researchers identify potential modification sites related to diseases such as cancer, neurodegenerative disorders, and metabolic disorders.

### Drug Discovery
Can assist in discovering new therapeutic targets by locating functionally important cysteine residues.

### Protein Engineering
Useful for designing stable industrial enzymes and engineered proteins.

### Proteomics and Bioinformatics
Acts as a supporting tool for large-scale protein sequence analysis.

### Laboratory Prioritization
Allows researchers to focus expensive wet-lab experiments only on the most promising PTM candidates.

---

## Machine Learning Workflow

<pre><code>Protein Sequences
       ↓
Sequence Window Extraction
       ↓
BLOSUM62 Encoding
       ↓
Feature Matrix
       ↓
SMOTE Balancing
       ↓
Train/Test Split
       ↓
Model Training
       ↓
Evaluation (ROC-AUC, Precision, Recall, F1)
</code></pre>

---

## Dataset

The dataset contains fixed-length amino acid sequence windows centered on cysteine residues.

- Positive samples: Modified cysteine sites
- Negative samples: Unmodified cysteine sites
- Total samples: 11,149

---

## Feature Engineering

### BLOSUM62 Encoding

Each amino acid in the sequence window is converted into a numerical representation using the **BLOSUM62 substitution matrix**, which captures:

- Evolutionary similarity
- Biochemical similarity
- Structural relationships between amino acids

This produces a compact numerical feature vector for machine learning.

---

## Handling Class Imbalance

Biological datasets are highly imbalanced. To address this, **SMOTE (Synthetic Minority Over-sampling Technique)** was applied to balance the positive and negative classes before training.

---

## Models Compared

| Model | AUC Score | Training Time |
|------|-----------|----------------|
| Linear SVM | 0.6167 | ~259 s |
| Random Forest | 0.9516 | ~4 s |
| XGBoost | 0.9514 | ~0.8 s |

### Final Selected Model: **XGBoost**

XGBoost was chosen because it achieved excellent predictive performance while requiring the least training time.

---

## Final Results

- Accuracy: **~91%**
- ROC-AUC: **> 0.95**
- High precision for modified cysteine prediction
- Strong overall classification performance

---

## Technologies Used

- Python 3
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)

---

## How to Run

### Clone the repository

<pre><code>git clone https://github.com/DGAN45/ML--PROJECTS.git
cd ML--PROJECTS/PTM_PREDICTION USING MACHING LEARNING
</code></pre>

### Run the notebook

Open the Jupyter notebook or upload it to **Google Colab**.

---

## Future Improvements

- Incorporate physicochemical properties
- Use AlphaFold-derived structural features
- Apply deep learning (LSTM, Transformer, ProtBERT, ESM)
- Validate on independent experimental datasets
- Extend from binary PTM prediction to multi-PTM classification

---

## How This Project Can Help Other Processes

This work is not limited to PTM prediction. The same pipeline can be adapted for:

- Protein function prediction
- Mutation effect analysis
- Enzyme activity prediction
- Peptide classification
- Disease-associated residue prediction
- Other bioinformatics classification problems

The combination of **BLOSUM62 encoding + SMOTE + ensemble learning** forms a reusable framework for many biological sequence analysis tasks.

---

## Conclusion

This project demonstrates that biologically meaningful sequence encoding combined with modern machine learning techniques can effectively predict cysteine PTM sites. Ensemble methods such as Random Forest and XGBoost successfully capture the complex non-linear patterns present in protein sequence data, providing a practical and efficient alternative to purely experimental screening approaches.

---

## Authors

- Shreya Banerjee
- Debangan Halder
- Sathi Das
- Radheshyam Singh

Department of Computer Science and Technology  
A.P.C. Ray Polytechnic

---

## Project Guide

**Priti Das**

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## Acknowledgement

We sincerely thank the Department of Computer Science and Technology, A.P.C. Ray Polytechnic, and our project guide for their guidance and support throughout this project.

