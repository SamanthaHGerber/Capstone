**Capstone Title**

Using Text Classification to Detect Sentiment (Positive, Neutral, or Negative) in Tweets Regarding Airlines

Airline Tweet sentiment analysis by Samantha Gerber

**Executive Summary**

The data is from Kaggle. The data are a collection of Tweets from Crowdflower's Data for Everyone library, and posts were collected in February of 2015.


**Research Question**

What words lead to positive, negative, and neutral tweets about airlines?

**Rationale**

The data task is to train and tune multi-class classification models that group Tweets into positive (1), neutral (0), and negative (-1) classes. This question is important because it helps airline determine what words/actions are causing positive, negative, or neutral sentiment. This can help them focus on things that make customers happy and improve things that customers complain about (such as flight delays and cancellations). This analysis will also help airlines craft better tweets that have positive sentiment, so their passengers can retweet them.

**Data Source**

[Link](https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment)

**Code Files**

[Part 1](https://github.com/SamanthaHGerber/Capstone/blob/main/Gerber%20Capstone%20(Part%201).ipynb)

[Part 2](add link)

**Methodology**
-**Data Understanding**
  - Use Pandas to Read CSV Dataset
  - Perform exploratory analysis to idenitfy how the Tweets are represented across sentiments, what airlines and how much each one is being Tweeted at, the reason for negative Tweets, retweet count distribution, and user timezone count.
<img width="788" alt="Screenshot 2023-12-10 at 3 13 08 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/2da28762-477c-4c7e-bbaf-4cb490c9166c">
<img width="774" alt="Screenshot 2023-12-10 at 3 14 48 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/d6d292d0-6d6d-4ccf-8c16-7466d97ade86">
<img width="773" alt="Screenshot 2023-12-10 at 3 15 12 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/27791ffa-4390-49f4-9eb4-9e92b226816a">
- **Train/Test Split**
    - Use train/test split to separate train = 75% and test = 25%
    
-**Data Processing**
  - Tokenization
  - Stop word removal
  - Punctuation removal
  - Lower casing
  - Stemming
  - @AirlineName removal
  
-**Modeling**
  - Logistic Regression
  - Naive Bayes
  - Decision Tree
  - Support Vector Classifier (SVC)

-**Analyze Model Performance**
  <img width="741" alt="Screenshot 2023-12-10 at 3 19 37 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/c33103eb-3942-4d1f-8c20-a2e0592a512e">
- Pick Best Model: SVC
<img width="673" alt="Screenshot 2023-12-10 at 3 20 29 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/f1b717d0-032a-43a1-a69d-8225199c1e1b">
- Analyze total word length by sentiment and average word length
<img width="374" alt="Screenshot 2023-12-10 at 3 21 38 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/ef05ed1c-b385-47ad-8fac-bb29a00fc80b">

-**Generate Word Clouds**
<img width="709" alt="Screenshot 2023-12-10 at 3 22 36 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/bd7c4b25-9764-47f1-a9c1-8f95f472bfcc">
<img width="655" alt="Screenshot 2023-12-10 at 3 22 53 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/1403c733-8294-442a-93ac-772b94e68646">
<img width="659" alt="Screenshot 2023-12-10 at 3 23 27 PM" src="https://github.com/SamanthaHGerber/Capstone/assets/138829845/3d0d0b68-1907-4487-a1bf-b7ea5b6708c9">

- **Identify the 20 Most Common Words for Each Sentiment**
  - Top 20 words for sentiment 0 (neutral): 'flight', 'http', 'thank', 'need', 'pleas', 'help', 'fli', 'dm', 'book', 'ticket', 'chang', 'tomorrow', 'time', 'travel', 'fleek', 'check', 'know', 'fleet', 'cancel', 'way'
  - Top 20 words for sentiment 1 (positive): 'thank', 'flight', 'great', 'http', 'love', 'servic', 'help', 'fli', 'custom', 'guy', 'good', 'time', 'airlin', 'best', 'awesom', 'got', 'make', 'work', 'appreci', 'today']
  - Top 20 words for sentiment -1 (negative): 'flight', 'hour', 'cancel', 'delay', 'custom', 'servic', 'time', 'help', 'wait', 'bag', 'hold', 'plane', 'tri', 'need', 'flightl', 'day', 'http', 'gate', 'fli', 'thank'

-**Find Overlapping Words Among the 20 Most Common Words for Each Sentiment**
  - http
  - fli
  - flight
  - thank
  - time
  - help

**Next Steps and Recommendations**

It could be helpful to do a global analysis using the ELI5 and LIME libraries and a local analysis to determine model feature weights (both positive and negative). 

It would be useful to train more complex and advanced models to see if they could better predict the sentiments of Tweets, as the best model (SVC) has accuracy below 80%. It would be great to get accuracy above 95% if possible in the future. Ensemble methods, Recurrent Neural Networks, and Convolutional Neural Networks could lead to a better and more accurate models. 

Further exploration of the top words for each sentiment could be done with the other models built: Logistic Regression, Naive Bayes, and Decision Tree.

It could be interesting to look at words that only appear in top 20 lists for Tweets of each sentiment and create a list to easily predict future posts.
