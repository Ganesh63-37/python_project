# python_project
# Banking Loan Approval Analysis

An Exploratory Data Analysis (EDA) project evaluating the factors that influence bank loan approvals. This project analyzes customer demographics, financial metrics, and credit scores to identify patterns distinguishing approved from rejected loan applications.

## Dataset

The analysis is based on `LoanApproval.csv`, which contains 4,269 records and 13 initial features. 

*   **Target Variable:** `loan_status` (Approved: ~62% | Rejected: ~37%)
*   **Key Features:** 
    *   `no_of_dependents`, `education`, `self_employed`
    *   `income_annum`, `loan_amount`, `loan_term`
    *   `cibil_score` (renamed to `credit_score` during cleaning)
    *   Asset values (`residential_assets_value`, `commercial_assets_value`, `luxury_assets_value`, `bank_asset_value`)

## Prerequisites

The following Python libraries are required to run the Jupyter Notebook:
*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`

## Project Workflow

1.  **Data Loading & Inspection:** 
    *   Loaded data into a Pandas DataFrame.
    *   Verified dataset shape (4269, 13) and checked for missing or duplicated values (0 nulls, 0 duplicates found).
2.  **Data Cleaning:**
    *   Removed leading/trailing whitespaces from string/categorical columns using a custom `delete_space` function.
    *   Renamed the `cibil_score` column to `credit_score` for clarity.
3.  **Exploratory Data Analysis (EDA):**
    *   Calculated core metrics: total approval/rejection rates, average loan amount (15.13M), average income (5.05M), and average credit score (~600).
    *   Identified high-risk customers (credit score < 500), making up roughly 32.8% of the applications.
4.  **Feature Engineering:**
    *   Created a new categorical feature `credit_grp` segmenting credit scores into `low` (<500), `mid` (500-600), and `high` (>600) risk tiers.
5.  **Data Visualization:**
    *   **Correlation Heatmap:** Visualized relationships between continuous numerical variables.
    *   **Distributions:** Plotted histograms for annual income, loan amount, and residential asset values.
    *   **Categorical Breakdowns:** Created countplots for loan status distributions across self-employment, loan terms, and credit groups.
    *   **Outlier & Spread Analysis:** Utilized boxplots to map `no_of_dependents` and `credit_score` against loan status.
    *   **Scatter Plots:** Charted credit score vs. loan amount, differentiated by final loan status.

## Usage

1. Clone this repository.
2. Ensure the dataset `LoanApproval.csv` is updated to the correct local path (default in the notebook is `D:\LoanApproval.csv`).
3. Run the cells in `banking_loan_approvel.ipynb` sequentially to reproduce the data cleaning steps and visualizations.
