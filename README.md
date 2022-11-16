# What defines your relationship with a beer?
ADA-cadabra group

## Abstract:
Beer is an interesting cultural product. When it comes to a beer, there is a lot to talk about and many senses involved in a beer tasting experience. Sensory Evaluation is a common method of evaluating beer; it is conducted by each beer taster involves their sensory perception. There are four important main aspects of a beer that a person can evaluate: look, smell, taste and mouthfeel (palate). These affect one’s overall impression of a beer. The dataset we have consists of user reviews from beer reviewing websites that make use of sensory evaluation accompanied by a text review and some other data about the users, beers and breweries. The aim of this project is to uncover what defines one's relationship to a beer. To that end, we'll explore the different aspects of the data that could affect one's rating/review of a beer.

## Research question:
To unfold the sensory, cultural, geographical and potentially political story of how someone likes or dislikes a beer we’ll address several questions. 
What makes us like a beer the way we do? Is it the stimulation of our 5 senses through the different sensory cues a beer provides (visual, olfactory, gustatory ...) that make us judge a beer the way we do? Is it rather related to our entourage and we tend to drink local beers from our area by habit/culture? Or rather are there globally good beers that everyone everywhere like? Perhaps it is the popularity of a certain brewery that makes people consume their beers? And the list goes on.
Throughout this project, we’ll try to bring as many answers as possible to these questions in a spatial-temporal fashion: we have data that spans almost two decades and covers many American states and countries. In other words, it would be interesting to see if these answers vary from an area to another and over the years.

## Methods:
Dataset storage and processing
The text files for the reviews from the two websites and the matched data are extremely heavy. Thus, in the preprocessing part, we store the processed data frames (df_ratings_BA and df_RB_reviews) for reviews into csv files in order to access them more readily for the rest of the tasks. We added columns for those review dataframes with the user location and the brewery location for each review (by linking with the users and breweries data).

First idea: The influence of sensory cues on the perception of a beer
In order to determine which kind of sensory cues influence most one’s rating of a beer, we fit linear regression models on the overall rating for each of the sensory cues.

Second idea: Is a good beer a good beer everywhere? 
This idea stems from the fact that we have breweries and users coming from different locations. To investigate whether there is a bias towards consumption of local beers rather than just globally good beers, we first determine the beers that are globally perceived as the best. To do so we choose three criteria: we select beers that have been heavily reviewed by reviewers that have already written a lot of reviews and then select the top 20 beers from an overall rating perspective (averaged over the two rating websites). From there, we look at the number of reviewers that drink beers from their locations.

Third idea: 


## Internal milestones up until project Milestone P3:
Milestone 2
•	Loïc: 
•	Florian: 
•	Kish:  
•	Zeina: Investigate the second idea. Transform the review text files into readable dataframes. Create README.

