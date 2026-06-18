# Yelp Review Sentiment Classification (NLP)
Project Overview

This project applies Natural Language Processing (NLP) and Machine Learning techniques to classify Yelp customer reviews based on sentiment. The objective is to determine whether a review is strongly negative (1-star) or strongly positive (5-star) using only the review text.

By transforming unstructured text into numerical features and training a Naive Bayes classifier, the project demonstrates an end-to-end NLP workflow, including text preprocessing, feature engineering, model training, and evaluation.

Business Problem

Online reviews contain valuable customer feedback, but manually reading thousands of reviews is impractical.

The goal of this project is to build a machine learning model capable of automatically identifying review sentiment, allowing businesses to:

Monitor customer satisfaction at scale
Detect negative customer experiences early
Analyze customer feedback trends
Improve customer service and decision-making
Dataset

Source: Yelp Review Dataset

The dataset contains:

Review text
Star ratings (1–5)
User metadata
Business metadata

For binary sentiment classification, only:

1-star reviews (negative sentiment)
5-star reviews (positive sentiment)

were retained.

Project Workflow
1. Exploratory Data Analysis (EDA)

Performed exploratory analysis to better understand the dataset:

Dataset structure inspection
Review length analysis
Longest and shortest review identification
Star rating distribution analysis
Review length distribution by rating
Boxplot analysis of review lengths

Key insight:

Positive reviews significantly outnumber negative reviews, introducing class imbalance into the classification problem.
2. Text Preprocessing

A custom NLP preprocessing pipeline was developed to clean the review text before modeling.

The pipeline performs:

Punctuation removal
Lowercase conversion
Stopword removal using NLTK

Example:

Original Review

Amazing food! Highly recommended.

Processed Review

['amazing', 'food', 'highly', 'recommended']
3. Feature Engineering
Bag-of-Words (Count Vectorization)

The cleaned text was converted into numerical features using Scikit-Learn's CountVectorizer.

This technique:

Creates a vocabulary from all reviews
Counts occurrences of each word
Produces a sparse matrix representation of the corpus
4. Model Development
Multinomial Naive Bayes

A Multinomial Naive Bayes classifier was trained to predict review sentiment.

Why Naive Bayes?

Fast training
Effective on text data
Strong baseline model for NLP classification tasks
5. Model Evaluation

The model was evaluated using:

Confusion Matrix
Classification Report
Precision
Recall
F1 Score

The Bag-of-Words representation produced strong sentiment classification performance and successfully distinguished between positive and negative reviews.

TF-IDF Experiment

A second feature engineering approach was tested using:

TF-IDF (Term Frequency–Inverse Document Frequency)

The objective was to determine whether weighting words by importance would improve classification performance.

Result

TF-IDF combined with Multinomial Naive Bayes performed significantly worse than the Bag-of-Words approach.

Observations:

The model became heavily biased toward predicting positive reviews.
Most negative reviews were incorrectly classified as positive.
Class separation deteriorated substantially.
Conclusion

For this dataset and model combination:

Bag-of-Words outperformed TF-IDF and was selected as the preferred feature representation.

This experiment highlights the importance of evaluating multiple feature engineering approaches rather than assuming a more sophisticated technique will automatically improve performance.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
NLTK
Scikit-Learn
CountVectorizer
TF-IDF Transformer
Multinomial Naive Bayes
Key Skills Demonstrated
Natural Language Processing (NLP)
Text Cleaning & Preprocessing
Feature Engineering
Bag-of-Words Modeling
TF-IDF Vectorization
Sentiment Analysis
Machine Learning Classification
Model Evaluation
Exploratory Data Analysis (EDA)
Python Data Science Stack
Results & Impact

This project demonstrates the complete workflow required to transform raw customer feedback into actionable insights.

The final solution successfully:

Converts unstructured text into machine-readable features
Classifies customer sentiment automatically
Evaluates multiple feature engineering strategies
Identifies the most effective representation for review classification

The project reflects practical NLP skills that can be applied to customer feedback analysis, review monitoring systems, support ticket categorization, and sentiment analysis applications.

Future Improvements

Potential enhancements include:

Logistic Regression and Linear SVM comparison
Hyperparameter tuning
N-gram feature engineering
Word embeddings (Word2Vec, GloVe)
Deep Learning approaches (LSTM, GRU)
Transformer-based models (BERT)
Class imbalance handling techniques
