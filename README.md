💧 PCA on Water Potability Data

RPubs Report: View Full Report
https://rpubs.com/Trang_Hoang/1262508

📘 Overview

This project applies Principal Component Analysis (PCA) to the Water Potability Dataset to identify the most influential variables affecting water quality.
PCA is used to reduce data dimensionality, explore relationships between water quality indicators, and evaluate whether the dataset’s structure allows meaningful component extraction for predicting potability.

🎯 Objectives

Apply PCA for dimensionality reduction and pattern discovery

Identify key components that explain the majority of data variance

Explore correlations between water quality features

Assess whether PCA can help distinguish potable vs. non-potable water samples

📊 Dataset

Source: Kaggle – Water Quality and Potability

The dataset includes 10 attributes describing physical and chemical water quality indicators:


| Variable          | Description                                    |
| ----------------- | ---------------------------------------------- |
| `pH`              | Acidity or alkalinity of water                 |
| `Hardness`        | Measure of mineral content                     |
| `Solids`          | Total dissolved solids                         |
| `Chloramines`     | Chloramine concentration                       |
| `Sulfate`         | Sulfate concentration                          |
| `Conductivity`    | Electrical conductivity                        |
| `Organic_carbon`  | Organic carbon content                         |
| `Trihalomethanes` | Trihalomethanes concentration                  |
| `Turbidity`       | Clarity of water                               |
| `Potability`      | Target variable (1 = potable, 0 = not potable) |

⚙️ Methodology
🔹 1. Data Preparation

Removed rows with missing values using complete.cases()

Normalized variables to standardize scale

Conducted correlation analysis and pairwise plots (GGally)

Observation:

Most variables have low correlation coefficients, suggesting weak linear relationships.

Slight correlation between Sulfate and Hardness (≈ 0.16), but overall weak interdependence.

🔹 2. PCA Implementation

Performed PCA with prcomp() after centering and scaling

Selected components using Kaiser criterion (eigenvalue > 1)

Visualized explained variance using fviz_eig()

Key Findings:

First 6 components explain about 71% of total variance

Variables contributing most to principal components:

Hardness, Solids, Sulfate, and pH

Components Dim-3 to Dim-7 reflect chemical and turbidity factors

🔹 3. Biplot Visualization

Created PCA biplots with ggbiplot() to observe grouping by Potability (0 vs. 1)

Both groups show significant overlap on PC1 and PC2 → No clear separation

Interpretation:

PC1 (12.1% variance) and PC2 (11.7% variance) are insufficient for discriminating water potability

PCA does not reveal distinct patterns between potable and non-potable samples

📈 Results Summary
Aspect	Observation
Correlation	Weak across all features
Key Variables	Hardness, Solids, Sulfate, pH
Variance Explained	~71% by first six components
Group Separation	Overlapping classes (0 & 1)
Conclusion	PCA is not effective for potability prediction due to low feature correlation  
🧰 Tools & Libraries

Language: R

Libraries:
corrplot, clusterSim, GGally, factoextra, ggbiplot, gridExtra, devtools

Environment: RStudio

👩‍💻 Author

Trang Hoang  
🎓 Master’s Student in Data Science & Business Analytics, University of Warsaw  
💼 Formerly @ MoMo E-Wallet | Shopee Vietnam | NielsenIQ  
📫 trangphuong83p@gmail.com  

🌐 RPubs Portfolio
https://rpubs.com/Trang_Hoang
