# Predicting Tweet Virality using NLP and Machine Learning

## Overview
This project analyzes ~183K tweets from the 2019 Australian Federal Election to understand what drives retweet engagement. The analysis focuses on sentiment, emotions, topics, and tweet structure to evaluate their impact on virality.

---

## Problem
- What factors influence whether a tweet gets retweeted?
- Is sentiment a meaningful predictor of engagement?
- Do structural elements like hashtags and mentions matter more than text content?

---

## Dataset
- ~183,000 tweets  
- Timeframe: May 10 – May 20, 2019  
- Key fields: tweet text, retweet count, likes, timestamp, user metadata  

---

## Approach

### Data Processing
- Lowercasing, tokenization, stopword removal  
- Lemmatization using NLTK  
- Custom stopword removal for domain-specific terms  

### Feature Engineering
- Sentiment scores (TextBlob)  
- Emotion features (NRC Lexicon – 8 emotions)  
- Topic modeling using LDA (5 topics)  
- Structural features:
  - Tweet length  
  - Hashtag count  
  - Mention count  
  - URL presence  
  - Time-based features  

---

## Modeling

### Linear Regression
- Input: sentiment, emotions, topic weights  
- Result: very low explanatory power (R² ≈ 0)

### Gradient Boosting
- Target: log-transformed retweet count  
- Input: engineered + structural features  
- Captures non-linear relationships  

---

## Results

| Model | Features | Outcome |
|------|---------|--------|
| Linear Regression | Text-only | Poor performance |
| Gradient Boosting | Text + structural | Improved performance |

---

## Key Observations
- Most tweets receive zero retweets, leading to a highly skewed distribution  
- Sentiment and emotion features alone do not explain engagement well  
- Structural features such as hashtags and mentions are stronger indicators of virality  
- Feature engineering had a larger impact than model selection  

---

## Presentation
[View Final Presentation](./presentation/final_presentation.pptx)

---

## Tech Stack
- Python (Pandas, NumPy)  
- NLP: NLTK, TextBlob  
- Topic Modeling: Gensim  
- Machine Learning: Scikit-learn  

---

## How to Run

pip install -r requirements.txt  
jupyter notebook

---

## Contribution
Originally completed as part of a team. This repository reflects my work on data preprocessing, feature engineering, and model development.

- Built text preprocessing pipeline  
- Engineered sentiment, emotion, and topic features  
- Developed and evaluated Linear Regression and Gradient Boosting models
