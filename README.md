# LiDAR Noise Detection & Filtering using Machine Learning

## 📌 Overview

This project develops a **machine learning-based LiDAR point-cloud noise detection and filtering pipeline**. The objective is to analyze large-scale 3D sensor data, identify spatially abnormal points, and generate a cleaner point cloud for downstream analytics and perception applications.

The project focuses on **advanced data analytics, spatial feature engineering, anomaly detection, and 3D visualization**.

## 📊 Dataset

The dataset contains **13.1+ million LiDAR point records** with features including:

* `x` — X coordinate
* `y` — Y coordinate
* `z` — Z coordinate
* `i` — LiDAR intensity
* `t` — Timestamp
* `d` — Dynamic/static indicator
* `scene` — Scene identifier
* `frame` — Frame identifier

> **Note:** The dataset is not included in this repository because of its size. Place the dataset locally before running the notebooks.

## 🎯 Objectives

* Analyze large-scale LiDAR point-cloud data
* Identify spatial and statistical anomalies
* Engineer meaningful 3D geometric features
* Detect potential LiDAR noise without manually labeled noise data
* Filter anomalous points while preserving the underlying structure
* Visualize and compare point clouds before and after filtering

## 🔬 Methodology

```text
Raw LiDAR Data
       ↓
Data Cleaning
       ↓
Exploratory Data Analysis
       ↓
3D Feature Engineering
       ↓
KDTree Neighborhood Analysis
       ↓
Isolation Forest
       ↓
Noise / Outlier Detection
       ↓
Point Cloud Filtering
       ↓
Statistical Evaluation
       ↓
3D Visualization
```

## 🧠 Feature Engineering

The following features are derived from the raw LiDAR coordinates:

* 3D range/distance
* Azimuth
* Elevation
* Nearest-neighbor distance
* Local point density
* Neighborhood distance statistics
* Local variance
* Intensity-based characteristics

KDTree is used for efficient spatial-neighborhood analysis.

## 🤖 Machine Learning

The project uses **Isolation Forest**, an unsupervised anomaly-detection algorithm.

Each point is classified as:

```text
1  → Normal point
-1 → Potential anomaly / noise
```

This approach does not require manually labeled noise points and is therefore suitable for exploratory sensor-data quality analysis.

## 📈 Analytics & Evaluation

The filtering process is evaluated using:

* Total point count
* Detected anomaly count
* Noise percentage
* Point-density distributions
* Neighborhood statistics
* Spatial distribution of detected anomalies
* Before/after 3D visualization

## 🛠️ Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* SciPy
* Open3D
* Matplotlib
* Jupyter Notebook
* Joblib

## 📁 Project Structure

```text
LiDAR-Noise-Filtering/
│
├── data/
│   └── README.md
│
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Noise_Detection.ipynb
│   └── 04_Visualization.ipynb
│
├── models/
│   ├── lidar_isolation_forest.pkl
│   └── lidar_feature_scaler.pkl
│
├── results/
│   ├── filtered_point_cloud/
│   └── visualizations/
│
├── requirements.txt
└── README.md
```

## 🚀 Key Outcome

The project demonstrates how **advanced data analytics and unsupervised machine learning** can be applied to millions of 3D LiDAR measurements to identify abnormal spatial patterns and improve point-cloud data quality.

## 🔮 Future Improvements

* Compare Isolation Forest with DBSCAN, LOF, and statistical outlier removal
* Introduce supervised noise classification using synthetic noise labels
* Develop PointNet/PointNet++ based point-cloud denoising
* Incorporate temporal information across consecutive frames
* Evaluate denoising using quantitative geometric metrics
* Extend the pipeline for real-time LiDAR processing

## 👨‍💻 Author

**Muhammed Musharraf K**

Data Analytics | Machine Learning | Python | LiDAR & 3D Data
