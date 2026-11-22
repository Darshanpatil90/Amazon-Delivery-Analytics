
# Data Quality Report
## Project 3 – Delivery Route Delay Forecasting & Logistics Performance Analytics

### 1. Project Overview
The objective is to clean and preprocess the Amazon Delivery dataset.

### 2. Dataset Information
- Original Shape: 43,739 rows × 16 columns
- Final Shape: 43,739 rows × 28 columns
- Duplicate Records: 0

### 3. Missing Values Analysis & Treatment

**Agent_Rating**
- 54 missing and 53 invalid values above 5.
- Median imputation applied.
- Median: 4.7.

**Agent_Age**
- 38 invalid age values below 18.
- Median imputation applied.
- Median: 30.

**Store GPS Coordinates**
- 3,505 records contained (0,0) coordinates.
- Converted to missing values.
- Arbitrary coordinates were not imputed.

**Order_Time, Weather and Traffic**
- 91 records had missing values in all three columns.
- Missing values were preserved.
- Missing indicators were created.

### 4. Duplicate Records Check
No duplicate records were found.

### 5. Outlier Detection & Treatment
- IQR method applied to Delivery_Time.
- 79 outliers identified at 270 minutes.
- Outliers were retained as they may represent genuine delays.

### 6. Feature Engineering
Created features:
- Order_Year
- Order_Month
- Order_Day
- Order_DayOfWeek
- Order_Hour
- Order_Minute
- Pickup_Hour
- Pickup_Minute
- Pickup_Delay_Minutes
- Order_Time_Period
- Store_Location_Missing
- Order_Time_Missing

### 7. Final Data Validation
- Final Shape: 43,739 rows × 28 columns.
- Duplicate Rows: 0.
- Exported CSV successfully reloaded and verified.

### 8. Limitations
- Store GPS unavailable for 3,505 records.
- Order_Time, Weather and Traffic unavailable for 91 records.
- Missing values were preserved where reliable imputation was not possible.

### 9. Final Output
- File: amazon_delivery_cleaned.csv
- Location: data/processed/
- Final Shape: 43,739 rows × 28 columns.
