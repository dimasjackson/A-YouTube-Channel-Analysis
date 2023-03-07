# A YouTube Channel Evolution During Covid-19 Pandemic: From 100 to 4.5M subscribers!
### Data Mining · Extract, Transform and Load (ETL) · Exploratory Data Analysis (EDA)

**Problem:** How profitable is a YouTube channel?

**Solution:** I defined a Python function to extract the data of a channel from the
YouTube API, stored, processed and cleaned the data collected. After that, I estimated the
channel revenue and did an exploratory data analysis to get insights from the data.

**Result:** The analysis showed that the channel raised more than 1500% in two years reaching
a revenue from YouTube ads that could reach US$ 6 million.

## Abstract

During the Covid-19 pandemic and the social displacement adopted, some people increased their time watching educational and entertaining videos on YouTube, which caused a rapid growing of some channels during this period. In this project we will analyze how the YouTube chanell "Inventor 101" raised from near 100 subscribers to more than 4.5 million in 3 years. Inventor 101 is a DIY irish channel where the author publishes inventions and science experiments made by himself, every weeky. We will start extracting the data from the YouTube API and preprocessing/cleaning the data collected. After that, we will create data visualizations to get some insights and we will do a exploratory data analysis (EDA) to summarize their main characteristics. Finally, we will discuss the agregated value of our analysis to the Inventor 101 channel and other similar content.

## Table of Contents

* [1. Extracting and Cleaning the Data](#extraction)
* [2. Importing the Data](#imp)
* [3. Getting Insights: Exploratory Data Analysis](#eda)
* [4. Conclusion](#con)
* [5. References](#ref)

<a id="extraction" ></a>
# 1. Extracting and Cleaning the Data

We will start creating a function to request the data about the Inventor 101 channel from the [YouTube API](https://developers.google.com/youtube/v3). Firstly, it is necessary to inform your YouTube API key, which can be obtained from Google Developers using your Google account. If you want to get your own key, follow the tutorial [here](https://www.slickremix.com/docs/get-api-key-for-youtube/).
Also, the channel id, which appears at the end of the YouTube channel URL is needed. If you want to apply this function to analyze other channels, just change the channel id field.

<a id="imp" ></a>
# 2. Importing the Data

To avoid the necesity of requesting data from API every time the notebook is executed, its appropriate to import the data from the csv file. 

<a id="eda" ></a>
# 3. Getting Insights: Exploratory Data Analysis

In this section we will do a exploratory data analysis (EDA) to summarize the main features of the data and calculate some basical statistical quantities. In the YouTube [about](https://www.youtube.com/c/Inventor101/about) page we can find that Inventor 01 is a DIY irish channel where the author publishes inventions and science experiments every weeky. Yet, it contains the following subscribers milestones:

* 100 - 01/4/19 
* 5k - 26/4/19
* 50k - 03/7/19
* 100k - 13/11/19
* 200k - 23/1/20
* 300k - 04/2/20

Today (3/11/22) the channel have 4,54M subscribers, so we can conclude that the channel raised $1513\%$ from the beginning of 2020 to the middle of 2022. Also, the total number of visualization at the present moment is 1,133,012,958.

First we will take a look at basical statistical quantities of the data set:

![image](https://user-images.githubusercontent.com/114688989/223478657-b7cc1740-6839-4295-9ae1-f1679cd3a1a2.png)

The above table inform us that the mean number of visualizations is $4.4$M and $75\%$ of the videos was watched more than $4.5$M times. Moreover, the mean likes percentual is $1.3\%$ of views and the comment percentual rate is $0.03\%$. The most whatched video was seen nearly $70$ million times and the less popular $12.000$ times. 

The current minimum estimated revenue is:
$ 541567.85
The current maximum estimated revenue is:
$ 6498814.20

![image](https://user-images.githubusercontent.com/114688989/223478860-52b9cfb7-bc0f-4230-aa6f-fa749631be8e.png)


![image](https://user-images.githubusercontent.com/114688989/223478916-012fcc5e-6475-4c37-b31d-0f7213e7dc2b.png)

This plot illustrate that the number of views, likes and comments obeys the same pattern, these quantities are almost proportionals. It's a interesting question why the the fraction of likes and comments is approximately the same for all videos. This could be used to predict the number of likes a video will receive, given the expected number of visualizations.   

![image](https://user-images.githubusercontent.com/114688989/223479051-3a2ea7fa-c4dc-44dd-9563-982e2a3737ad.png)

The number of views, comments and likes are positive skewed i. e. a distribution where the mean, median, and mode of the distribution are positive rather than negative or zero. In this case data distribution occurs more on the one side of the scale with a long tail on the right side. It is also known as the right-skewed distribution, where the mean is generally to the right side of the data median. The cause of this skewness is that the views cannot be less than zero and some videos have a very high number of visualizations. The same occurs with likes and comments.

![image](https://user-images.githubusercontent.com/114688989/223479166-fbe4f81b-379a-42ad-a76f-dd49ca42df36.png)

Scatter plots confirms the linear relationship between likes, views and comments like we stated above.

![image](https://user-images.githubusercontent.com/114688989/223479240-23abe007-06e5-4886-9268-f22ae066e645.png)

We can see that the revenue decreased from 2020 but the videos published in 2021 and 2022 are still being watched, so this income can grow up in the future.

![image](https://user-images.githubusercontent.com/114688989/223479457-c1a415e5-b042-4864-8493-43bf12bdf67f.png)

![image](https://user-images.githubusercontent.com/114688989/223479567-7695c6f6-3aa2-4f96-8106-fdb326a10a8e.png)

![image](https://user-images.githubusercontent.com/114688989/223479689-00b64fa9-f3bb-40ad-9b36-cee06a0bff89.png)

This is the Pearson correlation coefficient matrix, with is a measure of linear correlation between two sets of data. It is the ratio between the covariance of two variables and the product of their standard deviations normalized such that the result always has a value between −1 and 1. This measure can only reflect a linear correlation of variables, and ignores many other types of relationships or correlations. 

We can see that the number of likes, views, comments and the income are highly correlated with each other. As we stated before, this quantities are nearly proportional to each other.

<a id="con" ></a>
# 4. Conclusion

In this project we buit a function to interact with an API to request data, starting from the request of a JSON file and storing the information in a Pandas data frame.
We also explored some tools from the packages Seaborn and Pandas and extract informations and insights from data. 

The data analysis showed that the Inventor 101 channel, raised more than $1500\%$ in two years reaching a ravenue from YouTube ads estimated in the range USD $500.000$ to USD $6.000.000$. Unfortunately, only the proprietary of the channel have access to the historical data of visualizations and subscribers, which allows a more accurately calculation. This information would allow other analysis like finding the channel growth rate over time and knowing what videos motivated more people to subscribe. Also, we learned that, although the total of visualizations decreased in 2021 and 2022, the likes percentual stabilized nearly $1\%$. This could indicate that the channel is conquering a loyal audience, which may keeps a hight income.


<a id="ref" ></a>
# 5. References

* [YouTube API](https://developers.google.com/youtube/v3)
* [Working with API - Strata Scratch](http://https://github.com/Strata-Scratch/api-youtube/blob/main/README.md)
* [Getting API Key for YouTube - Slick Remix](https://www.slickremix.com/docs/get-api-key-for-youtube/)
* [10 Fastest Growing YouTube Channels to Light Up Your Mind](https://filmora.wondershare.com/youtube/fastest-growing-youtube-channels.html)
* [Inventor 101 YouTube Channel](https://www.youtube.com/@Inventor101)









