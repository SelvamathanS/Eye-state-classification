# Eye Detection Classification

## Overview

This project builds and compares multiple machine learning models to classify **eye detection status (`EYEDETECTION`)** using data stored in **Snowflake**.
Models evaluated:

* K-Nearest Neighbors (KNN)
* Naive Bayes
* Logistic Regression

## Data Source

* Data is fetched from a **Snowflake** database using `snowflake-connector-python`.
* Table queried: `EYE` (schema: `PUBLIC`, database: `EYE`)

## Tech Stack

* Python
* Snowflake Connector
* Pandas, NumPy
* Scikit-learn
* Matplotlib

## Workflow

1. Connect to Snowflake and load data into a Pandas DataFrame
2. Split features and target (`EYEDETECTION`)
3. Apply appropriate feature scaling:

   * Normalizer for KNN
   * MinMaxScaler for Naive Bayes
   * No scaling for Logistic Regression
4. Train and evaluate models using accuracy
5. Compare model performance using a bar chart

## Models & Preprocessing

* **KNN**

  * Normalizer
  * `n_neighbors = 5`
* **Naive Bayes**

  * MinMax Scaling
  * GaussianNB
* **Logistic Regression**

  * Default configuration

## Evaluation

* Metric used: **Accuracy**
* Train/Test split: **80/20**
* Random state: `42`

## Output

* Accuracy score for each model
* Bar chart comparing model accuracies

## How to Run

1. Install dependencies:

   ```bash
   pip install snowflake-connector-python pandas numpy scikit-learn matplotlib
   ```
2. Update Snowflake credentials in the script
3. Run the notebook or Python script
