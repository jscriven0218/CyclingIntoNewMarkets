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

![image](https://github.com/user-attachments/assets/0556d601-5cb9-4d04-80cb-a6a4e2b28dee)

![CountPerMonth](https://github.com/user-attachments/assets/bc54bae4-a62c-4505-a934-eedf85153dba)

![AverageDurationPerMonth](https://github.com/user-attachments/assets/652cdeac-3c22-4160-ae42-1471839604b3)

![CountPerWeekday](https://github.com/user-attachments/assets/5bffd4e5-39b3-4dd3-8890-a19f132067d1)

![AverageDurationPerWeekday](https://github.com/user-attachments/assets/5da5ad2b-52fd-478c-8dec-02867388a137)


## Modeling


## Evaluation


## Conclusion



### Limitations and Next Steps


## Repository Navigation

* [.gitignore](.gitignore)
* [notebook.ipynb](Notebook.ipynb)
* [presentation.pdf](Presentation.pdf)
* [README.md](README.md)
