# Glass Identification – Classification with KNN & Decision Trees

**Course:** Practical Data Science with Python (Semester 1, 2024)
**Type:** Individual Machine Learning Project
**Institution:** RMIT University

## Project Overview

This project applies supervised machine learning to classify different types of glass based on chemical composition and refractive index. The work is motivated by **forensic science**, where accurate glass identification can support criminal investigations.

Two models were developed and compared:

* **K-Nearest Neighbours (KNN)**
* **Decision Tree Classifier**

The project emphasises **data preparation, hypothesis-driven EDA, model optimisation, and rigorous evaluation**.

---

## Dataset

* **Source:** UCI Machine Learning Repository – Glass Identification Dataset
* **Size:** 214 samples × 9 features + target label
* **Features:** RI, Na, Mg, Al, Si, K, Ca, Ba, Fe
* **Target:** `Type_of_glass` (categorical, 6 observed classes)
* **Notes:** One glass type (class 4) is not present in the dataset

The dataset is included as `glass.csv`.

---

## Tech Stack

* **Python**
* **pandas, numpy**
* **matplotlib, seaborn**
* **scikit-learn**
* **Jupyter Notebook**

---

## Approach

### 1. Data Preparation

* Verified no missing values using `isna()`
* Removed duplicate records
* Dropped non-informative identifier (`Id_number`)
* Converted target variable to categorical type
* Performed domain-aware outlier inspection (no removal due to chemistry constraints)

### 2. Exploratory Data Analysis (EDA)

* Statistical profiling (`describe`, skewness)
* Feature distributions (KDE, violin, histograms)
* Correlation heatmap and pairwise analysis
* Class imbalance assessment

📊 **Key plots are included in the README and notebook.**

---

## Hypothesis-Driven Analysis

Based on correlation analysis and visual exploration, the following hypotheses were formulated and evaluated:

* **H1:** Higher Calcium content is associated with higher Refractive Index
* **H2:** Increasing Silicon content slightly reduces Refractive Index
* **H3:** Aluminium and Barium show an inverse relationship, suggesting substitution effects in glass manufacturing
* **H4:** All glass types share a similar refractive index (~1.51), indicating RI alone is insufficient for classification
* **H5:** Silicon and Sodium exhibit weak negative correlation
* **H6:** No meaningful relationship exists between (Ba, Mg) and (Al, Mg)

These hypotheses guided feature interpretation and informed modelling decisions.

<img width="438" height="273" alt="image" src="https://github.com/user-attachments/assets/8d7bd327-fd74-454c-b0f3-566af883d303" />
<img width="386" height="304" alt="image" src="https://github.com/user-attachments/assets/909f4451-fc28-4afb-81f7-21fbecdefe21" />



---

## Modelling & Evaluation

### Models Implemented

* **KNN Classifier**
* **Decision Tree Classifier**

### Optimisation Techniques

* Min-Max feature scaling
* Manual hyperparameter tuning
* K-fold cross-validation
* Feature selection using hill-climbing strategy

### Evaluation Metrics

* Accuracy
* Cross-validated performance comparison

**Outcome:**
KNN consistently outperformed Decision Trees on the optimised feature set and was selected as the final recommended model.

---

## Results

* KNN achieved higher predictive accuracy than Decision Tree
* Feature scaling and selection significantly improved performance
* Cross-validation confirmed model stability

(Detailed metrics, confusion matrices, and plots are available in the notebook and report.)

---

## Repository Structure

```
├── glass.ipynb          # Full analysis & modelling notebook
├── glass.csv            # Dataset
├── report.pdf           # Detailed academic report
├── README.md            # Project overview (this file)
```

---

## Reproducibility

1. Clone the repository
2. Install dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Open and run `glass.ipynb`

---

## License & Academic Use

This project was developed as part of coursework at **RMIT University**.

* Dataset is sourced from the **UCI Machine Learning Repository**
* Code and analysis are shared **for educational and portfolio purposes only**
* Not intended for commercial use
