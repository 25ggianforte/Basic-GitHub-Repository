# Quantifying Sea Level Rise Displacement and Safe Relocation Zones in Miami-Dade County

## Project Overview
Miami-Dade County faces severe, immediate threats from climate change and sea level rise (SLR). Because the region is built on porous limestone and low-lying swampland, even minor increases in sea level threaten massive population centers and critical infrastructure. 

This spatial analysis project asks two critical questions:
1. How many residents will be permanently displaced by a 1-foot sea level rise?
2. Where is the optimal (safe and flat) high ground remaining in the county to relocate these displaced populations?

## Methodology & Tools
This project utilizes Python-based spatial data science to model environmental impact and human displacement. The analysis was conducted on the UIowa Argon High-Performance Computing (HPC) cluster.

* **Raster Analysis (Terrain Modeling):** Using the `rasterio` library, USGS 1/3 arc-second Digital Elevation Models (DEMs) were mosaicked and clipped to the county boundary. Map algebra was used to filter for elevations strictly above 3 meters (~10 feet) and calculate slope gradients to isolate buildable, flat terrain (The Atlantic Coastal Ridge).
* **Vector Analysis (Demographic Impact):** Using `geopandas`, NOAA 1-foot SLR inundation polygons were intersected with 2020 US Census Tract boundaries. Area-weighted interpolation was executed to accurately estimate the proportion of the population impacted within partially flooded neighborhoods.

## Preliminary Results & Data
Initial spatial calculations have successfully identified both the safe buildable zones and the projected human toll:

* **Displacement:** The area-weighted vector intersection indicates that a 1-foot sea level rise will permanently displace approximately **135,090 individuals** in Miami-Dade County.
* **Relocation:** Raster map algebra successfully isolated a narrow strip of high-elevation, low-slope ground along the eastern coastal ridge, mathematically proving the limited availability of safe relocation zones. 

The underlying code (`CODE.ipynb`) and data workflows generating these results have been pushed to this repository.
