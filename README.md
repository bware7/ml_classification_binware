# ml_classification_binware

## Overview
This project classifies SMS messages as "spam" or "ham" (not spam) using machine learning. I trained and compared two models—Logistic Regression and Random Forest—on the Kaggle SMS Spam Collection dataset. The goal was to predict spam accurately, a practical task for filtering unwanted messages.

- **Author**: Bin Ware
- **Date**: April 06, 2025
- **Notebook**: [classification_binware.ipynb](https://github.com/bware7/ml_classification_binware/classification_binware.ipynb)

## Dataset
The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset), contains 5572 SMS messages (87% ham, 13% spam). I used TF-IDF vectors (3000 features) from the text as input and a binary label (0 = ham, 1 = spam) as the target. It’s stored in `data/spam.csv`.

## Key Results
- **Logistic Regression**: Accuracy: 0.9695, Recall: 0.7718, Precision: 1.0000, F1-Score: 0.8712
- **Random Forest**: Accuracy: 0.9767, Recall: 0.8255, Precision: 1.0000, F1-Score: 0.9044
- Random Forest outperformed Logistic Regression, especially in recall, catching more spam despite the dataset’s imbalance.

## Setup Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/bware7/ml_classification_binware.git
   cd ml_classification_binware
   ```

2. **Set Up Virtual Environment**:
   ```bash
    Windows: py -m venv .venv then .\.venv\Scripts\activate
    Mac/Linux: python3 -m venv .venv then source .venv/bin/activate
    ```

3. **Install Dependencies:**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Run the Notebook:**:
   - Open classification_binware.ipynb in Jupyter or VS Code.
   - Select the .venv kernel and run all cells.


## Highlights

- Preprocessed text with TF-IDF to capture spam patterns.
- Explored data imbalance and message length trends.
- Compared models, showing Random Forest’s edge in spam detection.
- Reflections in the notebook detail my process and insights.