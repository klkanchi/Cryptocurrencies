# Cryptocurrencies


## Analysis Overview
The purpose of this project is to use unsupervised machine learning to analyze a database of cryptocurrencies and create a report including the traded cryptocurrencies classified by group according to their features.
This classification report could be used by an investment bank to propose a new cryptocurrency investment portfolio to its clients.
We use the following methods for the analysis:

1. preprocessing the database,
2. reducing the data dimension using Principal Component Analysis,
3. clustering cryptocurrencies using K-Means,
4. visualizing classification results with 2D and 3D scatter plots.

## Data Preparation
Read crypto_data.csv into Pandas. The dataset was obtained from CryptoCompare.

Discarded all cryptocurrencies that are not being traded.

Removed all rows that have at least one null value.

Filtered for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.

In order for the dataset to be comprehensible to a machine learning algorithm, its data should be numeric. Since the coin names do not contribute to the analysis of the data, deleted the CoinName from the original dataframe.

Converted the remaining features with text values, Algorithm and ProofType, into numerical data. To accomplish this task, used Pandas to create dummy variables.

Standardized the dataset so that columns that contain larger values do not unduly influence the outcome.

## Dimensionality Reduction

The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components 

The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame 

For the project, preserved 90% of the explained variance in dimensionality reduction.

## Clustering Cryptocurrencies Using K-means 

The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:

An elbow curve is created using hvPlot to find the best value for K 

Predictions are made on the K clusters of the cryptocurrencies’ data 

A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns:
Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class 

## Visualizing Cryptocurrencies Results

1. The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover (10 pt)
2. A table with tradable cryptocurrencies is created using the hvplot.table() function 
3. The total number of tradable cryptocurrencies is printed 
4. A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns 
5. A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point 


