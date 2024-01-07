# WQD7005-E-Commerce-Dataset
This repository is created to store all WQD7005 Alternative Assessment 1 Case Study on E-Commerce

## 1.0 Project Overview
This Case Study is being conducted to assess customer behaviour based on the shopping habits from e-commerce website which encompassing various customer attributes and purchase history over the years. The objective of this assessment is to gain customer insights as well as establish focused strategy to increase the subscription status rate by intepretating the predictive model results based on customer preferences and behaviors that drive the subscriptions. The result and insights shown in the assesment can be used by the business (end user) to develop targeted marketing strategies and personalized customer engagement initiatives.

## 2.0 Dataset Overview
The dataset that has been used for the assessment is obtained from Kaggle titled “Customer Behaviour and Shopping Habits Dataset” (https://www.kaggle.com/datasets/zeesolver/consumer-behavior-and-shopping-habits-dataset) which consists of  3,900 purchases with 18 attributes that similar to the dataset structure proposed for the assessment. 

It is to be noted all the required dataset structure from the assessment is available except 'LastPurchaseDate' however similar attributes to encounter this variable is available i.e. "Previous Purchases": Provides information on the number or frequency of prior purchases made by the customer, contributing to customer segmentation and retention strategies and "Frequency of Purchases".

For the "Memrbership Level" variable, initial data structure has no membership level however the dataset is being modified such a way that it meets the required data structure based on Subscription Status and Frequency of Purchase.

## 3.0 Data Mining Tools for E-Commerce Dataset 
The description of this assesment shall be read together with file Data Mining for E-Commerce Assessement Report that uploaded in this github file. 

### 3.1 SAS Enterprise Miner
SAS Enterprise Miner is an advanced analytics data mining tool that provides set of capabilities for data mining, predictive modeling, and machine learning tasks. The tool is designed to help to explore, develop, and deploy statistical models efficiently. With an interactive, graphical user interface, users can manage large volumes of data and create models using various statistical and machine learning techniques, including decsiion tree, classification, clustering and also offers features for model comparison, assessment, and ensemble model building.

For this assessment, main task in imputing the missing values as well as establishing the prediction model will be leveraging SAS-Enterprise Miner as this will ensure that the data quality objective is met.

### 3.2 Talend Data Preparation
Talend Data Preparation is a data cleaning and transformation tool that allows users to prepare for datamining project. This tool provides a user-friendly, web-based interface that enables data workers to access, cleanse, enrich, and transform data with features like filtering, sorting, standardisation, deduplication, and merging datasets. Users can also standardize data by applying various functions to correct, format, and enrich data, ensuring that it is ready for use in analytics, reporting, or integration tasks.

For this project, the e-commerce will be preprocessed and cleansed using Talend Data Preparation especially to quickly understand the data in terms of missing values, data quality as well as data understanding from the visualisation.

### 3.3 Talend Data Integration
Talend Data Integration is tools for integrating data across systems to enable seamless data integration and management across various sources and targets. The tool allows users for the extraction, transformation, and loading (ETL) of data between various databases, applications, and file formats. It supports batch and real-time integration processes and provides a broad connectivity palette to handle various data formats and sources. Users can design data integration jobs in a visual interface with drag-and-drop components and then execute these jobs to move and transform data according to business needs. Talend Data Integration is used to ensure data consistency, availability, and accessibility across the enterprise.

For this assessment, e-commerce dataset has been used to create new job which titles 'ecommerce' as well as adding and configuring the tFileInputDelimited for the e-commerce dataset. The step by step process on utilisation of the tools will be described in the subsequent question. However, based on the Running the job, the Talend Data Integration encounter an error. This is due to the:
•	There was a connection made to a socket on port 3735, which is likely for real-time debugging or statistics gathering.
•	Disconnected: The connection to the socket was disconnected normally.
•	Job ended: The job ecommerce ended with an exit code of 0 which indicates that the job has completed successfully without errors. If there was an error, we would typically see a non-zero exit code and an error message in the log.

Since there is  no other datasets will be integrated as well as Preprocessing and Data Mining job can be done with SAS E-Miner and Talend Data Preparation, hence the assesment using Talend Data Integration will be completed up to Run the Job using tFileInputDelimited and proceeded with Talend Data Preparation and SAS E-Miner.

### 4.0 Task Execution for E-Commerce Data Mining
#### 4.1 Data Import and Preprocessing 
##### 4.1.1 Data Import in Talend Data Preparation
The Talend Data Preparation for E-commerce can be retrieved here http://127.0.0.1:9090/#/playground/preparation?prepid=ce156939-d516-4f7e-b3e9-14dac8f870de. 

Prior importing the data in SAS E-Miner, the dataset is being imported to Talend Data Preparation in order to inspect the data and do necessary preprocessing to handle the missing values and any either anomalies or non-standardisation observed within the data. It is to be noted that, since the dataset in Kaggle is already cleaned data, hence the data is intentionally dirtied in order to showcase and demonstrate how data cleaning and preprocessing are executed for data mining.
Based on the dataset, there is some non-stanrdardisation of the datatype for attributes Season and Size where both datatype is changed to “text.

##### 4.1.2 Missing Values and Data Stnadardisation using Talend Data Preparation 
Based on the data inspection, it can be observed that few attributed have missing values for “Review Rating” where 195 records are missing and similarly for “Payment Method” where 390 records are missing from the dataset as shown in Figure 1.3 and Figure 1.4 respectively. The remaining attributes are acceptable where no missing values have been indicated. For handling missing values, the data will then be imputed using SAS E-Miner.

In order to ensure that Purchase Category is standardized, and more generalisation and customisation can be made to understand the customer behaviour, the Category will be only kept to four (4) main categories such as Clothing, Footwear, Outerwear and Accessories. Hence, the Category type shown in Figure 1.5 for Apparel, Footgear, Electronic and Household will be changed according to the relevant category mentioned above.

##### 4.1.3 Data Understanding in Talend Data Preparation 
In Talend Data Preparation, we are also able to understand the data in depth which will assist in getting more insights on customer behaviour. For example, based on Purchase Amount shown in Figure 1.7, it can be summarised that the maximum purchase of the transaction is USD 100 and minimum the purchase is USD 20 whilst average purchase amount for overall records is USD 59.76. With respect to the satisfaction level, maximum Review Rating given by customer is 4.0 over 5.0 with 177 occurrences in which overall satisfaction for the purchase by customer is 3.75 over 5.0.

##### 4.1.4 Data Import and Preprocessing with SAS E-Miner
To import the dataset in SAS, an ‘e-commerce’ diagram will be created to New Diagram.
From the “Sample” tab, select “File Import” and drag the node into the workspace. Right click the File Import and rename the node as “e-commerce.
It essential to edit the variable for the dataset to understand on customer behaviour. Hence the role of the dataset is amended as follows:

•	For Customer_ID, the Role is changed to “Rejected” and select “Yes” in Drop column as this attribute is insignificant for the analysis

•	For the Subscription_Status, the Role is changed to “Target” to indicate whether customer will continue the subscription or not. Based on Figure 1.12, we can summarised that majority of the customer opt to “No” subscription with 2897 no. of records (73%) 

Then, Run the “e-commerce” dataset and the summary of Results is demonstrated in Figure 1.13 

##### 4.1.5 Imputing Missing Values with SAS E-Miner
As described in the above section, there are missing values for “Review Rating” and “Payment Method” variables. Hence to handle the missing values, from “Modify” tab, select “Impute” and edit the variables for:
-	“Review Rating” to “Mean”
-	“Payment Method” to “Distribution”. Selecting “Distribution” for imputation means that the missing values will be imputed based on the statistical distribution of the non-missing values of that variable.


##### 4.1.6 Data Import and Integration with Talend Data Integration
A new project is created in Talend Data Integration which title as ‘e-commerce’. To create a New Job:

•	Right-click in the Repository panel on the left under Job Designs.

•	Choose Create job.

•	Provide a name for the job (e.g., "ecommerce ") and a description. Click Finish.

Then add a tFileInputDelimited Component:

•	This component is used to read delimited files like CSV.

•	From the Palette panel on the right, type "tFileInputDelimited" into the search bar.

•	Drag the tFileInputDelimited component to the design workspace.

Next Configure the tFileInputDelimited Component:

•	Click on the tFileInputDelimited component to select it.

•	In the Component panel below, set the properties:

- File Name/Stream: Browse to and select your CSV file.
- Row Separator: Set this to "\n" for new lines (most common for CSV files).
- Field Separator: Set this to  "," depending on file CSV is delimited.
- Header: Since the dataset obtain Header, hence, set this to 1.
- Under the Schema section, click on the Edit schema button. Here, define the columns in the CSV file by adding columns and specifying their data types. This schema should match the structure of CSV file.

Then, Run the Job to View Data. 
Based on the Running the job, the Talend Data Integration encounter an error. This is due to the:

•	There was a connection made to a socket on port 3735, which is likely for real-time debugging or statistics gathering.

•	Disconnected: The connection to the socket was disconnected normally.

•	Job ended: The job ecommerce ended with an exit code of 0 which indicates that the job has completed successfully without errors. If there was an error, we would typically see a non-zero exit code and an error message in the log.

Several attempts on refreshing and creating new job to ensure that job can be successfully Run in the tools such as creating e-commerce2 new job as well as restarting the PC, however similar results achieved. 
Hence for execution of Data Preprocessing using Talend Data Integration, the exercise using this tool will be excluded and assessment will be proceeded with Talend Data Preparation and SAS E-Miner as described in previous section.


#### 4.2 Decision Tree Model
To understand the customer behaviour, decision tree model is established. From “Model” tab, select “Decision Tree”. 
In order to splitting Role and Node, we need to define the Maximum Branch and Maximum Depth to 2 and 6 and Leaf Size Node to 5. We can maintain all the remaining default value and click “Run” to execute the model

Based on the above result, the decision tree model appears to predict 'Subscription Status', with different paths in the tree indicating the profiles of customers who are likely to subscribe or not, based on the input variables in “e-commerce” dataset that shown in Figure 2.3 and Figure 2.4. It can be seen that each node (representing in the box) represents a decision rule that splits the data based on the best predictor variable at that point. 
In the Decision Tree, we can see splits based on 'Discount Applied', 'MembershipLevel', 'Frequency of Purchases', and 'Purchase Amount (USD)'. The splits are binary, dividing records into two groups based on the criterion in each node.

The fact that 'Discount Applied' is the first split suggests it is an important predictor of 'Subscription Status' with important of 1.0000 followed by Membership Level with degree of important 0.4172. The Purchase_Amount_USD_ indicate least important on the customer subscription status with important 0.0735 as shown in Figure 2.5.

The decision tree model's predictive ability can be evaluated from the lift chart and fit statistics which can be observed from Figure 2.6 and Figure 2.7 respectively. From the chart. it seems that the predictive model to be performing better than random guessing but is not perfect. The point where the lift line is furthest above the baseline indicates where the model is most effective. The 'Depth' on the x-axis usually represents the percentage of the dataset or population. For example, a depth of 20 could represent the top 20% of predictions from the model. The lift chart typically starts high and then decreases. This is expected because we are capturing the best predictions first (those most likely to be true positives), and as we move through the population, the effectiveness of the model diminishes.

If the lift line is below the baseline, it indicates that the model is performing worse than random chance at that point. Based on the lift chart, the lift line shows that the model has good lift at the beginning, meaning it is effective at identifying positive outcomes, but the effectiveness decreases as we move through the population. This is typical behaviour for a lift chart and indicates that using the model to prioritize the outreach or interventions would be more effective than approaching customers randomly.

However, it is to be noted that there is misclassification rate in the Fit Statistics with 0.144103 which indicate that the percentage of the predictions were wrong, which can be a straightforward way of evaluating the model's accuracy. The misclassification rate of about 14.41% suggests that the model is relatively accurate, correctly classifying about 85.59% of cases.
The Average Squared Error (ASE) and Root Average Squared Error (RASE) provide measures of the model's error in terms of probability estimations for the classes. Based on the result, it can be seen that the ASE and RASE is lower which indicate the model is making fewer errors on average.
The 'Total Degrees of Freedom' being equal to the 'Number of Observations' suggests that this might be a simple model without many parameters, or it might be an indication of an error in reporting or calculation

In order to improve the prediction model, it would be also essential to look at the performance on a validation set to get a sense of how the model might perform on new or unseen data.

Now, we try to see how does changing the Maximum Branch and Depth and Node for Leaf Size and Number of Rules will affect the result. From the Property, we will specify the Maximum Branch and Maximum Depth to be 4 and 8 and and Node for Lead Size and Number of Rules to 10 (double from the first decision tree model).

Based on the result , the “Discount Applied” remain the first variable importance in the decision tree where it is the most significant predictor of “Subscription Status”. ”

For those who received a discount, 'MembershipLevel' is an important next predictor, with 'Frequency of Purchases' also playing a crucial role for customers with higher membership levels. 
The tree suggests that customers with "SILVER, GOLD" membership and "WEEKLY" purchase frequency have a higher likelihood (95.86% "YES") of subscribing.
In terms of comparison between the first and second Decision Tree Model, the choice between the two depends on the context and the goal of the analysis.

If interpretability and simplicity are priorities (for example, if the rules are to be communicated to a non-technical audience or if the model is to be implemented in a real-world scenario where simplicity is key), the second tree might be preferable.

If the goal is to maximize prediction accuracy and the additional complexity of the first tree offers a significant improvement in performance (as assessed by validation metrics), the first tree might be the better choice. In addition, it is t's also important to consider overfitting whereby more complex trees can fit the training data too closely, capturing noise rather than underlying patterns, which can lead to poor performance on new data. This is why model validation using separate datasets is crucial.



#### 4.3 Ensemble Model
In performing Ensemble Method, below steps will be executed in the SAS E-Miner. The Ensemble Node creates a new model by taking a function of posterior probabilities (for class targets) or the predicted values (for interval target) from multiple models. 

First, we need to drag and drop the "Ensemble" node from the “Model” tab into the workspace. To configure the Ensemble Node, double-click on the "Ensemble" node to configure its properties. We then specify type of ensemble method that need to be executed, in this case for Bagging (Bootstrap Aggregating), we will select "Bagging" as the method. Then, choose "Random Forest" as the algorithm within the bagging method settings. In SAS Enterprise Miner, Random Forest is a separate node, but it can also be part of the ensemble node options.

Connect the data source node to the "Ensemble" node and “Run” the result.

Based on the result shown in Figure 3.3, it can be seen be summarised that the model appears to have a moderate level of predictive accuracy, with a misclassification rate of 14% (0.144103). The ensemble method, which seems to be averaging predictions from a set of models, has been able to correctly identify a good proportion of both events (subscriptions – “YES”) and non-events (non-subscriptions “NO”).

Based on the Score Distribution Plot, it can be seen that the x-axis represents the model score, which is the predicted probability that an observation is an event (YES). Ideally, we want to obtain the blue line chart (events) high on the left (indicating high model scores for actual events) and the red line (non-events) high on the right (indicating low model scores for actual non-events).

In terms of Cumulative Lift Chart, it can be observed that the chart shows how much better the ensemble model is at predicting the target variable compared to a random guess. The "Cumulative Lift" line should ideally be above the "Baseline Cumulative Lift" line, which indicates the model is better than random chance.

For the Gain summary result, the model starts off capturing a high number of positive cases (subscriptions) quickly. This is evident in the steep initial slope of the Gain Line.
As more cases are considered, the incremental gains decrease. The Gain Line is above the Baseline, indicating that the model is doing better than random chance at identifying positive outcomes. The Best Gain Line indicates the maximum potential for gain, which is not fully visible in the chart but would typically be at or near the top of the chart, showing the theoretical maximum gain if every positive case was identified before any negative case.

Based on the overall Gain line chart, the ensemble model is effective, especially at the top end, meaning it is good at identifying the most likely positive outcomes. However, as it reach deeper into the population, the effectiveness diminishes, which is typical of such models. The model would be most useful for targeting the top-ranked individuals according to the model's scores, as that's where the most substantial gains are realized compared to random selection.

Based on the Fit Statistics, it can be summarised that the ensemble model seems to have a reasonably good fit with an Average Squared Error (ASE) of about 0.08, and a misclassification rate of about 14.41%.
The RASE suggests that the model's predicted probabilities are, on average, about 0.28 away from the actual binary outcomes, which could be considered moderate performance. The number of wrong classifications (562 out of 3900) provides a raw count of errors, which can be useful for assessing the model's performance in more tangible term.


### 5.0 Reflection and Learning Outcome
In summary, the the data mining assessment has been completed with 3 data mining tools i.e. SAS E-Miner, Talend Data Preparation and Talend Data Integration. Based on the assesment, we have gained a deeper understanding of e-commerce business overview performance, such as customer churn in terms of subscription sttatus, lifetime value through membership level, and purchasing patterns based on Frequency of Purchases and Amount Purchased as well as Discounted Price. These insights are very much appreciated in real world the importance of aligning data mining objectives with business goals to drive actionable insights.

There are also some challenges encounter during the assesment such as job execution error while executing task using Talend Data Integration, however there is no significant impact in completing the project as both SAS E-Miner and Talend Data Prepartion are able to be successfully executed for the project. In addition, data cleaning such as handling the missing values as well as data standardisation will take up most of the manhours as it is essential step to ensure that the data is reliable and data quality prior proceeding with further analytics.

Furthermore, other variable attributes that can also be considered in understanding the customer behaviour such as ShippingMethod, Purchase Category, Age, Size of Purchase etc. However, based on the executed model, those variables are not identified  to  be importance in impacting the subscription status of the customer, but still can be conisdered to be further explored to further understand and creating impactful e-commerce business strategy and marketing.
