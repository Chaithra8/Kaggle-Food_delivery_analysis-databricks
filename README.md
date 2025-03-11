# Kaggle Food Delivery Analysis with Databricks

## Project Overview
This project focuses on extracting food delivery data from the Kaggle API, transforming it using Databricks, and generating Delta tables for further analysis. The project includes data cleansing, performance tracking, and visualizations to explore various insights related to delivery efficiency, seasonal trends, and other influencing factors such as weather and traffic conditions.

## Key Features
- Extract food delivery data from Kaggle using the Kaggle API.
- Transform and clean the raw data with Databricks notebooks.
- Create Delta tables for storing cleaned data and analysis results.
- Visualize insights about delivery performance, seasonal trends, and traffic/weather impacts.

## Prerequisites

Before you begin, make sure you have the following:

1. **Databricks Community Edition Account**  
   Sign up for free at [Databricks Community Edition](https://community.cloud.databricks.com/).

2. **Kaggle API Token**  
   - Generate an API token from your [Kaggle account](https://www.kaggle.com/docs/api).
   - Download the `kaggle.json` file containing your API credentials.

3. **Kaggle Dataset**  
   Download the dataset from [Food Delivery Dataset - Kaggle](https://www.kaggle.com/datasets/gauravmalik26/food-delivery-dataset).

## Project Setup

Follow these steps to set up and execute the project in Databricks:

### 1. Set up Databricks Community Edition
- Create a Databricks account if you don't have one already: [Databricks Community Edition](https://community.cloud.databricks.com/).

### 2. Kaggle API Token Setup
- Generate your **Kaggle API token** from your [Kaggle account settings](https://www.kaggle.com/docs/api).
- Download the `kaggle.json` file containing your API credentials.
- Upload this JSON file to **Databricks File System (DBFS)** using the Databricks UI or CLI.

### 3. Create a Databricks Cluster
- In Databricks, create a cluster to run the code. You can follow the instructions in the Databricks documentation to set it up.

### 4. Data Extraction
- **Notebook**: `extract_food_delivery_data.ipynb`
  - This notebook extracts the raw food delivery data from Kaggle using the Kaggle API.
  - The raw data is then stored in a Delta table in the `landing` schema.

### 5. Data Cleaning
- **Notebook**: `clean_food_delivery_data.ipynb`
  - This notebook performs data cleansing operations (e.g., handling missing values, correcting data formats, etc.).
  - The cleaned data is then stored in a Delta table in the `staging` schema.

### 6. Data Analysis and Transformation
- **Notebook**: `analytics_food_delivery.ipynb`
  - This notebook applies various transformations to the cleaned data.
  - It generates **3 Delta tables** containing:
    1. **Delivery Performance Summary**: Tracks the performance of each delivery person.
    2. **Delivery Summary**: Aggregates delivery statistics based on year, month, city, and food type.
    3. **Order Count Variations**: Analyzes variations in order counts based on factors like weather, festive seasons, and traffic density.

## Notebooks

### 1. `extract_food_delivery_data.ipynb`
- Extracts food delivery data using the Kaggle API and stores it in a Delta table under the `landing` schema.

### 2. `clean_food_delivery_data.ipynb`
- Cleans the raw data by handling missing values, correcting column types, and creating a clean version of the data in the `staging` schema.

### 3. `analytics_food_delivery.ipynb`
- Analyzes the cleaned data and generates aggregated reports, including:
  - Delivery performance analysis by each delivery person.
  - Delivery summary (count, time taken, etc.) based on different dimensions (year, month, city).
  - Impact of weather, festive season, and traffic conditions on order count and delivery times.

## Running the Project

1. **Step 1**: Set up your Databricks environment by following the instructions in the "Project Setup" section.
2. **Step 2**: Execute the notebooks sequentially to extract, clean, and analyze the data:
   After each notebook execution, we can see respective schema and delta tables under "hive_metastore" which is the default catalog.
   - Run `extract_food_delivery_data.ipynb` to load raw data.
   - Run `clean_food_delivery_data.ipynb` to clean and preprocess the data.
   - Run `analytics_food_delivery.ipynb` to generate analysis results and summaries.
4. **Step 3**: Explore the generated Delta tables for insights and use the data for further analysis or visualization.

## Delta Tables

- **Landing Schema**: Contains the raw, unprocessed food delivery data.
- **Staging Schema**: Contains the cleaned data ready for analysis.
- **Analysis Results**: Delta tables containing aggregated performance metrics and delivery trends.

## Visualizations

Once the analysis results are available, you can use Databricks' built-in visualizations to explore:
- Delivery performance by person.
- Monthly delivery summaries (average time, total deliveries, etc.).
- The impact of traffic, weather, and festivals on delivery performance.

## Conclusion

This project demonstrates how to extract, clean, and analyze food delivery data using Databricks and the Kaggle API. By leveraging Delta tables, you can efficiently process and analyze large datasets while ensuring data quality and reliability.
