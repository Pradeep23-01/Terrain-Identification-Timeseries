# Terrain Recognition for Time Series Data

## Context:
Human locomotion naturally exhibits attributes of energy efficiency, stability, adaptability to the environment, and robustness. However, individuals with lower limb amputations experience a disruption in this inherent capability, necessitating the use of prosthetic devices to restore basic walking functionality. In the realm of lower-limb robotic prosthetics, incorporating context awareness holds significant potential to enhance the comfort and safety of amputees. 

This research endeavor aims to develop a terrain identification system utilizing data streams from inertial measurement units (IMUs) positioned on the lower limb. While existing prosthetic leg systems typically rely on a combination of visual and inertial sensors, our investigation seeks to evaluate the viability of terrain identification based solely on inertial data, excluding visual input. By discerning distinct terrain types through this information, the control mechanisms of robotic prosthetic legs can be dynamically adjusted to accommodate changes in the surrounding environment.

## Data:
Here is a brief description of the data:
- "_x" files contain the xyz accelerometers and xyz gyroscope measurements from the lower limb.
- "_x_time" files contain the time stamps for the accelerometer and gyroscope measurements. The units are in seconds and the sampling rate is 40 Hz.
- "_y" files contain the labels. (0) indicates standing or walking in solid ground, (1) indicates going down the stairs, (2) indicates going up the stairs, and (3) indicates walking on grass.
- "_y_time" files contain the time stamps for the labels. The units are in seconds and the sampling rates is 10 Hz.

Detailed Dataset available here: https://ieee-dataport.org/open-access/lower-limb-prostheses-environmental-context-dataset

## Preprocessing Data
The first step in the code is preprocessing the data into X, Y, and Z coordinates. This is done to ensure that the data is in a format that can be easily used for further analysis.

## Apply Windowing Function
Next, a windowing function is applied to the preprocessed data. This is done to smooth out any irregularities in the data and make it more suitable for modeling.

## Train Test Split
The preprocessed and windowed data is then split into training and testing sets. This is done to ensure that the model is trained on a subset of the data and tested on another subset, in order to prevent overfitting.

# Time Series Classification:
## Model Training and Evaluation
After the data has been split, a machine learning model is trained on the training set. The model is then evaluated on the testing set to determine its accuracy, f1-score and performance.

## Predictions for Subject 9 to 12
Once the model has been trained and evaluated, it is used to make predictions on a separate set of data corresponding to subjects 9 to 12.

## Verification of Shapes of Predictions
Finally, the shapes of the predictions made by the model are verified. This is done to ensure that the predicted values are in the correct format and can be easily interpreted for further analysis.

# Time Series Forecasting:
For the same data we can forecast the data 

These are some Time series model used in this work:

- **VAR (Vector Autoregression)**:
VAR is a statistical model used to analyze the relationship between multiple time series variables. It is an extension of the autoregressive (AR) model that considers the dependencies among multiple variables. In VAR, each variable in the system is regressed on its own lagged values and the lagged values of all other variables in the system. VAR models are widely used for forecasting and analyzing the dynamic interactions between variables in economic, financial, and social sciences.

- **CNN 1D (Convolutional Neural Network 1D)**:
CNN 1D is a type of convolutional neural network specifically designed for processing one-dimensional sequential data such as time series. Unlike traditional CNNs used for image analysis, CNN 1D applies one-dimensional convolutions and pooling operations over the input data. The convolutional layers in a CNN 1D capture local patterns and features in the time series data, while the pooling layers downsample the data and extract the most salient features. CNN 1D models have been successfully applied to various time series tasks such as speech recognition, signal processing, and anomaly detection.

In the realm of time series data analysis, LSTM (Long Short-Term Memory) models have proven to be effective in capturing long-term dependencies and sequential patterns. When it comes to leveraging LSTM for time series data, three notable variations. Let's explore each of these variations in the context of the provided inputs and conditions.

- **Multi-input LSTM**: The Multi-input LSTM extends the traditional LSTM architecture by incorporating multiple input streams. In this case, the inputs consist of two components: class information and the time series data. By combining these inputs, the Multi-input LSTM can learn from both the class-specific features and the temporal dynamics of the time series. This variation allows the model to capture the relationship between the class variable and the corresponding time series patterns, enabling more accurate predictions and analysis.

- **Conditional LSTM**: The Conditional LSTM introduces the concept of conditioning into the LSTM framework, where the model's predictions are conditioned on a specific variable. In this scenario, the LSTM is conditioned on the class variable. By incorporating the class variable as a conditioning factor, the Conditional LSTM can tailor its predictions based on the given class information. This variation is particularly useful when different classes exhibit distinct patterns in the time series data, allowing the model to adapt its predictions based on the specific class context.

- **Attention-based LSTM** : The Attention mechanism, when combined with LSTM, allows the model to focus on relevant information by assigning varying levels of importance to different components of the input sequence. In the context of the provided inputs, the Attention-based LSTM utilizes attention mechanisms not only on the time series data but also on the class variable. By attending to the class variable, the model can dynamically weigh its influence on the predictions, effectively capturing the class-specific patterns in the time series data.

By incorporating these variations of LSTM models - Multi-input LSTM, Conditional LSTM, and Attention-based LSTM - into time series analysis, we can harness the potential of LSTM for capturing complex dependencies and leveraging additional information such as class variables. These variations provide flexibility in modeling time series data by incorporating class-specific features, conditioning on relevant variables, and applying attention mechanisms to focus on important components. 

Overall, the code in this file provides a comprehensive pipeline for preprocessing, modeling, and evaluating human activity recognition data.
