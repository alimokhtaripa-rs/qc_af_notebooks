# Wildfire Remote Sensing Notebooks

This repository contains three Jupyter notebooks used to check the quality of Level-2 FOREST-2 product and NRT AF detections. 
Additionally, you may use this repository to download, process, and analyze MODIS/VIIRS data and perform QA/AF diagnostics.

## Notebooks
- **modis_download_process.ipynb** — MODIS download & pairing (L1B/GEO/AF).
- **viirs_download_process.ipynb** — VIIRS download & pairing (L1B/GEO/AF).
- **analysis_qc_af.ipynb** — Quality checks, false positives, Active Fire overlays/diagnostics.

## Environment
Use either Conda or pip. The **minimum** Python version recommended is 3.10.

### Option A — Conda
```bash
conda create -n wildfire-rs python=3.10
conda activate wildfire-rs
# Main Dependencies
conda install -c conda-forge numpy pandas matplotlib scipy rasterio fiona shapely pyproj geopandas affine pyresample h5py pyhdf contextily matplotlib-scalebar tzdata
# Remaining (if any) via pip
pip install earthaccess geemap earthengine-api __future__ csv datetime getpass ipython math os pathlib re socket typing
```

### Option B — pip (works well on Linux/Mac with build tools; Windows may prefer Conda)
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Secrets & Data
- The notebooks expect credentials via environment variables or interactive prompts.
- Data (HDF/H5/GeoTIFF/shape files/Tables/Figures) are **NOT** included. Adjust local paths in the first config cells.

## Reproducing
1. Create the environment (Conda or pip).
2. Launch Jupyter (Or VS Code):
   ```bash
   jupyter lab
   ```
3. Open a notebook, review the top configuration cells (date ranges, AOI shapefile paths, base directories), and run.

---

## Dependencies by notebook
- **modis_download_process.ipynb**: __future__, csv, datetime, earthaccess, fiona, getpass, numpy, os, pathlib, pyhdf, pyproj, pyresample, rasterio, re, shapely, socket, typing, tzdata
- **viirs_download_process.ipynb**: __future__, csv, datetime, earthaccess, fiona, getpass, h5py, numpy, os, pathlib, pyproj, pyresample, rasterio, re, shapely, socket, typing, tzdata
- **analysis_qc_af.ipynb**: __future__, affine, contextily, csv, datetime, earthengine-api, fiona, geemap, geopandas, ipython, math, matplotlib, matplotlib-scalebar, numpy, pandas, pathlib, pyproj, rasterio, re, scipy, shapely, typing, tzdata
