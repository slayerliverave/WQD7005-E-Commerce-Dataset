# WQD7005-E-Commerce-Dataset
This repository is created to store all WQD7005 Alternative Assessment 1 Case Study on E-Commerce

### Project Overview
This Case Study is being conducted to assess customer behaviour based on the shopping habits from e-commerce website which encompassing various customer attributes and purchase history over the years. The objective of this assessment is to gain customer insights as well as establish focused strategy to increase the subscription status rate by intepretating the predictive model results based on customer preferences and behaviors that drive the subscriptions. The result and insights shown in the assesment can be used by the business (end user) to develop targeted marketing strategies and personalized customer engagement initiatives.

### Dataset Overview
The dataset that has been used for the assessment is obtained from Kaggle titled “Customer Behaviour and Shopping Habits Dataset” (https://www.kaggle.com/datasets/zeesolver/consumer-behavior-and-shopping-habits-dataset) which consists of  3,900 purchases with 18 attributes that similar to the dataset structure proposed for the assessment. 

It is to be noted all the required dataset structure from the assessment is available except 'LastPurchaseDate' however similar attributes to encounter this variable is available i.e. "Previous Purchases": Provides information on the number or frequency of prior purchases made by the customer, contributing to customer segmentation and retention strategies and "Frequency of Purchases"

For the "Memrbership Level" variable, initial data structure has no membership level however the dataset is being modified such a way that it meets the required data structure based on Subscription Status and Frequency of Purchase

### Data Mining Tools for E-Commerce Dataset
#### 1. SAS Enterprise Miner
SAS Enterprise Miner is an advanced analytics data mining tool that provides set of capabilities for data mining, predictive modeling, and machine learning tasks. The tool is designed to help to explore, develop, and deploy statistical models efficiently. With an interactive, graphical user interface, users can manage large volumes of data and create models using various statistical and machine learning techniques, including decsiion tree, classification, clustering and also offers features for model comparison, assessment, and ensemble model building.

For this assessment, main task in imputing the missing values as well as establishing the prediction model will be leveraging SAS-Enterprise Miner as this will ensure that the data quality objective is met.

#### 2. Talend Data Preparation
Talend Data Preparation is a data cleaning and transformation tool that allows users to prepare for datamining project. This tool provides a user-friendly, web-based interface that enables data workers to access, cleanse, enrich, and transform data with features like filtering, sorting, standardisation, deduplication, and merging datasets. Users can also standardize data by applying various functions to correct, format, and enrich data, ensuring that it is ready for use in analytics, reporting, or integration tasks.

For this project, the e-commerce will be preprocessed and cleansed using Talend Data Preparation especially to quickly understand the data in terms of missing values, data quality as well as data understanding from the visualisation.

#### 3. Talend Data Integration
Talend Data Integration is tools for integrating data across systems to enable seamless data integration and management across various sources and targets. The tool allows users for the extraction, transformation, and loading (ETL) of data between various databases, applications, and file formats. It supports batch and real-time integration processes and provides a broad connectivity palette to handle various data formats and sources. Users can design data integration jobs in a visual interface with drag-and-drop components and then execute these jobs to move and transform data according to business needs. Talend Data Integration is used to ensure data consistency, availability, and accessibility across the enterprise.

For this assessment, e-commerce dataset has been used to create new job which titles 'ecommerce' as well as adding and configuring the tFileInputDelimited for the e-commerce dataset. The step by step process on utilisation of the tools will be described in the subsequent question. However, based on the Running the job, the Talend Data Integration encounter an error. This is due to the:
•	There was a connection made to a socket on port 3735, which is likely for real-time debugging or statistics gathering.
•	Disconnected: The connection to the socket was disconnected normally.
•	Job ended: The job ecommerce ended with an exit code of 0 which indicates that the job has completed successfully without errors. If there was an error, we would typically see a non-zero exit code and an error message in the log.

Since there is  no other datasets will be integrated as well as Preprocessing and Data Mining job can be done with SAS E-Miner and Talend Data Preparation, hence the assesment using Talend Data Integration will be completed up to Run the Job using tFileInputDelimited and proceeded with Talend Data Preparation and SAS E-Miner.

### Task Execution for E-Commerce Data Mining
##### 1. Data Import and Preprocessing 
###### 1.1 Data Import in Talend Data Preparation
The Talend Data Preparation for E-commerce can be retrieved here http://127.0.0.1:9090/#/playground/preparation?prepid=ce156939-d516-4f7e-b3e9-14dac8f870de. 
Data Import in Talend Data Preparation
Prior importing the data in SAS E-Miner, the dataset is being imported to Talend Data Preparation in order to inspect the data and do necessary preprocessing to handle the missing values and any either anomalies or non-standardisation observed within the data. It is to be noted that, since the dataset in Kaggle is already cleaned data, hence the data is intentionally dirtied in order to showcase and demonstrate how data cleaning and preprocessing are executed for data mining.
Based on the dataset, there is some non-stanrdardisation of the datatype for attributes Season and Size where both datatype is changed to “text
