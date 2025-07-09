
# Provincial Maternal-Health Risk Dashboard

[Made with JupyterLab]

## Project Overview

This repository hosts a **research-style dashboard** that visualizes maternal-health risks across Pakistan’s provinces, based on PDHS 2017–18 indicators.  
By combining publicly available survey data with GIS shapefiles from GADM, you get:

- **Provincial choropleth** of composite Risk Score  
- **Static bar plots** of individual indicators (ANC coverage, SBA coverage, facility density)  
- A **detailed HTML report** (`provincial_research_report.html`) summarizing data, methods, and key findings  

## Repository Structure



.
├── README.md
├── LICENSE
├── prov\_pdhs\_maternal\_health.csv      # Raw PDHS-derived CSV
├── gadm41\_PAK\_shp/                    # GADM v4.1 Admin-1 shapefile
│   ├── gadm41\_PAK\_1.shp
│   └── … (auxiliary shapefile components)
├── maternal\_risk\_dashboard.ipynb      # JupyterLab analysis & plotting code
├── static\_anc\_anc\_\_bar.png            # ANC coverage bar chart
├── static\_sba\_coverage\_\_bar.png       # SBA coverage bar chart
├── static\_facility\_density\_bar.png    # Facility density bar chart
├── static\_maternal-health\_risk\_bar.png# Risk Score bar chart
├── static\_pakistan\_risk\_map.png       # National choropleth
├── static\_prov\_risk\_choropleth.png    # Provincial choropleth
├── static\_prov\_top5\_bar.png           # Top‑5 risk provinces bar chart
└── provincial\_research\_report.html    # Stand‑alone HTML research report



## Purpose & Goals

1. **Data Exploration**  
   - Clean and normalize province names  
   - Validate Risk Score formula:  
     \[  
       \text{Risk\_Score} = 100 - \frac{\text{ANC\_coverage (\%)} + \text{SBA\_coverage (\%)}}{2}  
     \]

2. **Spatial Visualization**  
   - Merge PDHS data with GADM Admin-1 shapefiles (Pakistan)  
   - Generate static choropleth (`.png`) and an interactive HTML report  

3. **Research-Ready Report**  
   - Fully self-contained HTML (`provincial_research_report.html`)  
   - Styled for readability (Times New Roman, embedded images, JavaScript selector for chart toggling)  
   - Key findings highlighted for policymakers and public health researchers  

## Data Sources

- **PDHS 2017–18**: Provincial antenatal care (ANC) and skilled birth attendance (SBA) statistics  
- **GADM v4.1**: Admin-1 boundaries for Pakistan  
- **Project CSV**: `prov_pdhs_maternal_health.csv` – cleaned and standardized  

## Dependencies & Installation

This project uses Python 3.10+ and the following libraries:

```bash
pip install pandas geopandas matplotlib plotly
````

> If you run into GEOS/PROJ conflicts, see [Geopandas install guide](https://geopandas.org/install.html).

## How to Run

1. **Clone the repo**

   ```bash
   git clone https://github.com/youruser/gul952.git
   cd gul952
   ```

2. **Verify your data & shapefile paths** in the first notebook cell.

3. **In JupyterLab**

   ```bash
   jupyter lab
   ```

   * Open `maternal_risk_dashboard.ipynb`
   * Execute all cells (ensuring `%matplotlib inline` is enabled).

4. **Generate HTML report**
   After running the final cell, you’ll see a link to open `provincial_research_report.html`.

5. **View static images**
   All `.png` files are output to the repo root—ideal for embedding in presentations or web pages.

## What You’ll See

* **Choropleth**: Provinces colored by Risk Score (red = higher risk)
* **Bar Charts**: Ranked provinces for each indicator
* **Interactive HTML**: Dropdown to switch between bar charts and narrative conclusions

---

## Useful Links

* [Pakistan DHS 2017–18 Report](https://dhsprogram.com/pubs/pdf/FR354/FR354.pdf)
* [GADM Database v4.1](https://gadm.org/)
* [GeoPandas Documentation](https://geopandas.org/)
* [Plotly Python](https://plotly.com/python/)

```
```
