# Data-Mining

One of my personal projects to build up my skills on data science and machine learning

1. Data Mining

Made use of location data and different location data providers, such as Foursquare. Made RESTful API calls to the Foursquare API to retrieve data about venues in different neighborhoods around the world. Scraping web data and parsing HTML code. 

2. ETL & Feature Engineering

Utilized Python and its pandas library to manipulate, explore and analyze the data. 

3. Data Visualization

Utilized Folium library to communicate results and findings



# Problem Statement

## In London, my friend, Mark is looking to open a fish and chips restaurant, where would I recommend that he open it?

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



# 3. Exploratory Data Analysis
In this section, I'll attempt to document the exploratory data analysis process.

## 3.1 Calculation of target variable 
The target variable for analysis is to determine where should we locate our new fish and chip restaurants in England. Initially, I decided on London but then realised that the datasets for London is actually quite less so England was chosen in the end. First, we extract the venues of different neighborhoods using the Foursquare APIs and it is determined that there is only 94 unique categories of the extract datasets/venues. Second, we attempt to identify trends of venues in the dataset. It is interesting to note that from the analysis, there are actually a couple of neighborhoods that inhibit the same pattern. Third, we try to access the accessibility of the given neighborhood and we have done it from the viewpoint of a person taking public transport and definitely, one can perform change it to determing accessibility of a given neighborhood based on the amount of car parks, parking lots that they have. Fourth, we attempt to recommend locations one should setup the restaurant. 

## 3.2 Accessibility of a given neighborhood based on busstop and train station
An aspect identified for analysis is to determine the accessibility of a neighborhood. In this case, we look at the amount of busstops and train statons there are in a neighborhood. First, we filter the data to look at neighborhoods in England. We noticed that there are actually duplicates in the dataset, sometimes the same neighborhood belongs to two different countys. There are also other instances of duplicates there are entries that are different. In this cases, we have decided to always keep the first entry and drop the rest. Please refer to the jupiter notebook for the folium plot of the neighborhoods. We have identified the followings:

After extracting the busstop and train station datasets from the neighborhoods. From the analysis, the neighborhood with the most bus stop is 
1. Abbots Leigh
2. Abbotsely
3. Abington Vale
4. Acle
5. Acton Green

And similary, the neighborhood with the most train stations is 
1. Acklington
2. Abbas Combe
3. Abbotsmead
4. Accrington
5. Acton Green


## 3.3 Amount of fish and chips shops in London
First, we need to extract the neighborhood information from the dataset. Then we make use of the foursquare APIs and by specifying search query as Fish and Chips we can get the list of shops with fish and chip in the name of the restaurant. Also it is possible for a restaurant selling fish and chips to not have fish and chip in the name. For my analysis, I'll ignore this case. As the amount of the fish and chips shops in London is alot excluding the fast food restaurants which are also quite similar. I would recommend one looking to set up a fish and chips restaurant to choose another location instead of England and/or London.



# 4. Predictive Modelling
In this section, I attempt to identify trends within neighborhoods to gain insights.

## 4.1 Applying clustering algorithms
We applied one hot encoding to the dataset in order to use clustering algorithms and we aim to identify the top 10 venues of a given neighborhood. We applied K-means clustering to the dataset and noticed that two cluster that inhibit interesting results. For one of them, the first ten of most common venues are actually the same and in the order of 1st to 10th, they are:

1. Pub
2. Yoga Studio
3. French Restaurant
4. Department Store
5. Discount Store
6. Dive Bar
7. English Restaurant
8. Farmers Market
9. Fast Food Restaurant
10. Fish & Chips Shop

And the following lists are the neighborhoods in this cluster:

1. Abbotskerswell
2. Abbots Worthy
3. Aberford
4. Abington Pigotts
5. Abthorpe
6. Aby
7. Acaster Malbis
8. Ackleton
9. Acton

From the analysis, we see that food actually dorminates the ten top list of items in this cluster. We cab conclude that England'ers loves food. Or rather, food and beverages business is very competitive and it would be tough. For the second cluster, ableit a smaller one, we see a similar pattern. 

## 4.2 Problems and Solution 
The problem with the K-means clustering is from the result of the clustering, only 2 cluster out of 5 is relevant to our analysis. We observe the results of the other 3 clusters are actually somewhat random. This actually occurs as there is simply not enough correlation between the neighborhoods and hence, we can either reduce the number of K and re-do the analysis. Or we can actually attempt to analyse the neighborhoods based on new measures and/or collect more data. This is a common problem for data analyst. Or simply we can attempt the cluster the neighborhoods in a different way.




# 5. Conclusion
In this analysis, we managed to identify potential neighborhoods to setup a restaurant. However, this list is not exhaustive and one can disagree with the methods used for analysis. More datasets can be collected to improve the analysis and as trends always change, the analysis done today might not be relevant a few months from now. So it is actually important to perform the analysis and make an informed decision as to where to set-up a fish and chip restaurant in London. As fish and chips restaurant are very common in London, one should consider other places to setup their restaurant. 





