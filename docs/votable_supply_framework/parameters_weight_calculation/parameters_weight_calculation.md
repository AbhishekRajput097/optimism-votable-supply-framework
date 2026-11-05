# Correlation and Weightage Calculation for Parameters

## Introduction

This file analyzes the relationship between various parameters and **Votable Supply**. The goal is to calculate correlation coefficients between parameters and Votable Supply, determine weightage for each parameter, and provide a range for the weightages based on their correlation strength. This will help in assigning appropriate weights to parameters based on their impact on Votable Supply.

## Data

The dataset consists of values for the following parameters from **December 10, 2023, to November 30, 2024**:

- **AVPI (Actual Voting Power Index)**
- **PR (Participation Ratio Index)**
- **OP Price**
- **LAR (Liquidity Activity Ratio Index)**
- **Votable Supply**

### CSV File Format

The data is stored in a CSV file with the following columns:
- `Date` — Date of the data entry
- `AVPI` — Actual Voting Power Index
- `PR` — Participation Ratio Index
- `OP Price` — Historical OP Price Data
- `LAR` — Liquidity Activity Ratio Index
- `Votable Supply` — The votable supply data

Example:

| Date       | AVPI  | PR   | OP Price | LAR   | Votable Supply |
|------------|-------|------|----------|-------|----------------|
| 2023-12-10 | 0.10  | 0.45 | 3.20     | 1.20  | 45000          |
| 2023-12-11 | 0.12  | 0.50 | 3.30     | 1.15  | 46000          |

## Methodology

### 1. **Correlation Calculation**

The first step involves calculating the correlation coefficients between each parameter and the `Votable Supply`. The correlation matrix gives us an understanding of how strongly each parameter is related to `Votable Supply`.

#### Steps:
- **Load the Data**: The dataset is loaded from a CSV file.
- **Filter Numeric Columns**: Exclude the `Date` column as it contains string data.
- **Calculate Correlation**: Using the correlation function, the correlation matrix is computed for numeric columns.
- **Interpret Correlation**: The absolute values of correlations are used to determine which parameters are most strongly associated with `Votable Supply`.

### 2. **Weight Calculation**

Once the correlations are calculated, the next step is to assign weights based on the correlation strength. The weight for each parameter is determined by the absolute correlation with `Votable Supply`, ensuring the total weight sums to 1.

#### Formula for Weight Calculation

For each parameter, the weight is calculated based on its absolute correlation with `Votable Supply`. The formula is as follows:

$$
\text{Weight} = \frac{\left|\text{Correlation of Parameter with Votable Supply}\right|}{\sum \left|\text{Correlation of all parameters with Votable Supply}\right|}
$$

Where:
- **Correlation of Parameter with Votable Supply** is the absolute correlation value between the parameter and Votable Supply.
- **Sum of all absolute correlations** is the sum of the absolute values of the correlations of all parameters with Votable Supply.

#### Example Output:
The following weights are calculated based on correlation strength:

| Parameter      | Weight  |
|----------------|--------|
| AVPI           | 0.218  |
| PR             | 0.135  |
| OP Price       | 0.518  |
| LAR            | 0.129  |

### 3. **Weightage Range Calculation**

To ensure that the assigned weights are adaptable, we calculate the range of each parameter's weight. The range is determined by adding and subtracting a factor (typically the standard deviation) from the weight.

#### Steps:
- **Calculate Mean and Standard Deviation**: For all weights, calculate the mean and standard deviation.
- **Apply Range**: For each parameter, the range is calculated as:

$$
\text{Range} = [\text{Weight} - k \times \text{Std Dev}, \text{Weight} + k \times \text{Std Dev}]
$$

Where \( k \) is a factor (typically 1) that determines the width of the range.

## Files Included

1. **`correlation_weights.ipynb`**:
   - Calculates the correlation between each parameter and `Votable Supply`.
   - Computes weights based on correlation strength.

2. **`weightage_range.ipynb`**:
   - Takes the weights from `correlation_weights.py` and calculates the range for each parameter’s weight.
   - Uses standard deviation for determining the weightage range.
