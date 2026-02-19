# Traffic Collision Data Analysis

## Project Overview

This project presents an Exploratory Data Analysis (EDA) of California traffic collision data using **PySpark** and **AWS services**. The primary objective is to employ data analytics techniques to clean, transform, and explore crash data to support traffic safety and urban planning. By utilizing **Apache Spark**, the analysis efficiently handles large-scale datasets to identify crash trends, high-risk locations, and key contributing factors.

## Business Value

Traffic collisions pose significant risks to public safety, necessitating continuous monitoring for improved safety measures. This analysis provides government agencies and city planners with data-driven insights to:

* Improve infrastructure and optimize traffic management.


* Analyze patterns related to accident severity and location-based risks.


* Enable faster, informed decision-making by processing vast amounts of data in real-time using **AWS S3** for scalable storage.



## Dataset Description

The dataset consists of records from the **Statewide Integrated Traffic Records System (SWITRS)**. It is structured into four primary tables:

* **Collisions**: Information about the incident location and vehicles involved.

* **Parties**: Details on groups involved, including age, sex, and sobriety.

* **Victims**: Information regarding injuries of specific individuals.

* **Locations**: Geographical data and road intersection details.



## Tech Stack

* **Distributed Computing**: Apache Spark (PySpark).

* **Cloud Storage**: AWS S3.

* **Language**: Python/PySpark SQL.

* **Visualization**: Compatibility for Tableau/Power BI.



## Data Preparation & ETL Process

1. **Data Loading**: Loaded into separate DataFrames for cleaning.


2. **Cleaning & Imputation**:
* Identified and dropped sparse columns with over 15% missing values.

* Removed rows with critical missing values in columns like `jurisdiction`, `officer_id`, `beat_number`, `primary_road`, `secondary_road` and `collision_time` .

* Imputed other missing values using the mean or mode (e.g., `victim_age` filled with mean).


3. **Deduplication**: Duplicate records were removed using the `dropDuplicates()` method.


4. **Outlier Analysis**: Numerical outliers in columns such as `distance` and `victim_age` were detected and handled using the **Interquartile Range (IQR)** method.


5. **Final Counts**: After cleaning, the dataset contained **715,855** collision records and **944,131** victim records.


## Key Insights

* **Collision Severity**: Over 50% of recorded collisions resulted in property damage only.


* **Weather & Lighting**: A majority of collisions occur in clear weather. While most take place in daylight, a substantial portion occurs in "dark with street lights".


* **Demographics**: There is a high frequency of victims in the 16–25 age range, with a notable peak at age 31.


* **Temporal Trends**:
* **Peak Days**: Fridays see more collisions compared to other weekdays.

* **Peak Hours**: A significant peak occurs between 3:00 PM and 6:00 PM, with the highest frequency around 5:00 PM.

* **Geographic High-Risk Areas**: **Los Angeles** was identified as the county with the highest collision count (over 230,000).


## Recommendations & Policy Implications

* **Strategic Audits**: Prioritize safety audits for top high-risk counties like Los Angeles, Orange, and San Diego.

* **Infrastructure Improvements**: Target peak collision hours with improved street lighting and automated traffic monitoring.

* **Traffic Management**: Optimize signal timing to manage flow during peak hours and reduce rear-end collisions.

* **Targeted Interventions**: Implement specialized driver training or safety campaigns for high-risk age demographics.

* **Predictive Modeling**: Use historical data hotspots to develop models for proactive intervention and signage placement.
