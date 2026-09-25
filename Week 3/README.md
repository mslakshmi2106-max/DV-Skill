## Apple Stock Analysis
Project Overview
This project analyzes Apple Inc. (AAPL) stock market data using Python. The dataset is processed to calculate daily price changes, daily returns, percentage changes, and key stock statistics. A line chart is also generated to visualize the stock's closing price trend over time.

Objectives
Load and analyze Apple stock data.
Clean and preprocess the dataset.
Calculate daily price changes and returns.
Identify stock performance trends.
Visualize closing prices using a line chart.
Technologies Used
Python
Pandas
NumPy
Matplotlib
Jupyter Notebook / Google Colab
Dataset Columns
Date
Open
High
Low
Close
Volume
Project Workflow
1. Import Libraries
The required libraries are imported:

Pandas
NumPy
Matplotlib
2. Load Dataset
The Apple stock dataset is loaded from an Excel file.

3. Data Exploration
Basic dataset inspection is performed using:

head()
tail()
info()
4. Data Cleaning
Check for missing values.
Remove duplicate records.
Convert Date column into datetime format.
Sort data by date.
5. Feature Engineering
The following metrics are calculated:

Daily Price Change
Daily Price Change = Close Price − Previous Day Close Price

Daily Return (%)
Daily Return = ((Close − Open) / Open) × 100

Daily Percentage Change (%)
Daily Percentage Change = (Daily Price Change / Previous Close Price) × 100

6. Statistical Analysis
The project calculates:

Highest Stock Price
Lowest Stock Price
Average Closing Price
Average Trading Volume
Minimum Trading Volume
Maximum Trading Volume
7. Loss Analysis
The days with the biggest percentage losses are identified and displayed.

8. Data Visualization
A line chart is plotted showing:

Date on X-axis
Closing Price on Y-axis
Output
The project provides:

Cleaned stock dataset
Daily return analysis
Percentage change analysis
Trading volume statistics
Biggest loss days
Closing price trend chart
Conclusion
This project demonstrates how Python can be used for stock market data analysis. By calculating returns, percentage changes, and visualizing stock trends, users can better understand Apple stock performance and market behavior.
