# Deep Learning–Based Cosmetic Sales Prediction

This project explores whether customer purchase behaviour for cosmetic products can be predicted using transactional, demographic, and engagement data. The goal was to evaluate the feasibility of predictive modeling in a realistic marketing and retail analytics setting, rather than to force high accuracy where the data does not support it.

---

## Problem Statement

Given customer, product, pricing, and engagement attributes, predict whether a customer will purchase a cosmetic product. The target variable is binary (`Sales_Prediction`), indicating purchase or non-purchase.

The project also explores whether the same data can support basic customer segmentation and product recommendation use cases.

---

## Dataset Overview

The dataset contains:
- **18 features** including price, rating, age, engagement metrics (likes, shares, comments), campaign indicators, seasonality, brand, product type, skin type, income level, and location
- **Binary target variable** indicating purchase behaviour
- Both numerical and categorical variables, requiring careful preprocessing

Initial exploration showed weak correlations between most features and the target variable, making this a challenging prediction task.

---

## Data Exploration & Feature Engineering

Key steps included:
- Descriptive statistics and correlation analysis
- Point-biserial correlation for numerical vs binary target
- Cramér’s V for categorical associations
- PCA and UMAP for visual inspection of class separability
- Feature engineering such as:
  - Mean purchase rates at customer, product, brand, and product-type levels
  - Aggregated spending behaviour
  - Campaign response rates
  - Binning of age into groups

Despite extensive exploration, no strong natural separation between purchasers and non-purchasers was observed.

---

## Modeling Approach

Multiple models were tested to assess predictive potential:

### Models Implemented
- Artificial Neural Network (ANN)
- Logistic Regression
- Random Forest
- KMeans clustering for behavioural segmentation
- Stacked ANN + Random Forest (exploratory)

### ANN Architecture
- 4 hidden layers (100, 64, 48, 16 units)
- ReLU activation
- Dropout (40%)
- L1 regularization
- Adam optimizer
- Binary cross-entropy loss

Hyperparameter tuning was attempted using Optuna, but performance improvements were marginal.

---

## Results & Evaluation

- Model accuracy hovered around **50–53%**, close to random guessing
- Precision for purchasers (Class 1) was higher than recall for non-purchasers
- AUC-ROC scores remained close to 0.5 across models
- PCA, UMAP, and clustering confirmed weak class separability

Rather than indicating poor modeling, these results highlight a realistic scenario where available features do not strongly explain purchase behaviour.

---

## Recommendation System (Exploratory)

A basic collaborative filtering approach was implemented using:
- User–item interaction matrix
- Truncated SVD for dimensionality reduction
- Top-N product recommendations per customer

While exploratory and unvalidated due to lack of ground truth labels, this component demonstrates how the same data could support recommendation use cases even when classification performance is limited.

---

## Key Takeaways

- Not all business problems are prediction-friendly, even with advanced models
- Thorough exploration and honest evaluation are critical in applied analytics
- Weak performance can itself be a valuable insight for business decision-making
- Recommendation and segmentation approaches may be more suitable than pure classification in such contexts

---

## Tools & Technologies

- Python
- Pandas, NumPy, Scikit-learn
- TensorFlow / Keras
- Optuna
- Matplotlib, Seaborn
- PCA, UMAP

---

## Files

- `Deep_Learning_Cosmetic_Sales_Prediction_Report.html` – model development code in html
- `Deep_Learning_Cosmetic_Sales_Prediction_Report.pdf` – full analysis and discussion

---

## Author

Sneh Pahuja  
Business Analytics | Computer Science  
