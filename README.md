## Predictive Model for Air Quality in Oshodi, Lagos State
Incase the project file above return an error, you can alternatively access the file by clicking [here](https://nbviewer.org/github/abdulmumeen-abdullahi/Predictive-Model-for-Air-Quality-in-Oshodi-Lagos-State/blob/main/Dec%2017%20-%20Jan%2018%20Air%20Quality%20in%20Oshodi.ipynb).

### Overview of the Problem <br /> 
There is a saying that every household in Nigeria has at least one family member in Lagos. Lagos is the largest city in sub-Saharan Africa and the third fastest-growing city on the continent, with a population exceeding 15 million. However, this rapid growth has brought significant challenges, particularly in air quality management. Air pollution in Lagos poses a major threat to sustainable development and the health of its residents, especially in densely populated areas like Oshodi. <br />
One of the key issues is the difficulty in forecasting the increase in PM2.5 and other air pollution indices. This challenge often results in inefficient resource allocation for Government agencies and misses opportunities for businesses. <br />
This project aims to address these issues by building a predictive model that analyzes PM2.5 trends between December 2017 and January 2018, forecasting future values, and providing actionable insights for policymakers and businesses.

### Data Used
The dataset for this project was sourced from [openAfrica](https://open.africa/dataset/sensorsafrica-airquality-archive-oshodi-lagos). The dataset was in seperate files and was merged into a dataframe. The original data was in a merged format inside a column and was processed into the following columns:

•	Sensor_id: Identification number of the sensors used in recording the values.

•	Sensor_type: Types of sensors used for data collection.

•	Location: Identification of the data collection points.

•	Lat and Lon: Latitude and longitude of the collection points.

•	Timestamp: Date and time of the readings.

•	Value_type: The specific air pollutant captured.

•	Value: The measured value of the pollutant.

### Methodology <br />
**1. Data Preprocessing**

•  Split the merged dataset into separate columns.

•  Filtered data to include only readings from sensor_id 7, the P2 value type, and values less than 500.

•  Renamed the "value" column to P2 and converted timestamps to the Africa/Lagos timezone.

•  Resampled the P2 values hourly and forward-filled missing values using the mean.

**2. Exploratory Data Analysis (EDA)**

•  Plotted a time series graph to visualize PM2.5 trends.

•  Calculated and visualized weekly rolling averages.

•  Created a lag feature, P2.L1, to account for temporal dependencies. <br />
The lag feature helps identify relationships between current and previous readings, enhancing the model's predictive accuracy.

•  Plotted a scatter graph to analyze correlations between PM2.5 values and their lagged counterparts.

**3. Model Training**

•  Split the dataset into 80% training and 20% testing sets.

•  Established a baseline model using the mean value of the target variable (P2) and calculated the Mean Absolute Error (MAE).

•  Utilized Autocorrelation (ACF) and Partial Autocorrelation (PACF) plots to determine optimal lag values for ARIMA and other models.

**4. Model Selection and Evaluation**

Trained and evaluated several models: <br />
•	Linear Regression

•	Autoregressive (AR)

•	Autoregressive Integrated Moving Average (ARIMA) (chosen for its accuracy and robustness). <br />
Performed hyperparameter tuning and compared MAEs. The ARIMA model achieved the best performance with an MAE of 6.2.

**5. Model Explanation**

•  Evaluated residuals (differences between actual and predicted values) using time series, histogram, and ACF plots.

•  Conducted walk-forward validation to assess future prediction accuracy.

•  Visualized the relationship between actual and predicted values on a time series plot.

### Results <br />

•	Benchmark (Baseline) Model: The benchmark MAE was calculated to be 17.0, based on the mean of the training target variable (P2).

•	Autoregressive Integrated Moving Average (ARIMA): The ARIMA model achieved an MAE of 6.2, which is significantly lower than the baseline, indicating better performance.

**Other Models:**

o	Linear Regression: MAE = 6.9

o	Decision Tree Regressor: MAE = 5.2 <br />
The ARIMA model demonstrated the most significant reduction in error, outperforming the baseline by 10.8 points.

### Impact and Benefits of the Model <br />
The predictive model can help government agencies allocate resources more effectively for air quality control and make data-driven policy decisions to enforce environmental regulations. It also provides climate-related businesses with insights to identify areas with high demand for air purification solutions. Businesses can leverage this information for targeted marketing strategies to enhance customer reach. Ultimately, the model supports improved resource management, better policies, and increased profitability for stakeholders. <br />
This project demonstrates the potential of predictive modeling in addressing real-world challenges like air pollution. By accurately forecasting PM2.5 trends, the model offers valuable insights for government agencies and businesses, contributing to a cleaner and more sustainable Lagos.

**NOTE**: For deployment in real-world applications or customization to fit specific business needs, feel free to contact me.

[Abdullahi Olalekan Abdulmumeen](https://www.linkedin.com/in/abdulmumeen-abdullahi-olalekan) <br />
Applied Data Scientist <br />
Olalekanabdulmumeen3@gmail.com
