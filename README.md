# Advanced Data Mining for Data-Driven Insights and Predictive Modeling

## Project Deliverable 1: Data Collection, Cleaning, and Exploration

### Dataset

This project uses the **Breast Cancer Wisconsin Diagnostic Dataset**,
available through the `sklearn.datasets` module in Scikit-learn.

The dataset contains 569 records and 30 numeric predictor attributes.
The target variable, `diagnosis`, identifies each record as either
malignant or benign. The dataset is suitable for this project because it
meets the assignment requirement of at least 500 records and 8--10
attributes and provides numeric measurements that can be explored
through descriptive statistics and visualizations.

### Tools and Libraries

-   Python
-   Google Colab / Jupyter Notebook
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Scikit-learn

### Project Work Completed

The Jupyter Notebook carries out the following steps:

1.  Imports the required Python libraries.
2.  Loads the Breast Cancer Wisconsin Diagnostic Dataset.
3.  Creates a Pandas DataFrame and adds the diagnosis target column.
4.  Inspects the dataset dimensions, column names, data types, and
    summary statistics.
5.  Checks for missing values and handles any that are present.
6.  Checks for duplicate records and removes duplicates if found.
7.  Checks diagnosis categories, infinite values, and numeric data.
8.  Identifies potential outliers using the Interquartile Range (IQR)
    method.
9.  Creates visualizations to examine selected feature distributions and
    potential outliers.
10. Examines diagnosis counts and feature relationships using plots and
    a correlation heatmap.
11. Compares selected numeric attributes across the diagnosis
    categories.
12. Saves the cleaned dataset as `breast_cancer_cleaned.csv`.
13. Summarizes the findings to guide future modeling work.

### Data Cleaning

The notebook checks every column for missing values. If missing numeric
values are found, they are filled using the median of the corresponding
column. If the diagnosis target has missing values, the mode is used.

Duplicate rows are identified and removed. Numeric columns are also
checked for positive or negative infinity; any such values are replaced
with missing values and then filled using the column median.

Potential outliers are identified using the IQR rule. They are reviewed
rather than automatically removed because extreme measurements may
represent genuine observations and may contain useful information.

### Exploratory Data Analysis

The notebook includes:

-   A diagnosis count plot to show the distribution of malignant and
    benign records.
-   Histograms to examine the distributions of selected numeric
    attributes.
-   Boxplots to inspect potential outliers.
-   A correlation heatmap to examine relationships among numeric
    attributes.
-   Boxplots comparing selected measurements across diagnosis
    categories.
-   A table of the strongest numeric feature correlations.

These analyses help identify patterns, differences between diagnosis
groups, and relationships among features. The findings can inform
feature selection and preparation for later modeling.

### Key Findings

In the jupyter notebook.

### Challenges and How They Were Addressed

-   **Dataset access:** The dataset is loaded directly from
    Scikit-learn, avoiding the need to download and manually upload a
    separate dataset file.
-   **Data quality checks:** Missing values, duplicates, inconsistent
    target categories, and infinite numeric values are checked.
-   **Potential outliers:** The IQR method is used to flag unusual
    values. They are retained for review rather than removed without
    justification.
-   **Feature relationships:** A correlation matrix and heatmap are used
    to make relationships among numeric attributes easier to inspect.
-   **Reproducibility:** The notebook contains the code needed to load,
    inspect, clean, visualize, and save the dataset.

### Files

-   `Deliverable_1_Data_Collection_Cleaning_Exploration.ipynb` ---
    Jupyter Notebook containing the code and analysis.
-   `breast_cancer_cleaned.csv` --- Cleaned dataset generated when the
    notebook is run.

### How to Run

1.  Open [Google Colab](https://colab.research.google.com/).
2.  Select **File → Upload notebook**.
3.  Upload `Deliverable_1_Data_Collection_Cleaning_Exploration.ipynb`.
4.  Select **Runtime → Run all**.
5.  After execution, download `breast_cancer_cleaned.csv` from the Colab
    Files panel if you need to include it in the repository.

### Future Work

The cleaned dataset and exploratory findings will support the next
project stages. Deliverable 2 will focus on feature engineering,
regression modeling, model evaluation, and cross-validation. Later
deliverables will address classification, clustering, association rule
mining, and final recommendations.
