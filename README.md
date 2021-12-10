
**


`              	`**DATA MINING** 

`  		`**PROJECT**


`                               `*Telco Customer Churn Using K-Modes Clustering*

- *Rudraksh Mishra*















**TABLE OF CONTENTS**

` `TOC \h \u \z [**Project Title](h#_o3cnwqkgw54q)**	 PAGEREF \_o3cnwqkgw54q \h **3**

[**Team Members](h#_uak89b5crlti)**	 PAGEREF \_uak89b5crlti \h **3**

[**Project Contact Person](h#_2vspky7re0y)**	 PAGEREF \_2vspky7re0y \h **3**

[**Problem Description](h#_38hneh4xcup2)**	 PAGEREF \_38hneh4xcup2 \h **3**

[**Mining Topics](h#_s9h7ak8l3t0s)**	 PAGEREF \_s9h7ak8l3t0s \h **4**

[5.1 Data preprocessing steps and storing choices](h#_9j38qm6dq1al)	 PAGEREF \_9j38qm6dq1al \h 4

[5.2 Data Visualization](h#_tk11tby6bg67)	 PAGEREF \_tk11tby6bg67 \h 4

[5.3 Data cleaning- cleaning false data](h#_ky0pvgm1hnbr)	 PAGEREF \_ky0pvgm1hnbr \h 6

[5.4 Outlier Detection/ Anomaly Detection:]( h )	 PAGEREF \_3mrv4srqmrxg \h 6

[5.5 Feature selection- chi2:](h#_g50w2t39ipcl)	 PAGEREF \_g50w2t39ipcl \h 8

[5.6 Association Rule Mining](h#_gsbpg9frp1cr)	 PAGEREF \_gsbpg9frp1cr \h 10

[5.7 K Elbow Method:](h#_rqi91jxclwj5)	 PAGEREF \_rqi91jxclwj5 \h 11

[5.8 Silhouette Method:](h#_le23hwazfpxr)	 PAGEREF \_le23hwazfpxr \h 12

[5.9 KModes Clustering & MCA:](h#_9oo8w13t9j3w)	 PAGEREF \_9oo8w13t9j3w \h 14

[**Limitations of the clustering methods](h#_6gayqp65rn8g)**	 PAGEREF \_6gayqp65rn8g \h **15**

[**Dataset source and attributes]( h )**	 PAGEREF \_k3umgqey7g7o \h **16**

[8.1 Roles and responsibilities](h#_du6p88bp0mr5)	 PAGEREF \_du6p88bp0mr5 \h 19

[8.2 Deliverables and tentative schedule:](h#_qqzi9031srzv)	 PAGEREF \_qqzi9031srzv \h 19

[**References]()**	 PAGEREF \_8wfweys31rh5 \h **20**




1. # **Project Title**
Telco Customer Churn Clustering

1. # **Team Members**
Ambika Chundru (<ajc7832@psu.edu>)

`          `Ashwath Ramesh (<akr6021@psu.edu>)

`          `Rudraksh Mishra (<rjm7016@psu.edu>)

1. # **Project Contact Person**
Rudraksh Mishra (<rjm7016@psu.edu>)

1. # **Problem Description**
This project aims to find interesting patterns and information from the past data collected using various data mining methods. This is done by forming clusters by identifying and grouping similar data points.

1. # **Mining Topics** 
### **5.1 Data preprocessing steps and storing choices**
The data preprocessing steps include: -

1. After importing the data and necessary libraries all the columns in the table are converted into categorical data with most of them being binary.
1. All the rows with ‘tenure’ equal to 0 were dropped and those also with a null value in monthly charge were dropped. 
1. Tenure and monthly charges which were originally float and were converted into categorical data.
1. One Hot encoding is done, where all the categorical data has been represented in a binary form.
### **5.2 Data Visualization**
- This is a visualization of the frequency distribution of monthly charges and tenure.  From this, we can observe that people with low tenure have a high chance of churning, at the same time people with high monthly charges have a high probability of churning too.
- This visualization shows the percentage of the people who churned sorted by their tenure in months.

- Through this visualization, we can observe that the count of the people who churned is high when the contract is month-to-month.

- Through this visualization, we can see that customers who have type month-to-month contracts are not yet loyal. Hence, the customers who use to have a month-to-month contract have a higher possibility of churn than the others. 

### **5.3 Data cleaning- cleaning false data**
** The dataset we inherited was filled with unwanted and false data which had to be removed. 

The column ‘Customer\_ID’ provided us with no useful information in predicting if the customer will churn or not and thus it was dropped.

All the rows with ‘tenure’ equal to 0 were dropped and those also with a null value in monthly charge were also dropped.

### **5.4 Outlier Detection/ Anomaly Detection:**
Here we used the PyOD library with an outlier factor of 6% to find the outliers in the data. PyOD is a comprehensive and scalable Python toolkit for detecting outlying objects in multivariate data. We used Isolation Forest and ABOD methods for outlier detection.

Isolation Forest uses decision trees, in these trees, partitions are created by first randomly selecting a feature and then selecting a random split value between the minimum and maximum value of the selected feature.

Whereas, ABOD assesses the broadness of the angular spectrum of a point as an outlier factor.

Observations:

- From Isolation Forest:

Outliers detected: 423 

Inliers detected: 6620



- From Angle-based Outlier Detector (ABOD):

Outliers detected: 0

Inliers detected: 7043


### **5.5 Feature selection- chi2:**
Feature selection is a process where those features in a data frame that contribute most to the output are automatically selected. Having irrelevant features in the data could reduce the accuracy of the model and thus leading to poor output.

In chi2 feature selection, we intend to find out the dependency of the churn, which is the target variable based on other factors. We use the chi2 value to determine this. The hypothesis taken at first is that the churn is independent of the feature and when the chi2 value is high, this hypothesis is proven to be incorrect. Using this we can select the features that have a higher effect on the churn rate and focus on that.

Observations:

The chi2 feature selection scores of the input features

Plotting the result of the test:

From the results above we chose the top 10 features and reshaped the data frame accordingly.

The 10 features were SeniorCitizen, Partner, Dependents, Tenure, Onlinesecurity, Techsupport, Contract, Paperlessbilling, Paymentmethod, Monthlycharges

The reshaped data frame:
**

### **5.6 Association Rule Mining**
Association rule mining is done to find interesting frequent itemsets. We can use the findings to better predict if the customer will churn or not. We use the apriori algorithm to find the frequent itemsets with minimum support of 0.9 as the threshold. Association rules have been done with lift as 1 as the minimum threshold.

Observations:

Using the apriori algorithm, these were the frequent itemsets when churn=1:

Using the apriori algorithm, these were the frequent itemsets when churn=0:


### **5.7 K Elbow Method:** 
This method uses the optimum value of the number of clusters. This runs the kmode clustering on a loop each time increasing the value of the number of clusters and then plotting the result against the number of clusters to get a curve. The point at which the curve bent and gives a shape of the ‘elbow’ is chosen as the optimum number of clusters. We choose that point since; it is the point at which the Sum of the Square of Errors first starts to diminish.

Observations:


### **5.8 Silhouette Method:**
It is another method used to find the optimum value for K. It is used to analyze the mean distance between the clusters and is considered a better method than Elbow since it is less ambiguous. It is done by using the silhouette score which is calculated using the mean intracluster distance and the mean nearest cluster distance

Observations:

The silhouette score is:

The result of the silhouette score plotted against the number of clusters:



### **5.9 KModes Clustering & MCA:**
Kmeans is generally the most commonly used clustering technique. But it only works for the numerical data. It’s actually not suitable for the data that contains the categorical data type. So, Huang, in 1998, proposed an algorithm called k-Modes which is created in order to handle clustering algorithms with the categorical data type.

Observation:

After the K modes clustering has been done with the number of clusters chosen to be 3. Each cluster has been given a label and they have been added to the data frame:



The properties of the centroids of three clusters were noted and observed:

The resulting clusters were also plotted using MCA.  MCA is applicable specific to categorical features. The idea of MCA is to apply CA into the one-hot encoded version of the dataset. The result is like the PCA or CA result, two principal components with SVD result as the values. The results are then plotted in a 2-dimensional plot based on the cluster they belong to.

1. # **Limitations of the clustering methods**
   - **KModes:** 
   - Data types can only be categorical, cannot be a mix of categorical and numerical.
   - The feature on which the disagreement matters. Because K-Modes simply counts the number of dissimilarities, it doesn’t matter to the algorithm on which “features” points are different. If a given category is particularly prevalent, this may become an issue as the algorithm will not take it into account when clustering.

- **Association Rule Mining:**
- They have a large number of discovered rules with low comprehensibility.

1. # **Dataset source and attributes**
The data is taken from the public repository in the Kaggle database. It was posted by [*BlastChar*](https://www.kaggle.com/blastchar) and is called Telco Customer Churn Data. The link is as follows: - [https://www.kaggle.com/blastchar/telco-customer-churn]( h )

The data consists of 7043 records, each representing a customer, and 21 fields namely: -

1) Customer ID – Its object Data type. All the values in it are unique hence it is used as a primary key
1) Gender – It’s a binary categorical (object) Data type. It represents the gender of the customer either male or female.
1) Seniorcitizen – It’s an Integer data type. It shows if the customer is a senior citizen or not. Yes, represents they are and No represents they aren’t.
1) Partner - It’s a binary categorical (object) Data type. It shows if the customer has a partner or not. Yes, represents they have and No represents they don’t.
1) Dependents - It’s a binary categorical (object) Data type. It shows if the customer they have any dependents or not. Yes, represents they have and No represents they don’t.
1) Tenure - It’s an Integer data type. It shows the number of years the customer has held the service.
1) PhoneService: - It’s a binary categorical (object) Data type. It shows if the customer they have phone service or not. Yes, represents they have and No represents they don’t.
1) MultipleLines: - It’s a nominal categorical (object) Data type. It shows if the customer they have multiple phone services or not. Yes, represents they have, No represents they don’t, and No phone service represents they don’t even have 1 phone service.
1) PaperlessBilling: - It’s a binary categorical (object) Data type. It shows if the customer they have enrolled for paperless billing. Yes, represents they have and No represents they don’t.
1) MonthlyCharges: - It’s a float data type. It shows the amount of monthly charge of the service the customer pays.
1) Churn: - It’s a binary categorical (object) Data type. It shows if the customer they have churned or not. Yes, represents they have and No represents they don’t.
1) InternetService: - It’s a nominal categorical (object) Data type. It shows if the customer they have phone service or not. DSL represents they use DSL service, Fiber Optics represents they use fiber optics and No represents they don’t use any service.
1) OnlineSecurity: - It’s a nominal categorical (object) Data type. It shows if the customer they have an Online Security to their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) OnlineBackup: - It’s a nominal categorical (object) Data type. It shows if the customer they have an Online Backup to their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) DeviceProtection: - It’s a nominal categorical (object) Data type. It shows if the customer they have a Device Protection to their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) TechSupport: - It’s a nominal categorical (object) Data type. It shows if the customer they have a Tech Support to their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) StreamingTV: - It’s a nominal categorical (object) Data type. It shows if the customer can stream TV using their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) StreamingMovies: - It’s a nominal categorical (object) Data type. It shows if the customer can stream movies using their internet service or not. Yes, represents they have, No represents they don’t, and No internet service represents that they don’t have any internet service.
1) Contract: - It’s a nominal categorical (object) Data type. It represents the type of contract the customer has. Month to month, represents they have a month-to-month contract, One year represents they must pay yearly, and Two years represents that they have a two-year contract.
1) PaymentMethod: - It’s a nominal categorical (object) Data type. It represents the payment method that the customer use. A mailed check means the user mails the payment, an electronic check means the user sends an e-check, a Credit card means the user uses a credit card and a Bank transfer means the user sends the money via a bank transfer.
1) TotalCharges: - It’s a nominal categorical (object) Data type. Each value represents the total amount paid by the customer.

The dataset is in .csv format.

1. **Deliverables**

### **8.1 Roles and responsibilities**
- Rudraksh Mishra: pilot presentation, data visualization, use elbow method, and Silhouette method, apply k modes clustering to see optimum k values, Feature extraction- MCA, final presentation, writing the report, creating the PowerPoint
- Ambika Chundru: Data preprocessing, data cleaning, applying chi-square feature selection poster preparation, writing the report, creating the PowerPoint, final presentation.
- Ashwath Ramesh: readme document, writing the report, PowerPoint, final presentation.

### **8.2 Deliverables and tentative schedule:** 
- Chose a data mining project and deliver a pilot presentation (Week 1)
- First, we import and clean the data. (Week 2)
- Then we pre-process it by standardizing (Week2)
- ` `Relationships between different attributes (correlations in the data) and build visualization to support them. (Week 2)
- Feature selection using chi-square feature selection (Week 2)
- Apply k-mode clustering algorithm, Association rule mining, k++ elbow method, silhouette method to see optimum k values. (Week 3 & 4)
- Feature extraction- MCA (week 4)
- Final presentation and plotting observed results (Week 5)


1. # **References**
1) <https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113>
1) <https://www.kaggle.com/blastchar/telco-customer-churn>
1) <https://www.kaggle.com/ashydv/telecom-churn-prediction-logistic-regression>
1) <https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9>
1) [https://amva4newphysics.wordpress.com/2016/10/26/into-the-world-of-clustering-algorithms-k-means-k-modes-and-k-prototypes/comment-page-1/]( h )
1) [https://www.kaggle.com/supratimhaldar/telco-customer-churn-exploratory-data-analysis]( h )
1) [https://medium.com/@techtangent.in/visualizing-the-telco-churn-dataset-and-picking-up-the-important-features-94bc154e4153]( h )
1) [https://www.kaggle.com/nasirislamsujan/an-eda-on-telco-customer-churn-prediction]( h )
1) <https://docs.tibco.com/data-science/GUID-F0FC2493-A73D-4BE8-A3F8-6E26C6057371.html>
1) <https://www.analyticsvidhya.com/blog/2021/01/in-depth-intuition-of-k-means-clustering-algorithm-in-machine-learning/>
1) [https://towardsdatascience.com/silhouette-method-better-than-elbow-method-to-find-optimal-clusters-378d62ff6891#:~:text=The%20silhouette%20method%20computes%20silhouette,each%20object%20has%20been%20classified]( h ). 

