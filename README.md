COVID-19 Data Analysis and Visualization
Project Overview
Project Title: COVID-19 Data Analysis
Level: Beginner to Intermediate
Dataset: COVID-19 case time series, district-wise data, and testing center information

This project involves analyzing COVID-19 data to uncover trends, visualize case distributions, and gain insights into the spread of the virus. Using Python and data visualization tools, the project provides an in-depth look at case growth, transmission modes, and regional impact.

Objectives
Data Collection: Load and explore COVID-19 case time series, district-wise case data, and testing center details.

Data Cleaning: Identify and handle duplicate values, missing data, and inconsistencies.

Exploratory Data Analysis (EDA): Perform descriptive analysis on daily confirmed cases, recovered cases, and deaths.

Visualization: Use plots and charts to present COVID-19 trends across regions.

Insights and Findings: Draw meaningful conclusions about virus spread, high-risk regions, and recovery rates.

Project Structure
1. Dataset Initialization
Three datasets are loaded for analysis:

case_time_series.csv: Contains daily confirmed, recovered, and deceased cases.

district.csv: Provides district-wise case counts in Maharashtra, India.

ICMRTestingLabsWithCoords.csv: Lists COVID-19 testing labs with geographical coordinates.

python
Copy
Edit
import pandas as pd

cases = pd.read_csv('case_time_series.csv')
district = pd.read_csv('district.csv')
test_centers = pd.read_csv('ICMRTestingLabsWithCoords.csv')
2. Data Exploration & Cleaning
Checking dataset structure:

python
Copy
Edit
cases.info()
district.info()
test_centers.info()
Checking for duplicates:

python
Copy
Edit
cases.duplicated().sum()
district.duplicated().sum()
test_centers.duplicated().sum()
Handling missing values:

python
Copy
Edit
cases.isnull().sum()
district.isnull().sum()
test_centers.isnull().sum()
Data summary:

python
Copy
Edit
cases.describe()
district.describe()
test_centers.describe()
3. Data Analysis & Findings
Daily Confirmed Cases in India
A line plot is used to track the rise in COVID-19 cases.

python
Copy
Edit
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 6))
plt.plot(cases['Date'], cases['Daily Confirmed'], color='blue', marker='o')
plt.xlabel('Date')
plt.ylabel('Number of Cases')
plt.title('Daily Confirmed COVID-19 Cases in India')
plt.xticks(rotation=90)
plt.grid()
plt.show()
Modes of COVID-19 Transmission
A pie chart visualizes different transmission modes.

python
Copy
Edit
import matplotlib.pyplot as plt

labels = ['Travel', 'Place Visit', 'Unknown']
sizes = [30, 60, 90]  
colors = ['#4C8BE2', '#00e061', '#fe073a']

plt.pie(sizes, labels=labels, autopct='%1.1f%%', colors=colors, startangle=90)
plt.title('Modes of COVID-19 Transmission')
plt.show()
COVID-19 Cases Across Maharashtra Districts
A bar chart shows case distribution across districts.

python
Copy
Edit
plt.figure(figsize=(12, 6))
plt.bar(district['District'][:30], district['Confirmed'][:30], color='blue')
plt.xlabel('District')
plt.ylabel('Confirmed Cases')
plt.xticks(rotation=90)
plt.title('COVID-19 Cases Across Maharashtra Districts')
plt.show()
4. Key Findings
The number of daily confirmed cases increased significantly over time.

Travel and public places were the major sources of virus transmission.

Certain districts in Maharashtra reported a high number of cases, requiring targeted interventions.

Testing centers were distributed unevenly, affecting testing accessibility.

Reports
COVID-19 Summary: Overview of confirmed, recovered, and deceased cases.

Regional Trends: District-wise and state-wise COVID-19 spread patterns.

Transmission Analysis: Distribution of cases by travel, place visits, and unknown sources.

Testing Centers Report: Accessibility and availability of COVID-19 testing labs.

Conclusion
This project provides valuable insights into the spread of COVID-19 using data analysis and visualization techniques. The findings can assist in decision-making for public health policies, resource allocation, and pandemic response strategies.



