# Vessel-Flag-Change-Prediction

This notebook trains a binary classifier to predict whether a vessel will change its flag based on AIS ship attributes. It proceeds in clear, reproducible steps:
1. Load Data
* Read ais_shipinfo.csv and set up the working DataFrame

2. Clean & explore
* Remove exact duplicates and obvious invalid rows.
* Inspect distributions and outliers to understand scale and potential data issues.
* Check missing values to plan imputation.

3. Create the target
* Derive a binary label that marks vessels with a historical registry/flag change (1) vs. no change (0).
* Verify class balance to anticipate imbalance handling.

4. Feature engineering
* Build informative features (e.g., vessel age, time under current flag, selected numeric specs).
* Encode categorical fields (e.g., ship type, current flag).
* Optionally drop leaky or low-signal columns (IDs, raw text).

5. Train/validation split
* Split into train/test (e.g., 80/20) to evaluate generalization.

6. Preprocessing pipeline
* Scale numeric features for model stability
* Handle imbalance on the training set with SMOTE to reduce bias toward the majority class.
* Keep transformations in a single pipeline for clean, repeatable runs.

7. Modeling (Decision Tree)
* Fit a Decision Tree classifier as a strong, interpretable baseline.
* Tune depth/leaf settings to balance bias–variance.

8. Evaluation
* Report precision, recall, F1, accuracy and plot a confusion matrix to see error types.
* Show feature importance to understand key drivers of flag change.
