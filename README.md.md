# Iris Flower Species Classification

A machine learning project that classifies iris flowers into three species — *Iris-setosa*, *Iris-versicolor*, and *Iris-virginica* — using sepal and petal measurements.

## Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Technologies Used](#technologies-used)
- [Project Workflow](#project-workflow)
- [Machine Learning Models](#machine-learning-models)
- [Evaluation](#evaluation)
- [Repository Structure](#repository-structure)
- [Installation and Usage](#installation-and-usage)
- [Results](#results)
- [Limitations](#limitations)
- [References](#references)

## Project Overview

The Iris Flower Classification project applies supervised machine learning to predict a flower's species from four numerical measurements. The workflow includes data inspection, exploratory data analysis, preprocessing, model comparison, test-set evaluation, and prediction for a new sample.

This project was developed as a machine learning internship task.

## Objectives

- Load and inspect the Iris dataset.
- Check for missing values, duplicate rows, and class distribution.
- Explore relationships between numerical features using visualizations.
- Prepare the data for model training.
- Compare multiple classification algorithms.
- Evaluate the selected model on a held-out test set.
- Demonstrate a prediction for a new flower sample.

## Dataset

The project is designed to use the Iris dataset available from Kaggle:

- **Dataset:** [Iris Species — Kaggle](https://www.kaggle.com/uciml/iris)
- **Expected observations:** 150
- **Species:** 3
- **Measurements:** 4 numerical features

### Features

| Feature | Description |
|---|---|
| `SepalLengthCm` | Sepal length in centimetres |
| `SepalWidthCm` | Sepal width in centimetres |
| `PetalLengthCm` | Petal length in centimetres |
| `PetalWidthCm` | Petal width in centimetres |
| `Species` | Target class of the flower |

The optional `Id` column is an identifier and is excluded from model training because it is not a flower measurement.

**Dataset note:** Ensure that `data/Iris.csv` contains the dataset required by your internship. If the task specifically requires the file downloaded from Kaggle, download it from the link above and place it in the `data` directory.

## Technologies Used

- **Python** — programming language
- **Pandas** — data loading and manipulation
- **NumPy** — numerical operations
- **Matplotlib** — plotting
- **Seaborn** — statistical visualizations
- **Scikit-learn** — preprocessing, model training, cross-validation, and evaluation
- **Joblib** — saving the trained model
- **Jupyter Notebook** — interactive development and analysis

## Project Workflow

1. **Load the data:** Read `Iris.csv` into a Pandas DataFrame.
2. **Inspect the data:** Review column names, data types, descriptive statistics, missing values, duplicate rows, and species counts.
3. **Explore the data:** Use pair plots, a correlation heatmap, and boxplots to investigate feature relationships.
4. **Prepare the features:** Separate the four measurement columns (`X`) from the target column (`y`).
5. **Split the dataset:** Use a stratified 80/20 train-test split with a fixed random seed.
6. **Preprocess:** Apply `StandardScaler` within each model pipeline. This ensures scaling is fitted on the relevant training data rather than the held-out test data.
7. **Compare models:** Evaluate candidate classifiers using stratified 10-fold cross-validation on the training set.
8. **Evaluate the selected model:** Fit the selected classifier on the full training set and evaluate it on the held-out test set.
9. **Make a prediction:** Demonstrate species prediction for a sample with four flower measurements.
10. **Save the model:** Export the fitted pipeline using Joblib.

## Machine Learning Models

The notebook compares these classification algorithms:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- Gradient Boosting

The model with the highest mean cross-validation accuracy is selected for the final test-set evaluation. The test set is kept separate from model selection.

## Evaluation

The notebook reports the following metrics:

- **Accuracy:** proportion of test samples classified correctly.
- **Precision:** proportion of predictions for a class that are correct.
- **Recall:** proportion of actual samples in a class that are identified correctly.
- **F1-score:** harmonic mean of precision and recall.
- **Confusion matrix:** counts correct predictions and misclassifications for each species.

It also visualizes cross-validation model comparison and Random Forest feature importance.

## Repository Structure

```text
iris-flower-classification/
├── Iris_Flower_Classification.ipynb
├── data/
│   └── Iris.csv
├── requirements.txt
├── .gitignore
└── README.md
```

The notebook saves the trained model as `iris_classifier.joblib` when its model-export cell is run. This generated file may be kept locally or committed to the repository if needed.

## Installation and Usage

### 1. Clone the repository

Replace `YOUR-USERNAME` with your GitHub username:

```bash
git clone https://github.com/YOUR-USERNAME/iris-flower-classification.git
cd iris-flower-classification
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the notebook

```bash
jupyter notebook
```

Open `Iris_Flower_Classification.ipynb` and run the cells in order, from top to bottom. Ensure that `data/Iris.csv` is in the expected location.

## Results

The notebook calculates cross-validation scores and final test-set metrics when executed.

In the recorded run included with this project, the selected Support Vector Machine model achieved **96.67% test accuracy** on 30 held-out samples. Results can vary if the dataset, split, model configuration, or software versions change. Re-run the notebook and confirm the outputs before reporting this figure as your final result.

## Limitations

- The Iris dataset is small and contains only three flower species.
- Results on this dataset do not guarantee similar performance on other flower datasets or real-world images.
- Test accuracy depends on the data split and model configuration.
- The model uses numerical measurements; it does not classify flower photographs.

## References

1. Kaggle. [Iris Species Dataset](https://www.kaggle.com/uciml/iris).
2. Scikit-learn. [Official Documentation](https://scikit-learn.org/stable/).
3. Pandas. [Official Documentation](https://pandas.pydata.org/docs/).
4. Matplotlib. [Official Documentation](https://matplotlib.org/stable/).
5. Seaborn. [Official Documentation](https://seaborn.pydata.org/).

---

**Project:** Iris Flower Species Classification  
**Task:** Machine Learning Internship  
