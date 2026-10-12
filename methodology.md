# Methodology
By applying five different regression models - LR, RF, DT, SVM and KNN, we propose to predict Dhaka's AQI of the following day, based on the AQI's of six major cities in Dhaka - Dhaka Metropolitan, Paltan, Azimpur, Tongi, Dohar and Narayanganj. 

1. Dataset\
  The dataset used in this study was obtained from Kaggle that contains  103 cities covering all major regions of Bangladesh, more than 3.19 million hourly observations starting from 2000 to 2026, of 8 pollutant measurements: PM10, PM2.5, CO, CO₂, NO₂, SO₂, O₃, along with AQI values. We filtered the dataset for the six major cities inside Dhaka only (Dhaka Metropolitan, Paltan, Azimpur, Tongi, Dohar and Narayanganj), and collected the hourly records from December 2025 to September 2026 only. 

2. Data Cleaning\
  We filtered the dataset first to take only the six citied inside Dhaka (Dhaka Metropolitan, Paltan, Azimpur, Tongi, Dohar and Narayanganj). We converted the timestamps into dates, and then aggregated the hourly AQI values for each city into daily observations. For this puepose, we used daily mean pollutant concentrations and daily maximum AQI. We also checked for missing calendar dates, such as July 15, 16, 17 were missing and excluded them.

3. Feature Engineering\
  We aggregated the hourly pollutant values using city name and date, into daily observations. We dropped the AQI metric in European style, as we will use US AQI metric only. Finally, we used the six pollutant measurements  as inputs. We also created a new feature where we assigned for each city the next day's AQI, only when the next available observation was exactly one calendar day later. This is our target feature.  

4. Model Selection\
  We proposed five regression models, namely LR, RF, DT, SVM and KNN on the dataset to find out the performance of each model and which one gives the best prediction. The dataset was split into test and train data based on chronological order - train dataset contains all entries before July 2026, while test dataset contains the rest. The models were trained using train dataset and test dataset were kept unseen.

5. Evaluation Metrics\
  We used three metrics to evaluate the performance of each model:
    * MAE: Mean Absolute Error. The lower the MAE, the higher predictive accuracy and the smaller errors on average.
    * RMSE: Root Mean Square Error. It penalizes larger prediction errors more strongly than MAE.
    * R2: It measures how much variation in the test target is explained relative to a baseline that predicts the test-set mean.
