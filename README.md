# Rain Prediction using Machine Learning

This project is aimed at predicting whether it will rain in different locations of Australia using machine learning. The dataset used for this project was obtained from [Kaggle] and it contains various features such as location, date, temperature, humidity, pressure, and wind speed, among others.


Content
This dataset contains about 10 years of daily weather observations from many locations across Australia.

RainTomorrow is the target variable to predict. It means -- did it rain the next day, Yes or No? This column is Yes if the rain for that day was 1mm or more.

Data Description
Location - Name of the city from Australia.
MinTemp - The Minimum temperature during a particular day. (degree Celsius)
MaxTemp - The maximum temperature during a particular day. (degree Celsius)
Rainfall - Rainfall during a particular day. (millimeters)
Evaporation - Evaporation during a particular day. (millimeters)
Sunshine - Bright sunshine during a particular day. (hours)
WindGusDir - The direction of the strongest gust during a particular day. (16 compass points)
WindGuSpeed - Speed of strongest gust during a particular day. (kilometers per hour)
WindDir9am - The direction of the wind for 10 min prior to 9 am. (compass points)
WindDir3pm - The direction of the wind for 10 min prior to 3 pm. (compass points)
WindSpeed9am - Speed of the wind for 10 min prior to 9 am. (kilometers per hour)
WindSpeed3pm - Speed of the wind for 10 min prior to 3 pm. (kilometers per hour)
Humidity9am - The humidity of the wind at 9 am. (percent)
Humidity3pm - The humidity of the wind at 3 pm. (percent)
Pressure9am - Atmospheric pressure at 9 am. (hectopascals)
Pressure3pm - Atmospheric pressure at 3 pm. (hectopascals)
Cloud9am - Cloud-obscured portions of the sky at 9 am. (eighths)
Cloud3pm - Cloud-obscured portions of the sky at 3 pm. (eighths)
Temp9am - The temperature at 9 am. (degree Celsius)
Temp3pm - The temperature at 3 pm. (degree Celsius)
RainToday - If today is rainy then ‘Yes’. If today is not rainy then ‘No’.
RainTomorrow - If tomorrow is rainy then 1 (Yes). If tomorrow is not rainy then 0 (No).
Rain prediction for next day
The targets of the analysis are:

To analyze the dataset content using EDA and to understand if it's possible build one model allowing to predict weather for the whole Australian continent or not.

To train a model allowing to predict rain for tomorrow with the highest accuracy, F1 score and ROC-AUC metric.

To evaluate feature importance of a model and to analyze the most impactful factors. The dataset was taken from Kaggle repository: Rain in Australia
