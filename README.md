# What defines your relationship with a beer?
ADA-cadabra group

## Abstract:
Beer is an interesting cultural product. When it comes to a beer, there is a lot to talk about and many senses involved in a beer tasting experience. Sensory Evaluation is a common method of evaluating beer; it is conducted by each beer taster and involves their sensory perception. There are four important main aspects of a beer that a person can evaluate: look, smell, taste and mouthfeel (palate). These affect one’s overall impression of a beer. The dataset consists of user reviews from beer reviewing websites that make use of sensory evaluation accompanied by a text review and some other data about the users, beers and breweries. The aim of this project is to uncover what defines one's relationship to a beer. To that end, we'll explore the different aspects of the data that could affect one's rating/review of a beer.

## Research question:
To unfold the sensory, cultural, geographical and even political story of how someone likes or dislikes a beer, we’ll address several questions. 
What makes us like a beer the way we do? Is it the stimulation of our 5 senses through the different sensory cues a beer provides (visual, olfactory, gustatory ...) that make us judge a beer the way we do? Is it rather related to our entourage and we tend to drink local beers from our area by habit/culture? Or rather are there globally good beers that everyone everywhere like? Perhaps it is the popularity of a certain brewery that makes people consume their beers? And the list goes on.
Throughout this project, we’ll try to bring as many answers as possible to these questions in a spatial-temporal fashion: we have data that spans almost two decades and covers many American states and countries. In other words, it would be interesting to see if these answers vary from an area to another and over the years.

## Methods:
#### Dataset storage and processing:
The text files for the reviews from the two websites and the matched data are extremely heavy. Thus, in the preprocessing part, we store the processed data frames (df_BA_reviews and df_RB_reviews) for reviews into csv files in order to access them more readily for the rest of the tasks. We enriched the review dataframes by adding columns for those review dataframes with the user location and the brewery location for each review (by linking with the other users and breweries data).
We then explore the different ideas we want to implement in the notebook:


#### First idea: The influence of sensory cues on the perception of a beer
This idea aims to find the various relationships of the sensory attributes of the beer with its ratings. In order to determine which kind of sensory cues influence most one’s rating of a beer, we initially try to find the linear relationships. To do so, we fit a linear regression model on the overall rating for each of the sensory cues, namely, palate, aroma, taste, and appearance. We also find the Pearson's correlation coefficient to determine the strength of these linear relationships. Initial analysis showed that taste had the strongest linear impact on the rating of the beers (R value of 0.959) followed by Aroma (R value of 0.87). To further analyse these relationships, we aim to find non linear relationships of the sensory features with the ratings as well. Furthermore, using two key natural language processing techniques, i.e. word extraction and word embeddings, we aim to find the reviews that talk about these sensory features in greater details and put that into context of perception (ratings) of the beer. 

#### Second idea: Is a good beer a good beer everywhere? 
This idea stems from the fact that we have breweries and users coming from different locations. To investigate whether there is a bias towards consumption of local beers rather than just globally good beers, we first determine the beers that are globally perceived as the best. To do so we choose some filtering criteria: we select beers that have been heavily reviewed by reviewers that have already written a lot of reviews and then select the top 20 beers from an overall rating perspective (averaged over the two rating websites). From there, we look at the number of reviewers that drink beers from their locations.
However, we’ll need to normalize those numbers as we might have a very high number of reviewers because a state/country has a larger population.  
Since the final idea is to construct an interactive map (we plan to use the [folium](https://python-visualization.github.io/folium/) library as it is a commonly used library to for interactive maps), we would like to construct it such that when we hover over it, we get information about:
-	The best beer of the area with its average score and data about the beer in a visual way
-	Which countries review this beer the most and data about the users
Once this has been done, we can do some analysis to see which words used are most used per country to describe beer. To do so we’ll process the textual data using “Term Frequency — Inverse Data Frequency” (TF-IDF).


#### Third idea: Investigating political and cultural influence on beer reviews
We are interested in factors that influence our relationship with the beer we drink. One factor that is very interesting to investigate on is politics.
We want to find a way to find links between the ratings of beers and political climates. We looked into 5 different events:
- Investigating how the trading war between China and the USA affected the ratings of US users on Chinese beers.
- How the Brexit affected beer ratings.
- The effect of the Anheuser-Busch scandal on beer reviews (watered down Budweiser beers).
- The effect of the financial crisis of 2008 on beer reviews.
- The effect on the reviews of beers produced using genetically modified crops.

<details><summary>Detailed decsription here (click me)</summary>
<p>

#### 
a) The first idea we came up with was to investigate how the trading war between China and the USA affected the ratings of US users on Chinese beers.
We prioritise this question for several reasons.
First: the trading war was a lot in the media, so many people were aware of the tensions. <br>
Second: as we googled a few of the Chinese beer from the dataset, we discovered, that on the bottles of the beers we observed, there was always some writing in Chinese. This would facilitate infer, that consumers are aware that they are drinking Chinese beer.<br>
Third: The trading war affected the lives of people. Through the increased taxes, some products got more expensive and other products could be less exported which led to a loss of workplaces. <br>
We first investigated the period for which we have datapoints in general. <br>
Unfortunately, the data ranges from 1996 to 2017. The trading war started under the presidency of Donald Trump, who was elected in 2016. So, the reviews will only insufficiently describe the time of the trading war. <br>
However, we did not give up, and we found a book describing the public US opinion towards China and how it evolved over time (including during the years from 1996 to 2017). <br>
The book is called "Winning American Hearts and Minds" by Xiuli Wang. <br>
We planned to search for a correlation between the public opinion and the reviews given to Chinese beers.<br>
We have seen that we have at least 188 Chinese breweries in the dataset. At least, because there were breweries from RatingBeer (RB) and BeerAdvocate (BA). They use different wordings, which makes it hard to detect redundant breweries from both datasets. Therefore, we used a conservative approach and considered only the breweries from the dataset with more Chinese breweries.<br>
The 188 breweries produce a total of 1316 beers. <br>
We found a total number of around 3’700 US reviews on Chinese beers. <br>
We plotted it over the different years and for 75% of the years we have more than 350 reviews. We don’t know whether we will observe significant effects, but we can proceed with this question in milestone P3.  <br>

  </p>
  <p>
b) As we still would like to investigate political events or climates, we thought about the Brexit. In June 2016 the British population decided in a referendum called “Brexit” that they want to leave the European union (EU). <br>
This has made big waves in global politics and influenced the relationship of GB with other countries in various manners. It weakened the European collaboration and on the same hand affected the GB-US relationships, as the Britain were looking for new trading partners.<br>
In this part we want to investigate how the ratings of US users on British beer changed after the Brexit.<br>
We get a total of 168’000 reviews of US users on British beer. To our disadvantage, only around 5’000 of these ratings were given after Brexit.<br>
We intend to investigate two things: <br>
First: The scores that were given before and after the Brexit and whether they evolved differently after Brexit. <br>
Second: Whether the number of reviews given per period of time changed. This is interesting because less reviews could indicate a reduce in consumption of British beer. <br>
As it would be interesting to get an idea of how the effect differs from one state to another, we also plotted the distributions of ratings over the different states. Especially for the ratings after Brexit we see that we have a few states with very little reviews. <br>
Half of the states have 80 or fewer ratings. Therefore, for this question we propose to group democratic voting and republican voting states. We need to be aware of the swing states and either integrate them into the group of the political party that won the election for the presidency election which took place in the same year as the Brexit, or we make a third group consisting of the swing states.  <br>
    </p>
     <p>
c) To compare political influence on the different states we need more data. To have more data we plotted the origins of the beers rated by US users.
We observed that most of the US ratings were on US beers. <br>
So we switched strategy. Instead of asking questions about international relations, we try to grasp political energy inside the country.
One type of event that could have an influence on reviews is the scandal.<br>
We stumbled over a scandal, where the US brewery Anheuser-Busch was accused of watering down their beer called Budweiser.<br>
The lawsuit that was discussed in the media and might have had an influence on the ratings on beers of Anheuser-Busch (AB).<br>
We have a nice base, as there are 74’000 ratings on AB beers of US users. <br>
We investigated the distribution over the different states and could see that 25% of the states have more than 2000 ratings while we have also 25% with less than 400 ratings.<br>
We will try to investigate how the watering scandal (and other, there are a few AB scandals) in milestone P3.<br>
Should there not be sufficient data in some states, we will consider grouping them with similar states.<br>
       </p>
<p>
d) As a fifth question we want to find out how the economic situation affects our beer experience. We choose the financial crisis of 2008 as the economic event of question.<br>
We filter the reviews for texts mentioning defined, price related words. The list with the words is found in the notebook and will be completed during the milestone P3.<br>
We will see how the relative frequency of those words vary over time and whether we can see a trend before and after the crisis of 2008.<br>
There are roughly 190’000 reviews mentioning at least one of our price related words. This is a dataset with which we will happily continue in milestone P3.
         </p>
           <p>
e) Genetic engineering is a very emotional topic. We stumbled over a US-article discussing the issue of genetically modified crops used in the production of beer.
We first scan the reviews for text reviews where a set of defined gentech related words. The words can be reviewed in the notebook.
We found a total of 225 reviews mentioning words related to genetic engineering.
In milestone P3 we will investigate whether these reviews correlate with good scores or bad ones to get an idea about the acceptance of biotechnology.
The sentiment analysis allows us to get an idea about the standpoints of the users. If we there will be both positive and negative feedbacks in approximately the same number, we can compare the variance with the global variance to see whether genetic engineering polarizes more than other features.
</p>
</details>

#### Fourth idea: Grouping users by categories
Finding categories to group the users. Experienced users vs Unexperienced: I first tried to separate experencied users. I made the assumptions that they would write longer comments. But there is no clear demarcations in the length of the comments. I pursued with another assumptions that experienced users would have written more reviews. I found out that most of the ratings gave no textual reviews. The distribution of reviews' amount per user follows a power law. <br>
I then thougt of getting rid of hate comments. For that I would need to do sentiment analysis. I started simply by categorizing the comments into positive or negative sentiment. The sentiment analyser was found on huggingface.co (distilbert-base-uncased-distilled-squad). The goal will be to tune the sentiment analyser for beer comments. So we could be more specific about the catgeories.

## Internal milestones up until project Milestone P3:

### Milestone 2 
•	Loïc:    Investigate the fourth idea, textual analysis.<br>
•	Florian: Investigate the third idea and data storage<br>
•	Kish:    Investigate the first idea. Try to find non linear relationships and extract reviews containing the sesnory cues. <br>
•	Zeina:   Investigate the second idea. Transform the review text files into readable dataframes. Create README. <br>

### Proposed timeline
Step 1: 25/11/22 Finish preprocessing <br>
Step 2: 02/12/22 Complete Second and Third part which are already well advanced<br>
Step 3: 09/12/22 Textual data analysis (Sentiment analysis, TF-IDF) + Finish the sensory analyses <br>
Step 4: 16/12/22 Start the interactive map<br>
Step 5: 23/12/22 Finish the P3

### Milestone 3

Political: Flo <br>
Location: Zeina <br>
Text: Loïc <br>
Sensory Values: Kish

