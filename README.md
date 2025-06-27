# LSTM-based Air Pollution Prediction 🌬️📊


## Project Overview 📈

This repository contains a deep learning project focused on predicting air pollution levels using Long Short-Term Memory (LSTM) neural networks. The project leverages a time-series dataset of air pollution and weather conditions to forecast future pollution concentrations, specifically PM2.5. 💨

## Problem Statement ⚠️

Accurate prediction of air pollution is critical for public health and environmental management. This project addresses the challenge of forecasting PM2.5 concentrations by identifying temporal dependencies and patterns within historical environmental data. 😷🏙️

## Dataset 📁

The project utilizes the `pollution.csv` dataset, which typically contains hourly data on:
* PM2.5 concentration (the target variable) 🏭
* Various weather conditions such as dew point (DEWP), temperature (TEMP) 🌡️, pressure (PRES), wind direction (cbwd) 🧭, cumulated wind speed (Iws), cumulated hours of snow (Is) ❄️, and cumulated hours of rain (Ir) 🌧️.

The dataset used is commonly sourced from publicly available repositories, such as the UCI Machine Learning Repository or Kaggle, pertaining to air quality in cities like Beijing, China. 🇨🇳

## Project Structure 🏗️

The repository is organized as follows:

├── pollution.csv                # The dataset used for training and testing
├── LSTM_Air_Pollution_Predictor.ipynb # Jupyter Notebook containing the code
├── README.md                    # This README file
└── requirements.txt             # List of Python dependencies



## Methodology 🧠

The core of this project involves building and training an LSTM model for multivariate time series forecasting. The key steps implemented are:

1.  **Data Loading and Preprocessing:** 🧹
    * Loading the `pollution.csv` dataset.
    * Handling missing values (if any).
    * Encoding categorical features (e.g., wind direction) using Label Encoding.
    * Normalizing numerical features using `MinMaxScaler` to scale data between 0 and 1.
      
2.  **Time Series Framing (Supervised Learning):** 🕰️
    * Transforming the raw time series data into a supervised learning problem using lagged observations (e.g., using the previous hour's data to predict the current hour's pollution).
      
3.  **Data Splitting:** ✂️
    * Dividing the dataset into training and testing sets based on a time-based split (e.g., first year for training, subsequent data for testing).
    * Reshaping the input data (`X`) into the 3D format required by LSTMs: `[samples, timesteps, features]`.
      
4.  **LSTM Model Architecture:** 🔗
    * A Sequential Keras model is defined.
    * One or more LSTM layers are used to capture temporal dependencies.
    * A Dense output layer is used for predicting the single PM2.5 value.
    * The model is compiled with a suitable loss function (e.g., Mean Absolute Error - MAE) and an optimizer (e.g., Adam).
      
5.  **Model Training:** 🏋️
    * The LSTM model is trained on the prepared training data.
    * Validation is performed on the test set during training to monitor performance.
      
6.  **Prediction and Evaluation:** ✨
    * Making predictions on the unseen test data.
    * Inverting the scaling on predictions and actual values to get them back into their original scale.
    * Evaluating the model's performance using metrics such as Root Mean Squared Error (RMSE).
    * Visualizing actual vs. predicted pollution levels. 📊

## Getting Started ▶️

To run this project locally, follow these steps:

### Prerequisites ✅

* Python 3.x 🐍
* Jupyter Notebook (optional, but recommended for `.ipynb` file) 📓
* The required Python libraries listed in `requirements.txt`.

### Installation 🚀

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/emmanueljirehb/LSTM-using-Air-Pollution-dataset.git](https://github.com/emmanueljirehb/LSTM-using-Air-Pollution-dataset.git)
    cd LSTM-using-Air-Pollution-Predictor
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

### Usage 🏃‍♂️

1.  **Ensure the `pollution.csv` dataset is in the root directory of the cloned repository.**
    (If it's not present, you might need to download it from a source like Kaggle or UCI Machine Learning Repository and place it there.)

2.  **Open the Jupyter Notebook:**
    ```bash
    jupyter notebook LSTM_Air_Pollution_Predictor.ipynb
    ```

3.  **Run all cells in the notebook** to execute the data preprocessing, model training, prediction, and evaluation steps.

## Results 📉

(Here, you can add a brief summary of your model's performance, e.g., the final RMSE, and ideally, include a plot showing actual vs. predicted values. You can generate and save plots from your notebook and then embed them here.)

Example:
The model achieved an RMSE of `[Your RMSE Value]` on the test set, demonstrating its ability to forecast PM2.5 levels.


## Technologies Used 🛠️

* Python 3.x 🐍
* Pandas 🐼
* NumPy
* Scikit-learn
* Keras / TensorFlow
* Matplotlib 📊

## Future Enhancements 🚀💡

* Experiment with different LSTM architectures (e.g., stacked LSTMs, Bidirectional LSTMs).
* Hyperparameter tuning using techniques like Grid Search or Random Search. ⚙️
* Incorporate more sophisticated feature engineering.
* Explore other deep learning models for time series forecasting (e.g., GRU, CNN-LSTM hybrids).
* Real-time data integration and prediction. 📡
