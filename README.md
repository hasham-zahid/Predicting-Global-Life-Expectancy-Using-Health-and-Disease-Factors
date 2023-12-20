# Predicting Global Life Expectancy Using Health and Disease Factors

### Introduction to the Project
Many studies have been conducted in the past on factors affecting life expectancy, such as demographic variables, income and GDP, mortality rates and crime. However, it was found that the effect of immunization and the overall human development index was not taken into account as much as it should have in the past. Studies have also been done using only one year for all the countries, however, this dataset ranges from the year 2000-2015, which would offer more insight into the trends over the course of multiple years for all the countries. Important immunization records such as Hepatitis B, Polio, Measles and Diptheria will also be considered, especially in the aspect of infant immunization and life expectancy. 

Since the observations in this dataset are based on different countries, it will be easier for a country to look at which aspect or area of their healthcare system they should focus on to increase overall life expectancy and decrease infant and adult mortality. This project will be using regression to determine and predict life expectancy of countries using multiple health factors and demographics. Machine learning and AI models can help in identifying the root cause or problem for many countries. In this project, machine learning models such as Linear Regression, K-Nearest Neighbors Regressor, Support Vector Regressor and Random Forest Regressor will all be used to predict life expectancy. 

The data used in this project is publicly avaiable from the World Health Organization (WHO) and can be obtained from [https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated]. The dataset contains life expectancy, health, immunization, and economic and demographic information about 179 countries from 2000-2015 years. The dataset has 21 variables and 2864 rows. The data was already cleaned, as the author of the dataset took the initial dataset and used multiple more publicly available datasets from the WHO to fix missing values, remove inaccurate data, and obtain more accurate information about the data. Exploratory data analysis was applied to the data, including trends in the data and correlation between variables. Feature engineering was performed on the dataset. Cross Validation was performed on all models; 5-fold for the hyperparameter randomized search and then another 10-fold cross validation for the final model to ensure the models did not have a large standard deviation and were stable. Fit times for all the models were also calculated, and the metrics used to asses the models were Mean Absolute Error, Mean Squared Error, Root Mean Squared Error, and R2 score. 

### Dataset Information
The Global Health Observatory (GHO) data respository under the World Health Organization keeps track globally of the health status, development index, and many other related factors for all countries in the world. The datasets are all available publicly for the purpose of data analytics. This specfic dataset relates to life expectancy, and ranges from 2000-2015 for 179 different countries. Health factors for all these countries were collected by the author of the dataset from the WHO data respository site, and the corresponding economic data was collected from the United Nations website. The dataset contains 21 different variables and 2846 rows, with 20 predicting variables. All predicting variables were further divided into several broad categories including: ​Immunization related factors, Mortality factors, Economical factors and Social factors. The individual data was obtained from multiple different sources from the World Health Organization (WHO) data repository and then merged together into one comprehensive dataset. More information can be found on the dataset page [https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated]. The dataset can also be found in this GitHub respository. Attribute information can also be found in the Exploratory Data Analysis jupyter notebook above. 

### Insights About the Data
For full EDA and visulization, refer to the notebook above. These are some of the trends related to life expectancy.

#### Correlation Matrix 

![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/4b34ba61-d87d-42c7-ac8f-aeef3d36185a)

#### Developed vs Developing Nations Life Expectancy

To no surprise, the developed nations do on average have a much higher life expectancy than developing nations. There are also far more nations listed as developing than developed by the WHO.
![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/a8319d06-262a-42c5-a9b7-d2176ecde775)
![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/c11de1e8-ab3b-4940-9228-ff8796023962)

#### Life Expectancy by Region 

In terms of differnt regions of the world, the European Union and North America have the highest life expectancy, as well as being the most educated regions of the world. Conversly, Africa seems to be the poorest, least education and has the lowest life expectancy from all regions by far. Most regions except Europe, North America and the Middle East are also quite poor (in the context of GDP per capita). The EU also seems to have the most outliers when it comes to GDP per capita, with quite a few nations having upwards of $80,000 or more.

![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/9ca0acb8-b446-4d40-8612-83d788d92441)


#### Infant and Adult Mortality 

Infant mortality and adult mortality go hand in hand. As infant mortality decreases, life expectancy increases. The same is true for adult mortality. Most nations with a high adult mortality and high infant mortality have generally very low life expectancies. 

![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/b1432d1f-9567-4925-ab24-79774909560c)


#### Behavioural Factors Affecting Life Expectancy 

Alcohol consumption does not seem to play a large factor in life expectancy, as some of the richest nations with the highest life expectancy consume quite a lot of alcohol. On the other hand, BMI and GDP are quite related. Nations with a low average BMI and low GDP generally have less life expectancy overall. This is most likely due to malnutrition, among other things, such as gut disease and lack of clean water. 

#### Education, Income and Population Density in Relation to Life Expectancy

Not surprisingly, countries that have higher education also in general have higher life expectancy, as well as higher GDP per capita. Poorer countries with low education have the least life expectancy. Population density does not seem to play a significant role in life expectancy. However, there are a few nations that have extremely high populations and average to less than average life expectancy. It is, however, not a very strong correlation. 

#### Immunization and Disease 

High infant deaths are significantly related to low infant immunization rates. Many nations with low immunization rates for hepatitis, polio, and measles also, unsurpsingly have very high amounts of infant deaths and low overall life expectancy. HIV incidents are also strongly correlated with life expectancy. Countries with high incidents of HIV also have high adult mortality, as well as low life expectancy. 

![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/b12779e6-6910-4221-a64b-4d54bdf68ade)
![image](https://github.com/hasham-zahid/Predicting-Global-Life-Expectancy-Using-Health-and-Disease-Factors/assets/148837970/f8ae059f-1b2b-47a2-ad59-4d9556f19670)


### Model Performance and Results 
| Model | MAE | MSE | RMSE | R2-Score | Fit Time |
| ----- | -------- | --------- | ------ | -------- | -------- |
| Linear Regression | 1.13103 | 1.98158 |  1.40769 |  0.976379 | 0.00311s |
| K-Nearest Neighbors | 0.485439 | 0.586934 | 0.766116 | 0.993003 | 0.00308s |
| Random Forest Regressor | 0.29498 | 0.194373 | 0.440877 | 0.997683 | 3.60819s |
| Support Vector Regressor | 1.10975 | 1.99531 | 1.41255 | 0.976215 | 0.28429 |

Overall, the recommended model is random forest regressor, with a really high r2 value and low error rates. However, it was also the most computationally complex. In this regard, K-Nearest Neighbors performed almost as well, with slightly higher error rates but was the quickest out of all the algorithms. SVM was the weakest model and also took longer than both K-NN and linear regression to fit, so it is not recommended. 
