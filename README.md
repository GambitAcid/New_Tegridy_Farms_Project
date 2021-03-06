# Tegridy Farms Project 

Team Members: Ronnie Phillips, Rashmi Rekha, Lynne Freilich, and Nashra Khan

Project Description/Outline:

In our contemporary world of politically correctness, where general consensus of culture shuns, cancels, or otherwise finds most anything offensive, one show has remained a constant. A bright lit star in woke cultures night sky. A small group of Coloradoan 4th graders have remained banded together refusing to go down despite the ever-evolving rejection of everything deemed ‘not ok’. But are they starting to cave? This is a quantitative sentiment analysis of dialogue of the characters, jokes, and offensiveness of the TV series SouthPark. We want to do a deep dive into the words of SouthPark and see if we can pick out some underlying trends to see if one of TV’s more extreme shows has become less offensive as time has progressed. Our groups null hypothesis is that SouthPark has not changed at all in offensiveness over time even as culture has become more sensitive to the type of jokes the SouthPark built its show upon. Our hypothesis is assumed to be true and thus will be tested against the shows extreme language, usage of racial dialogue, radical ideologies, political jokes, religious jokes, and other criteria and parameters to create a sentiment analysis of the shows offensiveness. We will also look at user ratings of seasons or episodes correspond to those characters saying the most slanderous things. We will then use linear regression to determine if the show has become less offensive or more offensive over time and subsequently more or less popular. After our analysis is conducted from the collected data, we will either accept or reject our null hypothesis for the alternative hypothesis which is a.) The shows offensiveness has decreased over time or b.) The shows offensiveness has increased over time.

#### Question: Has SouthPark become less offensive over time? We will be using linear equation where M is the slope of the line to see if the slope becomes positive, negative, or neutral.

#### Null Hypothesis: SouthPark has not changed at all over time H0: M in M = 0 
#### Alternative Hypothesis 1: SouthPark has become less offensive over time HA1: M < 0 
#### Alternative Hypothesis 2: SouthPark had become more offensive over time HA2: M > 0  

Research Questions to Answer:

Is there a correlation between seasons and negative dialogue? Essentially has the show become more or less offensive over time.  
  *  Is there a correlation between later seasons having less offensive dialogue?   
  *  Is the language of SouthPark more or less foul as seasons progressed?  
  *  Which set of characters had the foulest language?   
  
### Data
Kaggle: South Park Dialogue: More than 70,000 lines of dialogue by season, episode, and character https://www.kaggle.com/datasets/tovarischsukhov/southparklines    
Screen scrapes from South Park Fandom by episode via Copy/paste to csv.file - VBA to remove scene information from dialogue 
https://southpark.fandom.com/wiki/South_Park_Archives   
Offensive Word List https://www.cs.cmu.edu/~biglou/resources/bad-words.txt 

### Python Libraries
TextBlob: sentiment analysys 
NLTK: tokenizing using TweetTokenizer
NLTK: Stopwords and Punctuation lists
Collections: Counter for wordtypes 
Matplotlib, WordClooud: visualizations

### Initial Data Gathering   
Our initial data source is Seasons 1 -18 found on Kaggle, to complete our dataset through all aired seasons we scraped additional script data from SouthParkFandom.wiki. The newly added data went through the additional steps of having season and episode information added to the lines of dialogue. The script data had embedded scene data included, this was stripped out using a VBA script and saved back to a .csv file.  The main python script was modified to look for new season information and if available perform some final cleaning and add it to the dataset. 

### Dataset processing 

The complete dataset was first tokenized and stripped of punctuation and parsed into three distinct lists for further analysis. These lists are represented below by words clouds of the 25 most frequently occurring words in each list.

  A list of all the words used in South Park ![image](https://user-images.githubusercontent.com/98897041/166171557-401205b0-4aa6-4d70-815b-27b9fc2033aa.png)  
  This list is not likely to provide much insight for our analysis as the most common words used on South Park are the most common words in the English language.
	A list of all words with standard NLTK stop words removed 
  
  A list of all words with standard NLTK stop words removed. ![image](https://user-images.githubusercontent.com/98897041/166171425-9130cfcc-f6df-4273-ad55-137121136297.png)   
  The second list provides a more representative set of words that describe the dialogue of South Park.
  
  A list of offensive words used in South Park  
  The display of this word cloud has been supressed due to it offensive nature. It may be found in the image folder of this respository  
  The third list demonstrates there is a wide variety of offensive words that we can analyze.
  

  ### Wordlist Analysis 
  
  When we examine our first measure of offensiveness, the use of offensive language, we see that the amount of offensive language has decreased over the run of the series. The offensive language decline has not been regular, the peak use of offensive words occurred in season three and continued to decline until after season 10 when it rose again experiencing its second peak in season 13 then steadily declined through the most recent season.
  
![image](https://user-images.githubusercontent.com/98897041/166173321-61454ba4-c77e-492a-9b86-593e542dcf85.png)
![image](https://user-images.githubusercontent.com/98897041/166174446-ce1bc36a-37dd-4d2c-a89b-1d7db08abd3b.png)

#### Note: in the graphs it can been seen that season 24 had a lower offensive word count than season 25, this drop is due to an overall drop in dialogue.  Season 24 is an official season however it had only two extended episodes (because…  COVID). Season 25 returned to the 10 episode format. 
  


### Sentiment Analysis

We used TextBlob to evaluate the sentiment of each line of dialogue. Sentiment describes the over all feeling of a statement, for example the sentence "I am happy to be here.", would score a strong positive sentiment, because of both the language used and lack of additional statements to change it. The statement "Why would you do that terrible thing.", would produce a negative sentiment. It is important to note the statement "You did a terribly good job!", to the reader of that statement it is clear, that it is an strongly positive statement. TextBlob returns a mixed evaluation of this statement, it returns a mildly positive score, and a high subjectivity score. The first chart looks at only those scores above zero and shows that the positive sentiment of South Park over the seasons has declined, the second chart looks at only those scores below zero and shows that the negative sentiment has increased over time. We used sentiment analysis as a second measure against our hypothesis, dialogue that is net positive has decreased over time and negative sentiment has increased. If offensive language were the only factor in determining if a statement were positive or negative, we would expect that negative sentiment would have declined over time. The third chart displays the subjectivity over time, we can view this as type of error rate for the first two charts. While the regression line points to a minor decline in subjectivity, the scatter points show that season 19 scored particularly high and seasons 22 and 24 scored particularly low. Additional analysis would have to be done on those seasons, one of the seasons in question, season 24, was produced and aired during the pandemic. This metric implies that the series has become statistically more negative over time.

The correlation between both factors is -0.66
![image](https://user-images.githubusercontent.com/98897041/166174473-773384a8-5dab-4c23-8534-826a127d07e8.png)

The correlation between both factors is 0.4
![image](https://user-images.githubusercontent.com/98897041/166174504-c4dd513f-f9fb-4b88-a6a5-41180817e625.png)

The correlation between both factors is -0.37
![image](https://user-images.githubusercontent.com/98897041/166259769-1482e308-4026-4537-ae9e-2e439ab5ba7d.png)


### Additional Analysis
The r-squared between Word Count vs Offensive Word Count: 0.155

![image](https://user-images.githubusercontent.com/101225094/166391851-e41d0ea0-8620-4bed-9d5f-87074ab06923.png)

The r-squared between Season vs Positive Polarity: 0.713

![image](https://user-images.githubusercontent.com/101225094/166391778-a518bdca-f75f-469f-9090-8a32d470349a.png)

The r-squared between Season vs Negative Polarity: 0.071

![image](https://user-images.githubusercontent.com/101225094/166391759-ef1e3d69-4830-4f57-909d-e5e154265381.png)

The correlation between Word Count and Subjectivity is 0.29

The r-squared between Word Count vs Subjectivity: 0.083

![image](https://user-images.githubusercontent.com/101225094/166391737-00d59bf1-be57-4e3c-87b9-cda610c96284.png)




