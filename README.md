# Data-Driven Disaster Preparedness: Predicting Rain and Storm Events Across CALABARZON Cities Using Machine Learning

## Project Overview
This project develops an end-to-end supervised and unsupervised machine learning pipeline to classify rain and thunderstorm events across **18 cities in Region IV-A (CALABARZON)**, including Batangas City, Lipa City, Bacoor, Imus, Dasmariñas, Calamba, Antipolo, and Lucena. Following all 10 stages of the Machine Learning Life Cycle in Python (`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`), we evaluate **Logistic Regression** (91.24% accuracy) and **Random Forest Classifier** (92.37% baseline accuracy; 91.32% tuned accuracy with `class_weight='balanced'`, boosting rain recall from 0.26 to 0.49 and F1-score to 0.51) on a leak-free 80/20 stratified split, alongside **K-Means Clustering** ($k = 3$) for operational weather risk profiling.

---

## Group Members & Assigned Roles
* **Ruben M. Luvedeces** — *Data Engineer* (Monthly CSV merging, CALABARZON regional filtering, median imputation, and timestamp conversion)
* **Jonalyn C. Carandang** — *Data Analyst* (Exploratory data analysis, 5 statistical visualizations, and meteorological interpretations)
* **Trishia Mae Mahusay** — *Machine Learning Engineer* (Feature engineering, 80/20 stratified split, model training, GridSearchCV tuning, error analysis, and K-Means clustering)
* **Aireen Librea** — *Project & Documentation Lead* (Repository management, IEEE technical paper in Overleaf, deployment/ethics plan, and defense coordination)

---

## Dataset Sourcing & Documentation
* **Dataset Name:** Philippine Major Cities Weather Data (Filtered to Region IV-A / CALABARZON)
* **Source Repository:** [Kaggle Dataset Link](https://kaggle.com)
* **License:** Open Public Research / Educational Use
* **Date Retrieved:** November 26, 2026
* **Dimensions:** 58,319 three-hour weather observations (rows) × 18 retained features (columns) spanning November 2023 to December 2024 across 18 CALABARZON cities.

### Data Dictionary

| Variable | Data Type | Role | Description & Units |
| :--- | :--- | :--- | :--- |
| **`city_name`** | Categorical (`string`) | Input Feature | Monitored CALABARZON city (18 cities), encoded via One-Hot Encoding. |
| **`datetime`** | Datetime (`Asia/Manila`) | Transformed | Local Philippine observation timestamp used to extract `Month`, `Hour`, and `Is_Wet_Season`. |
| **`main.temp`** | Numerical (`float`) | Input Feature | Ambient air temperature in degrees Celsius (`°C`). |
| **`main.feels_like`** | Numerical (`float`) | Input Feature | Heat-index adjusted temperature (`°C`). |
| **`main.pressure`** | Numerical (`float`) | Input Feature | Atmospheric sea-level pressure in hectopascals (`hPa`). |
| **`main.humidity`** | Numerical (`float`) | Input Feature | Relative air humidity percentage (`%`). |
| **`wind.speed`** | Numerical (`float`) | Input Feature | Sustained wind speed in meters per second (`m/s`). |
| **`wind.gust`** | Numerical (`float`) | Input Feature | Peak wind gust speed (`m/s`), missing values imputed with median (`4.47 m/s`). |
| **`clouds.all`** | Numerical (`integer`) | Input Feature | Total sky cloud cover percentage (`%`). |
| **`visibility`** | Numerical (`float`) | Input Feature | Horizontal visibility distance in meters (`m`), imputed with median (`10,000 m`). |
| **`Month / Hour`** | Numerical (`integer`) | Engineered | Extracted calendar month (`1–12`) and local hour (`0–23`). |
| **`Is_Wet_Season`** | Binary (`integer`) | Engineered | Philippine monsoon indicator (`1` = June–November, `0` = December–May). |
| **`Is_Rain_Storm`** | Binary (`integer`) | **Target Variable** | Binary weather target (`1` = Rain or Thunderstorm, `0` = Non-Rain). |

---

## Repository Structure
* `project_code.ipynb` — Complete 10-stage Machine Learning Life Cycle Jupyter Notebook.
* `calabarzon_weather.csv` — Filtered CALABARZON dataset (`58,319` rows).
* `Technical_Paper.pdf` — Final two-column IEEE conference paper.
* `README.md` — Project overview, team roles, and dataset documentation.
