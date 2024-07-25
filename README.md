### Customer Segmentation (Clustering) Methodology

#### Summary

This project aims to analyze customer behavior and segment customers into distinct groups to enable targeted marketing strategies.

#### Data Preprocessing and Feature Engineering
The dataset, loaded into a pandas DataFrame, is first inspected for missing values using visualizations from the `missingno` library. Missing values are dropped, and duplicate rows are checked and removed.

Feature engineering involves creating new features such as `Age`, derived from `Year_Birth`, and `Spent`, calculated by summing various spending columns. Simplifications and transformations are applied to other columns: `Marital_Status` is recoded to `Living_With` to indicate partnership status, and `Children` is derived from `Kidhome` and `Teenhome`. `Family_Size` and `Is_Parent` are created to further describe household characteristics, and education levels are grouped into three categories. Redundant columns are dropped to streamline the dataset.

#### Exploratory Data Analysis (EDA)
EDA involves generating summary statistics and visualizing relationships between features. Scatter plots, histograms, and pie charts are used to explore distributions and correlations. Outliers in `Age`, `Income`, and `Spent` are detected using box plots and the IQR method, with extreme outliers removed to improve model performance.

#### Dimensionality Reduction and Clustering
The dataset is scaled using `StandardScaler` to normalize features. Principal Component Analysis (PCA) reduces the dataset to three principal components, retaining most of the variance and simplifying the data.

The optimal number of clusters is determined using the Elbow Method with `KElbowVisualizer`, identifying four clusters. Agglomerative Clustering segments the data, and the results are visualized in a 3D plot.

#### Cluster Analysis and Customer Profiling
**Cluster 0:** Low Spending, Low Income, Young Parents 
**Strategy:** Offer budget-friendly products and promotions targeting young families.
**Marketing:** Highlight discounts on essential household items and family-friendly events.

**Cluster 1:** Average Spending, Average Income, Older Parents with Teenagers
**Strategy:** Introduce mid-range products and value packs tailored to larger families.
**Marketing:** Promote back-to-school offers, family vacations, and parenting resources.

**Cluster 2:** High Spending, High Income, Non-Parents or Small Families
**Strategy:** Focus on premium products and exclusive experiences.
**Marketing:** Use targeted campaigns emphasizing luxury, quality, and exclusivity.

**Cluster 3:** Low Spending, Average Income, Older Parents
**Strategy:**  Provide loyalty programs and bundled deals to increase spending.
**Marketing:** Encourage repeat purchases through personalized offers and senior discounts.

