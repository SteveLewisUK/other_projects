# Hotel Room Price Analysis

### Contents
1. [Objectives](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#objectives)
2. [Data](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#data)
3. [Method and Tools Used](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#method-and-tools-used)
4. [Conclusions](https://github.com/SteveLewisUK/datascience_bootcamp_projects/blob/main/classifying_IMDB_movie_reviews/README.md#conclusions)<br />


### Objectives
A Product Owner at an online travel company was contemplating implementing 'urgency messages' on the website such as:
* “Prices have been rising. Book now to lock in your rates!” 
* “Your check-in is fast approaching. Book now to lock in your rates!”

An analysis was requested of the movement of the price of hotel rooms as the day approaches the check-in date.<br />


### Data
The data was randomly sampled booking data from five different cities with check-in dates between 10/10/2016 – 12/31/2016. 

Here's the description of selected fields:
|**Field** |**Description**|
|:------------- | :----------|
|# | No of record in each dataset|
|Hotel ID | Property identification number|
|City ID | City identification number|
|Star rating | The property’s star rating|
|Accommodation Type Name | The property’s accommodation type |
|Chain Hotel | Whether the property is part of a chain or not|
|Booking date | Date of booking made|
|Check-in date | Date of check-in |
|Check-out date | Date of check-out |

There were 5 datasets which, when concatenated, had a totoal of 49,064 rows.<br />


### Method and Tools Used
***Step 1***: Exploratory Data Analysis and visualiation; Horizontal Bar Plot, Stacked Bar Plot, KDE Plot (re-indexed axes to account for years with no movies or reviews)\
***Step 2***: Normalised text including using Regular Expressions. Tokenised and Lemmatised text using the NTLK (Natural Language Toolkit) and the SpaCy libraries\
***Step 3***: Converted the text data into numeric data for model training by calculating TF-IDF vectors. Also Vectorised the Test data\
***Step 4***: Trained Logistic Regression model with these TF-IDF values for both the NTLK and the SpaCy data. Trained LGMB Classifier with SpaCy and TF-IDF\
***Step 5***: Used BERT to get Word Embeddings from the texts. Used these to train a further Logistic Regression Model\
***Step 6***: Plotted F1 Score, ROC Curves and Precision/Recall for each model. Compareed models based on F1 Score.<br />


### Conclusions
Both the initial Logistic Regression models (trained on NTLH and ScaCy lemmatised data) performed equally well according to the F1 scores obtained on the test set data.  When tested on additional reviews in the project, the SpaCy model seemed to outperform the NTLK one. However, it took much more time to get the vectors from the text lemmatised with the SpaCy library, than with the NTLK library.

The LGBMClassifier performed less well than expected, though this could be improved potentially with hyper-parameter tuning.

Creating Word Embeddings with BERT is only practical on a GPU. In this project only 200 reviews out of over 47,000 were used to reuce model training time.  However, based on a small test of 10 reviews, many of the predictions seemed accurate.  A few seemed less reasonable, but that was to be expected given the small training set for the Logistic Regression/BERT model. 
