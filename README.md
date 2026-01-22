# 🌌 Stolen Stars: India’s Disappearing Darkness
### A 10 Year Radiometric Study of Artificial Light at Night (2014 to 2023)

> **"We often measure urbanization by the land it consumes, but rarely by the sky it erases every year."**

This repository contains the data and analytical framework for an investigation into the radiometric transformation of the Indian night sky. This project was developed for the Gradient magazine to explore the intersection of environmental change and economic theory.

---

## 🌠 About the Project
This study explores the "Efficiency Trap" by applying Jevon’s Paradox to show how the adoption of efficient LEDs has paradoxically increased India's light footprint rather than saving energy. By tracking 10 years of satellite data, I analyzed how darkness, which is a form of Environmental Capital, is being rapidly depreciated across INDIA.

---

## 🛠 Methodology: Technical Steps
This project utilizes the NOAA VIIRS Day/Night Band (DNB) sensor to quantify light levels.

### 1. Data Retrieval via Google Earth Engine (GEE)
The 10-year longitudinal time series was aggregated using the GEE Python API as seen in `nighttime2.ipynb`:
* **Collection**: The `NOAA/VIIRS/DNB/MONTHLY_V1/VCMSLCFG` collection was used for monthly cloud-free radiance composites.
* **Process**: I applied a `.mean()` reducer over each calendar year (2014-2023) to generate stable annual composites. 
* **Extraction**: Radiance values were sampled at specific coordinates for the 7 ROIs using a `.reduceRegion()` function at a 500-meter scale to ensure localized accuracy.

### 2. The 2017 Calibration Shift
A critical technical step was accounting for a systematic instrumental calibration update in January 2017. 
* **Statistical Integrity**: To avoid sensor induced artifacts, this study interprets the slope and direction of the trend rather than absolute values across the 2017 boundary.

### 3. The 2016 Radiance Dip
Observers may notice a dip in the 2016 data for sites like Araku or Spiti. This is identified as a likely artifact of the pre 2017 stray light correction algorithm, which often under estimated radiance in low light regions before the calibration overhaul.

---

## 📈 Key Insights
* **The Himalayan Paradox**: Regions like Hanle and Spiti are experiencing a "slow brightening". This is exacerbated by the Snowglow effect, where the high reflectivity of snow acts as a mirror for artificial light.
* **Ecological Fragmentation**: In Wayanad, spreading radiance is creating a "light fence," which is a barrier of glare that fragments critical nocturnal wildlife corridors.
* **Urban Saturation**: Varanasi’s 22.57% radiance increase post LED retrofit suggests that efficiency without regulation merely accelerates light pollution.

---

## ⚠️ Prerequisites: Caution
**Note for execution:**
* **Authentication**: Running the data extraction code in nighttime2.ipynb requires a registered Google Earth Engine account.
* **Static Review**: If you do not have a GEE account, you are invited to browse the pre rendered analysis and visualizations already present in the notebook.

---

## 📂 Repository Contents
* `dark_sky_viirs_timeseries.csv`: The 10 year derived dataset used for the final analysis.
* `nighttime2.ipynb`: Python notebook containing the GEE extraction logic and Matplotlib visualization.
* `viirs output b and w magazine version`: High resolution imagery prepared for publication.

---

## 📫 Contact
**Abhilasha Das**
* [LinkedIn](https://www.linkedin.com/in/abhilasha-das-375a95324)
* [GitHub](https://github.com/AbhilashaxData)
