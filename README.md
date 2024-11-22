---

# Investment Portfolio Analysis - Project 1

## Project Overview
This project analyzes a diverse investment portfolio consisting of stocks, ETFs, an index, and Forex pairs. Using a structured ELT pipeline, the project demonstrates data extraction, cleaning, transformation, loading, and analysis to evaluate the performance of the portfolio across various financial metrics.

---

## Features
- **Portfolio Composition**:
  - **Stocks**: Apple (AAPL), Johnson & Johnson (JNJ), JPMorgan Chase (JPM), Microsoft (MSFT)
  - **ETFs**: SPDR S&P 500 ETF Trust (SPY), Vanguard Total Stock Market ETF (VTI)
  - **Index**: Nasdaq 100 (NDX)
  - **Forex Pairs**: Euro/US Dollar (EURUSD), US Dollar/Japanese Yen (USDJPY)
  
- **Initial Investment**: $100,000 evenly distributed across all assets ($12,500 each).

- **Metrics Analyzed**:
  - Stocks & ETFs: Total return, cumulative return, volatility, 10-day and 100-day moving averages, Sharpe ratio, beta.
  - Forex Pairs: Total return, cumulative return, percentage change.
  - Index: Price index, volatility.

---

## Pipeline Architecture
The project follows an ELT (Extract, Load, Transform) pipeline, ensuring data quality, consistency, and accuracy.

### 1. **Extraction**
   - **Source**: Data fetched from the Polygon.io API.
   - **Tools**: Python with `Requests`, `Pandas`, `Datetime`, and other libraries.
   - **Output**: Raw data stored as CSV files.

### 2. **Cleaning**
   - Ensured consistent date formatting.
   - Renamed columns for clarity.
   - Handled missing values through forward filling.
   - Added relevant calculated fields for further analysis.

### 3. **Loading**
   - Used `pyodbc` to connect to a SQL Server database.
   - Loaded cleaned data into SQL tables using SQL `INSERT` statements.

### 4. **Transformation**
   - Implemented a **Star Schema** in SQL for efficient data analysis.
   - Created SQL Views to calculate financial metrics like returns, volatility, moving averages, and more.

---

## Analysis Highlights
### Stock and ETF Metrics
- **Volatility**: AAPL exhibited significant spikes, while ETFs (SPY, VTI) were stable.
- **Cumulative Returns**: AAPL and MSFT had the highest growth; JNJ showed negative returns.
- **Moving Averages**: Identified trends with 10-day and 100-day moving averages.
- **Risk-Adjusted Returns**: Sharpe ratios indicated areas for optimization.

### Forex Metrics
- **USDJPY**: Strong upward trend with higher volatility.
- **EURUSD**: Relatively stable but less profitable.

### Index Metrics
- **Nasdaq 100**: Showed a bullish trend with decreasing volatility toward the period's end.

### Portfolio Metrics
- **Profit**: $32,330.32 over three years.
- **Annualized Return**: Consistent 20%.
- **Volatility**: Decreased over time, indicating stabilization.
- **Sharpe Ratio**: Highlighted the need for periodic rebalancing.

---

## Files Included
1. **Jupyter Notebooks**:
   - `P1 - Data Cleaning.ipynb`: Python code for data extraction and cleaning.
   - `P1 - Visualization.ipynb`: Python code for analysis and visualization.
   
2. **SQL Scripts**:
   - `Project1SQL - Loading Tables.sql`: Script to create and populate SQL tables.
   - `P1 - Star Schema.sql`: SQL for star schema design.
   - `P1 - Metric Views.sql`: SQL views for calculating financial metrics.

---

## Future Recommendations
- Increase allocation to high-performing stocks like AAPL and MSFT.
- Reduce or monitor allocation to underperforming assets like JNJ.
- Explore additional Forex pairs for diversification.
- Regularly rebalance the portfolio based on performance metrics like Sharpe ratio and volatility.

---

## How to Use
1. **Requirements**:
   - Python 3.x with `pandas`, `requests`, `pyodbc`, and other required libraries.
   - A running SQL Server instance.
   - Access to Polygon.io API for data extraction.

2. **Steps**:
   - Run the data extraction script to fetch raw data from Polygon.io API.
   - Execute the data cleaning notebook to preprocess and save cleaned data.
   - Use SQL scripts to create tables, load data, and transform it for analysis.
   - Visualize and analyze the portfolio using the provided visualization notebook.

---

## Author
**Jacob Mannix**  
Graduate, Bachelor of Computer Science  
Florida State University  

---
