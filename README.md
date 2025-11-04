# 🌍 Country Development Classification Using Hierarchical Clustering

## 📘 Project Overview
This project classifies countries into development groups using **Hierarchical Clustering** (agglomerative and/or divisive).  
By analyzing socio-economic and demographic indicators, the aim is to discover natural groupings of countries (e.g., developed, developing, emerging) and provide interpretable visualizations such as dendrograms and cluster summaries.

---

## 📊 Dataset
- **Possible sources:** World Bank, UN, Gapminder, or a cleaned CSV containing country-level indicators.  
- **Typical features used (examples):**
  - GDP per capita (current US$)
  - Human Development Index (HDI)
  - Life expectancy at birth
  - Literacy rate / mean years of schooling
  - Unemployment rate
  - Poverty rate / Gini coefficient
  - Population density
  - Healthcare access indicators (physicians per 1,000, hospital beds)
  - Internet penetration / mobile subscriptions
- **Target:** No labeled target — unsupervised learning to discover clusters.

---

## 🧠 Algorithm Used
- **Hierarchical Clustering** (Agglomerative Clustering recommended)
  - Linkage methods: `ward`, `average`, `complete`, `single`
  - Distance metrics: Euclidean (common), Manhattan or others as needed
- **Supporting techniques:**
  - Standardization/Scaling (e.g., `StandardScaler`)
  - Dimensionality reduction for visualization (PCA or t-SNE)

---

## ⚙️ Steps Involved
1. **Load dataset** (CSV / API from World Bank or other sources).  
2. **Explore & clean data:** handle missing values, outliers, and inconsistent entries.  
3. **Feature selection & engineering:** derive per-capita or normalized indicators when needed.  
4. **Scale features** using StandardScaler or MinMaxScaler.  
5. **Choose distance metric & linkage** method; try multiple linkages for robustness.  
6. **Build hierarchical clustering model** (e.g., `sklearn.cluster.AgglomerativeClustering`) or compute linkage matrix (`scipy.cluster.hierarchy.linkage`).  
7. **Plot dendrogram** to inspect cluster formation and choose number of clusters.  
8. **Cut the dendrogram** at chosen level or set `n_clusters` to obtain cluster labels.  
9. **Evaluate clusters** using silhouette score, Davies–Bouldin index, and cluster stability checks.  
10. **Analyze clusters:** compute summary statistics per cluster (mean GDP, HDI, etc.), map clusters on world map, and visualize with radar charts / boxplots.  
11. **Interpret results & report insights.**

---

## 🔍 Evaluation & Visualization
- **Dendrogram:** primary tool for inspecting hierarchical structure and selecting cut height.  
- **Silhouette score:** numeric measure for cluster quality (note: for hierarchical clustering compute after assigning labels).  
- **Cluster profiles:** tables showing average values of features per cluster to interpret development levels.  
- **Geographic visualization:** map clusters by country (choropleth) to show spatial patterns.  
- **PCA / t-SNE scatter:** visualize high-dimensional separation in 2D.

---

## 📈 Expected Results & Insights
- Identification of groups such as highly developed, emerging economies, low-income countries, and outliers.  
- Insight into which indicators (e.g., GDP per capita vs. HDI vs. healthcare access) drive cluster separation.  
- Actionable visualizations for policymakers, NGOs, and researchers to prioritize interventions.

---

## 🛠️ Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-learn (`AgglomerativeClustering`, `StandardScaler`, `silhouette_score`)
- SciPy (`linkage`, `dendrogram`)
- Matplotlib, Seaborn, Plotly (for interactive plots)
- GeoPandas / Folium (for choropleth maps)
- Optional: PCA / t-SNE from scikit-learn

