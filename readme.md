# 🍎 Project 1 – Affordability of a Healthy Diet

## 📑 Table of Contents
- [📌 Overview](#-overview)
- [📊 Dataset](#-dataset)
- [❓ Research Questions](#-research-questions)
- [🔍 Methods](#-methods)
- [📈 Results & Implications](#-results--implications)
- [📚 Requirements](#-requirements)
- [⚙️ How to Run](#️-how-to-run)
- [🙏 Acknowledgements](#-acknowledgements)

---

## 📌 Overview
The affordability of a healthy diet is a critical issue for global food security and public health.  
While starchy staples often provide cheap calories, nutrient-rich foods such as fruits, vegetables, and animal-source products can remain out of reach for many populations.  

This project analyzes **World Bank Cost of a Healthy Diet (CoHD)** data to explore food group prices and their relationship to the **percentage of the population unable to afford a healthy diet**.  
The analysis follows the **CRISP-DM process** (Cross Industry Standard Process for Data Mining).  

> 📝 This project was completed as part of the **Udacity Data Science Nanodegree Program (Project 1)**.  
There is also an accompanying Medium post:  
[How Affordable is a Healthy Diet?](https://medium.com/@san.merkel/how-affordable-is-a-healthy-diet-72b50295a46e)  
---

## 📊 Dataset
- **File:** `data/nutri_data.csv`  
- **Coverage:** 192 countries (2017–2024)  
- **Note:** Only **2021** had complete values for food groups; **158 countries** had full records.  
- **Columns:**
  - `Time`: Year of observation  
  - `Country Name`: Country identifier  
  - `Cost of fruits in PPP dollars [CoHD_f_PPP]`  
  - `Cost of vegetables in PPP dollars [CoHD_v_PPP]`  
  - `Cost of starchy staples in PPP dollars [CoHD_ss_PPP]`  
  - `Cost of animal source foods in PPP dollars [CoHD_asf_PPP]`  
  - `Cost of legumes, nuts and seeds in PPP dollars [CoHD_lns_PPP]`  
  - `Cost of fats and oils in PPP dollars [CoHD_of_PPP]`  
  - `Percent of the population who cannot afford a healthy diet [CoHD_headcount]` (**target variable**)  

---

## ❓ Research Questions
1. What is the distribution of food group costs across countries?  
2. Which food costs correlate most with the unaffordability of a healthy diet?  
3. Can we predict unaffordability based on food group prices?  

---

## 🔍 Methods
- **Data Cleaning:** replaced missing values (“..” → NaN), selected 2021 data, dropped incomplete rows  
- **EDA:** histograms, descriptive statistics  
- **Correlation Analysis:** correlation matrix and interpretation  
- **Modeling:** RandomForestRegressor (scikit-learn) to capture non-linearities and feature interactions  
- **Evaluation:** RMSE, R²  

---

## 📈 Results & Implications
- **Distributions:** Staples, legumes, and oils are cheapest (< 0.6 PPP dollars), while animal-source foods are the most expensive (> 0.8 PPP dollars). Fruits and vegetables show wider variation across regions.  
- **Correlations:** Unaffordability is strongly linked to the price of **animal-source foods (r ≈ 0.66)**, with staples (0.42) and oils (0.47) also important. Fruits (–0.44) and vegetables (–0.26) show negative correlations.  
- **Model Performance:** A Random Forest model achieved RMSE ≈ 16.1 and R² ≈ 0.65, confirming that food prices alone explain much of the variation in diet affordability.  

**Takeaway:** Affordability is most sensitive to the prices of calorie-dense foods (staples, oils, animal products). Ensuring access to these basics is key for reducing unaffordability. At the same time, achieving **dietary diversity** remains a global challenge, requiring policies that also improve access to fruits and vegetables.  

---

## 📚 Requirements
The following Python libraries are required:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- jupyter

---

## ⚙️ How to Run

### Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run the notebook
```bash
run jupyter notebook nutrition_data.ipynb
```

---

## 🙏 Acknowledgements
Dataset: World Bank – Cost of a Healthy Diet