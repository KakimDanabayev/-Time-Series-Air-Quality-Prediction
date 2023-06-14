## [Time-Series] Air-Quality-Prediction Dataset
![beijing-air-pollution](https://user-images.githubusercontent.com/127029668/222965243-f963b139-091a-42bd-b9f2-84ccfa152eef.jpg)

The dataset contains PM2.5 of hourly averaged responses from sensors embedded in an Air Quality Device recorded by the US Embassy in Beijing from 2010 to 2014 (four years).

## Objective of projects
- Conduct an analysis of multivariate time and use LSTM to predict future air pollution level using the past values, develop and compare different approaches to time-series problems.

## Role
Worked 21 hours a week as a data scientist to perform and developed a model that could predict time-series prediction tasks.
Data Analysis (using different analysing techniques) & Visualisation
Data Preprocessing for LSTM models  
Feature Engineering using various techniques 
Feature Selection 
Building and testing LSTM models
Fine Tuning of models hyperparameters 
Fine-grained models evaluation
Final results visualisation & reporting  

## Models 

### LSTM Model with 50 neurons.

In the first model we will define the LSTM with 50 neurons in the hidden layer without a Dropout Layer. Next there will be an output layer for predicting pollution. In the batch size we used three days (24*3 Hours) data. Optimizer function we used Adam method. Loss function we used means absolute error. Verbose we put 1 to observe loss and validation loss and shuffle False not to reorganize the dataset and use the data that we have for the consistency in results.

### LSTM Model with 256 neurons.

The second model will define the LSTM with 256 neurons in the first hidden layer and a Dropout Layer of 0.25. Next we put a BatchNormalization to normalize the contributions to a layer for every mini-batch and also for regularization and not using another dropout function. Then we put the final output layer for predicting pollution. In the batch size we used seven days (24*7 Hours) data. Optimizer function we used Adam method. Loss function we used means squared error. Loss function we used means absolute error. Verbose we put 1 to observe loss and validation loss and shuffle False not to reorganize the dataset and use the data that we have for the consistency in results. 

### LSTM Model with 512 neurons.

In model 3 we define the LSTM with 512 neurons in the first hidden layer and a Dropout Layer of 0.2. Next we add 2 BatchNormalization to normalize the contributions to a layer for every mini-batch and also for regularization. Then we put the final output layer for predicting pollution. We also used dense layers for changing the dimension of the vectors by using every neuron. Similarly, we have one output layer for predicting pollution. In the batch size we used ten days (24*10 Hours) data. Optimizer function we used Adam method. Loss function we used means squared error. Loss function we used means absolute error. Verbose we put 1 to observe loss and validation loss and shuffle False not to reorganize the dataset and use the data that we have for the consistency in results.    

### LSTM Model with several LSTM layers.

In model 4 we will define the LSTM with 100 neurons in the first hidden layer and a Dropout Layer of 0.3,Next there will be another hidden layer of 50 neurons and a Dropout of 0.2. Similarly, there will be two more hidden layers with respective 0.2 Dropouts and 50 neurons. In the Final Layer, 1 neuron in the output layer for predicting pollution. In the activation Function we used a linear function, because of the sequential dataset. In the batch size we used three days (24*3 Hours) data. Optimizer function we used Adam method. Loss function we used means squared error. By monitoring the value of the test data loss function, stop the training model when it is not decreasing, and save the current best model.

### Information about city 

Beijing is the capital city of the People’s Republic of China and was formerly known as Peking. It is the world’s most populous city with an estimated population of over 21 million residents. The city is located in the northern part of China and covers an area of 16,500 square kilometres. In 2019 China was classed as the 11th dirtiest country in the world. The city of Beijing was ranked at 201.

Beijing air pollution is mainly caused by vehicle emissions and the burning of coal to produce electricity. Other factors that influence air quality in Beijing include the manufacturing industry and population growth. Of the twenty cities throughout the world with the worst air quality, 16 of them are located in China. Because of this, its Environmental Sustainability Index is ranked towards the bottom amongst countries worldwide.

An increase in personal wealth can also have an influence here. With surplus money at the end of each month, an individual is more able to buy a car. The number of motor vehicles in Beijing in 2017 was estimated at 5.5 million.

Source: iqair https://www.iqair.com/china/beijing

## Air pollution influence to health

Most common health issues are a sore throat and cough. Over the past decade, lung cancer rates have risen by over 60%. Other consequences of air pollution in Beijing include yellow skies, higher mortality rates, and cancelled flights due to low visibility levels.

Air pollution is very serious in many parts of the world. Nine out of ten people in the world breathe polluted air, and the death toll caused by air pollution reaches 7 million every year. Up to one third of deaths caused by stroke, lung cancer and heart disease are due to air pollution. Air pollution is everywhere. No matter where you live, you cannot escape. The fine pollutants in the air break through our body's defences, penetrate into our respiratory and circulatory systems and damage our lungs, heart and brain.

The pollutant that affects people the most is particulate matter, usually abbreviated as PM and used as a measure of air pollution. Although particles with a diameter of 10 microns or less (≤PM10) can penetrate and embed deep in the lungs, the ones that are more harmful to health are those with a diameter of 2.5 microns or less (≤PM2.5). These particles are very small, only one 60th the diameter of a human hair.

Source: iqair https://www.iqair.com/china/beijing

## Attribute Information:
- no: row number
- year: year of data in this row
- month: month of data in this row
- day: day of data in this row
- hour: hour of data in this row
- pm2.5: PM 2.5 concentration (ug/m^3)
- DEWP: Dew Point (a,,f) (the temperature to which air must be cooled to become saturated with water vapor, assuming constant air pressure and water content.)
- TEMP:Temperature (a,,f)
- PRES: Pressure (hPa)
- cbwd: Combined wind direction
- lws: Cumulated wind speed (m/s)
- Is: Cumulated hours of snow
- Ir: Cumulated hours of rain

## Conclusion & Findings 

This hourly dataset contains the PM2.5 data from US Embassy in Beijing that tracked the city pollution level from 2010-2014. We found that there was a positive correlation between "Temperature" ad "Dew point" variables (r = 0.82), and negative correlation between "PRES" and "Dew point" (r = -0.78), "Pres" and "Temperatures" (r = -0.83). Therefore, while "Temperature" is increasing the "Dew point" is increasing too. While "PRES" is decreasing, "Dew point" is increasing.

First, the highest pollution level was tracked when the temperature was between -10 and 0 degrees of Celsius. We also found out that dew point, atmospheric temperature, atmospheric pressure have cyclicity.

Second, meteorological feature weather parameters (dew point, atmospheric temperature, atmospheric pressure, wind direction, wind speed, snow, rain) affect air quality. For example, high wind speed will reduce the concentration of PM2.5, high humidity generally worsens air pollution, and high air pressure generally results in good air quality. Therefore, meteorological parameters are of prime importance for the task of forecasting air quality.

Third, when wind speed was reaching 400-500 (m/s) the level of pollution in the city was low whereas when the wind speed was low below 100 (m/s) the level of pollution was high. In the meantime, the temperature did not predict pollution level based on this graph.

Fourth, we found out that when there were more than 20-25 hours of snow, the level of pollution in the city was not as low as if it was with the rain. In the case when it was 30-36 hours of rain, the level of pollution in the city was low whereas when there was no rain the level of pollution was high.

Fifth, in each 47 weeks from 2010-2014, when the wind speeds were slow the air pollution was high. Each 7th week from 2010-2014 air pollution was the worst during the winter time due to the colder weather and high energy consumption.

Sixth, from 2010 to 2014, in February, June and October there was the highest level of pollution. In October the wind speeds were slow during that period of time and as a result, the polluted air stayed in the capital for a longer time. Air quality decreases during the summer because of the heat and sunlight. Finally, air pollution is worse in the winter time because colder and drier air traps bring more pollution. The most polluted quarter from 2010 to 2014 was Q1 due to the cold weather and the massive use of coal during the winter time. We found out that Beijing air pollution is mainly caused by vehicle emissions and the burning of coal to produce electricity.

Seventh, the basic LSTM model with 50 neurons in the hidden layer without a Dropout Layer and one output layer for predicting pollution showed the minimal amount of the error (RMSE: 24.573, Test MAE: 13.078). With the basic model, the model 4 with 4 LSTM layers, dropout functions, and one output layer also showed the minimal amount of the error (RMSE: 26.083, Test MAE: 13.894).
