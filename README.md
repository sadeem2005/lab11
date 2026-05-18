# lab11

1. Why is this an unsupervised learning problem?There is no target column and no predefined labels for this class of data, making it an unsupervised learning problem. You would want to find natural groups of customers based on their credit card behavior.
 
2.Why did we remove the CUST_ID column?We removed the CUST_ID column because it is only a unique identifier for each customer and does not provide any behavioral information useful for clustering.

3. Which columns had missing values?The columns that had missing values were identified using:
df.isnull().sum()
In this dataset, missing values are commonly found in columns such as MINIMUM_PAYMENTS and CREDIT_LIMIT.

4. How did you handle the missing values?For dealing with missing values we applied mean imputation:
df = df.fillna(df.mean()). Each missing value was replaced by the mean value for the column.

5.  Why is scaling important before applying K-Means?The reason scaling is necessary is that K-Means utilizes Euclidean distance to determine the similarity of observations. Distance calculation of the data for features with different sizes would be dominated by features with larger numerical ranges if the data is not standardized.
  
6.  Which K value did you choose?chose K = 4 because the elbow curve showed a noticeable bend around 4 clusters, indicating diminishing returns after that point. Similarly, the silhouette score was relatively high at K = 4, suggesting that the clusters were reasonably well separated.
    
7.   Based on the cluster summary table?According to the cluster summary table:
Cluster 0: Low balances, low spenders -- typically inactive or low-usage customers.
Cluster 1: Frequent purchase clients and frequent transaction customers; probably customers who are active and valuable.
Cluster 2: High cash advances and high balances: could be leaning towards credit to use for cash needs.
Cluster 3: Moderate users and balanced spending pattern
   
8.   Which cluster may represent high-value customers?The cluster with the highest values for purchases, credit limit, and payment activity likely represents high-value customers.
  
9.   Which cluster may represent customers who rely more on cash advance?The cluster with the highest average CASH_ADVANCE value represents customers who depend more on cash advances
  
10.  How can a company use these clusters for marketing strategy?These clusters allow a company to create targeted marketing campaigns. Reward high-value customers with premium offers and loyalty programs. Encourage low-usage customers with promotions and incentives. Develop tailored credit products based on each segment’s spending behavior.
