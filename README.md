![SunRiseRide](https://github.com/user-attachments/assets/b1c70fbd-4fa8-432f-be04-ebf056166e8a)

# Cycling Into New Markets
Analysis by Jordan Scriven  

## Business Understanding
The city of Merrytown is interested in adding bicycles to the downtown area.  They'd love to see citizens cycling over driving on daily commutes, when possible, and spending weekends visiting all their favorite places by bike.  Studies have shown how cycling can improve both physical and mental health along with cutting down on traffic, minimizing noise and emissions pollution, and increase urban livability.

In addition, it is cheaper to build and maintain the infrastructure for bikes over cars.  That said, prior to making the move to purchase the bikes and set up the infrastructure, the city of Merrytown wanted to analyze the likelihood that the new bicycles would be a success.  They would like to be able to predict the time that these bikes would be used.

## Data Understanding

The city of Austin, Texas, comparable to Merrytown in population demographics, climate and infrastructure, has maintained [records](https://www.kaggle.com/datasets/jboysen/austin-bike?select=austin_bikeshare_trips.csv) of their city bicycles for years, including routes, duration of rides, type of user and the date of the ride.

This data includes information on nearly 650,000 bicycle rides over 1,000 plus different days.

In addition to the data on cycling, our analysis requires the weather information for the city over the same time span.  Austin KATT station has recorded that [data](https://www.kaggle.com/datasets/grubenm/austin-weather) and made it readily available on WeatherUnderground.com.  The weather data includes information on temperature, dew point, humidity, sea level, visibility, and wind.  Events such as thunderstorms, fog, and rain are also noted.   

### Data Preparation
In a first step to analyzing the data, we clean it up - We removed outliers for very long bike rides, which may be the result of a bike being lost or never returned.  We check for roundtrips that didn't last more than a minute, indicating the bike was not used, and removed those. Our database is large enough that we can remove those records with missing information.

### Exporatory Data Analysis

To analyze the data and determine that it is a good fit for our predicitions in Merrytown, we look at many things.  We examine the most common routes, number of rides per month and per day of week and duration of rides based on month and day of the week.

![StationMap](https://github.com/user-attachments/assets/0556d601-5cb9-4d04-80cb-a6a4e2b28dee)

![CountPerMonth](https://github.com/user-attachments/assets/bc54bae4-a62c-4505-a934-eedf85153dba)

![AverageDurationPerMonth](https://github.com/user-attachments/assets/652cdeac-3c22-4160-ae42-1471839604b3)

![CountPerWeekday](https://github.com/user-attachments/assets/5bffd4e5-39b3-4dd3-8890-a19f132067d1)

![AverageDurationPerWeekday](https://github.com/user-attachments/assets/5da5ad2b-52fd-478c-8dec-02867388a137)

## Modeling

To model the average bike ride duration per day based on date, day of the week, and daily weather conditions, we employ the SARIMAX model (Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors). We first consolidate all relevant variables, such as ride durations, weather metrics (e.g., temperature, humidity), and calendar features—into a single, time-indexed DataFrame. Before fitting the model, we assess the stationarity of the time series using statistical tests. Since the data meets the stationarity assumption, we proceed by splitting the dataset into training and testing sets, for accurate forecasting and evaluation.

![DurationSeries](https://github.com/user-attachments/assets/3e0e2618-f44c-4a99-ac0e-7709fc3af02c)

![CoutnSeries](https://github.com/user-attachments/assets/dae4ff36-2eb0-4d4e-b384-833c20b4498b)

## Evaluation

![DurationForecast](https://github.com/user-attachments/assets/3579dfe6-b34e-4c8d-a5b6-c99654613e56)

After fitting the original model to the training data and running the model on our testing data, we compare those predictions to the actual testing dataset.  The RMSE for this model is 2.71.

After running a grid search, the updated model dropped the RMSE to 2.43.  These results tell us that, on average, the model's predictions are within 2.43 minutes of the actual daily average bike ride duration.  Based on the mean of the daily average bike ride duration, this is a 15.85% relative error.  These statistics indicate that this model is reasonably effective at capturing the relationship between weather, date and ride duration.

Evaluating the model on number of bike rides per day rather than duration of bike rides did not provide us with a reasonable relationship.

## Conclusion

Using this model to predict the duration of a ride given the day and weather patterns allows us to predict the use of bicycles in another town based on their weather patterns.

### Limitations and Next Steps

The largest limitation in this analysis is that the demographics of the two cities are the same.  It would be a good next step to bring in studies regarding the city populations.  If the populations differ greatly on age, gender or activity level, we will want to adjust the model accordingly.

Additionally, while our weather model was good for predicting the duration of a bike ride, it was not great for predicting the number of bike rides on a given day.  We will want to research and model what other factors could be influencing the number of rides in a given day.

Using those two pieces of information we can predict how many bikes we will need in Merrytown.  We can determine how much money it will bring in based on the number rides and duration.  We can also determine if specials on poor weather days or offering commuter discounts would be beneficial.

## Repository Navigation

* [.gitignore](.gitignore)
* [notebook.ipynb](Notebook.ipynb)
* [presentation.pdf](Presentation.pdf)
* [README.md](README.md)
