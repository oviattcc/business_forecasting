# Business Forecasting Using Statistical, ML, Deep Learning and Transformer Models

In this class project, we examined an anonymized hotel dataset of 18 different properties, where we were tasked with selecting the best forecasting approach to predict the next 28 days.

## Python Notebook

 - [Full Code](https://github.com/oviattcc/business_forecasting/blob/main/Banks_Claypool_Oviatt_Final_Code.ipynb)

## Forecasting Procedure

In this project, we developed a forecasting framework to compare several different models on the same dataset using a 28-day forecast horizon. We began by exploring the data to understand the main patterns, such as overall trends, seasonality, and variation across locations. During this stage, we cleaned missing or inconsistent values and created additional time-based features like numerical day, month, and week indicators to help the models recognize repeating patterns.
After preparing the data, we tested a wide range of forecasting methods. Our baseline models included Naive, Seasonal Naive, AutoETS, and AutoARIMA, which helped us establish a simple reference point. We then added machine learning models such as XGBoost and LightGBM to see whether they could capture more complex relationships in the data. To incorporate deep learning, we used NHITS, which is built for long-horizon forecasting. We also included TimeGPT as a modern pretrained model capable of learning broader time series structure.
To make the comparison fair, we used a rolling time-series cross-validation setup with five windows. Each model was trained using past data and then asked to predict the next 28 days, which ensured every model was evaluated on data it had not seen before. We measured accuracy using MAE, MAPE, and RMSE. Since each metric highlights a different kind of forecasting error, using all three gave us a more complete understanding of how the models performed. We also counted how many times each model ranked first across locations and folds. After identifying the best performer, we created visual plots to compare its forecasts with the actual values.


## Main Results

The results showed that AutoARIMA was the strongest overall performer across most locations. It worked especially well in places with clear seasonal patterns, and it also handled moderate to high demand variability more effectively than the other models. AutoARIMA’s ability to automatically detect the right structure for each series helped it adapt well across different conditions.
The machine learning and deep learning models had mixed results. XGBoost and LightGBM performed well at a few locations with more irregular patterns, and NHITS captured long-range structure in some cases. TimeGPT also produced solid forecasts, particularly in smoother series. However, none of these models outperformed AutoARIMA on average or across the majority of evaluation metrics.
The rolling cross-validation setup helped us see these differences clearly. Because each model had to repeatedly predict real future windows, we were able to compare them in a realistic way. AutoARIMA consistently produced strong MAE, MAPE, and RMSE values across all five windows. This suggests that, for this dataset and a 28-day forecast horizon, a classical model can outperform more complex approaches. Overall, the project shows that using a structured cross-validation process with a diverse set of models provides a reliable way to identify the best forecasting method for operational use.

Below is the plot of the forecasted 

![Final Plots](https://github.com/oviattcc/business_forecasting/blob/main/Banks_Claypool_Oviatt_Final_Plots.png)

