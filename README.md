# Sentiment Analysis Project : Project Overview
* Created a project that tends to recognize the sentiments from text through Natural Language Processing using a pretrained BERT transformer with a testing f1 score equals to 87 %.
* Collected data to work with from kaggle (a dataset named `SMILE Twitter Emotion Dataset` within Datasets section).
* Explored our data to extract some relevant insights and patterns and cleaned it up to make it ready for the modeling phase.
* Tokenized & encoded the data and trained a pre-trained BERT transformer from `HuggingFace` called `bert-base-uncased` on it.

## Code and Resources used
<b>Python Version :</b> 3.9<br>
<b>Packages :</b> Numpy, Pandas, Matplotlib, Seaborn, Pytorch, Scikit-learn, transformers<br>
<b>For Web Framework Requirements :</b> `pip install -r requirements.txt`

## Data Collection
Collected data from kaggle to get a dataset that has 3085 TWITTER annotations. With every annotation, we got the following :
* Annotation ID
* Content of a TWITTER annotation in the format of a text
* Category of text that describes the sentiments extracted from it (It could be happy, sad, angry, surprise, disgust, not-relevant and more).

## Data Preprocessing
Clean the data up to make it ready for modeling process. I made the following changes:
* Dropped categories that have two different sentiments or more at the same time
* Dropped non-sense categories (The one named nocode)
* Created a variable named label that has the sentiments encoded

## Model Building
First, I splitted up data in training and test sets with test size of 15 %. I also tokenized and encoded each text using a pre-trained BERT Tokenizer to it make ready to be fed to a model.<br>I expedited the data processing by transforming our dataset into a dataloader, trained a pre-trained BERT model by setting up `AdamW` as an optimizer, `linear_schedule_with_warmup` as a scheduler and `f1-score` & `accuracy` as performance metrics.

## Model Performance
Our deep learning model has performed very well on test set as we get the following as final results:
* <b>Training loss :</b> 0.65
* <b>Testing loss :</b> 0.65
* <b>Testing f1 score :</b> 87.16 %
