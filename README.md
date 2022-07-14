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
