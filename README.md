# Athlete Wellness & Injury Risk Classification

## 📘 Project Overview

This project aims to analyze the relationship between **self-reported wellness scores** and **objective workload measures (ACWR: Acute:Chronic Workload Ratio)** to predict athlete health status. The motivation stems from the reality that athletes may feel ready to play, but physiological data often tells a different story. By using machine learning models, we assess whether athletes are truly healthy or at risk of injury — with the ultimate goal of improving injury prevention strategies.

We use real-world sports science data from the [SoccerMon dataset](https://zenodo.org/record/10033832) to compute wellness scores and ACWR, train classification models, and visualize model behavior.

---

## 💾 Dataset

We use the SoccerMon dataset, which includes:
- 33,849 subjective wellness records (sleep quality, soreness, readiness, etc.)
- 10,075 objective training load and GPS-tracked reports
- Data collected from two elite Norwegian women's soccer teams over the 2020–2021 seasons

Reference: [Nature Scientific Data Paper](https://www.nature.com/articles/s41597-024-03386-x)

---

## ⚙️ Setup Instructions

### 🔧 How to Run The Project
Open the Athlete_Analysis.ipynb notebook in Jupyter Notebook or Google Colab.

If using Colab, mount Google Drive to access the CSV files using:

```
from google.colab import drive
drive.mount('/content/drive')
```
Make sure the CSV file paths are correct (e.g., /content/drive/MyDrive/cs426/subjective/wellness/).

Run all notebook cells to:

Clean and transform the data

Compute average wellness scores per player

Merge subjective wellness with objective ACWR scores

Generate labels for “healthy” vs “at-risk” status

Train and evaluate classification models

Generate visualizations (confusion matrix, percent correct per class, correlation heatmap)

## 🤖 Machine Learning Tasks
# Classification Task
We trained several binary classification models to predict athlete health status (healthy = 1, at-risk = 0) based on:

- wellness_score (self-reported)
- acwr (objectively measured)
- acwr range of 0.8 < x < 1.3 is healthy (1) and below 0.8 and above 1.3 is at-risk (0)
# Models Used
- Decision Tree Classifier
- Random Forest Classifier
- K-Nearest Neighbors Classifier

Each model was trained and tested using train_test_split and evaluated using:
- Accuracy
- F1 Score
- Confusion Matrix
- Correct vs Incorrect Predictions per Class (as %)
- Visualization of prediction behavior across classes
