# Cafe Sales Dirty Sales Exploratory Data Analysis & Inference

## Description
This project is under DES432: Statistics and Data Modeling subject, focusing on cleaning and analyzing a dirty dataset of cafe sales to extract meaningful insights. The dataset is sourced from Kaggle and contains various inconsistencies, missing values, and incorrect formatting. The goal of this project is to perform data wrangling, handle missing values logically, and conduct Exploratory Data Analysis (EDA) to visualize sales trends.

## Dataset
- **Source**: Kaggle (`ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training`).
- **File**: `dirty_cafe_sales.csv`.
- **Features**: Transaction ID, Item, Quantity, Price Per Unit, Total Spent, Payment Method, Location, and Transaction Date.

## Tech Stack
- **Python**
- **Pandas** (Data Manipulation)
- **NumPy** (Numerical Operations)
- **Matplotlib & Seaborn** (Data Visualization)
- **Kagglehub** (Dataset Download)

## Methodology

### 1. Data Cleaning & Preprocessing
- Replaced invalid string values such as `'ERROR'` and `'UNKNOWN'` with standard `NaN` values.
- Checked for and monitored duplicated transactions.
- Converted the `Quantity`, `Price Per Unit`, and `Total Spent` columns to numerical formats.

### 2. Exploratory Data Analysis #1 (Before Imputation)
- **Missingness Analysis**: Visualized the density, proportion, and distribution of missing values across different columns using bar plots to plan the imputation strategy.
- Detected anomalies and structural errors in the raw data.

### 3. Missing Value Imputation
Instead of simply dropping missing values, logical relationships between columns were used to calculate and recover lost data:
- **Price Per Unit & Item**: Mapped missing prices based on a predefined dictionary of the `Item` sold, and inferred missing items using the known `Price Per Unit`.
- **Total Spent**: Calculated missing values using the formula `Price Per Unit * Quantity`.
- **Quantity**: Derived missing values using the formula `Total Spent / Price Per Unit`.
- **Price Per Unit**: Derived remaining missing values using the formula `Total Spent / Quantity`.

### 4. Exploratory Data Analysis #1 (After Processing)
Once the dataset was cleaned and fully imputed, a second round of EDA was performed to uncover actual business insights
- **Sales Distributions**: Plotted a histogram with a KDE curve to show the distribution of Total Spent.
- **Categorical Breakdowns**: Created boxplots to visualize the overall Total Spent and the Total Spent partitioned by individual Items.
- **Variable Relationships**: Generated a scatter plot to explore the correlation between Quantity and Total Spent, categorized by Item.

### 5. Statistical Inference
To move beyond descriptive statistics, rigorous statistical methods were applied to the cleaned dataset:
- **Confidence Intervals**: Calculated confidence intervals for key numerical metrics to estimate the true population parameters.
- **Hypothesis Testing**: Conducted formal hypothesis tests to determine if observed differences in sales across locations are statistically significant or due to random chance.

## Installation and Usage
1. Clone the repository:
   git clone <your-repo-url>
2. Install the required dependencies:
pip install pandas numpy matplotlib seaborn kagglehub
3. Run the Jupyter Notebook Project1.ipynb to execute the step-by-step cleaning process and view the generated visualizations.
