# 🍎 Project 1 – Affordability of a Healthy Diet

## 📌 Overview
The affordability of a healthy diet is a critical issue for global food security and public health.  
While starchy staples often provide cheap calories, nutrient-rich foods such as fruits, vegetables, and animal-source products can remain out of reach for many populations.  

This project analyzes **World Bank Cost of a Healthy Diet (CoHD)** data to explore food group prices and their relationship to the **percentage of the population unable to afford a healthy diet**.  
The analysis follows the **CRISP-DM process** (Cross Industry Standard Process for Data Mining).  

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

## 📈 Results
- **Distributions:**  
  - Starchy staples, legumes, and oils are cheapest (mostly < 0.6 PPP dollars)  
  - Animal-source foods are most expensive (often > 0.8 PPP dollars)  
  - Fruits and vegetables show wider distributions, reflecting regional variation  
- **Correlations with unaffordability:**  
  - Positive:  
    - `Cost of animal source foods in PPP dollars [CoHD_asf_PPP]` (**r ≈ 0.66**)  
    - `Cost of fats and oils in PPP dollars [CoHD_of_PPP]` (**r ≈ 0.47**)  
    - `Cost of starchy staples in PPP dollars [CoHD_ss_PPP]` (**r ≈ 0.42**)  
  - Negative:  
    - `Cost of fruits in PPP dollars [CoHD_f_PPP]` (**r ≈ –0.44**)  
    - `Cost of vegetables in PPP dollars [CoHD_v_PPP]` (**r ≈ –0.26**)  
  - Weak:  
    - `Cost of legumes, nuts and seeds in PPP dollars [CoHD_lns_PPP]` (**r ≈ –0.08**)  
- **Model Performance (Random Forest):**  
  - RMSE ≈ **16.1** (percentage points)  
  - R² ≈ **0.65**  

---

## 🌍 Broader Implications
Ensuring access to affordable **calorie-dense foods** appears to be a prerequisite for improving diet affordability globally.  
At the same time, long-term health requires policies that also make **nutrient-rich foods** more accessible.  
Data-driven approaches like this can help identify priority areas for intervention.  

In short: while many countries provide cheap staples, the challenge of achieving **dietary diversity** remains.  
Making healthy diets affordable everywhere will require coordinated action on both price stability and income growth.  

---

## ⚙️ How to Run
1. Clone this repository:  
   ```bash
   git clone https://github.com/yourusername/PROJECT_1_NUTRITION.git
   cd PROJECT_1_NUTRITION
