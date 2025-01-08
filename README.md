Airbnb Listing Analysis: Paris Data Project

🏠 Project Overview

This project analyzes Airbnb listings in Paris to determine the impact of recent regulations on pricing, availability, and the number of hosts over time. The dataset includes detailed information on various Airbnb listings, such as neighborhoods, prices, and host activity. The project aims to provide insights into how the Airbnb market in Paris has changed over the years and what trends can be observed.

Technologies Used:

Python

Pandas

NumPy

Matplotlib

Jupyter Notebook

📊 The Dataset

The data used for this project is sourced from a publicly available Airbnb Listings dataset. The dataset contains over 560,000 records across 10 major cities, including Paris. For this project, the data is filtered to focus solely on Paris listings.

Key Fields:

host_since: Date when the host started listing on Airbnb

neighbourhood: The neighborhood where the listing is located

price: The price per night for the listing

accommodates: Number of people the listing can accommodate

📋 Project Objectives

Profile and Clean the Data: Prepare the dataset for analysis by filtering for Paris listings, handling missing values, and converting data types.

Prepare Data for Visualization: Aggregate data by neighborhoods, hosts, and time to create meaningful dataframes for analysis.

Visualize and Summarize Findings: Use visualizations to show the impact of regulations on the number of hosts, average prices over time, and more.

📌 Key Findings

The number of hosts in Paris peaked around 2016 and has since declined.

Prices vary significantly across neighborhoods, with the most expensive areas being concentrated in central Paris.

The average price per night shows an upward trend in recent years.

🛠️ Code Walkthrough

1. Data Cleaning and Profiling

The initial step involves loading the dataset, filtering it for Paris listings, and handling missing values.

# Import necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load the dataset
listings = pd.read_csv('Data/listings.csv', encoding='ISO-8859-1', parse_dates=['host_since'])

# Filter data for Paris listings
listings_paris = listings.query("city == 'Paris'")

2. Data Preparation for Visualization

This section creates new DataFrames by grouping data to prepare for visual analysis.

# Create a table showing average prices by neighborhood
paris_listings_neighbourhood = listings_paris.groupby('neighbourhood').agg({'price':'mean'}).sort_values(by='price', ascending=False)

3. Visualizations

The project includes bar charts and line plots to showcase trends in the data.

# Plot average prices by neighborhood
paris_listings_neighbourhood.plot.bar(title='Average Price by Neighbourhood in Paris', ylabel='Price')
plt.show()
