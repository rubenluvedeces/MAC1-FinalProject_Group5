# Dataset Documentation

## 1. Dataset Metadata
* **Dataset Name:** Philippine Major Cities Weather Data (Filtered to Region IV-A / CALABARZON)
* **Source Platform:** Kaggle
* **Direct Source URL:** https://kaggle.com
* **License:** Open Public Research / Educational Use License (CC0 / Public Domain on Kaggle)
* **Date Retrieved:** November 26, 2026
* **Original Dimensions:** 447,165 rows × 27 columns across 138 Philippine cities (14 monthly archives from November 2023 to December 2024)
* **Filtered Study Dimensions (`calabarzon_weather.csv`):** 58,319 rows × 27 raw columns (18 retained features after cleaning) across 18 cities in Region IV-A (CALABARZON): Antipolo, Bacoor, Batangas City, Biñan, Cabuyao, Calamba, Cavite City, Dasmariñas, General Trias, Imus, Lipa City, Lucena, San Pablo, San Pedro, Santa Rosa, Santo Tomas, Tanauan, and Tayabas.

## 2. Data Dictionary

| Column Name | Data Type | Modeling Role | Description & Units |
| :--- | :--- | :--- | :--- |
| `city_name` | Categorical (`string`) | Input Feature | Name of the monitored CALABARZON city (18 cities), encoded via One-Hot Encoding (`drop='first'`). |
| `datetime` | Datetime (`Asia/Manila`) | Input Feature (Transformed) | Local Philippine observation timestamp converted from UTC, used to extract `Month`, `Hour`, and `Is_Wet_Season`. |
| `main.temp` | Numerical (`float`) | Input Feature | Ambient air temperature in degrees Celsius (`°C`). |
| `main.feels_like` | Numerical (`float`) | Input Feature | Human-perceived temperature accounting for humidity and wind (`°C`). |
| `main.pressure` | Numerical (`integer`) | Input Feature | Atmospheric sea-level pressure in hectopascals (`hPa`). |
| `main.humidity` | Numerical (`integer`) | Input Feature | Relative air humidity percentage (`%`). |
| `wind.speed` | Numerical (`float`) | Input Feature | Sustained wind speed in meters per second (`m/s`). |
| `wind.gust` | Numerical (`float`) | Input Feature | Peak wind gust speed (`m/s`); 8,547 missing values imputed with column median (`4.47 m/s`). |
| `clouds.all` | Numerical (`integer`) | Input Feature | Total sky cloud cover percentage (`%`). |
| `visibility` | Numerical (`float`) | Input Feature | Horizontal visibility distance in meters (`m`); 56 missing values imputed with median (`10,000.00 m`). |
| `Month` | Numerical (`integer`) | Engineered Feature | Calendar month (`1` to `12`) extracted from `datetime`. |
| `Hour` | Numerical (`integer`) | Engineered Feature | Hour of observation (`0` to `23`) extracted from `datetime`. |
| `Is_Wet_Season` | Binary (`integer`) | Engineered Feature | Philippine monsoon indicator (`1` = June–November wet season, `0` = December–May dry season). |
| `Is_Rain_Storm` | Binary (`integer`) | **Target Variable** | Binary weather classification target derived from `weather.main` (`1` = Rain or Thunderstorm, `0` = Non-Rain conditions). |
