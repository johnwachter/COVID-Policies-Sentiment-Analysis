## COVID-Policies-Sentiment-Analysis
Partial Collection of data, scripts, and reporting from a project looking at public sentiment toward COVID mitigation policies

## Microblogging platforms like Twitter provide a robust pipeline for examining public perceptions during crisis events. Twitter’s real time coverage of crisis events serves as both a mode of information sharing and a platform for engaging in topical discourse. These content sharing practices encapsulate the views and opinions of users providing a meaningful avenue for analyzing public sentiment at scale during crises.

## Research Objectives
Limiting the scope to two states (Washington and Florida) in the country that has the largest number of recorded infections, it is hypothesized that there are regional differences in how the population perceives COVID-19 mitigation strategies and that these perceptions and viewpoints will be shared on Twitter and be reflected in the practices and mobility patterns of different states. 

## The objective of the project is to:
- Identify public sentiment towards COVID-19 mitigation policies in the aforementioned states using Twitter data.
- Identify the degree to which the viewpoints of mitigation policies expressed on Twitter reflect social attitudes and practices and resulting impact on the spread of COVID-19 in the aforementioned states.

## Data
To understand the public perception towards COVID-19 policies, we collected various types of data over a course of 3 months from the following sources:
- Tweets from Twitter using Twitter IDs from Github Repository & Twitter Developer Accounts, and Samples from the University of Washington's Center for an Informed Public's dataset
- Global Mobility Report made publicly available by Google
- Global time series of case and death data made available by John Hopkins University’s Center for Systematic Science & Engineering

We gathered over a 100 Million Twitter IDs - a 19-digit number that uniquely identifies a Tweet - from the Github repository of two researchers at the University of Southern California (Chen, 2020). The researchers tracked a variety of terms associated with COVID-19. 15.75% of the IDs - over 16 million - were randomly sampled, and each ID converted into a JSON object that contained all information associated with each tweet (hundreds of variables) using a command line tool called [Twarc](https://github.com/DocNow/twarc). Next, user-defined locations and reverse geocoding were employed to capture tweets from users based in Florida or Washington. This resulted in a final curated dataset with 52,437 observations and three variables; timestamp of the tweet, the full text of each tweet, and whether the tweet was associated with Washington or Florida. The [scripts](/scripts) used for the analysis are available on this repo.

Below are two static images of interactive dashboards that provide an overview of the Twiter data and the Google Mobility data:

![Overview of Tweets](/images/TweetsOverview.PNG)




![Overview of Mobility](/images/Mobility_CaseCounts.PNG)

## Modeling
In order to identify the abstract topics from our collection of tweets, we used a Latent Dirichlet Allocation (LDA) model. This generative probabilistic model is a tool used in Natural Language Processing and aims to surface similarities in documents - or in this case tweets - by generating a distribution of words over topics, and topics over documents. [Luis Serrano](https://github.com/luisguiserrano) has a great [introductory video](https://www.youtube.com/watch?v=T05t-SqKArY) on developing an intuition for how LDA models generate topics The distribution and root meaning of the words within the corpus are used to determine individual topics. More details on modeling choices can be found in [this jupyter notebook](https://github.com/johnwachter/COVID-Policies-Sentiment-Analysis/blob/master/scripts/Text%20Analysis%20of%20Tweets.ipynb), and the [models](/lda_models) are available on this repo. Please note that the html files don't render well in github, but [here](https://htmlpreview.github.io/?https://github.com/johnwachter/COVID-Policies-Sentiment-Analysis/blob/master/lda_models/LDA_Vis_Mod1.html) is one example of an interactive LDA model. 
