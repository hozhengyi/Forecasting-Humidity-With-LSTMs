# Relative Humidity Forecasting with Univariate LSTMs
Multivariate approach to relative humidity forecasting using LSTMs trained on US NSRDB datasets
Authors: [Ho Zheng Yi](https://github.com/hozhengyi), [Mayank Jain](https://github.com/jain15mayank), [Soumyabrata Dev](https://github.com/Soumyabrata)
With the spirit of reproducible research, this repository contains all the codes required to produce the results in the manuscript:

Ho. Z.Y, Jain. M and Dev, S.(2021). Stateful Neural Networks for Relative Humidity Forecasting

All code is written in Python 3.7

see my slides at https://docs.google.com/presentation/d/1PbFpqZ0tOpQJGvHdPQ_EGJroVBX2LmHM6-kdwXLvHfc/edit?usp=sharing

# Code Organisation
## Dependencies
The following libraries should be installed before the execution of the codes:
- Numpy 1.20 `pip install numpy`
- Pandas 1.2 `pip install pandas`
- matplotlib 3.4 `pip install matplotlib`
- Tensorflow 2.4 `pip install tensorflow`

## Data Files
The data used in this work is provided by the National Solar Radiation Database (NSRDB) and can be downloaded via API requests. Detailed download instructions are provided [here](https://nsrdb.nrel.gov/data-sets/api-instructions.html). Download the relative humidity values over mainland United States from 1998 to 2019, totalling 192720, and extract relative humidity values from Station ID: 878848 (GMT -6). 

The following file contains the training/validation data used in this work.


## Scripts
The following list is a description of each Python script contained in this repository.

# Running
