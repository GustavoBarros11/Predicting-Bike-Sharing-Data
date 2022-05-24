# **Predicting Bike Sharing Data**
This is my implementation of the Predicting Bike Sharing Data Project****<br/>
From Udacity Deep Learning Nanodegree, 1° project of the course<br/>
`Deep Learning Project`<br/>

![jpg](imgs/img1.jpg)

In this project, i built my first neural network utilizing concepts of Object-Oriented Programming (OOP), and used it to predict daily bike rental ridership. I have been provided with some template code, but they left the implementation of the neural network up to me. This project corresponded to the first project of the Udacity Deep Learning Nanodegree program, a compound of 5 total projects that a finished successfully.

# Table of Contents
- [**Predicting Bike Sharing Data**](#predicting-bike-sharing-data)
- [Table of Contents](#table-of-contents)
- [Business Problem](#business-problem)
- [Project Assumptions](#project-assumptions)
- [Data Dictionary](#data-dictionary)
- [Solution Planning](#solution-planning)
  - [Final Product](#final-product)
  - [Tech Stack](#tech-stack)
  - [Process and Methods](#process-and-methods)
- [Business Insights](#business-insights)
- [Conclusion](#conclusion)
- [References](#references)
- [Next Steps](#next-steps)

# Business Problem
For this project you'll build a
neural network to predict bike-sharing
rides. Imagine yourself owning a bike sharing
company like Cycle Hop. You want to
predict how many bikes you need because
if you have too few you're losing money
from potential riders. If you have too
many you're wasting money on bikes that
are just sitting around. So you need to
predict from historical data how many
bikes you'll need in the near future. A
good way to do this is with a neural
network which is exactly what you'll do.
In this notebook, you'll implement a
neural network and train it on
historical data to make predictions. The main goal is to successfully build an algorithm that can bring real-world value to this company, by improving one key features on its business model, utterly bringing more value to the company.

# Project Assumptions
* The dataset records daily historical data from January 1 2011 to December 31 2012
* The number of riders is split between casual and registered
* Some days don't have exactly 24 entries in the data set

# Data Dictionary
The dataset consists of hourly ridership data from days ranging from January 1 2011 to December 31 2012, this dataset has 17 columns and 17379 entries (rows).

    instant        - record index
    dteday         - date
    season         - season (1:winter, 2:spring, 3:summer, 4:fall)
    yr             - year (0: 2011, 1:2012)
    mnth           - month ( 1 to 12)
    hr             - hour (0 to 23)
    holiday        - weather day is holiday or not (extracted from [Web Link])
    weekday        - day of the week
    workingday     - if day is neither weekend nor holiday is 1, otherwise is 0.
    weathersit :
                   - 1: Clear, Few clouds, Partly cloudy, Partly cloudy
                   - 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
                   - 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
                   - 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
    temp           - Normalized temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-8, t_max=+39 (only in hourly scale)
    atemp          - Normalized feeling temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-16, t_max=+50 (only in hourly scale)
    hum            - Normalized humidity. The values are divided to 100 (max)
    windspeed      - Normalized wind speed. The values are divided to 67 (max)
    casual         - count of casual users
    registered     - count of registered users
    cnt            - count of total rental bikes including both casual and registered

# Solution Planning
## Final Product
At the end of this project i will have built a notebook with both analysis and predictions about the next month number of riderships and a python script with a neural network created based on the principles of OOP.

## Tech Stack
* Python
* Numpy and Pandas
* Matplotlib

## Process and Methods
* [Step 0](#step0): Knowing the Data
  * METHOD:
    - Read the dataset documentation and print some early metrics and info about the dataset along the path.
* [Step 1](#step0): Import Dataset
  * METHOD:
    - Import relevant libraries into the notebook 
    - Download and import dataset from https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset
    - Display summary Info and Metrics
* [Step 2](#step0): Clean and Pre-process Data
  * METHOD:
    -  Check for null and duplicated values
    -  Create some dummy_variables
    -  Scale target variables
    -  Split data into training, testing and validation sets
* [Step 3](#step0): Build the model
  * METHOD:
    ![image](imgs/neural_network.png)
    1. Implement the sigmoid function to use as the activation function. Set `self.activation_function` in `__init__` to your sigmoid function.
    2. Implement the forward pass in the `train` method.
    3. Implement the backpropagation algorithm in the `train` method, including calculating the output error.
    4. Implement the forward pass in the `run` method. 
* [Step 4](#step0): Train, Test and Validate
  * METHOD:
    -  Trainig: Here i'll set the hyperparameters for the network and be using a method know as Stochastic Gradient Descent (SGD) to train the network, among other things.
    -  Testing: Here, i'll use the test data to view how well my network is modeling the data.
    -  Validating: Here, i'll further check if my model has low bias and variance, and most important, it's not overfitting.
* [Step 5](#step0): Conclusion
  * METHOD:
    -  Make assessments of the whole process, double check key steps, and try to think in numerical terms how much this model may impact positively the finances of the company.

# Business Insights
I found that Bike-sharing rental process is highly correlated to the environmental and seasonal settings, such as holidays, climate, special events and Meteorological Seasons. Beyond the actual daily number of rides that can be used to efficiently manage the number of bikes available on the streets in a particular day, we can use the insights mentioned aboove to create special marketing strateies among with discounts, to increase the number of users in those particular days. All of this added can for shure increase the efficiency of the company's business model and retain more active daily users.

# Conclusion
* **Regarding the model**:
  * The model predict the data pretty well. It fails in some periods of time when the data shows some unsual pattern, such as long holidays and so on. Because they are isolated cases, it means that these patterns are only present in tiny pieces of the data, becoming harder to the model learn them.
* **Regarding the Business Insights**:
  * This type of project is key to the company business model, finding a way to not waste money with lack of demand and idle products is a huge problem that many companies face. Such a solution, using ML and Data Science can bring a lot of value to those companies.

# References
- Dataset: https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset
- Project's oficial repo: https://github.com/udacity/deep-learning/tree/master/first-neural-network
# Next Steps
- Create a more robust network using popular ML frameworks
- Try to generate more insights about this business problems (make more analysis)
- Plot some graphs
- Make a Dashboard of this project on Streamlit
- Provide an actual estimate, in dollar, of how much money the implementation of this project can save for Cycle Hop.