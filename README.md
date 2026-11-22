# Advanced Data Mining for Data-Driven Insights and Predictive Modeling

## Project Deliverable 1: Data Collection, Cleaning, and Exploration

### Dataset

This project uses the **California Housing** dataset, available through the `sklearn.datasets` module in Scikit-learn (`fetch_california_housing`). It is the same dataset used in Deliverables 2 and 3.

- **Number of records:** 20,640 (one record per census block group)
- **Predictor attributes:** 8 numeric attributes (`MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`)
- **Target variable:** `median_house_value`, expressed in units of $100,000 (for example, 2.0 represents $200,000)

The dataset meets the assignment requirement of at least 500 records and 8–10 attributes, and it provides numeric measurements that can be explored through descriptive statistics and visualizations.

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
2.  Loads the California Housing dataset.
3.  Creates a Pandas DataFrame and renames the target to `median_house_value`.
4.  Inspects the dataset dimensions, column names, data types, and summary statistics.
5.  Checks for missing values and handles any that are present.
6.  Checks for duplicate records and removes duplicates if found.
7.  Checks the target range, the value ceiling, infinite values, and numeric data.
8.  Identifies potential outliers using the Interquartile Range (IQR) method.
9.  Creates visualizations to examine selected feature distributions and potential outliers.
10. Examines the target distribution and feature relationships using plots and a correlation heatmap.
11. Compares selected attributes across median house value quartile bands.
12. Saves the cleaned dataset as `california_housing_cleaned.csv`.
13. Summarizes the findings to guide future modeling work.

### Data Cleaning

The notebook checks every column for missing values. If missing numeric values are found, they are filled using the median of the corresponding column. The California Housing data arrives complete, so no values were filled in this run.

Duplicate rows are identified and removed. Numeric columns are also checked for positive or negative infinity; any such values are replaced with missing values and then filled using the column median.

The target is capped at 5.0. The notebook counts the records at that ceiling (27 records, 0.13%) and reports them rather than changing them, because the true prices for those blocks are unknown.

Potential outliers are identified using the IQR rule. They are reviewed rather than automatically removed because extreme block-group averages may represent genuine observations, such as sparsely populated areas, and may contain useful information.

### Exploratory Data Analysis

The notebook includes:

-   A histogram of the target, marking the 5.0 ceiling.
-   Histograms to examine the distributions of selected attributes.
-   Boxplots to inspect potential outliers.
-   A correlation heatmap to examine relationships among numeric attributes.
-   Boxplots comparing selected attributes across median house value quartile bands.
-   A table of the strongest numeric feature correlations.

These analyses help identify patterns, differences between value bands, and relationships among features. The findings can inform feature selection and preparation for later modeling.

### Key Findings

- Median income has the strongest positive correlation with median house value (r ≈ 0.69 on the full dataset).
- The target is right-skewed (mean about 2.07, median about 1.80) and capped at 5.0, so the top of the price range is partly censored.
- The IQR method flags about 2.5% of records for average rooms, 3.4% for average occupancy, and 5.8% for population. Many are real block-group averages from sparsely populated areas, so they were reviewed rather than removed.
- Latitude and longitude are strongly negatively correlated with each other (r ≈ −0.93), so geography is largely a single signal.

### Challenges and How They Were Addressed

-   **Dataset access:** The dataset is loaded directly from Scikit-learn, avoiding the need to download and manually upload a separate dataset file.
-   **Data quality checks:** Missing values, duplicates, the target range and ceiling, and infinite numeric values are checked.
-   **Potential outliers:** The IQR method is used to flag unusual values. They are retained for review rather than removed without justification.
-   **Feature relationships:** A correlation matrix and heatmap are used to make relationships among numeric attributes easier to inspect.
-   **Plotting compatibility:** A seaborn histogram raised an error with the installed pandas version, so the target histogram uses Matplotlib directly.
-   **Reproducibility:** The notebook contains the code needed to load, inspect, clean, visualize, and save the dataset.

### Files

-   `Deliverable_1_Data_Collection_Cleaning_Exploration.ipynb` --- Jupyter Notebook containing the code and analysis.
-   `california_housing_cleaned.csv` --- Cleaned dataset generated when the notebook is run.

### How to Run

1.  Open [Google Colab](https://colab.research.google.com/).
2.  Select **File → Upload notebook**.
3.  Upload `Deliverable_1_Data_Collection_Cleaning_Exploration.ipynb`.
4.  Select **Runtime → Run all**.
5.  After execution, download `california_housing_cleaned.csv` from the Colab Files panel if you need to include it in the repository.

### Future Work

The cleaned dataset and exploratory findings will support the next project stages. Deliverable 2 focuses on feature engineering, regression modeling, model evaluation, and cross-validation. Later deliverables address classification, clustering, association rule mining, and final recommendations.
