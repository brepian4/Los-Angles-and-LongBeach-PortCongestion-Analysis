# LA & Long Beach Port Congestion Analysis

## Overview
This project analyzes and visualizes maritime port congestion at the **Port of Los Angeles** and the **Port of Long Beach**, the two busiest ports in the United States. Using **Automatic Identification System (AIS)** data from **January 1, 2024**, the project extracts specific geographical coordinates to provide insights into vessel behavior, traffic patterns, and port utilization.

---

## Features

### Data Extraction & Cleaning
- Filters large-scale US port data down to the specific **LA/Long Beach region**
- Renames technical AIS columns for better readability

### Vessel Categorization
- Automatically classifies vessels as:
  - **Active**
  - **Idle**
  - **Mixed**
- Classification is based on **maximum speed** and **time spent moving**

### Interactive Trajectory Mapping
- Visualizes individual ship paths
- Displays overall traffic density using **Folium** and **Plotly**

### Congestion Insights
- Analyzes **speed distributions**
- Examines **vessel type frequencies** (Cargo, Tanker, Tug, etc.)
- Identifies potential congestion bottlenecks

---

## Data Source
The raw data consists of **AIS broadcasts** collected for all US ports on **January 1, 2024**.  
This project specifically uses the subset:

- `la_long_beach_data.csv`

This file contains filtered records for the **Southern California port complex**.

---

## Analysis Workflow

### 1. Filtering
- Geographic bounding boxes are used to isolate data for:
  - Port of Los Angeles
  - Port of Long Beach

### 2. Imputation
- Missing values for:
  - Vessel status
  - Vessel length
  - Draft  
- Filled using **mean** and **most-frequent** strategies

### 3. Mapping
- Numeric vessel-type codes are mapped to standard maritime categories for clarity

### 4. Visualization
- **Folium FastMarkerCluster**  
  - High-performance mapping of thousands of AIS data points
- **Plotly Bubble Charts**  
  - Explore the relationship between maximum speed and time spent moving
- **Speed Histograms**  
  - Provide a clear view of speed intensity across all tracked vessels

---

## Requirements
- Python 3.x  
- Pandas  
- NumPy  
- Matplotlib / Seaborn  
- Plotly  
- Folium  
- Scikit-learn
