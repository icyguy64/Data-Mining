# Data-Mining

One of my personal projects to build up my skills on data science and machine learning

1. Data Mining

Made use of location data and different location data providers, such as Foursquare. Made RESTful API calls to the Foursquare API to retrieve data about venues in different neighborhoods around the world. Scraping web data and parsing HTML code. 

2. ETL & Feature Engineering

Utilized Python and its pandas library to manipulate, explore and analyze the data. 

3. Data Visualization

Utilized Folium library to communicate results and findings


# Problem Statement

## In London, my friend, Mark is looking to open a fast-food restaurant, where would I recommend that he open it?

# 1.1 Background
With the rise of Youtube, Facebook, Amazon and many other such web services, recommender systems have made an impact in the lives of millions of people. In general, recommender systems are algorithms tuned to suggest relevant information to users and these systems are critical in some industries and will continue to spread into new/uncharted territories/industries. In some cases, they generate income when they are efficient and can even help companies stand out against the competition. Therefore, it is very advantageous for companies to leverage on these systems to predict trends and human behaviour and patterns to better position themselves in the near future and long term. 

# 1.2 Problem
Data that will aid in location selection for restaurants will be number of restaurants operating in the vicinity,  the flow of people within the area, ratings of restaurants, number of trending locations and opening hours of restaurants in the area. This project aim to answer the following question: "Where should you open a restaurant in London?" based on these data.

# 1.3 Interest
Business owners/investors will be very interested in the use of recommender systems to aid in the location selection of restaurants. Accurate prediction of restaurant location will help businesses gain a competitive advantage and benefit financially. Patrons to restaurants will also be interested in the restaurants location as one would not go to a restaurant if it is deemed too far or inconvenient.

# 2. Data acquisition and cleaning

# 2.1 Data Sources
Most of the data can be obtained using the Foursquare API. Data such as restaurants location, ratings, user reviews, venue's tips, number of tips, opening hours and trending restaurants in the area can be obtained with the Foursquare API. Web scraping will also be used to obtain useful information such as a restaurants menu, affordability of a place, customer feedback and many others.
A couple of websites will be scrapped using BeautifulSoup to aid in location selection.

# 2.2 Data Cleaning Steps
Data downloaded or scraped from websites, foursquare, etc were combined and stored together in a table. Firstly, I'll check the data sets for potential problems such as whether it is necessary to normalized the features when combining them. Secondly, is to check for outliers in the data. From the data, I'll deduce and decide whether the outlier will affect or impact the location selection algorithm or is it better to just omit the dataset. Thirdly, is to check for missing values in the data. Finally, is to inspect the dataset to make sure that it is ready for the next step.

# 2.3 Feature Selection
After data cleaning, I'll check for redundancy in the features as it will affect the bias of the algorithm that will be used for location selection and we might have two different restaurant having exactly the same set of features. It is also important to check the correlation of independent variables as this will bias the results of the analysis. Highly correlated features, only one of them will be selected and the others will be dropped from the dataset.



