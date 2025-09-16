### Predictive Fleet Maintenance

This project demonstrates an end-to-end Machine Learning Engineering pipeline to build a predictive maintenance solution for a fleet of industrial machines. The goal is to predict machine component failures in advance to enable proactive, cost-saving maintenance.

-----

### The Problem

Unplanned machine failures lead to significant costs for businesses, including lost revenue, expensive emergency repairs, and supply chain disruption. This project aims to solve this problem by developing a model that can forecast a machine's likelihood of failure within a specific time window.

-----

### The Solution: An End-to-End ML Pipeline

This project follows a complete ML Engineering lifecycle, from data processing to model deployment.

1.  **Data Engineering**: The core of this project involved transforming raw, multi-source data into a clean, model-ready dataset.

      * **Data Sources**: We integrated time-series telemetry data with event-based error, maintenance, and failure logs.
      * **Feature Engineering**: We created new, powerful features, including:
          * **Time since last maintenance** to capture the wear on a machine.
          * **Rolling counts of recent errors** to detect cumulative stress.
          * **Look-ahead binary labels** to predict failures within a 7-day window.

2.  **Modeling & Evaluation**: We used a two-step approach to build and evaluate our model.

      * **Baseline Model**: We trained a **Logistic Regression** model as a simple benchmark. We used **Precision**, **Recall**, and **F1-Score** to evaluate its performance, as accuracy is misleading for this highly imbalanced problem.
      * **Advanced Model**: We then trained a powerful **XGBoost** model to capture complex, non-linear relationships in the data.

3.  **Performance Analysis**: The final model was tuned to balance the trade-off between **Precision** (avoiding false alarms) and **Recall** (catching all failures).

-----

### Key Results

The XGBoost model significantly outperformed the baseline.

  * **Baseline (Logistic Regression)**
      * Precision: 0.25
      * Recall: 0.58
      * F1-Score: 0.35
  * **Final Model (XGBoost)**
      * Precision: 0.29
      * Recall: 0.95
      * F1-Score: 0.44

The high **Recall** of the final model (95%) is the most important result, as it shows the system is highly effective at catching impending failures.

-----

### How to Run the Project

The project is structured in a Jupyter Notebook. You will need to install the necessary libraries to run the code.

#### Prerequisites

  * Python 3.x
  * Jupyter Notebook
  * `pandas`
  * `scikit-learn`
  * `xgboost`
  * `joblib`

#### Installation

You can install all the required libraries using pip:

```bash
pip install pandas scikit-learn xgboost jupyter joblib
```

#### Steps

1.  Clone this repository to your local machine.
2.  Download the `PdM` dataset from [Kaggle](https://www.google.com/search?q=https://www.kaggle.com/datasets/sriharishetty1/predictive-maintenance-dataset).
3.  Place the CSV files in the project's root directory.
4.  Open the Jupyter Notebook and run the cells in order.
