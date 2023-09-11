# Natural_Language_Processing_NLP
Welcome to NLP-Wizards, your hub for practical Natural Language Processing (NLP) code. Our repository is a treasure chest of Python scripts and Jupyter notebooks designed to make NLP accessible and efficient.
Sure, here's a README file for your sentiment analysis code on the "amazon_alexa.tsv" dataset using TextBlob for polarity and subjectivity analysis:

---

# Sentiment Analysis with TextBlob

This repository contains a Python script for sentiment analysis performed on the "amazon_alexa.tsv" dataset using the TextBlob library. Sentiment analysis aims to determine the sentiment or emotional tone expressed in a piece of text. In this script, we analyze the polarity and subjectivity of the Amazon Alexa product reviews.

## Prerequisites

- Python 3.x
- pandas
- TextBlob

You can install TextBlob and other required packages using pip:

```bash
pip install textblob pandas
```

## Understanding the Code

The provided Python script (sentiment_analysis.py) performs sentiment analysis on the "verified_reviews" column of the "amazon_alexa.tsv" dataset. Here's a brief overview of the code:

1. Importing the necessary libraries:

   ```python
   import textblob
   from textblob import TextBlob
   import pandas as pd
   ```

2. Reading the dataset:

   ```python
   dataset = pd.read_csv("amazon_alexa.tsv", delimiter="\t")
   ```

3. Calculating the polarity and subjectivity for each review using TextBlob:

   ```python
   def get_sentiment_polarity(text):
       mytextblob = TextBlob(text)
       mypolarity = mytextblob.sentiment.polarity
       return mypolarity

   dataset["Polarity"] = dataset["verified_reviews"].apply(get_sentiment_polarity)
   ```

   ```python
   def get_sentiment_subjectivity(text):
       mytextblob = TextBlob(text)
       mysubjectivity = mytextblob.sentiment.subjectivity
       return mysubjectivity

   dataset["Subjectivity"] = dataset["verified_reviews"].apply(get_sentiment_subjectivity)
   ```

4. Displaying summary statistics:

   ```python
   dataset[["Length", "Polarity", "Subjectivity"]].describe()
   ```

## Usage

1. Make sure you have the required Python packages installed.

2. Place the "amazon_alexa.tsv" dataset in the same directory as the script.

3. Run the script:

   ```bash
   python sentiment_analysis.py
   ```

4. The script will calculate the polarity and subjectivity of each review and provide summary statistics.

## License

This code is provided under the MIT License. You are free to use and modify it as needed.

---

Feel free to customize this README file further to include additional details, acknowledgments, or usage instructions as needed for your specific project.
