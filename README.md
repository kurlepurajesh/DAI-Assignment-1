# DAI-Assignment-1
# Cafe Sales Data Analysis

## Overview
This project analyzes transactional data from a cafe to uncover sales trends, customer behavior, and data quality insights. The dataset includes **10,000 transactions** with details like items purchased, payment methods, locations, and transaction dates. Key steps included data cleaning, imputation, outlier treatment, and exploration of relationships between variables.

---

## Table of Contents
1. [Dataset Overview](#dataset-overview)
2. [Key Analysis Steps](#key-analysis-steps)
3. [Key Findings](#key-findings)
4. [Recommendations](#recommendations)
5. [Visualizations](#visualizations)
6. [Dependencies](#dependencies)
7. [How to Run](#how-to-run)

---

## Dataset Overview
### Features
- **Transaction ID**: Unique identifier for each transaction.
- **Item**: Product purchased (e.g., Coffee, Cake).
- **Quantity**: Number of units purchased.
- **Price Per Unit**: Cost per item.
- **Total Spent**: Total amount spent per transaction.
- **Payment Method**: Cash, Credit Card, Digital Wallet, or UNKNOWN.
- **Location**: In-store, Takeaway, or UNKNOWN.
- **Transaction Date**: Date and time of purchase.

### Data Quality Issues
- Missing values in `Item` (333), `Payment Method` (2,579), and `Location` (3,265).
- Invalid entries like `ERROR` in `Total Spent`.
- Outliers in numeric columns (`Quantity`, `Price`, `Total Spent`).

---

## Key Analysis Steps
1. **Handling Missing Data**  
   - Replaced placeholder strings (`ERROR`, `UNKNOWN`) with `NaN`.
   - Imputed numeric columns with median values.
   - Imputed categorical columns with the most frequent values.

2. **Data Type Conversion**  
   - Converted `Transaction Date` to datetime and extracted temporal features (Year, Month, Hour).

3. **Outlier Treatment**  
   - Capped outliers using the Interquartile Range (IQR) method.

4. **Relationship Analysis**  
   - Explored correlations between `Quantity`, `Price`, and `Total Spent`.
   - Analyzed popular items, payment methods, and sales trends over time.

---

## Key Findings
### 1. Numeric Relationships
- **Total Spent vs. Quantity/Price**:  
  - Strong positive correlation, but discrepancies found due to `ERROR` entries.  
- **Outliers**: Capped to stabilize trends (e.g., extreme quantities like 5+ units).

### 2. Categorical Insights
- **Top Items**: Coffee, Juice, Salad, and Cake (1,000+ transactions each).  
- **Payment Methods**: Digital Wallet (most frequent), Credit Card, Cash.  
- **Location**: Nearly equal split between In-store (3,017) and Takeaway (3,022).

### 3. Temporal Trends
- **Peak Hours**: Morning (8–10 AM) and afternoon (2–4 PM).  
- **Monthly Activity**: Higher sales in April and September.

---

## Recommendations
1. **Recalculate `Total Spent`** using `Quantity × Price Per Unit` to fix inaccuracies.  
2. **Investigate Missing Data**: Address gaps in `Location` and `Payment Method`.  
3. **Optimize Inventory**: Stock high-demand items (Coffee, Juice).  
4. **Promotions**: Target peak hours with discounts (e.g., morning coffee deals).  

---

## Visualizations
1. **Boxplots**: Before and after outlier treatment for numeric columns.  
2. **Correlation Matrix**: Relationships between `Quantity`, `Price`, and `Total Spent`.  
3. **Item Distribution**: Bar chart of top-selling items.  
4. **Hourly Sales**: Line graph showing transaction peaks.  

---

## Dependencies
- Python 3.8+
- Libraries: `pandas`, `numpy`, `scikit-learn`, `seaborn`, `matplotlib`  
- Jupyter Notebook (for interactive analysis)

---

## How to Run
1. Clone this repository:  
   ```bash
   git clone [https://github.com/kurlepurajesh/DAI-Assignment-1]
2. Install dependencies
   '''bash
   pip install pandas numpy scikit-learn seaborn matplotlib
3.Launch Jupyter Notebook
   '''bash
   jupyter notebook
4. Open cafe_sales_analysis.ipynb and run all cells
5. 
