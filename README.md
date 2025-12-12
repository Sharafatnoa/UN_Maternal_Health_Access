# 🌍 Global Maternal Health: The Geography vs. Wealth Divide

### A Data Science Mini-Project Analyzing Healthcare Inequality

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Library](https://img.shields.io/badge/Library-Pandas%20|%20ScikitLearn-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
This project investigates a critical question in global health equity: **What determines if a woman gets access to life-saving maternal care?** Is it driven by where she lives (Urban vs. Rural) or by her economic status (Rich vs. Poor)?

Using data from the **UNICEF Maternal and Newborn Health Coverage Database**, this analysis applies statistical inference and Machine Learning to quantify the "Influence" of demographic factors on healthcare access across 100+ countries.

---

## ❓ Research Question & Hypotheses
**Research Question:** *How do urban–rural residence and household wealth influence access to maternal healthcare services among women aged 15–49?*

* **H1 (Geography):** Urban women have significantly higher access than rural women.
* **H2 (Wealth):** Household wealth is a stronger predictor of access than geography.
* **H3 (Systemic Link):** Countries that fail their rural populations also fail their poor populations (Inequalities are linked).

---

## 📂 Dataset
* **Source:** UNICEF Maternal and Newborn Health Coverage Database (2023).
* **Records:** ~364 country-level records spanning 190+ unique countries.
* **Key Indicators:** Institutional Delivery (INSTDEL), Antenatal Care (ANC1, ANC4).
* **Stratifiers:** Residence (Urban/Rural) and Wealth Quintiles (Poorest/Richest).

---

## ⚙️ Methodology (The Chain of Reasoning)
The project follows a complete Data Science lifecycle, pivoting strategies to overcome data limitations.

### 1. Data Wrangling
* **Challenge:** Raw data was in "Long Format" with independent stratifiers (no nested "Rural-Poor" data).
* **Solution:** Filtered for the latest survey year per country and performed **Pivot Transformations** to align Urban/Rural and Rich/Poor metrics side-by-side for mathematical comparison.

### 2. Statistical Inference (Hypothesis Testing)
* **Gap Analysis:** Calculated the "Urban-Rural Gap" and "Rich-Poor Gap" for every country.
* **Validation:** Used **Paired T-Tests** to confirm that these gaps are statistically significant ($p < 0.05$).

### 3. Unsupervised Learning (Clustering)
* **Goal:** To discover distinct "types" of inequality profiles among nations.
* **Model:** **K-Means Clustering** ($k=3$).
* **Validation:** Validated using the **Silhouette Score (0.56)** and **Elbow Method**.
* **Outcome:** Segmented the world into *Low*, *Moderate*, and *High Inequality* clusters.

### 4. Supervised Learning (Predictive Modeling)
* **Goal:** To scientifically quantify the "Influence" of Wealth vs. Residence.
* **Model:** **Random Forest Classifier**.
* **Target:** Predicting "Adequate Access" (Coverage $\ge$ 80%).
* **Outcome:** Generated a **Feature Importance** ranking to determine the dominant driver of access.

---

## 📊 Key Findings

### 1. Inequality is Systemic
A strong positive correlation (**$r \approx 0.88$**) was found between the Geographic Gap and the Wealth Gap. Countries do not trade off equity; failures accumulate.

### 2. Three Distinct Policy Profiles
The K-Means model identified three clusters of countries:
| Cluster | Rich-Poor Gap | Count | Description |
| :--- | :--- | :--- | :--- |
| **Low Inequality** | < 13% | 50 | High-performing systems. |
| **Moderate Inequality** | 13% - 42% | 34 | Visible but manageable gaps. |
| **High Inequality** | > 42% | 35 | Crisis states with systemic exclusion. |

### 3. Wealth is the Dominant Driver
The Random Forest analysis revealed that **Household Wealth** (being in the Poorest/Richest quintile) has a higher influence score than Residence.
> **Verdict:** *Poverty is a greater barrier to healthcare than physical distance.*

---

## 🛠️ Technologies Used
* **Python:** Core programming language.
* **Pandas & NumPy:** Data cleaning, pivoting, and manipulation.
* **Matplotlib & Seaborn:** Visualizations (Dumbbell charts, Regression plots, Heatmaps).
* **Scikit-Learn:** K-Means Clustering, Random Forest Classification, Model Evaluation metrics.

---

## 🚀 How to Run This Project
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/maternal-health-access.git](https://github.com/yourusername/maternal-health-access.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
    ```
3.  **Run the Notebook:**
    Open `MaternalHealthAccess.ipynb` in Jupyter Notebook or VS Code and run all cells.

---

## 📝 Limitations & Future Work
* **Aggregation Bias:** The dataset uses national averages, which risks the Ecological Fallacy.
* **Future Work:** Accessing micro-data (DHS Individual Recodes) would allow for Logistic Regression on specific "Rural-Poor" individuals to validate these findings at a granular level.

---

### Author
**Shamsunnur Ibn Arefin**
* Master's Student in Data Science
* University of Skövde
