# Remote Sensing Classification and Environmental Analysis with Google Earth Engine

This repository provides a Google Earth Engine (GEE) script for **land cover classification, clustering, and environmental data extraction**. The workflow focuses on forest health analysis in **Arizona, USA** using NAIP and Sentinel-2 imagery alongside precipitation data. Results can be exported for further analysis.

---

## Features

- **NAIP Imagery Processing**
  - Filter by date and study region
  - Clip images to custom polygon
  - Visualize RGB composites

- **Training Data Preparation**
  - Filter points inside study region (`newfc`)
  - Sample spectral values at points
  - Split dataset into training and validation

- **Random Forest Classification**
  - Train classifier using NAIP bands (R, G, B, N)
  - Classify imagery and visualize clusters
  - Compute accuracy with confusion matrices

- **Clustering**
  - K-Means unsupervised clustering
  - Visualize clusters with unique colors

- **Sentinel-2 Data Extraction**
  - Load and filter Sentinel-2 images
  - Extract band values at points
  - Export data as CSV

- **Precipitation Analysis**
  - Load NOAA CPC precipitation data
  - Compute mean precipitation over study region
  - Export time series

- **Export Options**
  - Export classified and raw images to Google Drive or GEE assets
  - Export tabular datasets for further analysis

---

## Workflow Overview

1. **Define Study Region** – Input a polygon geometry.
2. **Prepare Sample Points** – Filter and overlay training points (`newfc`).
3. **Image Preparation** – Load NAIP imagery, clip, and compute median composite. Optional: load Sentinel-2 imagery.
4. **Training & Classification** – Sample regions, train Random Forest, classify images, and assess accuracy.
5. **Clustering** – Apply K-Means to identify unsupervised groups.
6. **Environmental Analysis** – Extract precipitation time series.
7. **Export Results** – Save images and CSVs to Drive or GEE assets.

---

## Usage

1. Clone the repository.
2. Open [Google Earth Engine Code Editor](https://code.earthengine.google.com/).
3. Paste the script and define `region` and `newfc` FeatureCollection.
4. Run the script step by step.
5. Export results to Drive or GEE asset as needed.

---

## Dependencies

- [Google Earth Engine](https://earthengine.google.com/)
- NAIP imagery
- Sentinel-2 imagery
- NOAA CPC precipitation dataset

---

## Example Visualizations

- Classified land cover map
- NAIP image clusters
- Precipitation time series over study region
- Exported CSVs for spectral and environmental metrics

---

## Notes

- Adjust `scale` and `maxPixels` based on study area size.
- Ensure training points (`newfc`) are within the study region.
- `newfc` can be imported as a GEE asset or manually selected.
- Random Forest parameters can be tuned for better accuracy.

---

## License

MIT License
