# 🧠 NYPD Arrest Data Analysis – AI Classification Project

## 📘 Overview

This project uses machine learning classification techniques to analyze and predict criminal patterns from the [NYPD Arrest Data (YTD)]([https://catalog.data.gov/dataset/nypd-arrest-data-year-to-date](https://data.cityofnewyork.us/Public-Safety/NYPD-Arrests-Data-Historic-/8h9b-rp9u/about_data)). The aim is to uncover insights into crime demographics, trends, and categories that can support data-driven decision-making regarding urban safety.

---


## 🔍 Problem Statement

Safety is a critical concern when selecting a place to live, study, or work. Social perceptions of crime are often unreliable. This project provides a data-driven method to assess regional crime severity using arrest records, enabling more informed decisions.

---

## 🎯 Project Motivation

Crimes occur unpredictably and are increasingly enabled by technological means. Understanding patterns through AI can help anticipate and address emerging risks across different boroughs and demographics.

---

## 📂 Dataset Details

- **Source**: [NYC OpenData](https://catalog.data.gov/dataset/nypd-arrest-data-year-to-date)
- **Period**: 2018–2024  
- **Size**: ~195,000 records  
- **Features**: 19 columns including demographic, geographic, and legal information

### Key Insights:
- **Most crimes**: Kings County (Brooklyn)
- **Drug-related crimes**: Dominant in the Bronx
- **Demographics**: Majority of offenders are male and aged 25–44

---

## 🧾 Feature Categories

| Category                 | Features |
|--------------------------|----------|
| **Crime Description**    | `PD_CD`, `PD_DESC`, `KY_CD`, `OFNS_DESC`, `LAW_CODE`, `LAW_CAT_CD` |
| **Location Details**     | `ARREST_BORO`, `ARREST_PRECINCT`, `JURISDICTION_CODE` |
| **Offender Demographics**| `AGE_GROUP`, `PERP_SEX`, `PERP_RACE`, `X_COORD_CD`, `Y_COORD_CD`, `Latitude`, `Longitude` |

---

## ⚙️ Methodology

### 🔧 Data Preprocessing

- Dropped rows with missing values in key target columns (`LAW_CAT_CD`, etc.)
- Removed irrelevant features (`ARREST_KEY`, `PD_CD`, `KY_CD`, `Latitude`, `Longitude`, etc.)
- Simplified high-cardinality columns (e.g., grouped offense types in `OFNS_DESC`)
- Converted `ARREST_DATE` into:
  - Day of the week
  - Month
  - Time-of-day categories

These steps reduced dimensionality and improved model efficiency and interpretability.

### 📈 Model Targets

- `AGE_GROUP`
- `PERP_SEX`
- `PERP_RACE`
- `LAW_CAT_CD`

---

## 🧠 Algorithms Applied

| Algorithm           | Description |
|---------------------|-------------|
| **Naive Bayes**     | Assumes independence between features; simple and fast |
| **Decision Tree (J48)** | Rule-based classification using hierarchical splits |
| **Support Vector Machine (SVM)** | Optimal margin classifier using linear or kernel-based transformations |
| **K-Nearest Neighbors (KNN)** | Instance-based learning using neighborhood voting |
| **Neural Networks (ANN)** | Multi-layer perceptrons with activation functions |
| **Logistic Regression** | Linear classification using sigmoid function |

---

## 📊 Classification Accuracy

### Training Results:

| Algorithm           | AGE_GROUP | PERP_SEX | PERP_RACE | LAW_CAT_CD |
|---------------------|-----------|----------|-----------|-------------|
| Naive Bayes         | 58%       | 82%      | 46%       | 32%         |
| KNN                 | 54%       | 80%      | 43%       | 75%         |
| Decision Tree (J48) | 56%       | 79%      | 47%       | 76%         |
| Neural Networks     | 58%       | 82%      | 48%       | 76%         |
| Logistic Regression | 58%       | 82%      | 46%       | 70%         |
| SVM                 | 58%       | 82%      | 46%       | 70%         |

### Test Results:

| Algorithm           | AGE_GROUP | PERP_SEX | PERP_RACE | LAW_CAT_CD |
|---------------------|-----------|----------|-----------|-------------|
| Naive Bayes         | 39.53%    | 55.81%   | 38.61%    | 32.94%      |
| Lazy IBK            | 54.09%    | 55.81%   | 51.49%    | 41.18%      |
| Bagging             | 47.67%    | 56.98%   | 46.53%    | 42.35%      |
| Decision Tree (J48) | 47.67%    | 56.98%   | 49.51%    | 38.82%      |

---

## 🔗 References

- Djoshi, K. (2020). [GitHub – NYPD NYC Crime Data Analysis](https://github.com/KunalDJoshi/NYPD-NYC-Crime-data-analysis/blob/master/NYPD%20NYC%20Crime%20data%20analysis.pptx)

---

## 🚀 Getting Started

### Prerequisites:
- Python 3.x
- Jupyter Notebook / Google Colab
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

### Running the Project:
1. Clone or download the repository
2. Load the cleaned `.csv` file into your environment
3. Run the notebook/Colab script to:
   - Preprocess the data
   - Train classification models
   - Evaluate results and visualize insights

---

## 📌 Future Improvements

- Hyperparameter tuning for all models
- Use of ensemble methods like Random Forests and XGBoost
- Deployment as a real-time web app for urban crime forecasting

---
