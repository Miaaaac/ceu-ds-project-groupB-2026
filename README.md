# Quantifying Anthropogenic Influence on Spatial Avian Distribution

## CEU Data Science Project – Group B 2026


---

## Project Description
This project quantifies the influence of anthropogenic activity on avian 
behaviour in Europe between 2017 and 2022. We use two primary proxies for 
human activity: (1) nighttime light intensity derived from NASA VIIRS satellite 
imagery, and (2) air quality indicators (PM10) from AQICN. The study period 
encompasses the COVID-19 pandemic, which caused a sharp decline in human 
activity, allowing a quasi-experimental assessment of how reduced human 
presence affected bird spatial behaviour. Bird occurrence data is sourced 
from the eBird citizen science platform.

**Main Hypothesis:** Human activity has a significant effect on the spatial 
distribution of birds in Europe.

---

## Repository Structure

| Branch | Description |
|--------|-------------|
| `main` | merged final version |
| `final_version` | clean final notebooks + report (v1.0) |
| `all-work` | all original exploratory work from March 2026 |
| `mia_nightlights` | nightlights analysis (Mia) |
| `nika_nightlights` | nightlights analysis (Nika) |
| `nika_merged_data` | merged nightlights + eBird data |

### Final notebooks (`final_version` branch → `/notebooks/`):

| Notebook | Description |
|----------|-------------|
| `overall_layout.ipynb` | Overview and pipeline |
| `birds_inspect_data.ipynb` | eBird data inspection and cleaning |
| `air_polution.ipynb` | AQICN air quality analysis |
| `world_bank_data.ipynb` | World Bank WDI analysis |
| `city.ipynb` | City coordinates and distance computation |
| `analysis.ipynb` | Main spatial analysis |
| `native_european_bird_analysis.ipynb` | Native bird subgroup analysis |
| `migra_native_stat_tests.ipynb` | Native vs migratory statistical tests |
| `diurnal_nocturnal_stat_tests.ipynb` | Diurnal vs nocturnal tests |
| `spring_autumn_stat_tests.ipynb` | Spring vs fall migration tests |
| `regression_all.ipynb` | Multivariate regression (all species) |
| `regression_migra.ipynb` | Regression (migratory species) |
| `regression_native.ipynb` | Regression (native species) |

---

## Implementation

1. Clone the repository
2. Check the final_version branch (main is also good)
3. Install dependencies: pip install -r requirements.txt
4. Run notebooks in `/notebooks/`

---

## Data Sources

| Dataset | Description | Link |
|---------|-------------|------|
| eBird | Bird occurrence records | https://ebird.org/data/download |
| NASA VIIRS VNP46A4 | Annual nighttime light radiance (HDF5) | [https://ladsweb.modaps.eosdis.nasa.gov ](https://search.earthdata.nasa.gov/search/granules?portal=idn&p=C3365931269-LAADS&q=NIght%20Lights&sp[0]=75.45413%2C49.16726&qt=2023-01-01T00%3A00%3A00.000Z%2C2023-12-31T23%3A59%3A59.999Z&lat=54.897515259029426&long=82.9156553299572&zoom=4.115944238760764)|
| AQICN | City-level PM10 air quality index | https://aqicn.org/api |
| World Bank WDI | GDP per capita, agricultural land change | https://databank.worldbank.org |
| Natural Earth 1:10m | European city coordinates | https://www.naturalearthdata.com |

> **Note:** Raw data files are not stored in this repository due to file size.
> Please download from the links above and place files in a `/data/` folder before running the notebooks.
> Another option would be to check the link in the final_version branch $\rightarrow$ notebooks $\rightarrow$ `night_lights_notebook`, and this link is for the onedrive where parts of datasets are available
> Nightlights multi-CSV files and interactive folium maps are available on OneDrive (see `night_lights_notebook` for the link).

---

## Dependencies

Install all required packages with:
pip install -r requirements.txt

| Package | Purpose |
|---------|---------|
| `pandas`, `numpy` | Data manipulation |
| `geopandas`, `shapely`, `pyproj` | Geospatial analysis |
| `rasterio`, `h5py` | Raster and HDF5 processing |
| `scipy`, `statsmodels` | Statistical testing |
| `pymannkendall` | Mann-Kendall trend test |
| `matplotlib`, `seaborn` | Visualisation |
| `folium` | Interactive maps |
| `requests` | API access |
| `geopy` | Haversine distance computation |
| `wbdata` | World Bank data access |

---

## Methods Summary

1. **Data Collection** — eBird, NASA VIIRS, AQICN, WDI
2. **Preprocessing** — outlier removal, HDF5 extraction, spatial filtering
3. **EDA** — temporal trends, interactive folium map, PCA on WDI
4. **Feature Engineering** — Haversine distance from each bird observation to nearest city centre
5. **Hypothesis Testing:**
   - Weighted Least Squares (WLS) Regression
   - Mann-Kendall Trend Test
   - Difference-in-Differences (DiD) — COVID-19 natural experiment
   - Simple and Multivariate Linear Regression

---

## Authors

| Name |
|------|
| Maria Corduneanu-Huci |
| Shiwam K.C. |
| Thanika Haltrich |

CEU Department of Undergraduate Studies – Data Science and Society, 2026

---

## Release

- **v1.0** — Final submission, April 2026
- Tagged on `final_version` branch

---

## License

This project is licensed under the
**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**.

You are free to share and adapt this work, as long as you give appropriate
credit and distribute your contributions under the same license.

Full license text: https://creativecommons.org/licenses/by-sa/4.0/
