# 🩺 Diabetes Prediction

Predicting diabetes among individuals using the **2015 CDC BRFSS survey** — a large-scale US health survey of over 440,000 respondents. The project combines **R** for statistical analysis and feature selection with **Python** for machine learning and deep learning, covering the full data science pipeline from raw survey data to trained predictive models.

---

## 🧠 Overview

The 2015 Behavioral Risk Factor Surveillance System (BRFSS) survey contains ~440,000 rows and 330 columns of self-reported health, demographic, and lifestyle data. This project selects 22 diabetes-relevant features, cleans and rebalances the data, performs thorough EDA, runs statistical feature selection, and trains both classical ML and deep learning classifiers to predict diabetes status.

---

## 📓 Notebook

`Diabetes Prediction PDA-Walid.ipynb` — single end-to-end notebook covering all stages below.

---

## 🔄 Pipeline

**1. Data Loading & Preparation**
- Selected 22 features aligned with known diabetes risk factors (BMI, blood pressure, cholesterol, smoking, physical activity, diet, mental health, income, education, and more)
- Cleaned survey-specific encodings (replaced "don't know" / "refused" codes, rescaled BMI, standardised binary variables to 0/1)
- Final cleaned dataset: **253,680 rows × 22 columns**

**2. Exploratory Data Analysis (EDA)**
- Conducted in **R** using `tidyverse`, `ggplot2`, `corrplot`
- Chi-squared tests across all categorical features vs. the diabetes target
- Distribution plots, correlation matrices, and feature vs. target visualisations

**3. Feature Selection**
- Stepwise logistic regression (`step()` in R) on a 10,000-row subsample
- Reduced from 22 to **19 significant features** for model input

**4. Class Imbalance Handling**
- Original data heavily skewed toward non-diabetic class
- Pre-diabetes class merged into non-diabetic; dataset undersampled to a **50/50 binary split**

**5. Machine Learning**
- **Decision Tree Classifier** (max_depth=5)
- Metrics: Accuracy, AUC-ROC, classification report, confusion matrix, ROC curve
- Feature importance visualisation

**6. Deep Learning**
- **MLP Classifier** (sklearn `MLPClassifier`, logistic activation)
- Metrics: Accuracy, AUC-ROC

---

## 📊 Features Used

| Category | Features |
|---|---|
| Health indicators | High BP, High Cholesterol, Cholesterol Check, BMI, General Health |
| Lifestyle | Smoker, Physical Activity, Fruits, Vegetables, Heavy Alcohol Consumption |
| Medical history | Stroke, Heart Disease or Attack |
| Healthcare access | Any Healthcare, No Doctor due to Cost |
| Wellbeing | Mental Health, Physical Health, Difficulty Walking |
| Demographics | Sex, Age, Education, Income |

---

## 🗂️ Dataset

**2015 CDC BRFSS Survey** — available on [Kaggle](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system?resource=download&select=2015.csv)

Download the `2015.csv` file and update the `BASE_PATH` variable in the notebook to point to your local or Google Drive directory.

---

## ⚙️ Tech Stack

| Tool | Role |
|---|---|
| R (`tidyverse`, `ggplot2`, `corrplot`, `nnet`, `randomForest`) | EDA, statistical tests, feature selection |
| Python / pandas, NumPy | Data wrangling |
| scikit-learn | ML models, metrics, train/test split |
| rpy2 | R–Python interop in Google Colab |
| matplotlib | Visualisation |
| Google Colab + Drive | Development environment |

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/ehab-walid/Diabetes-Prediction.git
   cd Diabetes-Prediction
   ```

2. Install Python dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib rpy2==3.5.1
   ```

3. Download the [2015 BRFSS dataset](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system?resource=download&select=2015.csv) and update `BASE_PATH` in the notebook.

4. Open the notebook in Google Colab or Jupyter and run end-to-end.

> **Note:** R packages (`tidyverse`, `ggplot2`, `corrplot`, `nnet`, `randomForest`) are installed at the top of the notebook via `rpy2`. Colab is the recommended environment.

---

## 👤 Author

**Ehab Walid** — [GitHub](https://github.com/ehab-walid)
