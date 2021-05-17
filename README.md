# Relative Humidity Forecasting with Univariate LSTMs
Multivariate approach to relative humidity forecasting using LSTMs trained on US NSRDB datasets
Authors: [Ho Zheng Yi](https://github.com/hozhengyi), [Mayank Jain](https://github.com/jain15mayank), [Soumyabrata Dev](https://github.com/Soumyabrata)
With the spirit of reproducible research, this repository contains all the codes required to produce the results in the manuscript:

Ho. Z.Y, Jain. M and Dev, S.(2021). Stateful Neural Networks for Relative Humidity Forecasting

All code is written in Python 3.7. 
A powerpoint summary of this work is available in this repository as `UCD_Slides.pptx`.
![Alt text](/blob/main/train.png?raw=true "Training Loss")
![Alt text](/blob/main/valid.png?raw=true "Validation Loss")

# Code Organisation
## Dependencies
The following libraries should be installed before the execution of the codes:
- Numpy 1.20 `pip install numpy`
- Pandas 1.2 `pip install pandas`
- matplotlib 3.4 `pip install matplotlib`
- Seaborn 0.11 `pip install seaborn`
- statsmodels 0.12 `pip install statsmodels`
- Tensorflow 2.4 `pip install tensorflow`

## Data Files
The data used in this work is provided by the National Solar Radiation Database (NSRDB) and can be downloaded via API requests. Detailed download instructions are provided [here](https://nsrdb.nrel.gov/data-sets/api-instructions.html). Download the relative humidity values over mainland United States from 1998 to 2019, totalling 192720, and extract relative humidity values from Station ID: 878848 (GMT -6). 

The following file contains the training/validation data used in this work.


## Scripts
The following list is a description of each Python script contained in this repository.
- `NSRDB_data_agg.ipynb` Automates API downloads for NSRDB data, performs time-zone correction and saves it as CSV and Numpy File. Also performs ADFuller test 
- `data_input.ipynb` Perform loading from numpy, data normalization, setting up tf.data.datasets pipeline, as well as function definitions for learning rate schedulers.
-  `model_architecture.ipynb` Creates model architecture (as mentioned in the paper) using Keras' Sequential API
-  `model_config.ipynb` Instantiates callbacks, set save/load paths, set compile and fit configs
-  `plt_plotter.ipynb` Helper function to plot matplotlib graphs used in the paper

# Running
To replicate this paper's results, each script can be run sequentially. The steps are provided below in running order.
1. Download the dependencies
2. Acquire an API key from the NSRDB site [here](https://developer.nrel.gov/signup/).
3. Using `NSRDB_data_agg.ipynb`, enter your API key and download the dataset as Numpy and CSV files.
4. Using `data_input.ipynb`, specify your Numpy/CSV paths and create a tf.data.datasets instance. Hyper-parameters are listed inside the notebook.
5. Using `model_architecture.ipynb`, specify your model_choice and build the desired model. Hyper-parameters are listed inside the notebook.
6. Using `model_config.ipynb`, create callbacks, set load/save paths. Hyper-parameters are listed inside the notebook.
7. Run Keras' model.compile() and model.fit() given the configurations in `model_config.ipynb` (Step 6)
8. Plot results using `plt_plotter.ipynb`
