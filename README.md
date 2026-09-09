# 🏥 Insurance Cost Prediction - EDA & Feature Engineering

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)**, **Data Cleaning**, **Feature Engineering**, and **Feature Selection** on an Insurance dataset to identify the factors that influence medical insurance charges.

The objective is to understand the dataset, preprocess the data, engineer meaningful features, and determine the most important variables affecting insurance costs.

---

## 📂 Dataset Information

The dataset contains **1338 records** and **7 features**:

| Feature | Description |
|----------|------------|
| age | Age of the insured person |
| sex | Gender of the person |
| bmi | Body Mass Index |
| children | Number of dependents covered |
| smoker | Smoking status |
| region | Residential area |
| charges | Medical insurance cost |

---

## 🛠 Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-Learn
- SciPy

---

## 📊 Exploratory Data Analysis (EDA)

The following analyses were performed:

### Numerical Feature Analysis
- Distribution plots using Histograms
- KDE Curves
- Boxplots for Outlier Detection

Features analyzed:
- Age
- BMI
- Children
- Charges

### Categorical Feature Analysis
- Gender Distribution
- Smoker Distribution
- Children Count Distribution

### Correlation Analysis
- Heatmap visualization
- Correlation between numerical features

---

## 🧹 Data Cleaning

### Duplicate Removal
Duplicate records were removed from the dataset.

### Missing Value Check
No missing values were found in the dataset.

### Data Type Verification
All feature data types were verified before preprocessing.

---

## ⚙️ Feature Engineering

### Binary Encoding

#### Gender Encoding
```python
male   -> 0
female -> 1
```

#### Smoker Encoding
```python
no  -> 0
yes -> 1
```

---

### Feature Renaming

```python
sex    -> is_female
smoker -> is_smoker
```

---

### One-Hot Encoding

The region column was transformed using:

```python
pd.get_dummies()
```

Generated Features:

- region_northwest
- region_southeast
- region_southwest

---

### BMI Categorization

BMI values were categorized into:

| BMI Range | Category |
|------------|----------|
| <18.5 | Underweight |
| 18.5 - 24.9 | Normal |
| 25 - 29.9 | Overweight |
| ≥30 | Obese |

Dummy variables were then created for these categories.

---

### Feature Scaling

StandardScaler was applied on:

- age
- bmi
- children

to normalize feature values.

---

## 📈 Feature Selection

### Pearson Correlation

Correlation was calculated between features and insurance charges.

#### Top Correlated Features

| Feature | Correlation |
|----------|------------|
| is_smoker | 0.787 |
| age | 0.298 |
| bmi_category_Obese | 0.200 |
| bmi | 0.196 |

### Chi-Square Test

Categorical features were evaluated using Chi-Square testing.

#### Selected Features

- is_smoker
- region_southeast
- is_female
- bmi_category_Obese

---

## ✅ Final Features

The final dataset contains:

```python
[
 'age',
 'is_female',
 'bmi',
 'children',
 'is_smoker',
 'region_southeast',
 'bmi_category_Obese',
 'charges'
]
```

---

## 📁 Project Structure

```text
Insurance-Cost-Prediction/
│
├── insurance.csv
├── Insurance_EDA.ipynb
├── README.md
│
├── images/
│   ├── histograms.png
│   ├── boxplots.png
│   ├── heatmap.png
│
└── requirements.txt
```

---

## 🚀 How to Run

### Clone Repository

```bash
git clone https://github.com/your-username/Insurance-Cost-Prediction.git
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Insurance_EDA.ipynb
```

---

## 📌 Key Findings

- Smoking status has the strongest impact on insurance charges.
- Older individuals generally incur higher insurance costs.
- Obese individuals tend to have higher medical expenses.
- Region has a relatively smaller effect compared to smoking and age.
- Feature engineering significantly improves dataset quality for machine learning models.

---
