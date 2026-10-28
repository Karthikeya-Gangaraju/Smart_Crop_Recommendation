# Smart Crop Recommendation Using Machine Learning

## Overview
This project builds a machine learning workflow that recommends a crop from soil nutrient measurements and environmental conditions. It follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) methodology.

The notebook inspects and prepares a crop dataset, explores class distribution and feature correlations, trains four classification models, evaluates them, saves the selected model, and demonstrates a crop recommendation.

## Objectives
- Load and inspect the crop-recommendation dataset.
- Check missing values and duplicate records.
- Explore crop-class distribution and numerical-feature correlations.
- Prepare the input features and target label.
- Split the data into stratified training and testing sets.
- Compare Logistic Regression, Decision Tree, KNN, and SVM.
- Evaluate models using accuracy, macro precision, macro recall, and macro F1-score.
- Examine the selected model with a classification report and confusion matrix.
- Save the selected model and demonstrate a crop recommendation.

## Dataset
Expected dataset file: `Crop_recommendation.csv`

The dataset contains seven input features and one target column:

| Column | Description |
|---|---|
| `N` | Nitrogen |
| `P` | Phosphorus |
| `K` | Potassium |
| `temperature` | Temperature |
| `humidity` | Humidity |
| `ph` | Soil pH |
| `rainfall` | Rainfall |
| `label` | Crop class / target label |

The recorded dataset contains 2,200 records, seven input features, and 22 crop classes, with 100 records per class. The notebook checks for missing values and duplicates.

The notebook reads the dataset from `/content/Crop_recommendation.csv` in Google Colab. Upload or place the file at that location before running the notebook.

> Note: The report identifies the dataset as consistent with a publicly available crop recommendation dataset, but the exact source of the supplied CSV should be confirmed and cited before submission.

## Models
The notebook compares:
1. Logistic Regression
2. Decision Tree Classifier
3. K-Nearest Neighbors (KNN)
4. Support Vector Machine (SVM)

These are classification algorithms because the output is one of 22 crop labels. They align with the Logistic Regression, Decision Tree, KNN, and SVM topics listed in the lab syllabus.

## Workflow (CRISP-DM)
1. **Business Understanding** — formulate crop recommendation as a 22-class classification problem.
2. **Data Understanding** — inspect the dataset, missing values, duplicates, crop counts, and feature correlations.
3. **Data Preparation** — remove duplicate rows if present, select features and target, use imputation/scaling pipelines where implemented, and perform a stratified 80:20 split.
4. **Modelling** — train the four classifiers.
5. **Evaluation** — compare accuracy, macro precision, macro recall, and macro F1-score; inspect the classification report and confusion matrix.
6. **Deployment** — save the selected model and demonstrate a recommendation function.

## Train/Test Split
The notebook uses:
- Training records: 1,760
- Testing records: 440
- `test_size=0.20`
- `random_state=42`
- `stratify=y`

Stratification preserves the class proportions in the training and testing sets.

## Recorded Evaluation Results
Verify the metrics after your final notebook run.

| Model | Accuracy |
|---|---:|
| SVM | 98.41% |
| Decision Tree | 97.95% |
| KNN | 97.95% |
| Logistic Regression | 97.27% |

The notebook ranks models using **macro F1-score**, not accuracy alone. The recorded output ranks SVM first, with macro F1-score approximately 0.984038. Use the latest notebook output if results change after rerunning.

## Evaluation Metrics
- **Accuracy:** proportion of test predictions that are correct.
- **Macro precision:** average of per-class precision, giving each crop class equal weight.
- **Macro recall:** average of per-class recall, giving each crop class equal weight.
- **Macro F1-score:** average of per-class F1-scores; the notebook uses this metric to rank models.

## Requirements
The notebook uses common Python data-science and machine-learning libraries, including:
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- joblib

Refer to the notebook's import cells for the exact requirements.

## How to Run in Google Colab
1. Download `Smart_Crop_Recommendation_Syllabus_Aligned.ipynb`.
2. Open Google Colab: https://colab.research.google.com/
3. Select **File → Upload notebook** and upload the `.ipynb` file.
4. Upload or place `Crop_recommendation.csv` at `/content/Crop_recommendation.csv`.
5. Run the notebook cells from top to bottom.
6. Review the exploratory graphs, model comparison table, classification report, confusion matrix, and example recommendation.
7. Confirm that the selected model file is generated successfully.

## Limitations
- The model learns patterns from the supplied dataset and does not guarantee suitability for every farm, region, season, or field condition.
- The notebook uses a stratified hold-out test split; it does not perform cross-validation or hyperparameter tuning.
- Recommendations do not account for all real-world considerations, such as local weather forecasts, soil testing quality, crop prices, irrigation availability, or farmer-specific constraints.
- The notebook saves a model and demonstrates prediction; it is not a deployed website, mobile app, API, or production application.

## Project Files
- `Smart_Crop_Recommendation_Syllabus_Aligned.ipynb` — notebook containing data preparation, EDA, model training, evaluation, and prediction.
- `Crop_recommendation.csv` — required input dataset.
- A trained model file — generated by the notebook when its save cell is run.

## Author
- Name: G. Karthikeya
- Roll Number: 24501A4414
- Branch: CSD

Update the author details if this README is being used by another student.
