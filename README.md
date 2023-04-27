Module 10 Application
Challenge: Crypto Clustering
In this Challenge, you’ll combine your financial Python programming skills with the new unsupervised learning skills that you acquired in this module.

The CSV file provided for this challenge contains price change data of cryptocurrencies in different periods.

The steps for this challenge are broken out into the following sections:

Import the Data (provided in the starter code)
Prepare the Data (provided in the starter code)
Find the Best Value for k Using the Original Data
Cluster Cryptocurrencies with K-means Using the Original Data
Optimize Clusters with Principal Component Analysis
Find the Best Value for k Using the PCA Data
Cluster the Cryptocurrencies with K-means Using the PCA Data
Visualize and Compare the Results
Import the Data
This section imports the data into a new DataFrame. It follows these steps:

Read the “crypto_market_data.csv” file from the Resources folder into a DataFrame, and use index_col="coin_id" to set the cryptocurrency name as the index. Review the DataFrame.

Generate the summary statistics, and use HvPlot to visualize your data to observe what your DataFrame contains.

Rewind: The Pandasdescribe()function generates summary statistics for a DataFrame.

# Import required libraries and dependencies
# Load the data into a Pandas DataFrame
# Display sample data
# Generate summary statistics
# Plot your data to see what's in your DataFrame
Prepare the Data
This section prepares the data before running the K-Means algorithm. It follows these steps:

Use the StandardScaler module from scikit-learn to normalize the CSV file data. This will require you to utilize the fit_transform function.

Create a DataFrame that contains the scaled data. Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

# Use the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file
# Create a DataFrame with the scaled data
# Copy the crypto names from the original data
# Set the coinid column as index
# Display sample data
Find the Best Value for k Using the Original Data
In this section, you will use the elbow method to find the best value for k.

Code the elbow method algorithm to find the best value for k. Use a range from 1 to 11.

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

Answer the following question: What is the best value for k?
# Create a list with the number of k-values to try
# Use a range from 1 to 11
# Create an empy list to store the inertia values
# Create a for loop to compute the inertia with each possible value of k
# Inside the loop:
# 1. Create a KMeans model using the loop counter for the n_clusters
# 2. Fit the model to the data using `df_market_data_scaled`
# 3. Append the model.inertia_ to the inertia list
# Create a dictionary with the data to plot the Elbow curve
# Create a DataFrame with the data to plot the Elbow curve
# Plot a line chart with all the inertia values computed with 
# the different values of k to visually identify the optimal value for k.
Answer the following question: What is the best value for k?
Question: What is the best value for k?

Cluster Cryptocurrencies with K-means Using the Original Data
In this section, you will use the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the price changes of cryptocurrencies provided.

Initialize the K-Means model with four clusters using the best value for k.

Fit the K-Means model using the original data.

Predict the clusters to group the cryptocurrencies using the original data. View the resulting array of cluster values.

Create a copy of the original data and add a new column with the predicted clusters.

Create a scatter plot using hvPlot by setting x="price_change_percentage_24h" and y="price_change_percentage_7d". Color the graph points with the labels found using K-Means and add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

# Initialize the K-Means model using the best value for k
# Fit the K-Means model using the scaled data
# Predict the clusters to group the cryptocurrencies using the scaled data
# View the resulting array of cluster values.
# Create a copy of the DataFrame
# Add a new column to the DataFrame with the predicted clusters
# Display sample data
# Create a scatter plot using hvPlot by setting 
# `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`. 
# Color the graph points with the labels found using K-Means and 
# add the crypto name in the `hover_cols` parameter to identify 
# the cryptocurrency represented by each data point.

Optimize Clusters with Principal Component Analysis
In this section, you will perform a principal component analysis (PCA) and reduce the features to three principal components.

Create a PCA model instance and set n_components=3.

Use the PCA model to reduce to three principal components. View the first five rows of the DataFrame.

Retrieve the explained variance to determine how much information can be attributed to each principal component.

Answer the following question: What is the total explained variance of the three principal components?

Create a new DataFrame with the PCA data. Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

# Create a PCA model instance and set `n_components=3`.

# Use the PCA model with `fit_transform` to reduce to 
# three principal components.

# View the first five rows of the DataFrame. 
# Retrieve the explained variance to determine how much information 
# can be attributed to each principal component.

#### Answer the following question: What is the total explained variance of the three principal components?

**Question:** What is the total explained variance of the three principal components?

# Create a new DataFrame with the PCA data.
# Note: The code for this step is provided for you
# Creating a DataFrame with the PCA data
# YOUR CODE HERE!
# Copy the crypto names from the original data
# Set the coinid column as index
# Display sample data
Find the Best Value for k Using the PCA Data
In this section, you will use the elbow method to find the best value for k using the PCA data.

Code the elbow method algorithm and use the PCA data to find the best value for k. Use a range from 1 to 11.

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

Answer the following questions: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?
# Create a list with the number of k-values to try
# Use a range from 1 to 11
# Create an empy list to store the inertia values
# Create a for loop to compute the inertia with each possible value of k
# Inside the loop:
# 1. Create a KMeans model using the loop counter for the n_clusters
# 2. Fit the model to the data using `df_market_data_pca`
# 3. Append the model.inertia_ to the inertia list
# Create a dictionary with the data to plot the Elbow curve
# Create a DataFrame with the data to plot the Elbow curve
# YOUR CODE HERE!
# Plot a line chart with all the inertia values computed with 
# the different values of k to visually identify the optimal value for k.
#### Answer the following questions: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?
* **Question:** What is the best value for `k` when using the PCA data?
  * **Answer:** 
* **Question:** Does it differ from the best k value found using the original data?
  * **Answer:** no it is not
Cluster Cryptocurrencies with K-means Using the PCA Data
In this section, you will use the PCA data and the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the principal components.

Initialize the K-Means model with four clusters using the best value for k.

Fit the K-Means model using the PCA data.

Predict the clusters to group the cryptocurrencies using the PCA data. View the resulting array of cluster values.

Add a new column to the DataFrame with the PCA data to store the predicted clusters.

Create a scatter plot using hvPlot by setting x="PC1" and y="PC2". Color the graph points with the labels found using K-Means and add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

# YOUR CODE HERE!
# Initialize the K-Means model using the best value for k

# Fit the K-Means model using the PCA data

# Predict the clusters to group the cryptocurrencies using the PCA data

# View the resulting array of cluster values.

# Create a copy of the DataFrame with the PCA data

# Add a new column to the DataFrame with the predicted clusters

# Display sample data
# Create a scatter plot using hvPlot by setting 
# `x="PC1"` and `y="PC2"`. 
# Color the graph points with the labels found using K-Means and 
# add the crypto name in the `hover_cols` parameter to identify 
# the cryptocurrency represented by each data point.
Visualize and Compare the Results
In this section, you will visually analyze the cluster analysis results by contrasting the outcome with and without using the optimization techniques.

Create a composite plot using hvPlot and the plus (+) operator to contrast the Elbow Curve that you created to find the best value for k with the original and the PCA data.

Create a composite plot using hvPlot and the plus (+) operator to contrast the cryptocurrencies clusters using the original and the PCA data.

Answer the following question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Rewind: Back in Lesson 3 of Module 6, you learned how to create composite plots. You can look at that lesson to review how to make these plots; also, you can check the hvPlot documentation.

# Composite plot to contrast the Elbow curves
# YOUR CODE HERE!
# Compoosite plot to contrast the clusters
# YOUR CODE HERE!
Answer the following question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?
Question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Answer: # YOUR ANSWER HERE!

