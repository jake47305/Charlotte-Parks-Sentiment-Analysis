Charlotte Parks Sentiment Analysis

UNC Charlotte Data Science capstone (DTSC 4302, Spring 2025) Paper: Green Time Not Screen Time

Screen time among children has climbed sharply since 2020, while park visits have dropped. This project asks: what do people like and dislike about Charlotte's parks, and what could make them more appealing? We collected 3,164 Google Maps reviews across 16 Charlotte-Mecklenburg parks and used natural language processing to find what drives positive and negative experiences.

Key findings
Most reviews are positive. Of 3,098 written reviews, 2,205 (71%) were positive, 770 neutral, and 123 negative.
Highest and lowest rated: Freedom Park had the highest average sentiment (0.44 polarity); Robert L. Smith Park and Clanton Park had the lowest.
What people praise: walking trails, playgrounds, splash pads, disc golf, and basketball courts, especially features for children and families.
What people criticize: safety concerns, noise from nearby traffic and the light rail, and closed facilities.
Location matters. Urban parks near Uptown (ZIP 28202) drew more neutral and negative reviews, often about parking and safety. Z-score analysis flagged ZIP 28217 as a significant outlier, with far fewer positive reviews (z = −2.47) and more neutral ones (z = 2.55), suggesting parks there are forgettable rather than bad.
Methods
Data collection: scraped Google Maps reviews for 16 parks with at least 100 reviews each, spread across the county to avoid geographic bias.
Cleaning: merged reviews that the scraper split across multiple rows, removed emojis and special characters, removed park names, corrected spelling with TextBlob, removed stop words (NLTK plus custom), and mapped synonyms (e.g. "great", "awesome" → "good").
Sentiment scoring: TextBlob polarity (−1 to 1), labeled positive (≥ 0.25), neutral, or negative (< 0).
Feature analysis: bigram and 4-gram frequency by sentiment class, TF-IDF keywords by ZIP code, and LDA topic modeling (5 topics).
Classification: trained a logistic regression model on TF-IDF features (80/20 train/test split) to predict review sentiment.
Geographic analysis: geocoded parks with geopy, mapped review counts and sentiment by ZIP code with GeoPandas and Folium, and flagged outlier ZIP codes with z-scores.
Files
File	What it is
charlotte_parks_sentiment.ipynb	Full analysis notebook (Google Colab)
Green_Time_Not_Screen_Time.pdf	Final capstone paper

The raw review data isn't included. It contains reviewers' names, and Google's terms don't allow republishing it.

Tools

Python · Pandas · NLTK · TextBlob · Scikit-learn · GeoPandas · Folium · Matplotlib · Seaborn

Team

Aaron Spotts, Carlo Fairley, Jacob Turner, Jake Rice, Joe Posillico
