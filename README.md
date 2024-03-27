# CryptoClustering

In this challenge, we have to predict if cryptocurrencies are affected by 24-hour or 7-day price changes, using the knowledge of Python and unsupervised learning.

# Prepare the Data
1. Use the `StandardScaler()` module from `scikit-learn` to normalize the data from the CSV file.
2. Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
  a. Below is the screenshot of the first five rows of the scaled DataFrame:
![1](https://github.com/Pooja14n/CryptoClustering/assets/144713762/1659f1ef-75c2-4343-b66f-417842d9f87d)

# Find the Best Value for k Using the Original Scaled DataFrame
1. Use the elbow method to find the best value for `k` using the following steps:
  a. Create a list with the number of `k` values from 1 to 11.
  b. Create an empty list to store the inertia values.
  c. Create a `for` loop to compute the inertia with each possible value of `k`.
  d. Create a dictionary with the data to plot the elbow curve.
  e. Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for k.
  f. Answer the following question in your notebook: What is the best value for `k`?

# Cluster Cryptocurrencies with K-means Using the Original Scaled Data
1. Use the following steps to cluster the cryptocurrencies for the best value for `k` on the original scaled data:
  a. Initialize the K-means model with the best value for `k`.
  b. Fit the K-means model using the original scaled DataFrame.
  c. Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
  d. Create a copy of the original data and add a new column with the predicted clusters.
  e. Create a scatter plot using hvPlot as follows:
    (i)  Set the x-axis as "PC1" and the y-axis as "PC2".
    (ii) Color the graph points with the labels found using K-means.
    (iii)Add the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

# Optimize Clusters with Principal Component Analysis
1. Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
2. Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
  a. What is the total explained variance of the three principal components?
3. Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
  a. The first five rows of the PCA DataFrame should appear as follows:

# Find the Best Value for k Using the PCA Data
1. Use the elbow method on the PCA data to find the best value for `k` using the following steps:
  a. Create a list with the number of k-values from 1 to 11.
  b. Create an empty list to store the inertia values.
  c. Create a `for` loop to compute the inertia with each possible value of `k`.
  d. Create a dictionary with the data to plot the Elbow curve.
  e. Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.
  f. Answer the following question in your notebook:
    (i) What is the best value for `k` when using the PCA data?
    (ii)Does it differ from the best k value found using the original data?

# Cluster Cryptocurrencies with K-means Using the PCA Data
1. Use the following steps to cluster the cryptocurrencies for the best value for `k` on the PCA data:
  a. Initialize the K-means model with the best value for `k`.
  b. Fit the K-means model using the PCA data.
  c. Predict the clusters to group the cryptocurrencies using the PCA data.
  d. Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
  e. Create a scatter plot using hvPlot as follows:
    (i)  Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
    (ii) Color the graph points with the labels found using K-means.
    (iii)Add the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.
  f. Answer the following question:
    a. What is the impact of using fewer features to cluster the data using K-Means?
