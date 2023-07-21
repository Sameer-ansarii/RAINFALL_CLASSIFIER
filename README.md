# Rain Prediction using Machine Learning

This project is aimed at predicting whether it will rain in different locations of Australia using machine learning. The dataset used for this project was obtained from [Kaggle] and it contains various features such as location, date, temperature, humidity, pressure, and wind speed, among others.

# Content
* This dataset contains about 10 years of daily weather observations from many locations across Australia.
* RainTomorrow is the target variable to predict. It means -- did it rain the next day, Yes or No? This column is Yes if the rain for that day was 1mm or more.

# Data Description
* Location - Name of the city from Australia.
* MinTemp - The Minimum temperature during a particular day. (degree Celsius)
* MaxTemp - The maximum temperature during a particular day. (degree Celsius)
* Rainfall - Rainfall during a particular day. (millimeters)
* Evaporation - Evaporation during a particular day. (millimeters)
* Sunshine - Bright sunshine during a particular day. (hours)
* WindGusDir - The direction of the strongest gust during a particular day. (16 compass points)
* WindGuSpeed - Speed of strongest gust during a particular day. (kilometers per hour)
* WindDir9am - The direction of the wind for 10 min prior to 9 am. (compass points)
* WindDir3pm - The direction of the wind for 10 min prior to 3 pm. (compass points)
* WindSpeed9am - Speed of the wind for 10 min prior to 9 am. (kilometers per hour)
* WindSpeed3pm - Speed of the wind for 10 min prior to 3 pm. (kilometers per hour)
* Humidity9am - The humidity of the wind at 9 am. (percent)
* Humidity3pm - The humidity of the wind at 3 pm. (percent)
* Pressure9am - Atmospheric pressure at 9 am. (hectopascals)
* Pressure3pm - Atmospheric pressure at 3 pm. (hectopascals)
* Cloud9am - Cloud-obscured portions of the sky at 9 am. (eighths)
* Cloud3pm - Cloud-obscured portions of the sky at 3 pm. (eighths)
* Temp9am - The temperature at 9 am. (degree Celsius)
* Temp3pm - The temperature at 3 pm. (degree Celsius)
* RainToday - If today is rainy then ‘Yes’. If today is not rainy then ‘No’.
* RainTomorrow - If tomorrow is rainy then 1 (Yes). If tomorrow is not rainy then 0 (No). 

# The targets of the analysis are:
* To analyze the dataset content using EDA and to understand if it's possible build one model allowing to predict weather for the whole Australian continent or not.
* To train a model allowing to predict rain for tomorrow with the highest accuracy, F1 score and ROC-AUC metric.
* To evaluate feature importance of a model and to analyze the most impactful factors. The dataset was taken from Kaggle repository: Rain in Australia

# Model Building Report

**I tried out several classification algorithms and noticed that most of them were overfitting the data. After thorough evaluation, I selected Logistic Regression as the final model because it did not exhibit overfitting issues like the other algorithms. Logistic Regression performed well on the test data, showing the highest recall among the other models and a good f1-score. Furthermore, its balanced accuracy was better than other models. Based on these findings, I decided to focus on further improving the performance of the Logistic Regression model.**

**While analyzing the logistic regression results, I observed that the P-value of the 'location' variable was slightly high. However, I chose not to drop it because this feature is important for the analysis. Additionally, I performed hyperparameter tuning to optimize the model, but it did not have a significant impact on its performance.**

**Next, I examined the optimal threshold point for classification and found that using a threshold of 0.35 maximized the f1-score compared to other threshold values. However, I also considered the trade-off between accuracy, sensitivity, specificity, and f1-score against the predicted probabilities. After analyzing the results, I determined that a threshold of 0.49 provided a stable performance across all these metrics, making it the optimal threshold.**

**To further assess the model, I evaluated its performance using both the 0.35 and 0.49 thresholds. Additionally, I performed cross-validation, which led to improvements in both the f1-score and recall of the model. Choosing the threshold ultimately depends on the stakeholders involved and can be adjusted throughout the development process.**

## Model Summary

**0.50 as threshold**

| Metric   |	Train |	Test  |
|----------|----------|--------|
| Accuracy | 0.768505 |	0.774997|
|Precision	|0.775098|	0.479298|
|	Recall	|0.756523	|0.748375|
|	F1 Score|	0.765698|	0.584348|
|	Balanced Accuracy|	0.768505|	0.765253|

**0.35 as threshold**

|Metric|	Training Data|	Test Data|
|----------|------------|------------|
|	Accuracy|	0.753913|	0.684976|
|	Balanced Accuracy	|0.753913	|0.750358|
|	Precision|	0.705001	|0.389395|
|Recall	|0.873210|	0.863610|
|	F1 Score|	0.780141|	0.536766|
|ROC-AUC|0.75|0.75|
|True Positive (%)|	31.730769	|50.246035|
|True Negative (%)|	18.269231|	28.619958|
|False Positive (%)|	6.339509|	2.882478|
|False Negative (%)|	43.660491	|18.251530|


**0.49 as threshold**

|Metric|	Training Data|	Test Data|
|-----|----------------|-------------|
|	Accuracy	|0.768505|	0.774997|
|	Balanced Accuracy|	0.768505	|0.765253|
|	Precision|	0.775098|	0.479298|
|	Recall	|0.756523|	0.748375|
|	F1 Score|	0.765698|	0.584348|
|ROC-AUC| 0.77|0.77|
|True Positive (%)|	38.597836	|61.024104|
|True Negative (%)|	11.402164|	17.841888|
|False Positive (%)|	11.754774	|5.130511|
|False Negative (%)|	38.245226|	16.003497|

**Validation Data**

|F1 Score|Recall|
|------|-------|
|0.7654|0.7563|
    
### Top predictors

**Below are the top 10 variables that have the most significant impact on whether it will rain tomorrow or not.**

|Feature|	Coefficient|
|--------|-------------|
|	Humidity3pm|	1.119548|	
|	WindGustSpeed|	0.664005|	
|	Sunshine|	-0.398269|	
|	Pressure9am|	-0.315543|		
|	WindSpeed3pm|	-0.242641|	
|	WindDir3pm|	0.227509	|
|	MinTemp|	0.160660	|
|Rainfall|	0.145797	|
|	WindSpeed9am|	0.124911|	
| Location|	0.090725|	

**Variables with positive coefficient shows Positive correlation with 'RainTomorow' and negative coefficient shows inverse correlation with 'RainTomorow'.**

**Eg:- If the Humidity is high then probability of rain happening tommorrow is high and if the sunshine is high then probability of rain happening tommorrow is low.**
