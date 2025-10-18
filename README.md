# 🗺️ Colombo District Electoral Visualization

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![GeoPandas](https://img.shields.io/badge/GeoPandas-Used-brightgreen.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

This project visualizes **Colombo District's Divisional Secretariat Divisions (DSDs)** along with **voter registration and turnout statistics** using geospatial mapping.  
It merges shapefile data with statistical data and produces a **color-coded thematic map** that displays the **Unvoted Percentage** for each division.

---

## Overview

The script performs the following:
- Loads a **Colombo district shapefile** using **GeoPandas**
- Merges it with **voter registration data**
- Calculates:
  -  Registered Voters  
  -  Voted Count  
  -  Unvoted Count  
  -  Unvoted Percentage
- Generates a **custom-colored map** with division labels and percentages

---

## Data Sources

### Shapefile
- Path: `/content/Colombo/COLOMBO.shp`
- Contains boundaries of **Divisional Secretariat Divisions** (DSDs)
- Key column: `DSD_N` — used for merging with voter data

### Voter Data
Defined inside the script:

| Division | Registered | Voted | Unvoted | Unvoted_% |
|-----------|-------------|-------|----------|-----------|
| Colombo MC | 394,533 | 227,233 | 167,300 | 42.4% |
| Kaduwela | 204,547 | 115,255 | 89,292 | 43.7% |
| Dehiwala | 138,460 | 71,998 | 66,462 | 48.0% |
| ... | ... | ... | ... | ... |

---

## Data Processing Steps

1. **Load shapefile** using `geopandas.read_file()`
2. **Create DataFrame** for voter statistics
3. **Calculate** Unvoted count and Unvoted percentage
4. **Rename/align division names** with shapefile attribute `DSD_N`
5. **Merge** shapefile and data on `Division`
6. **Visualize** using Matplotlib:
   - Dark background  
   - Unique color for each division  
   - Division name + unvoted percentage labels

---

## Output Example

The final map highlights all **13 divisions of Colombo District** with their corresponding **Unvoted Percentage**.

Each region is:
- Shown in a unique color  
- Annotated with the division name  
- Labeled with the unvoted percentage (e.g. `Colombo – 42.4%`)

