# **Foundation Mission Request: Votable Supply Framework**

This repository contains datasets, calculated indices, and predictive models designed to analyze and forecast various metrics related to token liquidity, governance participation, price stability, and protocol activity. The data is well-organized into structured folders for raw data, processed indices, and predictions, ensuring ease of navigation and reproducibility.

---

## **Folder Structure**

### **1. Participation Ratio (PR)**
This folder contains data and predictive models to analyze the percentage of tokens actively participating in governance within the Optimism ecosystem.

- **Formula**: PR = Votable Supply / Circulating Supply

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Contains the raw data file (Votable and Circulating Supply) used to calculate PR.  
  Example: `OP_Token_VS_CS.csv`.
- **`processed/`**:  
  Contains processed data with calculated PR values for analysis.  
  Example: `PR_Indexed_Data.csv`.
- **`prediction/`**:  
  Contains forecasted values of PR for future dates.  
  Example: `PR_Predicted_Date.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for predictive modeling using the SARIMA model.  
  Example: `PR_SARIMA_Model.ipynb`.

---

### **2. Liquidity Activity Ratio (LAR)**
This folder contains data to measure the liquidity activity ratio of tokens, helping assess token circulation in the market.

- **Formula**: LAR = Volume Traded (24H) / Circulating Supply

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Contains raw datasets for calculating LAR.  
  Example: `token.csv`.
- **`processed/`**:  
  Contains calculated LAR values for analysis.  
  Example: `LAR_Indexed_Data.csv`.
- **`prediction/`**:  
  Contains forecasted LAR values for future dates.  
  Example: `LAR_Predicted_Date.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for LAR predictive modeling.  
  Example: `LAR_SARIMA_Model.ipynb`.

---

### **3. Price Stability Index (PSI)**
This folder contains data to measure token price fluctuations and assess stability.

- **Formula**: PSI = Average Price (7 Day) / Current Price

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Contains raw historical and latest price data.  
  Examples: `token.csv`, `latest_price.csv`.
- **`processed/`**:  
  Contains calculated PSI values for analysis.  
  Example: `Optimism_PSI_Indexed_Data.csv`.
- **`prediction/`**:  
  Contains forecasted PSI values for future dates.  
  Example: `PSI_Predicted_Date.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for PSI predictive modeling.  
  Example: `PSI_SARIMA_Model.ipynb`.

---

### **4. Voting Power Index (VPI)**
This folder contains data measuring the percentage of tokens locked in governance relative to trading activity.

- **Formula**: VPI = Votable Supply / Volume Traded (30D)

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Contains raw data used to calculate VPI.  
  Example: `Voting_Power_Index.csv`.
- **`processed/`**:  
  Contains calculated VPI values for analysis.  
  Example: `VPI_Indexed_Data.csv`.
- **`prediction/`**:  
  Contains forecasted VPI values for future dates.  
  Example: `VPI_Predicted_Date.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for VPI predictive modeling.  
  Example: `VPI_SARIMA_Model.ipynb`.

---

### **5. OP Price**
This folder contains data of historical OP price and future predicted OP price.

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Historical data of the OP price.  
  Example: `OP_Price.csv`.
- **`prediction/`**:  
  Contains forecasted OP price for future dates.  
  Example: `OP_Price_Predicted_Data.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for OP price predictive modeling.  
  Example: `OP_Price_SARIMA_Model.ipynb`.

---

### **6. Actual Voting Power Index (AVPI)**
This folder contains data measuring the percentage of tokens locked in governance relative to trading activity.

- **Formula**: AVPI = Actual Votable Supply / Volume Traded (30D)

#### Subfolders:
- **`Data/`**:
- **`raw/`**:  
  Contains raw data used to calculate AVPI.  
  Example: `Actual_Votable_Supply.csv`.
- **`processed/`**:  
  Contains calculated AVPI values for analysis.  
  Example: `Actual_VPI_Indexed_Data.csv`.
- **`prediction/`**:  
  Contains forecasted AVPI values for future dates.  
  Example: `Actual_VPI_Predicted_Date.csv`.

- **`Model/`**:
- Contains the Jupyter notebook used for AVPI predictive modeling.  
  Example: `Actual_VPI_SARIMA_Model.ipynb`.

---

### **7. Top 50 Protocols OP Locked**
This folder contains data for the top 50 protocols on the Optimism mainnet, focusing on OP tokens locked in these protocols.

#### Subfolders:
- **`Data/`**:
- Contains datasets for day-wise OP locked data for top 50 protocols.  
  Example: `protocol.csv`.

---

## **How to Use This Repository**

1. **Explore Raw and Processed Data**:  
 Navigate to the `Data/` folders to access raw input datasets or processed indices for each metric.

2. **Run Predictive Models**:  
 Open the respective `Model/` Jupyter notebook to review or run the SARIMA model for forecasting future values.

3. **Analyze Predictions**:  
 Use the `prediction/` subfolder under `Data/` to access forecasted values for each metric.

---

## **Dependencies**
To run the scripts and notebooks in this repository, install the required Python libraries:
- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `scikit-learn`

Install dependencies using:
```bash
pip install -r requirements.txt
  
  
  


 
