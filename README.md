<H3>ENTER YOUR NAME A SHARMILA 
<H3>ENTER YOUR REGISTER NO.212221230094
<H3>DATE:</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Type your objective based on the question
<H3>Program:</H3>
```
import pandas as pd
from textblob import TextBlob

# Read data from CSV file :

data = pd.read_csv("fb_sentiment.csv")

# Given name to count occurrences :

given_name = "Love"

# Initialize counters for sentiment analysis :

sentiment_counts = {'positive': 0, 'negative': 0, 'neutral': 0}

# Initialize and Count occurrences for the given name :

name_occurrences = sum(post.lower().count(given_name.lower()) for post in data['FBPost'])

# Perform sentiment analysis and count occurrences of the given name :

for post in data['FBPost']:
    polarity = TextBlob(post).sentiment.polarity
    sentiment_counts['positive'] += polarity > 0
    sentiment_counts['negative'] += polarity < 0
    sentiment_counts['neutral'] += polarity == 0

# Print sentiment analysis results :

print("Sentiment Analysis Results:")
for sentiment, count in sentiment_counts.items():
    print(f"{sentiment.capitalize()} sentiment: {count}")

# Print occurrences of the given name :

print(f"Occurrences of '{given_name}': {name_occurrences}")

```
<H3>Output:</H3>

![image](https://github.com/Sharmilasha/Project-Based-Experiment-AAI/assets/94506182/2726a7eb-cea7-4c49-abe7-359e0b1407da)

<H3>Inference:</H3>
Write about your learning experience out of this project. (What you have learned)
