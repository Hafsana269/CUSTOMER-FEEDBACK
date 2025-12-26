# Customer Feedback Analysis using Python and Power BI

## Overview

This project demonstrates how to analyze customer feedback using Python's Natural Language Processing (NLP) libraries and visualize the results in Power BI.

## Requirements

- Python 3.x
- NLTK library
- pandas library
- Power BI Desktop
- Matplotlib library
- Seaborn library

## Project Structure

- `data/`: contains the customer feedback dataset
- `scripts/`: contains Python scripts for data cleaning, sentiment analysis, and visualization
- `reports/`: contains Power BI reports and dashboards

## Usage

1. Install required libraries: `pip install nltk pandas matplotlib seaborn`
2. Run `data_cleaning.py` to clean and preprocess the dataset
3. Run `sentiment_analysis.py` to perform sentiment analysis on the dataset
4. Open `customer_feedback.pbix` in Power BI Desktop to view the report and dashboard

## Example Code
# Import required libraries
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

# Load dataset
df = pd.read_csv('data/customer_feedback.csv')

# Perform sentiment analysis
sia = SentimentIntensityAnalyzer()
df['sentiment'] = df['feedback'].apply(lambda x: sia.polarity_scores(x)['compound'])

# Visualize results
import matplotlib.pyplot as plt
import seaborn as sns
sns.set()
plt.figure(figsize=(10,6))
sns.countplot(x='sentiment', data=df)
plt.show()
# Power BI
The Power BI report includes the following visualizations:

- Sentiment Analysis: a bar chart showing the distribution of sentiment scores
- Feedback by Category: a stacked bar chart showing the distribution of feedback by category
