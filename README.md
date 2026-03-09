# Solar Farm Suitability Analysis – Southern Nevada
 
---

# Project Overview

This project identifies optimal locations for solar farm development in Southern Nevada using spatial analysis and multi-criteria decision modeling in ArcGIS Pro.

Southern Nevada receives nearly **4,000 hours of sunlight annually**, making it one of the most suitable regions in the United States for photovoltaic energy production. The purpose of this project is to determine which areas are best suited for solar farm development based on environmental, infrastructure, and land-use constraints.

The analysis integrates terrain characteristics, solar radiation potential, infrastructure proximity, and land protection status to generate a **Solar Suitability Index**.

---

# Study Area

Southern Nevada is characterized by:

- Arid desert landscapes
- High solar radiation levels
- Mountainous terrain
- Expanding energy infrastructure

These environmental conditions make the region highly favorable for renewable energy expansion.

---

# Data Sources

| Dataset | Source | Purpose |
|------|------|------|
| Protected Areas Database (PADUS) | United States Geological Survey (USGS) | Identify conservation restrictions |
| Roads Data | National Geospatial Data Asset (NGDA) | Accessibility analysis |
| Transmission Lines | Esri Federal GIS Community | Power grid connectivity |
| Digital Elevation Model (DEM) | USGS | Terrain analysis |
| Solar Radiation | ArcGIS Spatial Analyst | Solar energy potential |

All datasets were projected to **NAD 1983 UTM Zone 11N** to maintain spatial accuracy.

---

# Methodology

## 1 Terrain Analysis

Using DEM data, slope and aspect were derived to determine terrain suitability for solar infrastructure.

### Slope Classification

| Slope | Suitability |
|------|------|
| 0–3° | Highly suitable |
| 3–6° | Suitable |
| 6–10° | Moderate |
| 10–15° | Low |
| >15° | Unsuitable |

Flat terrain provides the best conditions for solar panel installation.

---

## 2 Aspect Analysis

Aspect determines the direction terrain faces relative to the sun.

In the Northern Hemisphere:

- South-facing slopes receive the greatest solar exposure
- North-facing slopes receive the least

Aspect values were reclassified to prioritize **south-facing terrain**.

---

## 3 Solar Radiation Modeling

Annual solar radiation was calculated using the **Area Solar Radiation Tool** in ArcGIS Pro.

Slope and aspect constraints were applied to remove:

- steep terrain
- north-facing slopes

Solar radiation values were reclassified into suitability classes.

| Radiation Value | Suitability |
|------|------|
| 1200–1360 | 1 |
| 1361–1520 | 2 |
| 1521–1680 | 3 |
| 1681–1840 | 4 |
| 1841+ | 5 |

---

## 4 Infrastructure Accessibility

Solar farms must be accessible and connected to the electrical grid.

Two Euclidean distance analyses were performed:

- distance to roads
- distance to transmission lines

Distances were reclassified into suitability rankings:

| Distance | Suitability |
|------|------|
| 0–50 m | 1 (Too close) |
| 51–500 m | 5 (Ideal) |
| 501–1000 m | 4 |
| 1001–2000 m | 3 |
| 2001–5000 m | 2 |
| 5000+ m | 1 (Too far) |

---

## 5 Land Use Restrictions

Land protection status was evaluated using the **Protected Areas Database (PADUS)**.

GAP classifications describe conservation protection levels:

- GAP 1–2: Highly protected conservation areas
- GAP 3–4: Lower protection levels

Areas with fewer conservation restrictions were considered more suitable for solar development.

---

# Weighted Overlay Analysis

A multi-criteria weighted overlay model was used to combine all variables.

| Factor | Weight |
|------|------|
| Solar Radiation | 30% |
| Roads Distance | 15% |
| Transmission Distance | 15% |
| Slope | 15% |
| Aspect | 15% |
| Land Protection (GAP Status) | 10% |

The final output produced a **Solar Suitability Index** ranging from low to high suitability.

---

# Results

The final suitability map identified numerous areas across Southern Nevada that are highly suitable for solar farm development.

Key findings include:

- Large areas of moderate to high suitability
- Several optimal locations occurring on state-owned land
- Limited transmission infrastructure in central areas constraining some development potential

These findings demonstrate the strong potential for expanding solar infrastructure throughout Southern Nevada.

---

# Maps

## Solar Radiation Map
![Solar Radiation Map](maps/solar_radiation_map.png)

## Slope Map
![Slope Map](maps/slope_map.png)

## Infrastructure Distance Map
![Infrastructure Map](maps/infrastructure_distance_map.png)

## Final Solar Suitability Map
![Final Suitability Map](maps/final_suitability_map.png)

---

# Skills Demonstrated

### GIS Analysis

- Raster analysis
- Terrain modeling
- Multi-criteria suitability modeling
- Weighted overlay analysis

### Spatial Techniques

- Euclidean distance analysis
- DEM analysis
- Solar radiation modeling
- Land use suitability modeling

### Software

- ArcGIS Pro
- ArcGIS Spatial Analyst

---

# Project Significance

This project demonstrates how GIS can support renewable energy planning by identifying optimal development locations while considering environmental and infrastructure constraints.

Spatial modeling approaches like this can assist policymakers, planners, and energy developers in expanding solar infrastructure efficiently and sustainably.

---

# Sources

Solar Energy Industries Association (SEIA)  
United States Geological Survey (USGS)  
Esri GIS Data Repository
