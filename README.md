### Bank_Campaign

The Business Objective is to increase term deposit subscriptions by identifying banking clients most likely to respond positively to direct telemarketing campaigns (y = 'yes'), enabling more effective customer targeting, higher conversion rates, and optimized marketing costs and resources.

### Analysis

The dataset contains **41,188 client records** with **20 input features** across client demographics, campaign contact details, and social/economic context indicators, alongside a binary target variable (`y`).

A baseline benchmark was created to establish a majority-class `DummyClassifier` predicting `'no'` for every client establishes the minimum performance threshold:
- Baseline Accuracy: 88.74%
- Baseline ROC-AUC: 0.5000
- Baseline F1-Score (`yes`): 0.0000

Dataset went through two phases
1) Simple Model
   - Client demographic features alone cannot push models past the **88.74% baseline accuracy**.
   - Unrestricted default `DecisionTreeClassifier` overfits the training data (`91.71%` train vs. `86.32%` test).
2) Improved Model
   - With the hyperparameter tuning and grid search, 
   - **Best Overall Model (Decision Tree):** Limiting tree depth (`max_depth=7`) eliminated overfitting, yielding the highest **ROC-AUC (`0.8060`)**, `90.11%` test accuracy, and a fast tuning time (`0.77s`).

### Conclusion 
Based on the the simple and improved models, I would recommend on using the improved model Decision Tree for lead ranking.  Decision Tree to score and rank customer call lists by subscription probability, providing call center managers with transparent, interpretable rules.

