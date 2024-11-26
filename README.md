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
2. Data Cleaning
The script performs the following data cleaning steps:

Remove null values: Removes any rows that contain missing values.
Remove duplicates: Identifies and removes duplicate rows if they exist (the script assumes there are no duplicates).
Remove invalid or inconsistent values: For example, submissions with 'N/A' points or invalid numerical values are excluded.
Handle outliers: Outliers in Time Consumed (ms) and Memory Consumed (bytes) columns are removed using the Z-score method.
3. Statistical Analysis
The script performs a Chi-Squared test to analyze the relationship between Problem Tags and Verdict. It tests the null hypothesis that there is no relationship between the problem tags and the verdicts (OK, WRONG_ANSWER, etc.).

Null Hypothesis (H₀): There is no relationship between Problem Tags and Verdict.
Alternative Hypothesis (H₁): There is a relationship between Problem Tags and Verdict.
Based on the p-value from the test, the script either accepts or rejects the null hypothesis.

4. Data Visualization
The script also includes basic visualizations to understand the distribution of verdicts based on problem tags and the time consumed by different verdicts.

Example visualizations include:

Countplot of verdicts by problem tags.
Boxplot of time consumed based on verdicts.
5. Save Cleaned Data
After cleaning the data and performing analysis, the script saves the cleaned data into a CSV file for further use.
```
python

df_cleaned.to_csv('cleaned_user_submissions.csv', index=False)
```
This saves the cleaned DataFrame to a file called cleaned_user_submissions.csv.

Example Output
Chi-Squared Test Results: The p-value will indicate whether there is a significant relationship between problem tags and verdicts.

For example:
```
text
Chi-Squared Test P-Value: 0.0000
There is a significant relationship between Problem Tags and Verdict.
```
Visualizations: The script will generate plots that display the distribution of verdicts across different problem tags and the time consumed based on verdicts.

Contributing
If you'd like to contribute to this project, feel free to fork the repository, make your changes, and submit a pull request.

License
This project is open-source and available under the MIT License.

Feel free to reach out if you have any questions or suggestions.
```markdown
### Key sections in the `README.md`:
1. **Title and Description**: Introduces the purpose of the project.
2. **Prerequisites**: Lists the libraries that need to be installed.
3. **Usage**: Provides details on how to run the script and what it does.
4. **Data Cleaning**: Explains the steps of cleaning the data, including null removal, duplicates, outliers, and inconsistent values.
5. **Statistical Analysis**: Describes the Chi-Squared test and its hypotheses.
6. **Data Visualization**: Mentions the types of visualizations the script generates.
7. **Saving Cleaned Data**: Explains how to save the cleaned dataset.
8. **Example Output**: Shows what kind of results the user can expect.
9. **Contributing**: Invites others to contribute to the project.
10. **License**: States the project's open-source license.

This format will make it clear for others to understand the project and how to use it. You can copy ```
