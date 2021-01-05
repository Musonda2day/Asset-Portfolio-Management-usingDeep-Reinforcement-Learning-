# Asset-Portfolio-Management-using-Deep-Reinforcement-Learning-

## Introduction
This repository represents work in progress for the Worldquant University Capstone Project titled: Asset Portfolio Management using Deep Reinforcement Learning (DRL).
The work presented explores the use of Deep Reinforcement Learning in dynamically allocating assets in a portfolio in order to solve the Tactical Asset Allocation (TAA) problem. 

## Objective
The objective of the project is to develop a model based Deep Reinforcement Learning Algorithms that will implement a Tactical Asset Allocation of a portfolio. 
The project aims to address the TAA problem by accurately capturing short to medium term market trends and anomalies in order to allocate the assets in a portfolio so as to optimize its performance by increasing the risk adjusted returns.

## Project Layout
The project is broken down in six parts in each of the attached notebooks as follows:

  **1.**	**Loading and Installing the Relevant Python Libraries**. The notebook gives the necessary libraries that are used for the implementation of the project. The FinRL library is utilized to implement our Deep Reinforcement Learning algorithms that are based on the Stable Baselines environments. In this notebook we clone the github repository for the FinRL library (https://github.com/AI4Finance-LLC/FinRL-Library). 

  Other relevant libraries include the PyPortfolioOpt librariy which make use of in implementing the Maximum Sharpe allocation strategy which is used as comparison against the performance of the DRL models. We also make use of the Ta-Lib to add technical indicators to our input data. The backtesting and evaluation of models is implemented using the Pyfolio library.

  **2.**	**Downloading the Data for the Analysis**. We make use of the YahooDownloader API in the FinRL library to get data for the 30 Dow Jones Industrial Average (Dow JIA) for the period 01 Jan 2009 to 31 December 2020. 
  The data is checked for any missing values and for any indicators with missing data for the period specified to ensure that all the tickers have equal number of data points for the analysis.
  After cleaning up, the data is saved in the csv format for use in the analysis.
  
 **3.**	**Feature Engineering and Data Preprocessing**. Feature Engineering and Data Preprocessing is performed on our dataset. We first load the saved csv file in a dataframe and then add technical indicators. A total of ten technical indicators have been added from the categories of Volume, Volatility, Trend and Momentum indicators. Additionally, we add covariance matrices with a one-year lookback to our input dataset. 
  After adding the indicators, the data is split into train and test data in the ration of 80/20 respectively. The processed data is stored in dataframes for use in the analysis. 
  
  **4.**	**Uniform Weights and Maximum Sharpe Strategies**. Two strategies are developed for comparison with the DRL models. We first build a naïve model which is based     on equal weight allocation. Then a model based on optimization of the risk adjusted returns (the Maximum Sharpe) is built. 

  The two portfolios are stored in data frames for Backtesting and benchmarking against the DRL models. 

  **5.**	**Deep Reinforcement Learning Portfolios**. Three DRL models are developed by making use of the FinRL Library which is based on the Stable Baselines environment. We present an implementation that explores the use of a number of technical indicators as inputs for solving the TTA problem. 

The three models which we implement are based on the Stable Baselines algorithms for Actor Critic (A2C), Proximal Policy Optimization (PPO) and Deep Deterministic Policy Gradient (DDPG) algorithms. 

The models implemented based on three algorithms are stored in dataframes for benchmarking and backtesting.

## Preliminary Results
From the preliminary results obtained we observe that the developed DLR models outperforms the naïve based equal weights allocation model and the best DRL model which is the A2C Model outperforms the Dow JIA Index which is the benchmark.
The Models however, are outperformed by the Maximum Sharpe model. This certainly shows that the developed models will need tuning of hyper-parameters and consideration of adding indicators that will make the training better.

## Further Works
The DRL Models have been built together with the benchmark models. The next step is to optimize the DRL models’ performance. As such, the following further works will be carried out before final conclusions and recommendations:

  **1. Feature Engineering**. Further Feature Engineering will be performed to consider addition of more relevant features to the models;

  **2. Hyper-parameter Tuning**. We will tune the hyper-parameters for the model such as the learning rate, number of raining steps etc. 

  **3. Reward Function Design**. The design of the reward function will be considered in the defined environment space.

  **4. Deep Reinforcement Learning Policy**. Further evaluation of the policies employed in the DRL models will be done to arrive at the most optimal policy.

Full List of Files and Folders included in the Repository
  **1.	Datasets Folder**. Stores the saved csv files for the dataset.

  **2.	Results Folder**. Stores the plots for the analysis.

  **3.	Tensorboard Log**. Stores the created logs for the training of the models.

  **4.	Trained Models**. Stores the DRL trained models.

  **5.	Relevant Libraries Installation Notebook.**

  **6.	Data Download Notebook.**

  **7.	Feature Engineering and Preprocessing Notebook.**

  **8.	Equal Weights and Max Sharpe Notebook.**

  **9.	DRL Portfolios Notebook.**

  **10.	Backtesting and Evaluation Notebook.**

  **11.	env_portfolio.py file**. This contains the class for the defined RL environment.

  **12.	Models.py file**. Contains the class for the DRL Agents which implement the different models.

The numbered notebooks are to be run in the order in which they have been defined. 
The repository will be updated accordingly once the models are properly tuned and then conclusions and recommendations will be updated together with the report.
