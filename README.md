# Spatial Analysis of Malaria Epidemiology in Kenya 🇰🇪

## **Project Overview**

This project conducts a **spatial econometric analysis** of malaria incidence across the **47 counties of Kenya**. By integrating epidemiological, climatic, demographic, and socio-economic variables, the study identifies statistically significant **malaria hotspots** and models the key drivers of disease transmission using a **Spatial Lag Model (SLM)**.

The findings show that malaria in Kenya is a **spatially dependent phenomenon**, influenced by rainfall patterns, ecological zones, and transmission spillover across neighboring counties.

---

## **🔍 Key Objectives**

### **1. Visualization**

* Produce choropleth maps showing malaria incidence across counties.
* Explore spatial clustering including hotspots and coldspots.

### **2. Spatial Diagnostics**

* Compute **Global Moran’s I** to assess overall clustering.
* Use **Local Indicators of Spatial Association (LISA)** to detect specific high-burden zones.

### **3. Spatial Econometric Modeling**

* Fit **Spatial Lag (SLM)** and **Spatial Error (SEM)** models.
* Test significance of climatic (rainfall, temperature), demographic (population), and socio-economic (poverty) drivers.

---

## **📊 Data Sources**

| Dataset Type           | Source                      | Description                             |
| ---------------------- | --------------------------- | --------------------------------------- |
| **Spatial Boundaries** | GADM v4.1                   | Kenya county shapefiles (vector data)   |
| **Epidemiology**       | Ministry of Health          | Malaria incidence per 1,000 population  |
| **Climate**            | Ecological zone simulations | Annual Rainfall (mm) & Temperature (°C) |
| **Socio-Economic**     | KNBS (2022)                 | Poverty Headcount Index                 |
| **Demographics**       | KNBS Projections (2025)     | Population totals per county            |

---

## **🛠️ Methodology & R Packages**

The analysis is conducted in **R** using the following libraries:

* **sf** – spatial vector data (shapefiles)
* **tmap** – static and interactive map visualization
* **spdep** – spatial weights, Moran’s I, LISA analysis
* **spatialreg** – spatial econometric models (SLM, SEM)
* **tidyverse** – data manipulation and cleaning
* **knitr** – exporting model summaries

---

## **📈 Key Findings**

### **1️⃣ Spatial Clustering**

* **Global Moran’s I = 0.35 (p < 0.001)**
  → Strong positive spatial autocorrelation.

#### **Hotspots (High-High Clusters)**

* Lake Endemic Zone: **Siaya, Kisumu, Busia, Kakamega, Homa Bay, Vihiga**

#### **Coldspots (Low-Low Clusters)**

* Central Highlands: **Nyeri, Meru, Nyandarua**
  → Low incidence due to **altitude-driven temperature suppression**.

---

### **2️⃣ Spatial Regression Modeling**

#### **Best Model:**

✅ **Spatial Lag Model (SLM)**
Lowest AIC = **475.67**

#### **Significant Predictors**

| Variable                 | Significance           | Interpretation                                |
| ------------------------ | ---------------------- | --------------------------------------------- |
| **Rainfall**             | p = 0.006              | Higher rainfall → higher malaria              |
| **Spatial Lag (ρ)**      | p = 0.027              | 37% of infection risk influenced by neighbors |
| **Poverty, Temperature** | Not significant in SLM | Effects overshadowed by spatial dependence    |

---

## **📁 Repository Structure**

```
spatial-malaria-kenya/
│
├── data/
│   ├── Kenya_County_Data_2025.shp      # Cleaned spatial dataset
│   └── raw_data/                       # Raw CSVs & shapefiles
│
├── maps/
│   ├── choropleth_incidence.png        # Incidence map
│   └── lisa_cluster_map.png            # LISA hotspot–coldspot map
│
├── scripts/
│   └── Malaria_Analysis.R              # Main analysis script
│
├── output/
│   └── Model_Summary.txt               # Spatial regression results
│
└── README.md
```

---

## **💻 How to Run This Project**

1. **Clone the repository**

   ```bash
   git clone https://github.com/username/spatial-malaria-kenya.git
   ```

2. **Open RStudio** and load:

   ```
   scripts/Malaria_Analysis.R
   ```

3. **Install required packages**

   ```r
   install.packages(c("tidyverse", "sf", "tmap", "spdep", "spatialreg", "knitr"))
   ```

4. **Run the script line-by-line** to:

   * Generate all maps
   * Compute spatial statistics
   * Fit spatial regression models

---

## 👥 Contributors

| Name             | Role                         |
| ---------------- | ---------------------------- |
| *[Student Name]* | Data Cleaning                |
| *[Student Name]* | ESDA & Mapping               |
| *[Student Name]* | Spatial Regression           |
| *[Student Name]* | Statistical Interpretation   |
| *[Student Name]* | Final Report & Documentation |

**Course:** STA 3010 – Statistical Modeling
**Institution:** United States International University–Africa (USIU-A)

---
