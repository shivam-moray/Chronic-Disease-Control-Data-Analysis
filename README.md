# Chronic-Disease-Control-Data-Analysis

## Dataset

Dataset had been released by Centre for Disease Control and Prevention which available on Kaggle.(https://kaggle.com/cdc/chronic-disease) A disease data collected across United States of America during the period 2001-2016. It consists of approximately 404k rows and 34 attributes. 

The dataset contains mostly categorical data such as Location, Topic, Question, Response, Stratification. ‘Topic’ contains 17 different major categories such as Alcohol, Asthama, Tobacco, Cancer in addition to it, in each topic there are a number of questions for example, in Alcohol topic the questions will be Alcohol among youth, Amount of alcohol excise tax by beverage type (beer).

‘DataValueUnit’ attribute consists of the units of measures, including percentages, dollar-amounts, years and cases per thousand. ‘DataValueType’ consists of categories such as Age-Adjusted mean, Crude Prevalence that provide insight into the data when comparing the values across states.

'DataValue’ consists of raw numbers that have a unit of measure specified. ‘Stratification’ related column comprises groups such as gender, overall, race and ‘StratificationCategory’ there is gender specified as male, female and types of race. The data has a tremendous variety of data and a considerable amount of effort because of the variety present in the dataset also data requires grouped, transformed and aggregated before generating the visualizations.

## Data Exploration, Processing, Cleaning and/or Integration
### Missing Data:

Visualizing missing values through heatmap gives a fairly good estimate of the density of data present in each column across the whole dataset. In the notebook a heatmap is used to visualize the missing data which I found is very intuitive from the tutorial at https://towardsdatascience.com/inspecting-a-cdc-chronic-disease-dataset-e1685a6b525a

### Data Processing and Exploratory Analysis

The GeoLocation attribute contains longitude and latitude clubbed to use them while plotting the maps I would need separate values as a float so two new columns were created by splitting the GeoLocation attribute. The data frame is then clubbed together into new subsets of the frame based on Topic, Question, Stratification, and Location. The exploratory analysis helped to identify the depth of data set where each Topic has around 12 questions associated with it that had different types of Stratification categories such as the gender, the race that can further be grouped by year.

The nutrition, physical activity, and weight status have shown exponential growth over the last 5 years so the data frames were aggregated around that topic. The Year column had missing values for the years between 2001 to 2005, 2007 and 2009 so the 2010 – 2015 time period was chosen as it didn’t have missing data. The attributes which could be used to aggregate and group together the data frame were chosen such as Location, Year, Topic, Question, Stratification, DataValue, DataValueUnit.

## Visualization 

### I)Top 5 chronic diseases with an increasing trend over the years 2010 - 2015

The top 5 topics have been taken and the scatter plot is generated and a lowess trend line is drawn which gives a smooth fit for the plot generated. The nutrition topic has a very steep increasing trend over the last 5 years. The black background has been given to grab the attention of the viewers also make the lines stand out. 

Colors have been chosen in such a way that they do not represent rank or order, further the font is Helvetica which is used by most of the US journals in their publications such as Springer(https://www.springer.com/gp/authors-editors/book-authors-editors/resources-guidelines/book-manuscript-guidelines/manuscript-preparation/5636)

### II) Distribution of Obesity among adults aged >=18 years of age among the countries

Choropleth map is used to show the percentage of obesity among adults in different counties and find out which ones demonstrate higher value. The font has been carried forward from the first graph and the color scale is chosen such that it becomes easier for the audience to distinguish between the difference between the lows and highs in the graph. 

The slider has year-wise data distributed on it which helps to stimulate which counties have higher values throughout the 5 years. Lighter areas are easier to focus on by ignoring the darker area. The midpoint for the scale has been set as 60, to ease the effort to distinctly distinguish the areas.

### III) Comparing obesity with no leisure time spend on physical activity
The grouped bar chart is used to compare obesity with the leisure time spent on physical activity, default scale was up to 70% because of which the legend would overlap the bar but by increasing the scale range there was pocket created for the legend. The animation shows that there has been no improvement in obese adults spending their leisure time for physical activity thus the cases increased throughout the year. 

This has taken the top 4 states which have a higher value of obesity among its population over the course of the last 5 years and failed to tackle it. The point here is, as population increase the cases reported also increase so the percentage remains constant, that is the main highlight here which might be missed out as the ‘%’ unit deceives the audience.

## Conclusion

The graph starts from the overview of the topic and then dives deeper into granular details giving the targeted audience an in-depth knowledge about the chronic disease indicators.

## References 
* Chronic Disease Indicators - https://kaggle.com/cdc/chronic-disease
* Manuscript preparation - https://www.springer.com/gp/authors-editors/book-authors-editors/resources-guidelines/book-manuscript-guidelines/manuscript-preparation/5636
* Plotly Python Graphing Library - https://plot.ly/python/
* Inspecting a CDC Chronic Disease Dataset, Medium - https://towardsdatascience.com/inspecting-a-cdc-chronic-disease-dataset-e1685a6b525a
