# Data Cleaning and Analysis - Bike Dataset

## Project Overview

This project focuses on cleaning and preprocessing a dataset containing information about various bikes. The dataset includes details such as power, displacement, fuel system, cooling system, and transmission type. The goal of this project is to improve data quality by handling missing values, converting data types, and removing duplicates.

## Files in this Repository

- **all\_bikez\_curated.ipynb** → Jupyter Notebook containing all data cleaning steps.
- **cleaned\_bike\_data.csv** → The cleaned and processed dataset.
- **README.md** → This file, documenting the project.

## Data Cleaning Steps

### 1. Removing Duplicates

- Initially, there were 8 duplicate rows, which were removed using `drop_duplicates()`.

### 2. Dropping Unnecessary Columns

- Dropped `Fuel control` and `Dry weight (kg)` due to a high percentage of missing data.

### 3. Handling Missing Values

- Checked for missing values (`NaN`) in each column.
- Removed rows with missing values in:
  - `Engine cylinder`
  - `Engine stroke`
  - `Model`
- Filled missing values using:
  - **Median** for numerical columns (`Power (hp)`, `Displacement (ccm)`, `Fuel capacity (lts)`, `Wheelbase (mm)`, `Seat height (mm)`).
  - **Mode** for categorical columns (`Fuel system`, `Cooling system`, `Transmission type`, `Gearbox`, `Category`, `Year`).
- Replaced `Unspecified category` with `NaN`.

### 4. Checking for Inconsistencies

- Applied `.unique()` to each column to identify inconsistencies.
- Standardized values in `Cooling system` column:
  - Replaced variations of `Air` (`'airr', 'air', 'the air'`) with `'Air'`.
  - Replaced variations of `Oil & Air` (`'Oil and air', 'Oil & air'`) with `'Oil & Air'`.
  - Replaced `'Liquids'` with `'Liquid'`.
- Cleaned `Year` column by stripping `'CE'` from the values.

### 5. Exporting Cleaned Data

- After processing, the cleaned dataset was saved as a CSV file for further analysis.

## Future Improvements

- Feature Engineering to extract more meaningful insights.
- Data Visualization to explore trends and patterns.
- Integration with Machine Learning models for predictions.

