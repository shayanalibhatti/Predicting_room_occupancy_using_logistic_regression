# Predicting Office Room Occupancy Using Logistic Regression 

### Introduction
In this repository, I used UCI's Occupancy Detection dataset to predict room occupancy prediction using logistic regression. This dataset is provided at https://archive.ics.uci.edu/ml/datasets/Occupancy+Detection+. This dataset contains parameters of an office room. Those parameters are Date, Temperature(in Celsius), Light (lux), CO2, Relative Humidity (%), Humidity Ratio and Occupancy, which is binary with 1 if room is not vacant and 0 otherwise. I used single hidden layer neural network to develop a classifier that tells if room is vacant or not.

### Data Visualization
I used Tableau for visualizing data as it is easy. On visualizing various parameters vs occupancy, following is observed:

1) Temperature vs Occupancy:
The picture below shows that temperature remains same between 20C to 25C if room is vacant or not. It makes sense because of possible air conditioning in the office.

![occupancy_vs_temperature](https://user-images.githubusercontent.com/41015749/73147003-62c20f80-4083-11ea-9fbf-e3d67859d968.jpg)

2) Light vs Occupancy:
The picture below shows that Light is more between 7am to 7pm when room is not vacant. And outside these times, light is 0 because office only has activity between 7am to 7pm.

![occupancy_vs_light](https://user-images.githubusercontent.com/41015749/73147075-c8160080-4083-11ea-98d0-075ecd33f658.png)

3) CO2 vs Occupancy:
The picture below shows that CO2 is high between 7am to 7pm when room is not vacant and low outside these times which makes sense as humans exhale CO2. So more CO2 means more humans.

![occupancy_vs_co2](https://user-images.githubusercontent.com/41015749/73147162-2ba02e00-4084-11ea-9872-a6bade2dd6bb.jpg)

4) Humidity vs Occupancy:
The relative humidity doesnt change whether room has occupancy or not, as evident in picture below:

![humidity_vs_occupancy](https://user-images.githubusercontent.com/41015749/73147232-9487a600-4084-11ea-95bb-06f52e2214ab.jpg)

### Preprocessing
I used Pandas to load the dataset. Following picture shows how our data looks like:
![data picture](https://user-images.githubusercontent.com/41015749/73147536-e41aa180-4085-11ea-815f-17a7f42a7516.png)

It can be seen that all columns except Date and Occupancy are continuous values. Since machine learning algorithms perform better when data is scaled, so I used Scikit-learn's Standard Scaler which scales data to have mean 0 and standard deviation 1.

### Machine Learning Algorithm
I used single hidden layer neural network with keras library for machine learning algorithm. Adam optimizer is used. Train-test split is kept at 80:20. Following accuracy and loss curves are observed:

![image](https://user-images.githubusercontent.com/41015749/73147883-9a32bb00-4087-11ea-876c-6186463c75b1.png)

![image](https://user-images.githubusercontent.com/41015749/73147898-a6b71380-4087-11ea-91ab-0d7e76f01807.png)

### Results
After training the algorithm, it is seen that our model fits data really well. Finally, predictions are computed and mean squared error between predictions and test set is found to be 0.05.

### Conclusion
By doing this project, it is seen how easy it is to use room parameters to train a neural network based classifier for room occupancy detection. 
