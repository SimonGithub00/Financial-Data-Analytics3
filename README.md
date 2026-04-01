# Financial Data Analytics: Company Clustering Analysis

## 📊 Project Overview

This project applies unsupervised machine learning techniques to identify distinct groups of companies based on key financial metrics. Using k-means clustering and advanced quantitative analysis, the project segments companies into meaningful clusters that reveal patterns in financial characteristics and valuation metrics.

**Goal:** Discover natural groupings in company financial data to identify distinct business profiles and investment categories.

---

## 🎯 Key Findings & Highlights

### Optimal Clustering Structure
- **6 Clusters identified** using the Elbow Method for optimal balance between model complexity and variance explained
- **4 Clusters preferred** when evaluated by Silhouette Score analysis for superior cluster separation
- Companies successfully segmented into distinct financial profiles

### Cluster Profiles

| Cluster | Size | Key Characteristics | Investment Profile |
|---------|------|-------------------|-------------------|
| **0** | 16% | Highest Debt Ratio, Lowest P/E | Pessimistic valuation on high debt |
| **1** | 7% | Highest P/E Ratio | Growth-optimistic, potentially overvalued |
| **2** | 21% | Lowest Beta, Low P/E, Stable metrics | Stable value stocks, low growth |
| **3** | 10% | Highest Price-to-Book | High market vs book value (HML factor traits) |
| **4** | 19% | Highest Beta | High market sensitivity, volatile |
| **5** | 27% | Largest Market Cap | Large-cap, established companies |

### Key Insights

✅ **Enterprise Value Drivers:**
- **Log Market Capitalization** (positive coefficient): Larger companies show higher enterprise values
- **Debt Ratio** (positive coefficient): Higher debt correlates with higher enterprise value
- Combined effect: Clusters 0 & 5 (45% of dataset) have 2-4x higher average enterprise values

✅ **Financial Metric Relationships:**
- Low correlation between individual financial metrics and enterprise value (R² = 0.017)
- Suggests multivariate nature of company valuation

✅ **Data Quality:**
- 8% outliers removed to improve clustering quality
- Final dataset contains 903 companies analyzed across 5 financial dimensions

---

## 🛠️ Tech Stack

| Category | Technology | Purpose |
|----------|-----------|---------|
| **Data Processing** | ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) | Data manipulation & analysis |
| **ML/Clustering** | ![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) | K-means clustering & metrics |
| **Visualization** | ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=python&logoColor=white) ![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat&logo=python&logoColor=white) | Static plots & statistical graphics |
| **Interactive Viz** | ![Plotly](https://img.shields.io/badge/Plotly-239120?style=flat&logo=plotly&logoColor=white) | Interactive exploration |
| **Financial Data** | ![yfinance](https://img.shields.io/badge/yfinance-FFB000?style=flat&logo=yahoo&logoColor=white) | Historical financial data retrieval |
| **Statistical Analysis** | ![Statsmodels](https://img.shields.io/badge/Statsmodels-3776AB?style=flat&logo=python&logoColor=white) | Linear regression & statistical tests |
| **ML Visualization** | ![Yellowbrick](https://img.shields.io/badge/Yellowbrick-3776AB?style=flat&logo=python&logoColor=white) | ML evaluation visualizations |

**Dependencies:** NumPy, SciPy, Warnings management

---


## 📈 Analysis Workflow

1. **Data Preparation**
   - Load financial dataset (symbol, beta, log market cap, P/E ratio, debt ratio, price-to-book ratio)
   - Standardize numerical features
   - Remove outliers using quantile-based filtering

2. **Cluster Optimization**
   - Elbow method: Identify optimal k by minimizing inertia
   - Silhouette analysis: Validate cluster separation quality
   - Compare metrics to select final clustering

3. **Cluster Characterization**
   - Compute mean financial metrics per cluster
   - Analyze distribution and size of clusters
   - Identify dominant financial characteristics

4. **Enterprise Value Modeling**
   - Correlation analysis with financial metrics
   - Multiple linear regression to identify value drivers
   - Interpret significant relationships

---

## 🔍 Key Visualizations

### 1. Pairplot Analysis
<img width="883" height="884" alt="image" src="https://github.com/user-attachments/assets/e04d26fd-cee1-42db-8b2d-aa129a217699" />

- **Purpose:** Identify correlations and outliers in financial metrics
- **Finding:** Visible outliers in P/E ratio, debt ratio, and price-to-book metrics

### 2. Elbow Method Visualization
<img width="544" height="359" alt="image" src="https://github.com/user-attachments/assets/9356c6e3-871c-48d5-9f51-29d2ccf78d64" />

- **Purpose:** Determine optimal number of clusters using distortion curve
- **Result:** Clear elbow suggests 6 clusters as optimal balance point

### 3. Silhouette Score Analysis
<img width="495" height="386" alt="image" src="https://github.com/user-attachments/assets/a58a6094-e074-4587-b4cf-c9f68d9ed201" />

<img width="495" height="386" alt="image" src="https://github.com/user-attachments/assets/074eed92-fcd3-4873-8878-96b3a6ceb730" />

<img width="512" height="386" alt="image" src="https://github.com/user-attachments/assets/b6c13490-a49c-4175-9608-8b8ec14fba2f" />

- **Purpose:** Evaluate cluster separation across k=2 to 7
- **Result:** Peak silhouette score at k=4, indicating best within-cluster cohesion

### 4. Cluster Distribution
<img width="498" height="359" alt="image" src="https://github.com/user-attachments/assets/0a2ccf8f-29a5-4bf6-bafa-4e971d2db82c" />

- **Purpose:** Show company distribution across identified clusters
- **Finding:** Balanced distribution with clusters 5, 2, 4 containing majority of companies

### 5. Mean Metrics by Cluster
<img width="1171" height="353" alt="image" src="https://github.com/user-attachments/assets/b44d27ba-b47d-4102-a88a-351731b921f2" />

- **Purpose:** Compare financial profiles across clusters
- **Finding:** Each cluster dominates 1-2 financial metrics, confirming distinct profiles

### 6. Enterprise Value Heatmap
<img width="535" height="423" alt="image" src="https://github.com/user-attachments/assets/e194a23e-4612-471e-ac0e-afac70e04020" />

- **Purpose:** Visualize correlation matrix of all variables
- **Result:** Weak individual correlations with enterprise value, suggesting multivariate effects

### 7. Linear Regression Results
- **Purpose:** Quantify impact of financial metrics on enterprise value
- **Finding:** Market cap and debt ratio are significant positive predictors

---

## 💡 Insights & Interpretations

### What This Means

1. **Market Efficiency**: The weak individual correlations with enterprise value suggest that company valuation is complex and requires considering multiple factors simultaneously.

2. **Cluster Validity**: Each cluster represents a distinct financial profile, making them potentially useful for:
   - Portfolio construction
   - Peer group analysis
   - Investment categorization

3. **Risk Assessment**: Beta clustering reveals market sensitivity patterns, useful for risk management and diversification strategies.

4. **Size Effect**: Dominant presence of large-cap companies (Cluster 5) in the dataset suggests survivorship bias.

---

## ⚠️ Limitations & Considerations

- **Unsupervised Method**: Clusters don't necessarily represent real-world investment categories
- **Data Sensitivity**: Results sensitive to k selection; cross-validation recommended
- **Size Imbalance**: Clusters 1 & 3 are smaller, potentially containing outliers
- **Feature Selection**: Analysis limited to 5 financial metrics; additional metrics may improve clustering
- **Point-in-Time Analysis**: Financial metrics are snapshots; temporal trends not considered

---


## 📊 Methodology Notes

**Standardization**: All features standardized using StandardScaler before clustering to ensure equal feature weighting.

**Optimization**: K-means initialized with multiple random seeds to avoid local minima.

**Validation**: Silhouette score (range: -1 to 1) used to validate cluster quality.

---
