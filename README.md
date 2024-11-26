# Codeforces User Submission Analysis

This repository contains a Python script that fetches a user's submissions from Codeforces using the Codeforces API, cleans the data, performs statistical analysis, and generates some basic visualizations. The goal is to understand the relationship between different variables such as Problem Tags, Verdicts, and Submission Metrics like Time and Memory Consumption.

## Features

- Fetch user submissions from the Codeforces API.
- Clean and preprocess the data, removing invalid entries and outliers.
- Perform statistical analysis to identify relationships between problem tags and verdicts.
- Visualize the relationship between problem tags and verdicts.
- Save the cleaned data for further analysis.

## Prerequisites

Before running the script, ensure you have the following Python libraries installed:

- `requests` - to fetch data from the Codeforces API.
- `pandas` - for data manipulation.
- `matplotlib` - for plotting data.
- `seaborn` - for statistical data visualization.
- `scipy` - for performing statistical tests like the Chi-Squared test.
- `numpy` - for numerical operations.

You can install the required libraries using `pip`:

```bash
pip install requests pandas matplotlib seaborn scipy numpy
```
Usage
1. Fetch Data
The script fetches a set number of submissions from a given Codeforces user. You can adjust the user handle and the number of submissions in the script.

```python

handle = "khaled40"  # Change to the desired Codeforces handle
count = 200           # Set the number of submissions to fetch
```
