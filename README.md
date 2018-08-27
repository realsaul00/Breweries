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

## EDA
The intent for this part of the project was understand the strenghts and weaknesses of the dataset. I printed value counts
and summaries for each column feature to understand each contributing feature. I went ahead and created several word clouds 
and word frequency distributions for the category feature which was all string objects. Understanding each feature allowed
to formulate an inital plan of attack. It was in this step that I discover the identity of the top six brewery markets in 
the U.S. 

## DATA PREP1
This notebook was a continuation of the previous one. For this section I contined exploring the dataset but with a plan in mind. First, I created six subsets for the top six brewery cities. I inspected to see what proportion of observations contained twitter account names and website information. Subsequently, I began experimenting with geopy to fill in missing latitude and longitude information. This however failed since the API would not time me out constantly. After several failed attempts I decided to resort back to Google Sheets and Awesome Table geocoding services. 

## DATA PREP2
After successfully filling for most missing values in latitude and longitude I continued with data preparation phase. I dropped eight rows where latitude and longitude could not be encoded. I then proceeded to plot the six brewery markets. I discovered that instead of six clusters I was seeing eleven clusters. I investigated the problem and it turns out that there two cities with the same name. I then used k-means to filter out the unwanted clusters.

## KNN IMPUTE
The dataset was almost ready for streaming, however the postalCodes column had 128 missing values. For practice, I decided to use KNN to impute for missing zip code values. I figured I can build an accurate KNN model using latitude and longitude as the predictors and would achieve a high accuracy rate. I first trained the model on the known observations and then when I was getting 90.5% accuracy I decided to apply the model on the missing observations and impute for missing values. I inspected the results and was satisfied with the output. 

## WORD COUNTER


