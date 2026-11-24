# Data-Driven Disaster Preparedness: Flood Risk Prediction for Metro Manila Using Machine Learning

## Project Overview
This project develops an end-to-end supervised and unsupervised machine learning pipeline to predict daily urban flood occurrences across four major cities in Metro Manila (**Quezon City, Marikina, Manila, and Pasig**). Following all 10 stages of the Machine Learning Life Cycle in Python (`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`), the study compares **Logistic Regression** (99.86% test accuracy, 0.92 flood recall) and **Random Forest Classifier** (100.00% test accuracy, 1.00 F1-score) on a leak-free 80/20 stratified split, alongside **K-Means Clustering** ($k = 3$) for operational weather risk profiling.

---

## Group Members & Assigned Roles
* **Ruben M. Luvedeces** — *Data Engineer* (Data loading, inspection, cleaning, and preprocessing pipeline)
* **Jonalyn C. Carandang** — *Data Analyst* (Exploratory data analysis, 5 statistical visualizations, and written interpretations)
* **Trishia Mae Mahusay** — *Machine Learning Engineer* (Feature engineering, 80/20 stratified split, model training, GridSearchCV tuning, error analysis, and K-Means clustering)
* **Aireen Librea** — *Project & Documentation Lead* (Repository management, IEEE technical paper in Overleaf, deployment/ethics documentation, and defense coordination)

---

## Dataset Sourcing & Documentation
* **Dataset Name:** Metro Manila Flood Prediction (2016–2020, Daily)
* **Source Repository:** [Kaggle Dataset Link](https://kaggle.com)
* **License:** Open / Educational Research Use
* **Date Retrieved:** November 18, 2026
* **Dimensions:** 7,308 daily observations (rows) × 7 attributes (columns) spanning January 1, 2016, to December 31, 2020.

### Data Dictionary

| Column Name | Data Type | Role | Description & Units |
| :--- | :--- | :--- | :--- |
| **`Date`** | Date (`datetime64`) | Input Feature (Transformed) | Date of daily environmental observation (`MM/DD/YYYY`), used to extract `Month` and `Is_Wet_Season`. |
| **`Location`** | Categorical (`string`) | Input Feature | Metro Manila city monitored (`Quezon City`, `Marikina`, `Manila`, `Pasig`), encoded via One-Hot Encoding. |
| **`Rainfall_mm`** | Numerical (`float`) | Input Feature | Total daily rainfall precipitation in millimeters (`mm`). |
| **`WaterLevel_m`** | Numerical (`float`) | Input Feature | Measured river or waterway water level in meters (`m`). |
| **`SoilMoisture_pct`** | Numerical (`float`) | Input Feature | Ground soil moisture saturation percentage (`%`). |
| **`Elevation_m`** | Numerical (`integer`) | Input Feature | City zone elevation above sea level in meters (`m`). |
| **`FloodOccurrence`** | Binary (`integer`) | **Target Variable** | Indicates whether flooding occurred (`1` = Flood Occurred, `0` = No Flood). |

---

## Repository Structure
* `project_code.ipynb` — Complete 10-stage Machine Learning Life Cycle Jupyter Notebook.
* `metro_manila_flood.csv` — Raw dataset file retrieved from Kaggle.
* `Technical_Paper.pdf` — Final 6-page two-column IEEE conference paper.
* `README.md` — Project overview, team roles, and dataset documentation.
