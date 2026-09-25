# Iris Flower Classification — Internship Task Report

## 1. Objective

Train a machine learning model to classify Iris flowers into one of three
species — **Setosa**, **Versicolor**, or **Virginica** — based on four
physical measurements, and evaluate how accurately it performs on unseen data.

## 2. Dataset

The classic **Iris dataset** (originally collected by Ronald Fisher, 1936;
hosted by the UCI Machine Learning Repository) is used. It is built directly
into Scikit-learn (`sklearn.datasets.load_iris`), so no manual download step
is required — this also guarantees a clean, well-formatted dataset with no
missing values.

| Property | Value |
|---|---|
| Samples | 150 (50 per species) |
| Features | 4 — sepal length, sepal width, petal length, petal width (all in cm) |
| Target classes | setosa, versicolor, virginica |
| Missing values | None |

A copy of the raw data is saved as `iris_dataset.csv` for reference.

## 3. Basic Classification Concepts

- **Classification** is a supervised learning task where a model learns to
  assign inputs to one of several predefined categories (here, a species),
  based on labeled training examples.
- **Features vs. Labels**: the 4 measurements are the *features* (inputs);
  the species is the *label* (output) the model learns to predict.
- **Train/Test Split**: the data is split so the model is trained on one
  portion (80%) and evaluated on a held-out portion (20%) it has never seen —
  this checks whether the model *generalizes* rather than just memorizing.
- **Stratified split**: the split preserves the original 50/50/50 class
  balance in both the train and test sets.
- **Feature scaling**: measurements are standardized (mean 0, standard
  deviation 1) before training, which matters for distance-based models like
  KNN and SVM.
- **Cross-validation**: in addition to the single train/test split, 5-fold
  cross-validation is run on the training data for a more robust accuracy
  estimate.

## 4. Exploratory Data Analysis

- `01_pairplot.png` — scatter plots of every feature pair, colored by
  species. **Petal length** and **petal width** separate the three species
  almost perfectly, while sepal measurements overlap more between
  versicolor and virginica.
- `02_correlation_heatmap.png` — petal length and petal width are very
  strongly correlated (≈0.96).
- `03_feature_boxplots.png` — distribution of each feature per species,
  confirming setosa is clearly distinct on petal measurements.

## 5. Models Trained

Five common classification algorithms were trained and compared on the same
train/test split:

| Model | Test Accuracy | 5-Fold CV Accuracy |
|---|---|---|
| **Support Vector Machine (RBF kernel)** | **96.7%** | 96.7% ± 3.1% |
| Logistic Regression | 93.3% | 95.8% ± 2.6% |
| K-Nearest Neighbors (k=5) | 93.3% | 96.7% ± 3.1% |
| Decision Tree | 93.3% | 94.2% ± 2.0% |
| Random Forest (200 trees) | 90.0% | 95.0% ± 1.7% |

See `04_model_comparison.png` for a visual comparison.

## 6. Best Model — Detailed Evaluation

**Support Vector Machine** performed best, with **96.7% accuracy** on the
test set (29/30 correct).

**Classification report:**

| Species | Precision | Recall | F1-score |
|---|---|---|---|
| setosa | 1.00 | 1.00 | 1.00 |
| versicolor | 1.00 | 0.90 | 0.95 |
| virginica | 0.91 | 1.00 | 0.95 |

- **Setosa** is classified perfectly every time — it's linearly separable
  from the other two species.
- The only error: **one versicolor sample was misclassified as virginica**
  (see `05_confusion_matrix.png`) — these two species are the most visually
  and measurement-wise similar, which is a well-known characteristic of this
  dataset.

## 7. How to Reproduce

```bash
pip install scikit-learn pandas matplotlib seaborn joblib
python iris_classification.py
```

All outputs (CSV data, plots, trained model, and this report's source
numbers) are regenerated in the `outputs/` folder.

## 8. Files Included

- `iris_classification.py` — full, commented pipeline (load → EDA → train →
  evaluate → save)
- `iris_dataset.csv` — the raw dataset
- `model_comparison.csv` — accuracy of all 5 models
- `results_summary.txt` — plain-text run log
- `best_iris_model.joblib` / `scaler.joblib` — the trained model, ready to
  reuse for predictions
- `01_pairplot.png`, `02_correlation_heatmap.png`, `03_feature_boxplots.png`,
  `04_model_comparison.png`, `05_confusion_matrix.png` — all EDA and
  evaluation charts

## 9. Conclusion

A simple SVM classifier reaches **96.7% accuracy** distinguishing three Iris
species from just four measurements, confirming that petal length and width
in particular carry almost all the information needed for this task. This
demonstrates the core classification workflow: load data → explore →
split → train → evaluate — the same pattern used for most supervised
learning problems.
