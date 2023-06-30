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

## Model Training and Evaluation
After the data has been split, a machine learning model is trained on the training set. The model is then evaluated on the testing set to determine its accuracy, f1-score and performance.

## Predictions for Subject 9 to 12
Once the model has been trained and evaluated, it is used to make predictions on a separate set of data corresponding to subjects 9 to 12.

## Verification of Shapes of Predictions
Finally, the shapes of the predictions made by the model are verified. This is done to ensure that the predicted values are in the correct format and can be easily interpreted for further analysis.

The Verified predictions are submitted for test scores.

Overall, the code in this file provides a comprehensive pipeline for preprocessing, modeling, and evaluating human activity recognition data.
