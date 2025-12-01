# Geospatial Analysis of Electric Vehicle (EV) Charging Station Demand in Berlin

This project analyzes the distribution of public EV charging stations in Berlin and compares it with residential population density to identify areas with high demand but insufficient charging infrastructure.  
The analysis is visualized through interactive geo-heatmaps using **Streamlit**, **Folium**, and **GeoPandas**.

🔗 **GitHub Repository:** https://github.com/rravii/BerlinGeoHeatmap  
🚀 **Live Demo (Streamlit App):** https://berlingeoheatmap.streamlit.app  

---

## 📌 Executive Summary

Electric vehicle adoption is rapidly increasing across Germany, yet public charging infrastructure in dense urban areas like Berlin remains inadequate.

This project:

- Compares **EV charging station availability (Supply)** with  
- **Residential population density (Demand)**  
- Across **Berlin’s postal codes (PLZ)** using geospatial heatmaps.

### **Key Finding**
There is a significant “**charging gap**” in areas inside the Berlin city ring—especially **Neukölln, Wedding, Friedrichshain, and Schöneberg**—where population density is high but public charging stations are limited.

---

## 📊 Datasets

| Dataset | Role | Source | Description |
|--------|------|--------|-------------|
| `Ladesaeulenregister.csv` | Supply Layer | Bundesnetzagentur | Locations + specifications of all public EV charging stations in Berlin |
| `plz_einwohner.csv` | Demand Layer | Statistical data sources | Number of residents per postal code |
| `geodata_berlin_plz.csv` | Spatial Boundaries | Open Data Berlin | Polygon geometry of Berlin postal code areas |

---

## 🗂 Project Structure




### **Main Components**
- **`main.py`** — entry point, loads config, coordinates full workflow  
- **`core/methods.py`** — data preprocessing, merging geospatial and tabular data  
- **`core/HelperTools.py`** — helper utilities (e.g., timer decorator)  
- **`data_quality_checker.py`** — automatic data quality validation  
- **Streamlit App** — interactive map visualization with demand & supply layers  

---

## 🌍 Visualizations

The Streamlit app displays:

### **1. Population Density (Demand)**
![Demand](images/residence.png)

Choropleth heatmap of residents per PLZ.

### **2. Charging Station Distribution (Supply)**
![Supply](images/charging_station.png)

Number of charging stations per PLZ.

### **3. KW-Based Layers (Additional Task 9)**
![KW Based](images/charging_station_kw.png)

Selectable layers for different charger power ratings (e.g., 11 kW, 22 kW, 50 kW, etc.).

---

## 🔍 Key Insights & Interpretation

### **A. High-Demand Zones (“Charging Deserts”)**
- **Neukölln (120xx)**  
- **Wedding (133xx)**  
- **Friedrichshain & Schöneberg**

High-density neighborhoods with very few chargers → **highest priority for expansion**.

### **B. Commercial Mismatch**
- **Marzahn-Biesdorf (1268x)**  
Plenty of chargers near commercial/road areas, but **residential areas remain underserved**.

### **C. Well-Supplied Areas**
- **Mitte & Charlottenburg** show balanced supply-demand conditions.  
- Outer suburbs (Frohnau, Wannsee) rely mostly on **private wallboxes**, so low public demand is expected.

---

## 🛠 Additional Tasks

### **Task 9 — KW-Based Layer Separation**
- Group stations by **power rating** and **postal code**  
- Produce separate map layers for each KW category  
- Helps identify where **fast chargers** (e.g., ≥50 kW) are lacking

### **Task 10 — Automated Data Quality Check**
Validates:

- **Necessary columns**
- **Data types**
- **Plausible value ranges**
- **Geospatial coordinate boundaries**
- **Distribution anomalies**

Ensures that incorrect or incomplete data does not influence analysis.

---

## ▶️ Running the Project

```bash
python -m venv .venv
.venv/Scripts/activate    # Windows
source .venv/bin/activate # Mac/Linux
pip install -r requirements.txt
streamlit run main.py
```

