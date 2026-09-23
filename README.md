# Python_Data_Cleaning_mini_project

# Healthcare Data Cleaning and Preprocessing

This repository contains a Python-based data cleaning and preprocessing pipeline applied to a healthcare dataset. The Jupyter Notebook (`Data_Cleaning_.ipynb`) demonstrates essential data wrangling techniques to prepare messy medical data for accurate downstream analytics.

## Dataset Overview
The project processes the `healthcare_data_cleaning_dataset.csv` file, which includes the following key patient attributes:
* `Patient_ID`, `Age`, `Gender`, `City`, `Diagnosis`, `Hospital_Visits`, `Treatment_Cost`, `Insurance_Coverage`, `Admission_Date`

## Key Data Cleaning Steps Performed
1. **Missing Data Identification & Imputation**: Calculated missing data percentages and applied median imputation for critical numeric fields like `Age` and `Treatment_Cost`.
2. **Duplicate Removal**: Identified and removed exact duplicate patient records to ensure data integrity.
3. **Data Quality Checks**: Detected and filtered out unrealistic entries (e.g., ages below 0 or above 100).
4. **Outlier Detection & Treatment**: Used the Interquartile Range (IQR) method to detect extreme `Treatment_Cost` values and applied Winsorization (capping at the 5th and 95th percentiles) to retain data without skewing analysis.
5. **Data Transformation**: Applied a logarithmic transformation (`log1p`) to the highly skewed `Treatment_Cost` data, normalizing the distribution for statistical modeling, visualized via Seaborn histograms.
6. **Time-Based Handling**: Converted `Admission_Date` to datetime objects, sorted the chronological sequence, and resolved missing temporal gaps using forward fill (`ffill`).

## Technologies Used
* **Python**
* **Pandas**: Data manipulation, aggregation, and time-series handling.
* **NumPy**: Statistical calculations and data clipping (Winsorization).
* **Matplotlib & Seaborn**: Visualizing data distributions before and after transformations.

## How to Run
1. Clone this repository to your local machine.
2. Ensure you have the required libraries installed:
   ```bash
   pip install pandas numpy matplotlib seaborn
