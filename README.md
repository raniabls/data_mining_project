# 🧪 Alloy Clustering Analysis

This project focuses on the preprocessing and clustering of metallic alloy data. It includes the extraction and transformation of chemical compositions into numerical features, validation of chemical elements, and application of clustering algorithms to identify groups of similar alloys based on their properties.

## 📁 Project Overview

The goal of this project is to:

- Import and clean alloy data from `.ods` spreadsheet files.
- Extract and normalize alloy compositions into numerical format.
- Validate the extracted chemical elements against the periodic table.
- Perform clustering using the KMeans algorithm.
- Evaluate clustering quality using the Silhouette Score.
- Compare clustering results across different subsets of the data.

## 🔧 Main Features

- **Data Cleaning & Transformation**: Parses complex alloy strings like `{[(Fe60 Co40)75 B20 Si5]96 Nb4}98 Cr2` and converts them into structured numerical values.
- **Alloy Composition Extraction**: Converts compositions into individual columns per element with their corresponding percentages.
- **Clustering Analysis**:
  - Applies KMeans clustering across different feature sets (composition only, composition + Tg, composition + Tg + Tx, full dataset).
  - Uses the elbow method and silhouette score to determine the best number of clusters.
  - Visualizes clustering results using PCA.


## 💾 How to Get the Files Locally

1. **Clone the repository** to your local machine:

```bash
git clone https://github.com/raniabls/data_mining_project.git
cd data_mining_project
