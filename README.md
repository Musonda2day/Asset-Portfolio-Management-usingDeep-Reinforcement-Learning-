# Asset-Portfolio-Management-using-Deep-Reinforcement-Learning-

## Introduction
This repository represents work for the Worldquant University Capstone Project titled: Asset Portfolio Management using Deep Reinforcement Learning (DRL).
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

Full List of Files and Folders included in the Repository

  **1.	Config Folder**. Contains the config.py file.

  **2.	Datasets Folder**. Contains downloaded data for the analysis.

  **3.	Results Folder**. Stores the plots for the analysis.

  **4.	Tensorboard Log**. Stores the created logs for the training of the models.

  **5.	Trained Models**. Stores the DRL trained models.

  **6.	Relevant Libraries Installation Notebook.**

  **7.	Data Download Notebook.**

  **8.	Stock Selection Notebook.**

  **9.	Feature Engineering and Preprocessing Notebook.**

  **10.	Feature Reduction Notebook.**

  **11.	Split Data Notebook.**

  **12.	Equal Weights and Max Sharpe Notebook.**

  **13.	DRL Portfolios Notebook.**

  **14.	Backtesting and Evaluation Notebook.**

  **15.	backtest.py file**. Contains functions applied for backtesting using the pyfolio library

  **16.	env_portfolio.py file**. This contains the class for the defined RL environment.

  **17.	Models.py file**. Contains the class for the DRL Agents which implement the different models.
  
  **18. MScFE_690_Final_Project_Report_Group 01**
  
  **19. MScFE_690_Capstone_Project_Presentation_Group 01**

The numbered notebooks are to be run in the order in which they have been defined. 
