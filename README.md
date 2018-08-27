# The Top Six
### Using Python, Machine Learning, and NLP to discover insightful data. 
You can download the complete 8260_1.csv file from https://www.kaggle.com/datafiniti/breweries-brew-pubs-in-the-usa

### by Saul Tamariz
MSDS696-Final Project

Check out my video at https://www.youtube.com/watch?v=EhDtFO1d0KE&feature=youtu.be

### About the Data
The dataset from kaggle.com contains 17,823 observations and 15 column features of breweries in the U.S
and abroad. Information such as Id, address, categories, city, country, hours, keys, latitude, longitude,
menus, name, postalCode, province, twitter, and websites is provided. There are many missing in key features 
such as latitude and longitude. Other categorical features such as address, city, and province information has 
mislabeled information. For this project, I will be using this dataset to understand the craft brewery market
in the U.S and find out what are top brewery cities in the country. 

### Data Science Problem
To conduct a successful Data Science project, one must first ask a question. For this project I wanted to know what 
people are saying about craft beer in the top six brewery cities of the nation. To accomplish this, I used various 
tools such as Python, Machine Leanrning, NLP, and Tableau.

### About the Project
This project has five main steps. The first step is to define a problem and ask a question. For this project, I have 
stated that my intent was to find out what people are saying in the top six brewery city markets. Step two, involved initial 
Exploratory Data Aanalysis(EDA) and the formulation of a plan of attack. The third step was extensive and exhausting as it involved data cleaning and preparation. The fourth step was to stream the data, and prepare the data for analysis. Finally, in step five I analyze and conclude with insights about the data. As you will see there are several files with capital letter that contain a Jupyter Notebook extention. I will provide a summary for each in the subsequent paragraphs. 

![pic2](https://user-images.githubusercontent.com/36432832/44660971-6ea92e00-a9c6-11e8-83e4-a669765f8454.png)


## EDA
The intent for this part of the project was understand the strenghts and weaknesses of the dataset. I printed value counts
and summaries for each column feature to understand each contributing feature. I went ahead and created several word clouds 
and word frequency distributions for the category feature which was all string objects. Understanding each feature allowed
to formulate an inital plan of attack. It was in this step that I discover the identity of the top six brewery markets in 
the U.S. 

![pic0](https://user-images.githubusercontent.com/36432832/44660883-39044500-a9c6-11e8-88a5-36877f813c1f.png)

## DATA PREP1
This notebook was a continuation of the previous one. For this section I contined exploring the dataset but with a plan in mind. First, I created six subsets for the top six brewery cities. I inspected to see what proportion of observations contained twitter account names and website information. Subsequently, I began experimenting with geopy to fill in missing latitude and longitude information. This however failed since the API would not time me out constantly. After several failed attempts I decided to resort back to Google Sheets and Awesome Table geocoding services. 

![pic3](https://user-images.githubusercontent.com/36432832/44661256-52f25780-a9c7-11e8-817c-1245ffeb4a7a.png)

## DATA PREP2
After successfully filling for most missing values in latitude and longitude I continued with data preparation phase. I dropped eight rows where latitude and longitude could not be encoded. I then proceeded to plot the six brewery markets. I discovered that instead of six clusters I was seeing eleven clusters. I investigated the problem and it turns out that there two cities with the same name. I then used k-means to filter out the unwanted clusters.

![pic4](https://user-images.githubusercontent.com/36432832/44661116-d95a6980-a9c6-11e8-88be-b1d4ead91133.png)

## KNN IMPUTE
The dataset was almost ready for streaming, however the postalCodes column had 128 missing values. For practice, I decided to use KNN to impute for missing zip code values. I figured I can build an accurate KNN model using latitude and longitude as the predictors and would achieve a high accuracy rate. I first trained the model on the known observations and then when I was getting 90.5% accuracy I decided to apply the model on the missing observations and impute for missing values. I inspected the results and was satisfied with the output. 

![pic5](https://user-images.githubusercontent.com/36432832/44661301-73221680-a9c7-11e8-80b0-5a0e4d5ce40c.png)

## STREAM TWEETS
The dataset was finally ready and I was ready to stream tweets for each brewery in the top six that contained a twitter name. I began with creating a list of those breweries. I used the Twitter API tweepy to stream tweets about breweries in the top six markets. Since Twitter API had limitations on the number tweets that could be streamed at a time, I decided to stream at least 1000 unique tweets per city. I after several hours I had a six csv files with 6280 tweets.

![pic6](https://user-images.githubusercontent.com/36432832/44661322-88974080-a9c7-11e8-9c7a-cd0931125c6d.png)

## TWEETS EDA
The goal for this section was to understand the newly streamed tweets. I went ahead and ploted density curves, histograms, and series plots regarding tweet lenght. I also analyzed the tweets for the different cities in word clouds to better understand the tweets and what they contained. It was in this section that realized and understood how you can spot trends and retweets by ploting tweets by lenght. 

![pic8](https://user-images.githubusercontent.com/36432832/44661362-abc1f000-a9c7-11e8-82a6-f9cc896019cd.png)

## TWEETS DATA PREP
The first step was to combine the six csv tweet files into one. I then introduced the tweet column feature to a function that would clea, filter, lowercase, and remove special characters from the tweets. I will then print out the result in a newly created column. Subsequently, I wanted to extract certain information from the tweet such what beer names people were tweeting about. I created a function that would return a beer name if one existed. A seperate function would return 'no beer found' for those rows that did not contain a beer name. Furthermore, I eliminated any duplicate values and my final output had 6018 total observations and 11 column features.

![pic7](https://user-images.githubusercontent.com/36432832/44661405-d1e79000-a9c7-11e8-8951-81150ac5c434.png)

## Conclusion & Insights
Some key insights that I take from this project is that breweries in the top six are more likely to have twitter and website account than those in other parts of the country. There is alot of cleaning and preparation that goes with NLP and there is no one size fits all solution. Furthermore, there is a lot of information that can be derived from the meta data of the piece of 
string as well. Finally, people are using industry specific applicaitons such as Untappd and DPBeerDashboard to tell the world what they are drinking. 

## What are people tweeting about?
![pic9](https://user-images.githubusercontent.com/36432832/44661445-f0e62200-a9c7-11e8-8b5b-c3d83ff825ac.png)

# What are people using to communicate about their craft beer?
![pic10](https://user-images.githubusercontent.com/36432832/44661476-05c2b580-a9c8-11e8-874a-f76d607ba2b1.png)

## What are the top tweeted beers?
![pic11](https://user-images.githubusercontent.com/36432832/44661498-107d4a80-a9c8-11e8-8ed1-bdcf77b18ed7.png)

## Wordclounds about tweets for the top six cities
![pic12](https://user-images.githubusercontent.com/36432832/44661503-196e1c00-a9c8-11e8-84f6-025f8a3c5d56.png)

## What are people Retweeting about in the top six cities?
![pic13](https://user-images.githubusercontent.com/36432832/44661526-2854ce80-a9c8-11e8-96af-f3cfeb44cec8.png)


## Sources
http://docs.tweepy.org/en/v3.5.0/api.html
https://www.youtube.com/watch?v=mcJ2wPgkavw
https://www.youtube.com/watch?v=ikSEtMp1WVM
https://www.youtube.com/watch?v=P_q0tkYqvSk&t=302s
https://chrisalbon.com
https://seaborn.pydata.org/index.html
https://www.datacamp.com/community/tutorials/pandas-tutorial-dataframe-python


