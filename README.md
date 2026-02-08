# Projection Space Exploration – Lifestyle Dataset

This project investigates how projection-based visualization techniques can be used
to explore and interpret high-dimensional lifestyle data. The focus is on uncovering
patterns, clusters, density variations, and outliers, and explaining these structures
in terms of the original physiological, activity-related, and nutritional features.

---

## 1. Dataset Overview

We use the **Lifestyle Dataset** from Kaggle:
https://www.kaggle.com/datasets/jockeroika/life-style-data

The dataset contains **20,000 samples** described by **54 features**, including:
- **Physiological attributes:** Age, BMI, fat percentage, heart rate metrics
- **Workout behavior:** Workout type, session duration, workout frequency, experience level
- **Nutritional information:** Caloric intake, macronutrient composition, water intake

The data is fully tabular, contains no missing values, and includes a mix of continuous
and categorical features, making it well-suited for projection-based exploration.

---

## 2. Research Questions & Motivation

The main goal of this project is to understand whether meaningful lifestyle patterns
emerge when projecting physiological, nutritional, and activity-related features into
a two-dimensional space.

Specifically, we investigate:
- Whether individuals naturally cluster based on **energy balance, body composition,
  and workout intensity**
- To what extent **categorical workout labels** explain separation compared to
  continuous lifestyle variables
- Whether projection methods reveal **gradients, dense regions, and outliers** that are
  difficult to observe in the original high-dimensional space

Projection-based visualization is particularly suitable here due to the large number
of interdependent continuous features, whose joint structure cannot be easily analyzed
using univariate or pairwise plots alone.

---

## 3. Preprocessing & Feature Encoding

- Numerical features were **standardized** to ensure comparable scales and meaningful
  distance computations.
- Categorical variables were **one-hot encoded**, preserving category information
  without introducing artificial ordering.
- Euclidean distance was used, as the final feature representation is continuous and
  normalized.

Features derived from others or used as labels were excluded from the projection and
instead used for visual encoding and interpretation.

---

## 4. Projection Methods

The following dimensionality reduction techniques were applied:

- **PCA (Principal Component Analysis)**  
  Used to obtain a global, linear overview of variance in the data and identify dominant
  contributing feature groups.

- **UMAP (Uniform Manifold Approximation and Projection)**  
  Applied to reveal non-linear, local structures and dense regions in the projection space.

- **t-SNE**  
  Used as a complementary non-linear projection to compare local neighborhood preservation
  with UMAP.

---

## 5. Pattern Selection & Clustering

To identify salient structures in the projection space, **DBSCAN** was applied to the
UMAP embedding. This density-based clustering approach allows the detection of coherent
clusters and outliers without assuming a predefined number of clusters.

Clusters were analyzed by aggregating and comparing their original feature distributions
to explain what differentiates them in the high-dimensional space.

---

## 6. Key Findings

- Global variance is primarily driven by **body composition, caloric intake, and
  caloric balance**, rather than workout type alone.
- PCA provides a coarse global structure but does not clearly separate lifestyle patterns.
- UMAP reveals well-defined local clusters and smooth gradients that are not visible
  in linear projections.
- Coloring the embeddings by caloric balance, BMI category, and calories burned exposes
  interpretable structure aligned with physiological and behavioral differences.
- DBSCAN identifies multiple lifestyle clusters with distinct profiles, which can be
  explained using a small subset of discriminative features.

---

## 7. Limitations & Lessons Learned

- Different projection methods emphasize different aspects of the data; no single
  embedding captures all relevant structure.
- Clustering results depend on both the chosen projection and hyperparameters.
- Global distances in non-linear embeddings should be interpreted with caution.

---

## 8. Outputs

- `Solution.ipynb` – Full analysis notebook  
- `Solution.html` – Static HTML export for GitHub preview

---

## 9. Repository Structure

- `data/` – Input datasets  
- `export/` – Notebook exports  
- `Solution.ipynb` – Final notebook  
- `Solution.html` – Rendered HTML version  
- `README.md` – Project report  
- `environment.yml` – Environment specification
