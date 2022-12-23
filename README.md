# Brew-havior: uncovering factors that affect your opinion about a beer.<br>
***Please refer to Milestone_P3 notebook***

 ADA-cadabra group
## Data story:
You can find our data story by following [this](https://flaubertepfl.github.io/) link

## Abstract:
Beer is an interesting cultural product. When it comes to a beer, there is a lot to talk about and many senses involved in a beer tasting experience. Sensory Evaluation is a common method of evaluating beer; it is conducted by each beer taster and involves their sensory perception. There are four important main aspects of a beer that a person can evaluate: look, smell, taste and mouthfeel (palate). These affect one’s overall impression of a beer. The dataset consists of user reviews from beer reviewing websites that make use of sensory evaluation accompanied by a text review and some other data about the users, beers and breweries. The aim of this project is to uncover what are some extrinsic and intrisinsic factors that can affect one's rating of a beer. 

## Research question:
What makes us like a beer the way we do:
- Is it the the stimulation of our 5 senses through the different sensory cues a beer provides (visual, olfactory, gustatory ...) that make us judge a beer the way we do?
- Do our location, habits, culture affect how we rate a beer? 
- Can major events your region goes through affect the way you review a beer?
Throughout this project, we’ll try to bring as many answers as possible to these questions in a spatial-temporal fashion: we have data that spans almost two decades and covers many American states and countries. 

## Methods:
#### Dataset storage and processing:
The text files for the reviews from the two websites are extremely heavy. In the preprocessing part, we store the processed data frames (df_BA_reviews and df_RB_reviews) for reviews into csv files in order to access them more readily for the rest of the tasks. We enriched the review dataframes by adding columns for those review dataframes with the user location and the brewery location for each review (by linking with the other users and breweries data).

#### First idea: The influence of sensory cues on the perception of a beer
Find relationships of the sensory attributes of the beer with its ratings. <br>
Method: fitting a linear regression model on the overall rating for each of the sensory cues (palate, aroma, taste, and appearance). Computing the Pearson's correlation coefficient to determine the strength of these linear relationships. 

#### Second idea: Does your location and/or culture affect your beer rating? 
Investigate whether there is a location/cultue bias to beer preferences. <br>
Method: Creating style vectors for each country (weight proportional to liking of a certain style). Running K-means clustering on the countries to identify regions that cluster together that would indicate a cultural bias. Analyzing the main interesting clusters in terms of style preferences and words used to describe those styles.


#### Third idea: Investigating political and cultural influence on beer reviews
The effect of the financial crisis of 2008 on beer reviews. <br>
Method: 

<br>
N.B: We have changed some directions of our projects from milestone P2 according to our findinfs: in the second idea we have fine-tuned our study into a cultural investigation rather than purely location based and omitted the idea of looking at the top 20 beers but rather considering all the beers and the different ratings. We have focused on one major event in the last part (the financial crisis).

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
•	Loïc:    <br>
•	Florian: <br>
•	Kish:     <br>
•	Zeina:   Doing the second idea: stye vectors per country, clustering and displaying on a map. Updating the README. Putting together the milestone P3 notebook. <br>

