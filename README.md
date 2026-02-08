# Projection Space Exploration – Lifestyle Dataset

This project explores a high-dimensional lifestyle dataset using projection-based
visualization techniques to uncover meaningful patterns, similarities, and differences
between individuals.

The analysis focuses on understanding how physiological, activity-related, and
nutritional features shape the projection space, and how these features explain
observed clusters, density variations, and outliers.

---
 
## Dataset

The dataset consists of **20,000 samples** described by **54 features**, covering:
- Physiological attributes (e.g., BMI, fat percentage, resting heart rate)
- Activity-related variables (e.g., workout frequency, session duration, calories burned)
- Nutritional information (e.g., caloric intake, macronutrient composition, water intake)

The data is fully tabular, contains no missing values, and includes a mix of continuous
and categorical features, making it well-suited for projection-based analysis.

---

## Methods

The following dimensionality reduction and analysis techniques were applied:

- **PCA (Principal Component Analysis)**  
  Used to obtain a global, linear overview of variance in the data and identify dominant
  contributing feature groups.

- **UMAP (Uniform Manifold Approximation and Projection)**  
  Applied to reveal non-linear, local structures and dense regions in the projection space.

- **t-SNE**  
  Used as a complementary non-linear projection for comparison.

- **DBSCAN Clustering (on UMAP space)**  
  Density-based clustering was applied to identify coherent lifestyle clusters and
  separate noise or outliers.

All features were standardized prior to projection. Categorical variables were encoded
using one-hot encoding where applicable.

---

## Key Findings

- Global variance in the data is primarily driven by **body composition**, **caloric intake**,
  and **energy balance**, rather than exercise type alone.
- UMAP reveals well-defined local structures and dense regions that are not visible in PCA.
- Coloring the projections by caloric balance, BMI category, and calories burned exposes
  smooth gradients and localized concentrations in the embedding.
- DBSCAN identifies multiple lifestyle clusters with distinct physiological and activity
  profiles, which can be explained using a small subset of discriminative features.

---

## Repository Structure

