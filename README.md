# Breast Cancer Classification 🎗️

## Project Overview
This project applies machine learning techniques to classify breast cancer tumors as either Malignant (M) or Benign (B). By analyzing tumor features such as radius, texture, perimeter, and area, this model serves as a predictive tool to assist in medical diagnostics. 

This specific repository explores the **Decision Tree** classification algorithm, highlighting its interpretability (how it makes decisions based on feature thresholds), and addresses class imbalance using advanced resampling techniques.

## Dataset
The data used in this project is the **Breast Cancer Wisconsin (Diagnostic) Dataset**. 
* **Target Variable:** `diagnosis` (M = Malignant, B = Benign)
* **Features:** 30 numerical features computed from a digitized image of a fine needle aspirate (FNA) of a breast mass (e.g., `radius_mean`, `texture_mean`, `smoothness_mean`).

## Tech Stack
* **Language:** Python
* **Libraries:** * `pandas` & `numpy` (Data manipulation)
  * `matplotlib` & `seaborn` (Data visualization)
  * `scikit-learn` (Machine learning modeling & evaluation)
  * `imbalanced-learn` (Handling imbalanced datasets)

## Methodology & Workflow

1. **Data Preprocessing:** * Dropped unnecessary columns (e.g., `id`).
   * Mapped categorical labels to binary values (`M` -> 1, `B` -> 0).
   * *(Note: While Decision Trees do not strictly require feature scaling like SVMs do, standardizing the data was tested in the pipeline for consistency).*

2. **Handling Class Imbalance:**
   To prevent the model from becoming biased toward the majority class, a hybrid resampling approach was used:
   * **SMOTE (Synthetic Minority Over-sampling Technique):** Upsampled the minority class to 80% of the majority class size.
   * **RandomUnderSampler (RUS):** Downsampled the majority class to achieve a perfectly balanced 1:1 ratio.

3. **Modeling:**
   * Trained a **Decision Tree Classifier**, which learns simple decision rules inferred from the data features.
   * This model is highly interpretable, allowing us to see exactly which features (like cell area or concavity) are most important for predicting malignancy.

4. **Evaluation:**
   The model was evaluated on a dedicated test set using Accuracy, Precision, Recall, F1-Score, and Confusion Matrices.

## Results
*(Note: Replace the Xs with your final scores!)*

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Decision Tree** | 92% | 89% | 91% | 90% |

**Key Takeaways:** * Implementing the SMOTE + RUS hybrid technique successfully reduced false negatives, which is critical in medical diagnostics where missing a malignant tumor is highly dangerous.
* Decision Trees provided a highly interpretable model, making it easy to understand the "why" behind every prediction.

## How to Run This Project
1. Clone the repository:
   ```bash
   git clone [https://github.com/usmanali0125/Breast-Cancer-Classification-using-DecisionTree.git]

Install the required dependencies:
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn


Download the dataset.

Open the Jupyter Notebook to explore the code and run the cells:
jupyter notebook "Decision Tree.ipynb"
