<H3>ENTER YOUR NAME: Abdullah R</H3>
<H3>ENTER YOUR REGISTER NO: 212223230004</H3>
<H3>DATE: 21-05-25 </H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:"How can we analyze the sentiment of a given set of text data and determine how many times a specific name appears within that text?"<H3>
 
 The Objective of this project is:
 
1. Perform Sentiment Analysis on text
(Find out if the text is positive, negative, or neutral.)

2. Count how many times your name appears in the text
(Find out how often a specific name is mentioned.)

In simple words:
You have some text (like Facebook posts, or fake data).
You analyze the "feeling" behind the text — happy, sad, angry, neutral.
You count how many times a given name (like Alex, Tom, or your name) shows up.

<H3>Program:</H3>

```
import json
from textblob import TextBlob

Load the fake Facebook data
with open('fake_facebook_data.json', 'r', encoding='utf-8') as f:
    fb_data = json.load(f)

Extract text
texts = []
for post in fb_data.get('posts', []):
    if 'data' in post and isinstance(post['data'], list):
        for item in post['data']:
            if 'post' in item:
                texts.append(item['post'])
    if 'title' in post:
        texts.append(post['title'])

Combine all text
full_text = " ".join(texts)

Sentiment Analysis
sentiment = TextBlob(full_text).sentiment
print(f"Sentiment polarity: {sentiment.polarity}, Subjectivity: {sentiment.subjectivity}")

Count occurrences of the name
your_name = "Alex"
name_count = full_text.lower().count(your_name.lower())
print(f"Occurrences of '{your_name}': {name_count}")

```

<H3>Output:</H3>

![image](https://github.com/user-attachments/assets/1117f22b-b5e5-4915-ae4b-0f694e0f37d4)

<H3>Inference:</H3>
1. How to read and process JSON files

You learn to load structured text data (like Facebook posts) into Python.

2. How to clean and extract useful information from text

You practice picking out just the parts you need (posts, comments, messages) from messy real-world data.

3. How to perform sentiment analysis

You learn how to detect emotions in text (positive, negative, neutral) using Python libraries like TextBlob.

4. How to search and count words in a large text

You practice basic string handling — finding how often a name appears.

5. How to work with external Python libraries

You learn how to install, import, and use libraries like textblob.

6. Basic Natural Language Processing (NLP) skills

You get your first hands-on experience in NLP — which is used in AI, Chatbots, Google Translate, etc.

7. How to interpret and present results

You learn how to explain what sentiment and word counts mean, and maybe visualize them (graphs, tables).
