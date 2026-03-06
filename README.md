# 🚚 Amazon Delivery Operations: Data Engineering & Analytics

## 📌 Project Overview
This project presents an end-to-end data pipeline designed to clean, transform, and analyze Amazon's delivery logistics data. The goal was to take a messy, raw dataset of **43,000+ records** and turn it into a structured source of truth to identify operational bottlenecks and performance drivers.

## 🛠️ Tech Stack
- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Matplotlib.
- **Domain:** Logistics & Supply Chain Analytics.

## ⚙️ Data Pipeline Stages

### 1. Data Cleaning (`Scripts/cleaning_code_project.py`)
The raw data contained several inconsistencies that were handled through:
- **Geospatial Correction:** Invalid coordinates (0.0) were identified and replaced with the **median coordinates of their specific Area** to maintain location accuracy.
- **Outlier Management:** Corrected unrealistic values for Delivery Agent Age (limited to 18-65) and Ratings (limited to 1-5).
- **Missing Data:** Imputed numeric gaps using Mean values and categorical gaps using Mode.
- **Midnight Logic:** Fixed time-calculation errors for orders placed before midnight but picked up after.

### 2. Feature Engineering
- **Haversine Distance:** Implemented the mathematical Haversine formula to calculate the physical distance (km) between stores and drop-off points.
- **Speed Metrics:** Calculated `Speed_kmph` to measure efficiency.
- **Segmentation:** Binned agents into groups (Young, Adult, Senior) and order ratings into (Low, Medium, High) for better reporting.



### 3. Business Analysis (`Scripts/analysis_code_project.py`)
The cleaned data was used to answer key business questions:
- **Weather & Speed:** Analyzed how conditions like Storms vs. Cloudy weather impact delivery windows.
- **Agent Performance:** Benchmarked different age segments to find which group provides the highest service quality.
- **Traffic Bottlenecks:** Quantified the delay impact of high traffic on metropolitan delivery times.

## 📊 Key Insights
- **Top Performance:** Senior agents consistently achieve higher ratings (~4.71) compared to younger segments.
- **Environmental Factors:** Cloudy weather correlates with the highest average delivery speeds, while high traffic causes an average **21% delay**.
- **Logistics Efficiency:** Motorcycles remain the most efficient vehicle for urban navigation under heavy traffic conditions.

## 📁 Repository Structure
- `Data/`: Contains the raw and cleaned CSV files.
- `Scripts/`: Contains the standalone Python scripts for cleaning and analysis.
- `README.md`: Project documentation.
