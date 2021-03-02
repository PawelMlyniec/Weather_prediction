# Weather_prediction

## Task
Given a dataset of weather data for different cities and days, train MLP network to predict mean temperature and whether there will be strong wind ( >= 8m/s) on the fith day.

Train network for the first three days.
For example given five days Mon-Fri predict weather on Friday given Monday, Tuesday and Wednesday.

Try different architectures. 

## Data
Dataset is in folder data.

Data description as in https://www.kaggle.com/selfishgene/historical-hourly-weather-data

## Solution
Solution was implemented using Tensorflow in Google Colab.
Consists of:
1. Reading data from files
2. Filling NA values
3. Combining data into proper dataframe (transposing and melting)
4. Aggregating data by day
5. Flattening data to receive time window in one row
6. One hot encoding label data
7. PCA preprocessing
8. Adding preprocessing one hot encoding layer with dictionary
9. Adding normalization layer
10. Data splitting
11. Testing different hyperparameters using tensorboard HPtuning:
  * Different learning rates using random search
  * Different number of layers and neurons
  * Different preprocessing
12. Testing different architectures (see graphs on the bottom):
  * Using only three days
  * Pretraining network to predict fourth day and then predicting fifth day using only fourth predicted day
13. Models ensembling:
  * Hard voting (classification)
  * Soft voting (classification)
  * Mean from 10 models (regression)
  * Mean from 10 models removing outliers (regression)

## Results
[Tensorboard regression, prediction using three days](https://tensorboard.dev/experiment/SaoJVRGuQbyMDm7WGsBs4Q/#scalars)

[Tensorboard regression, prediction using fourth day](https://tensorboard.dev/experiment/sD7eB3eVT8OtPGC52gxUew/)

[Tensorboard classification, prediction using three days](https://tensorboard.dev/experiment/xNkz8VaGQqCEQPZjKhXZrw/#hparams)

[Tensorboard classification, prediction using fourth day](https://tensorboard.dev/experiment/BaIEUVj6QJOfN1h0QGVRUQ/)

## Co-authors 
Ula Żukowska

## Documentation in Polish
1. Weather-description.pdf

## Info
Project is done as a part of the course "Neural Networks" at Warsaw University of Technology.

## Appendix Graphs
### Base model
![alt text](https://github.com/PawelMlyniec/Weather_prediction/blob/main/graphs/base_model.png)
### Base model with normalization layer
![alt text](https://github.com/PawelMlyniec/Weather_prediction/blob/main/graphs/base_model_norm.png)
### Pretrained model predicting forth day
![alt text](https://github.com/PawelMlyniec/Weather_prediction/blob/main/graphs/model_4d.png)
### Model using pretrained model
![alt text](https://github.com/PawelMlyniec/Weather_prediction/blob/main/graphs/model_4d_2.png)




