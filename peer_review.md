# Peer Review

**Reviewed By**: Bin Ware  
**Date**: April 06, 2025  
**Notebook Reviewed**: [ml_classification_terry.ipynb](https://github.com/TKonkin/ml-classification-terry/blob/main/ml_classification_terry.ipynb)  

## Review

### 1. Clarity & Organization
- **Positive**: Numbered sections (1-6) and clear headings make it easy to follow. Intro states the goal, and imports are at the top.
- **Constructive**: Code lacks comments (e.g., why `titanic_gender` for `y_test`). Add brief notes like `# Use gender_submission for test target`. Mixing code/output in markdown is messy—keep outputs in code cells.

### 2. Feature Selection & Justification
- **Positive**: `Age` as feature and `Survived` as target fit the goal. Historical reasoning ("women and children prioritized") is solid.
- **Constructive**: Using only `Age` limits results. `Sex` is preprocessed but unused—add it to `X_train` for better accuracy. Explain why it’s commented out.

### 3. Model Performance & Comparisons
- **Positive**: Decision Tree (accuracy 0.54) and Logistic Regression (accuracy 0.64) are evaluated with reports and matrices. Comparison notes precision/recall differences.
- **Constructive**: A table (`| Model | Accuracy | Precision | Recall |`) would clarify results. Logistic Regression’s 0.00 recall for class 1 needs more focus—tie it to imbalance. Test data setup (`titanic_gender`) may skew results; validate or merge datasets.

### 4. Reflection Quality
- **Positive**: Reflections after each section show honesty (e.g., pre-split challenge, beginner perspective).
- **Constructive**: Reflections are short. Expand Reflection 4—why low accuracy (single feature?). Fix Reflection 5’s contradiction (Decision Tree “better” vs. lower accuracy). Specify 6.3 steps (e.g., “tune tree depth”).

## Suggestions
- **Add Comments**: Use `# Median age for NaNs` to explain steps, especially test data logic.
- **Use `Sex`**: Train with `X_train = titanic_train[['Age', 'Sex']]`. It’s numeric and boosts survival prediction.
- **Table Comparison**: Add `| Model | Accuracy | Precision (0/1) | Recall (0/1) |` in 5.2 to highlight Logistic Regression’s class 1 failure.
- **Fix Imbalance**: Try `class_weight='balanced'` in `LogisticRegression` to address 0.38 `Survived` mean and fix recall.